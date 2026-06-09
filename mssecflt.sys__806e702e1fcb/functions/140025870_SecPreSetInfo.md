# SecPreSetInfo

- ea: `0x140025870`
- end: `0x140025af0`
- name: `SecPreSetInfo`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path`

## callees

- `0x14001030b`
- `0x140010317`
- `0x14001032f`
- `0x140010347`
- `0x140011610`
- `0x140011650`
- `0x140025738`
- `0x140025744`
- `0x140025768`
- `0x1400257ac`
- `0x1400257b8`
- `0x140025870`
- `0x140025af0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025ac5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025ac5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025956`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025956`
- `ntoskrnl!ExQueryDepthSList` at `0x140025a05`
- `ntoskrnl!ExQueryDepthSList` at `0x140025a05`

## pseudocode

```c
__int64 __fastcall SecPreSetInfo(__int64 a1, __int64 a2, struct _SLIST_ENTRY **a3)
{
  struct _SLIST_ENTRY *v4; // rdi
  unsigned int v7; // ebp
  int v8; // esi
  struct _FILE_OBJECT *v9; // rdx
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  bool v14; // zf
  char *v15; // rbx
  union _SLIST_HEADER *v16; // rcx
  char *v17; // rsi
  USHORT v18; // bx
  int v19; // eax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-48h] BYREF

  Context = 0;
  v4 = 0;
  *a3 = 0;
  v7 = 1;
  v8 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
  if ( !FltSupportsStreamHandleContexts_0(*(PFILE_OBJECT *)(a2 + 32)) )
    goto LABEL_25;
  if ( !FltSupportsStreamContexts_0(*(PFILE_OBJECT *)(a2 + 32)) )
    goto LABEL_25;
  v9 = *(struct _FILE_OBJECT **)(a2 + 32);
  if ( (v9->Flags & 0x280) != 0 )
    goto LABEL_25;
  v10 = (unsigned int)(v8 - 10);
  if ( (unsigned int)v10 <= 0x37 )
  {
    v11 = 0x80000000000201LL;
    if ( _bittest64(&v11, v10) )
      goto LABEL_12;
  }
  if ( v8 == 20 )
  {
    v14 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 49LL) == 0;
  }
  else
  {
    v12 = (unsigned int)(v8 - 4);
    if ( (unsigned int)v12 <= 0x3C )
    {
      v13 = 0x1000000000000281LL;
      if ( _bittest64(&v13, v12) )
        goto LABEL_12;
    }
    v14 = v8 == 72;
  }
  if ( v14 )
  {
LABEL_12:
    if ( FltGetStreamContext_0(*(PFLT_INSTANCE *)(a2 + 24), v9, &Context) < 0 )
      goto LABEL_25;
    v15 = (char *)SecData + 384;
    v16 = (union _SLIST_HEADER *)((char *)SecData + 384);
    ++*((_DWORD *)SecData + 101);
    v4 = ExpInterlockedPopEntrySList(v16);
    if ( !v4 )
    {
      ++*((_DWORD *)v15 + 6);
      v4 = (struct _SLIST_ENTRY *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v15 + 6))(
                                    *((unsigned int *)v15 + 9),
                                    *((unsigned int *)v15 + 11),
                                    *((unsigned int *)v15 + 10));
    }
    if ( !v4 )
      goto LABEL_25;
    if ( v8 == 4 )
    {
      v19 = SecPreSetBasicInfo(a1, a2, Context, v4);
    }
    else
    {
      if ( v8 != 10 )
      {
        switch ( v8 )
        {
          case 11:
LABEL_33:
            v19 = SecPreSetHardLinkInfo(a1, a2, Context, v4);
            goto LABEL_36;
          case 13:
            goto LABEL_32;
          case 19:
            SecPreSetAllocationInfo(Context, v4);
            goto LABEL_37;
          case 20:
            SecPreSetEndOfFileInfo(Context, v4);
            goto LABEL_37;
          case 64:
LABEL_32:
            v19 = SecPreSetDispositionInfo(a1, a2, (_DWORD)Context, (_DWORD)v4, v8 == 64);
            goto LABEL_36;
        }
        if ( v8 != 65 )
        {
          if ( v8 != 72 )
            goto LABEL_25;
          goto LABEL_33;
        }
      }
      v19 = SecPreSetRenameInfo(a1, a2, Context, v4);
    }
LABEL_36:
    if ( v19 < 0 )
      goto LABEL_25;
LABEL_37:
    *a3 = v4;
    return 5;
  }
LABEL_25:
  if ( Context )
    FltReleaseContext_0(Context);
  if ( v4 )
  {
    v17 = (char *)SecData + 384;
    ++*((_DWORD *)SecData + 103);
    v18 = *((_WORD *)v17 + 8);
    if ( ExQueryDepthSList((PSLIST_HEADER)v17) < v18 )
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v17, v4);
    }
    else
    {
      ++*((_DWORD *)v17 + 8);
      (*((void (__fastcall **)(struct _SLIST_ENTRY *))v17 + 7))(v4);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140025870  push    rbx
0x140025872  push    rbp
0x140025873  push    rsi
0x140025874  push    rdi
0x140025875  push    r12
0x140025877  push    r14
0x140025879  push    r15
0x14002587b  sub     rsp, 40h
0x14002587f  mov     rax, cs:__security_cookie
0x140025886  xor     rax, rsp
0x140025889  mov     [rsp+78h+var_40], rax
0x14002588e  mov     r15, rcx
0x140025891  mov     [rsp+78h+Context], 0
0x14002589a  xor     edi, edi
0x14002589c  mov     r12, r8
0x14002589f  mov     [r8], rdi
0x1400258a2  mov     r14, rdx
0x1400258a5  mov     rax, [rcx+10h]
0x1400258a9  mov     ebp, 1
0x1400258ae  mov     rcx, [rdx+20h]; FileObject
0x1400258b2  mov     esi, [rax+20h]
0x1400258b5  call    FltSupportsStreamHandleContexts_0
0x1400258ba  test    al, al
0x1400258bc  jz      loc_1400259D5
0x1400258c2  mov     rcx, [r14+20h]; FileObject
0x1400258c6  call    FltSupportsStreamContexts_0
0x1400258cb  test    al, al
0x1400258cd  jz      loc_1400259D5
0x1400258d3  mov     rdx, [r14+20h]; FileObject
0x1400258d7  test    dword ptr [rdx+50h], 280h
0x1400258de  jnz     loc_1400259D5
0x1400258e4  lea     eax, [rsi-0Ah]
0x1400258e7  cmp     eax, 37h ; '7'
0x1400258ea  ja      short loc_1400258FC
0x1400258ec  mov     rcx, 80000000000201h
0x1400258f6  bt      rcx, rax
0x1400258fa  jb      short loc_14002592C
0x1400258fc  cmp     esi, 14h
0x1400258ff  jz      short loc_14002591E
0x140025901  lea     eax, [rsi-4]
0x140025904  cmp     eax, 3Ch ; '<'
0x140025907  ja      short loc_140025919
0x140025909  mov     rcx, 1000000000000281h
0x140025913  bt      rcx, rax
0x140025917  jb      short loc_14002592C
0x140025919  cmp     esi, 48h ; 'H'
0x14002591c  jmp     short loc_140025926
0x14002591e  mov     rax, [r15+10h]
0x140025922  cmp     [rax+31h], dil
0x140025926  jnz     loc_1400259D5
0x14002592c  mov     rcx, [r14+18h]; Instance
0x140025930  lea     r8, [rsp+78h+Context]; Context
0x140025935  call    FltGetStreamContext_0
0x14002593a  test    eax, eax
0x14002593c  js      loc_1400259D5
0x140025942  mov     rbx, cs:SecData
0x140025949  add     rbx, 180h
0x140025950  mov     rcx, rbx; ListHead
0x140025953  add     [rbx+14h], ebp
0x140025956  call    cs:__imp_ExpInterlockedPopEntrySList
0x14002595d  nop     dword ptr [rax+rax+00h]
0x140025962  mov     rdi, rax
0x140025965  test    rax, rax
0x140025968  jnz     short loc_140025984
0x14002596a  add     [rbx+18h], ebp
0x14002596d  mov     edx, [rbx+2Ch]
0x140025970  mov     rax, [rbx+30h]
0x140025974  mov     r8d, [rbx+28h]
0x140025978  mov     ecx, [rbx+24h]
0x14002597b  call    cs:__guard_dispatch_icall_fptr
0x140025981  mov     rdi, rax
0x140025984  test    rdi, rdi
0x140025987  jz      short loc_1400259D5
0x140025989  mov     ecx, esi
0x14002598b  sub     ecx, 4
0x14002598e  jz      loc_140025A96
0x140025994  sub     ecx, 6
0x140025997  jz      loc_140025A81
0x14002599d  sub     ecx, ebp
0x14002599f  jz      loc_140025A6C
0x1400259a5  sub     ecx, 2
0x1400259a8  jz      loc_140025A4D
0x1400259ae  sub     ecx, 6
0x1400259b1  jz      loc_140025A3E
0x1400259b7  sub     ecx, ebp
0x1400259b9  jz      short loc_140025A2F
0x1400259bb  sub     ecx, 2Ch ; ','
0x1400259be  jz      loc_140025A4D
0x1400259c4  sub     ecx, ebp
0x1400259c6  jz      loc_140025A81
0x1400259cc  cmp     ecx, 7
0x1400259cf  jz      loc_140025A6C
0x1400259d5  mov     rcx, [rsp+78h+Context]; Context
0x1400259da  test    rcx, rcx
0x1400259dd  jz      short loc_1400259E4
0x1400259df  call    FltReleaseContext_0
0x1400259e4  test    rdi, rdi
0x1400259e7  jz      loc_140025AD1
0x1400259ed  mov     rsi, cs:SecData
0x1400259f4  add     rsi, 180h
0x1400259fb  mov     rcx, rsi; SListHead
0x1400259fe  add     [rsi+1Ch], ebp
0x140025a01  movzx   ebx, word ptr [rsi+10h]
0x140025a05  call    cs:__imp_ExQueryDepthSList
0x140025a0c  nop     dword ptr [rax+rax+00h]
0x140025a11  cmp     ax, bx
0x140025a14  jb      loc_140025ABC
0x140025a1a  add     [rsi+20h], ebp
0x140025a1d  mov     rcx, rdi
0x140025a20  mov     rax, [rsi+38h]
0x140025a24  call    cs:__guard_dispatch_icall_fptr
0x140025a2a  jmp     loc_140025AD1
0x140025a2f  mov     rcx, [rsp+78h+Context]
0x140025a34  mov     rdx, rdi
0x140025a37  call    SecPreSetEndOfFileInfo
0x140025a3c  jmp     short loc_140025AB1
0x140025a3e  mov     rcx, [rsp+78h+Context]
0x140025a43  mov     rdx, rdi
0x140025a46  call    SecPreSetAllocationInfo
0x140025a4b  jmp     short loc_140025AB1
0x140025a4d  mov     r8, [rsp+78h+Context]
0x140025a52  cmp     esi, 40h ; '@'
0x140025a55  mov     r9, rdi
0x140025a58  mov     rdx, r14
0x140025a5b  setz    al
0x140025a5e  mov     rcx, r15
0x140025a61  mov     [rsp+78h+var_58], al
0x140025a65  call    SecPreSetDispositionInfo
0x140025a6a  jmp     short loc_140025AA9
0x140025a6c  mov     r8, [rsp+78h+Context]
0x140025a71  mov     r9, rdi
0x140025a74  mov     rdx, r14
0x140025a77  mov     rcx, r15
0x140025a7a  call    SecPreSetHardLinkInfo
0x140025a7f  jmp     short loc_140025AA9
0x140025a81  mov     r8, [rsp+78h+Context]
0x140025a86  mov     r9, rdi
0x140025a89  mov     rdx, r14
0x140025a8c  mov     rcx, r15
0x140025a8f  call    SecPreSetRenameInfo
0x140025a94  jmp     short loc_140025AA9
0x140025a96  mov     r8, [rsp+78h+Context]
0x140025a9b  mov     r9, rdi
0x140025a9e  mov     rdx, r14
0x140025aa1  mov     rcx, r15
0x140025aa4  call    SecPreSetBasicInfo
0x140025aa9  test    eax, eax
0x140025aab  js      loc_1400259D5
0x140025ab1  mov     [r12], rdi
0x140025ab5  mov     ebp, 5
0x140025aba  jmp     short loc_140025AD1
0x140025abc  lfence
0x140025abf  mov     rdx, rdi; ListEntry
0x140025ac2  mov     rcx, rsi; ListHead
0x140025ac5  call    cs:__imp_ExpInterlockedPushEntrySList
0x140025acc  nop     dword ptr [rax+rax+00h]
0x140025ad1  mov     eax, ebp
0x140025ad3  mov     rcx, [rsp+78h+var_40]
0x140025ad8  xor     rcx, rsp; StackCookie
0x140025adb  call    __security_check_cookie
0x140025ae0  add     rsp, 40h
0x140025ae4  pop     r15
0x140025ae6  pop     r14
0x140025ae8  pop     r12
0x140025aea  pop     rdi
0x140025aeb  pop     rsi
0x140025aec  pop     rbp
0x140025aed  pop     rbx
0x140025aee  retn
```
