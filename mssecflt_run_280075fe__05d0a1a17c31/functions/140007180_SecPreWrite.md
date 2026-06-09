# SecPreWrite

- ea: `0x140007180`
- end: `0x140007348`
- name: `SecPreWrite`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1400057a8`
- `0x140006400`
- `0x140007180`
- `0x14001030b`
- `0x140010317`
- `0x14001032f`
- `0x14001033b`
- `0x140010347`
- `0x140011650`
- `0x1400233b4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400071f6`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400071f6`

## pseudocode

```c
__int64 __fastcall SecPreWrite(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v5; // r8d
  int v6; // edx
  PFLT_CONTEXT v8; // [rsp+40h] [rbp-28h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-20h] BYREF

  Context = 0;
  v8 = 0;
  *a3 = 0;
  if ( FltSupportsStreamHandleContexts_0(*(PFILE_OBJECT *)(a2 + 32))
    && FltSupportsStreamContexts_0(*(PFILE_OBJECT *)(a2 + 32))
    && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x280) == 0
    && ((**(_DWORD **)(a1 + 16) & 2) == 0 || IoGetTopLevelIrp() != (PIRP)2)
    && ((xmmword_14001B740 & 0x200) != 0 || (xmmword_14001B740 & 0x800000) != 0)
    && FltGetStreamContext_0(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    v5 = *((_DWORD *)Context + 4);
    if ( (v5 & 1) != 0 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(a2 + 32) + 32LL) || *(_DWORD *)(*((_QWORD *)Context + 1) + 64LL) == 1 )
        SecSendDasdAccessEvent(
          &Event21,
          a1,
          *((_QWORD *)Context + 1) + 24LL,
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL),
          *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL),
          *(_DWORD *)(*((_QWORD *)Context + 1) + 40LL) & 1,
          (*(_DWORD *)(*((_QWORD *)Context + 1) + 40LL) & 2) != 0);
    }
    else
    {
      v6 = **(_DWORD **)(a1 + 16) & 2;
      if ( !v6 || (v5 & 2) != 0 )
      {
        if ( v6 )
        {
          _InterlockedOr((volatile signed __int32 *)Context + 4, 4u);
        }
        else if ( FltGetStreamHandleContext_0(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v8) >= 0
               || (int)SecCreateHandleContext(a2, &v8) >= 0 )
        {
          SecSetObjectContextThread(v8, 1, 1, *(_QWORD *)(a1 + 8));
        }
      }
    }
    if ( v8 )
      FltReleaseContext_0(v8);
    FltReleaseContext_0(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x140007180  mov     [rsp+arg_18], rsi
0x140007185  push    rdi
0x140007186  sub     rsp, 60h
0x14000718a  mov     rax, cs:__security_cookie
0x140007191  xor     rax, rsp
0x140007194  mov     [rsp+68h+var_18], rax
0x140007199  mov     rdi, rdx
0x14000719c  mov     rsi, rcx
0x14000719f  mov     [rsp+68h+Context], 0
0x1400071a8  mov     [rsp+68h+var_28], 0
0x1400071b1  mov     qword ptr [r8], 0
0x1400071b8  mov     rcx, [rdx+20h]; FileObject
0x1400071bc  call    FltSupportsStreamHandleContexts_0
0x1400071c1  test    al, al
0x1400071c3  jz      loc_140007327
0x1400071c9  mov     rcx, [rdi+20h]; FileObject
0x1400071cd  call    FltSupportsStreamContexts_0
0x1400071d2  test    al, al
0x1400071d4  jz      loc_140007327
0x1400071da  mov     rax, [rdi+20h]
0x1400071de  test    dword ptr [rax+50h], 280h
0x1400071e5  jnz     loc_140007327
0x1400071eb  mov     rax, [rsi+10h]
0x1400071ef  mov     ecx, [rax]
0x1400071f1  test    cl, 2
0x1400071f4  jz      short loc_14000720C
0x1400071f6  call    cs:__imp_IoGetTopLevelIrp
0x1400071fd  nop     dword ptr [rax+rax+00h]
0x140007202  cmp     rax, 2
0x140007206  jz      loc_140007327
0x14000720c  mov     rcx, qword ptr cs:xmmword_14001B740
0x140007213  mov     rax, rcx
0x140007216  shr     rax, 9
0x14000721a  test    al, 1
0x14000721c  jnz     short loc_14000722B
0x14000721e  shr     rcx, 17h
0x140007222  test    cl, 1
0x140007225  jz      loc_140007327
0x14000722b  lea     r8, [rsp+68h+Context]; Context
0x140007230  mov     rdx, [rdi+20h]; FileObject
0x140007234  mov     rcx, [rdi+18h]; Instance
0x140007238  call    FltGetStreamContext_0
0x14000723d  test    eax, eax
0x14000723f  js      loc_140007327
0x140007245  mov     rcx, [rsp+68h+Context]
0x14000724a  mov     r8d, [rcx+10h]
0x14000724e  test    r8b, 1
0x140007252  jz      short loc_1400072B5
0x140007254  mov     rax, [rdi+20h]
0x140007258  cmp     qword ptr [rax+20h], 0
0x14000725d  jnz     short loc_14000726D
0x14000725f  mov     rax, [rcx+8]
0x140007263  cmp     dword ptr [rax+40h], 1
0x140007267  jnz     loc_14000730E
0x14000726d  mov     rax, [rsp+68h+Context]
0x140007272  mov     r8, [rax+8]
0x140007276  mov     r10d, [r8+28h]
0x14000727a  mov     r9, [rsi+10h]
0x14000727e  mov     ecx, r10d
0x140007281  shr     ecx, 1
0x140007283  and     cl, 1
0x140007286  and     r10b, 1
0x14000728a  mov     eax, [r9+18h]
0x14000728e  add     r8, 18h
0x140007292  mov     [rsp+68h+var_38], cl; char
0x140007296  mov     [rsp+68h+var_40], r10b; char
0x14000729b  mov     qword ptr [rsp+68h+var_48], rax; char
0x1400072a0  mov     r9, [r9+28h]
0x1400072a4  mov     rdx, rsi
0x1400072a7  lea     rcx, Event21; EventDescriptor
0x1400072ae  call    SecSendDasdAccessEvent
0x1400072b3  jmp     short loc_14000730E
0x1400072b5  mov     rax, [rsi+10h]
0x1400072b9  mov     edx, [rax]
0x1400072bb  and     edx, 2
0x1400072be  jz      short loc_1400072C6
0x1400072c0  test    r8b, 2
0x1400072c4  jz      short loc_14000730E
0x1400072c6  test    edx, edx
0x1400072c8  jnz     short loc_140007309
0x1400072ca  lea     r8, [rsp+68h+var_28]; Context
0x1400072cf  mov     rdx, [rdi+20h]; FileObject
0x1400072d3  mov     rcx, [rdi+18h]; Instance
0x1400072d7  call    FltGetStreamHandleContext_0
0x1400072dc  test    eax, eax
0x1400072de  jns     short loc_1400072F1
0x1400072e0  lea     rdx, [rsp+68h+var_28]
0x1400072e5  mov     rcx, rdi
0x1400072e8  call    SecCreateHandleContext
0x1400072ed  test    eax, eax
0x1400072ef  js      short loc_14000730E
0x1400072f1  mov     r9, [rsi+8]
0x1400072f5  mov     edx, 1
0x1400072fa  mov     r8d, edx
0x1400072fd  mov     rcx, [rsp+68h+var_28]
0x140007302  call    SecSetObjectContextThread
0x140007307  jmp     short loc_14000730E
0x140007309  lock or dword ptr [rcx+10h], 4
0x14000730e  mov     rcx, [rsp+68h+var_28]; Context
0x140007313  test    rcx, rcx
0x140007316  jz      short loc_14000731D
0x140007318  call    FltReleaseContext_0
0x14000731d  mov     rcx, [rsp+68h+Context]; Context
0x140007322  call    FltReleaseContext_0
0x140007327  mov     eax, 1
0x14000732c  mov     rcx, [rsp+68h+var_18]
0x140007331  xor     rcx, rsp; StackCookie
0x140007334  call    __security_check_cookie
0x140007339  mov     rsi, [rsp+68h+arg_18]
0x140007341  add     rsp, 60h
0x140007345  pop     rdi
0x140007346  retn
0x140011cdf  push    rbp
0x140011ce1  sub     rsp, 40h
0x140011ce5  mov     rbp, rdx
0x140011ce8  mov     rcx, [rbp+40h]; Context
0x140011cec  test    rcx, rcx
0x140011cef  jz      short loc_140011CF7
0x140011cf1  call    FltReleaseContext_0
0x140011cf6  nop
0x140011cf7  mov     rcx, [rbp+48h]; Context
0x140011cfb  call    FltReleaseContext_0
0x140011d00  nop
0x140011d01  add     rsp, 40h
0x140011d05  pop     rbp
0x140011d06  retn
```
