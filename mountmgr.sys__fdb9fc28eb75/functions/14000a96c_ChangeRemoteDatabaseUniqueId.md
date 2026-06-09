# ChangeRemoteDatabaseUniqueId

- ea: `0x14000a96c`
- end: `0x14000ac49`
- name: `ChangeRemoteDatabaseUniqueId`
- size: `733`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000d494`

## callees

- `0x140001ae0`
- `0x140002f80`
- `0x14000a810`
- `0x14000a96c`
- `0x14000b5e8`
- `0x140010600`
- `0x140011500`
- `0x1400135a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000aaa8`
- `ntoskrnl!ExAllocatePool2` at `0x14000aaa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab80`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000abc7`
- `ntoskrnl!RtlCompareMemory` at `0x14000aa78`
- `ntoskrnl!RtlCompareMemory` at `0x14000aa78`

## pseudocode

```c
__int64 __fastcall ChangeRemoteDatabaseUniqueId(__int64 a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // eax
  __int64 v7; // r8
  int RemoteDatabaseEntry; // ebx
  unsigned int v10; // r14d
  __int64 v11; // r8
  _DWORD *v12; // rdi
  SIZE_T v13; // rbx
  unsigned int v14; // ebx
  __int64 Pool2; // rax
  __int64 v16; // rsi
  unsigned int v17; // ecx
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  void *v20; // [rsp+20h] [rbp-18h] BYREF
  PVOID P; // [rsp+28h] [rbp-10h] BYREF
  char v22; // [rsp+98h] [rbp+60h] BYREF

  v20 = 0;
  P = 0;
  v22 = 0;
  v6 = OpenRemoteDatabase(a1, 0, &v22, &v20);
  RemoteDatabaseEntry = v6;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 69, v7, v6);
    return (unsigned int)RemoteDatabaseEntry;
  }
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 70, v7, 3221225626LL);
    return 3221225626LL;
  }
  v10 = 0;
  while ( 1 )
  {
    RemoteDatabaseEntry = GetRemoteDatabaseEntry(a1, v20, v10, (unsigned __int16 **)&P);
    if ( RemoteDatabaseEntry < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 71;
        goto LABEL_31;
      }
      goto LABEL_32;
    }
    v12 = P;
    if ( !P )
      goto LABEL_32;
    if ( *((_WORD *)P + 7) != *a2
      || (v13 = *((unsigned __int16 *)P + 7),
          RtlCompareMemory(a2 + 1, (char *)P + *((unsigned __int16 *)P + 6), v13) != v13)
      || (v14 = *v12 + *a3 - *a2, Pool2 = ExAllocatePool2(258, v14, 1098149453), (v16 = Pool2) == 0) )
    {
      v10 += *v12;
      goto LABEL_20;
    }
    *(_DWORD *)Pool2 = v14;
    *(_DWORD *)(Pool2 + 4) = v12[1];
    *(_WORD *)(Pool2 + 8) = 16;
    v17 = *((unsigned __int16 *)v12 + 5);
    *(_WORD *)(Pool2 + 10) = v17;
    *(_WORD *)(Pool2 + 12) = v17 + 16;
    *(_WORD *)(Pool2 + 14) = *a3;
    memmove((void *)(Pool2 + 16), (char *)v12 + *((unsigned __int16 *)v12 + 4), v17);
    memmove((void *)(v16 + *(unsigned __int16 *)(v16 + 12)), a3 + 1, *(unsigned __int16 *)(v16 + 14));
    RemoteDatabaseEntry = DeleteRemoteDatabaseEntry(a1, v20, v10);
    if ( RemoteDatabaseEntry < 0 )
      break;
    RemoteDatabaseEntry = AddRemoteDatabaseEntry(a1, v20, (_DWORD *)v16);
    if ( RemoteDatabaseEntry < 0 )
    {
      ExFreePoolWithTag(v12, 0);
      ExFreePoolWithTag((PVOID)v16, 0);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v19 = 73;
LABEL_31:
        WPP_SF_L(v18->AttachedDevice, v19, v11, (unsigned int)RemoteDatabaseEntry);
        goto LABEL_32;
      }
      goto LABEL_32;
    }
    ExFreePoolWithTag((PVOID)v16, 0);
LABEL_20:
    ExFreePoolWithTag(v12, 0);
  }
  ExFreePoolWithTag(v12, 0);
  ExFreePoolWithTag((PVOID)v16, 0);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v19 = 72;
    goto LABEL_31;
  }
LABEL_32:
  CloseFileHandleOutsideExtensionMutexLock(*(_QWORD *)(a1 + 152));
  return (unsigned int)RemoteDatabaseEntry;
}

```

## disassembly

```asm
0x14000a96c  push    rbp
0x14000a96e  push    rbx
0x14000a96f  push    rsi
0x14000a970  push    rdi
0x14000a971  push    r12
0x14000a973  push    r13
0x14000a975  push    r14
0x14000a977  push    r15
0x14000a979  mov     rbp, rsp
0x14000a97c  sub     rsp, 38h
0x14000a980  mov     r12, r8
0x14000a983  mov     [rbp+var_18], 0
0x14000a98b  mov     r13, rdx
0x14000a98e  mov     [rbp+P], 0
0x14000a996  lea     r8, [rbp+arg_18]
0x14000a99a  mov     [rbp+arg_18], 0
0x14000a99e  xor     edx, edx
0x14000a9a0  lea     r9, [rbp+var_18]
0x14000a9a4  mov     r15, rcx
0x14000a9a7  call    OpenRemoteDatabase
0x14000a9ac  cmp     [rbp+arg_18], 0
0x14000a9b0  mov     ebx, eax
0x14000a9b2  jz      short loc_14000A9ED
0x14000a9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9bb  lea     rdx, WPP_GLOBAL_Control
0x14000a9c2  cmp     rcx, rdx
0x14000a9c5  jz      loc_14000AC35
0x14000a9cb  mov     edx, [rcx+2Ch]
0x14000a9ce  test    dl, 1
0x14000a9d1  jz      loc_14000AC35
0x14000a9d7  mov     rcx, [rcx+18h]
0x14000a9db  mov     edx, 45h ; 'E'
0x14000a9e0  mov     r9d, eax
0x14000a9e3  call    WPP_SF_L
0x14000a9e8  jmp     loc_14000AC35
0x14000a9ed  cmp     [rbp+var_18], 0
0x14000a9f2  jnz     short loc_14000AA2C
0x14000a9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9fb  lea     rdx, WPP_GLOBAL_Control
0x14000aa02  cmp     rcx, rdx
0x14000aa05  jz      short loc_14000AA22
0x14000aa07  mov     eax, [rcx+2Ch]
0x14000aa0a  test    al, 1
0x14000aa0c  jz      short loc_14000AA22
0x14000aa0e  mov     rcx, [rcx+18h]
0x14000aa12  mov     edx, 46h ; 'F'
0x14000aa17  mov     r9d, 0C000009Ah
0x14000aa1d  call    WPP_SF_L
0x14000aa22  mov     eax, 0C000009Ah
0x14000aa27  jmp     loc_14000AC37
0x14000aa2c  xor     r14d, r14d
0x14000aa2f  mov     rdx, [rbp+var_18]
0x14000aa33  lea     r9, [rbp+P]
0x14000aa37  mov     r8d, r14d
0x14000aa3a  mov     rcx, r15
0x14000aa3d  call    GetRemoteDatabaseEntry
0x14000aa42  mov     ebx, eax
0x14000aa44  test    eax, eax
0x14000aa46  js      loc_14000ABFA
0x14000aa4c  mov     rdi, [rbp+P]
0x14000aa50  test    rdi, rdi
0x14000aa53  jz      loc_14000AC25
0x14000aa59  movzx   eax, word ptr [rdi+0Eh]
0x14000aa5d  cmp     ax, [r13+0]
0x14000aa62  jnz     loc_14000AB53
0x14000aa68  movzx   edx, word ptr [rdi+0Ch]
0x14000aa6c  lea     rcx, [r13+2]; Source1
0x14000aa70  add     rdx, rdi; Source2
0x14000aa73  mov     r8d, eax; Length
0x14000aa76  mov     ebx, eax
0x14000aa78  call    cs:__imp_RtlCompareMemory
0x14000aa7f  nop     dword ptr [rax+rax+00h]
0x14000aa84  cmp     rax, rbx
0x14000aa87  jnz     loc_14000AB53
0x14000aa8d  movzx   eax, word ptr [r13+0]
0x14000aa92  mov     ecx, 102h
0x14000aa97  movzx   ebx, word ptr [r12]
0x14000aa9c  mov     r8d, 41746E4Dh
0x14000aaa2  sub     ebx, eax
0x14000aaa4  add     ebx, [rdi]
0x14000aaa6  mov     edx, ebx
0x14000aaa8  call    cs:__imp_ExAllocatePool2
0x14000aaaf  nop     dword ptr [rax+rax+00h]
0x14000aab4  mov     rsi, rax
0x14000aab7  test    rax, rax
0x14000aaba  jz      loc_14000AB53
0x14000aac0  mov     [rax], ebx
0x14000aac2  mov     edx, 10h
0x14000aac7  mov     eax, [rdi+4]
0x14000aaca  mov     [rsi+4], eax
0x14000aacd  mov     [rsi+8], dx
0x14000aad1  movzx   ecx, word ptr [rdi+0Ah]
0x14000aad5  mov     [rsi+0Ah], cx
0x14000aad9  mov     r8d, ecx; Size
0x14000aadc  lea     eax, [rdx+rcx]
0x14000aadf  mov     [rsi+0Ch], ax
0x14000aae3  lea     rcx, [rsi+10h]; void *
0x14000aae7  movzx   eax, word ptr [r12]
0x14000aaec  mov     [rsi+0Eh], ax
0x14000aaf0  movzx   edx, word ptr [rdi+8]
0x14000aaf4  add     rdx, rdi; Src
0x14000aaf7  call    memmove
0x14000aafc  movzx   ecx, word ptr [rsi+0Ch]
0x14000ab00  lea     rdx, [r12+2]; Src
0x14000ab05  movzx   r8d, word ptr [rsi+0Eh]; Size
0x14000ab0a  add     rcx, rsi; void *
0x14000ab0d  call    memmove
0x14000ab12  mov     rdx, [rbp+var_18]
0x14000ab16  mov     r8d, r14d
0x14000ab19  mov     rcx, r15
0x14000ab1c  call    DeleteRemoteDatabaseEntry
0x14000ab21  mov     ebx, eax
0x14000ab23  test    eax, eax
0x14000ab25  js      loc_14000ABB1
0x14000ab2b  mov     rdx, [rbp+var_18]
0x14000ab2f  mov     r8, rsi
0x14000ab32  mov     rcx, r15
0x14000ab35  call    AddRemoteDatabaseEntry
0x14000ab3a  xor     edx, edx; Tag
0x14000ab3c  mov     ebx, eax
0x14000ab3e  test    eax, eax
0x14000ab40  js      short loc_14000AB6C
0x14000ab42  mov     rcx, rsi; P
0x14000ab45  call    cs:__imp_ExFreePoolWithTag
0x14000ab4c  nop     dword ptr [rax+rax+00h]
0x14000ab51  jmp     short loc_14000AB56
0x14000ab53  add     r14d, [rdi]
0x14000ab56  xor     edx, edx; Tag
0x14000ab58  mov     rcx, rdi; P
0x14000ab5b  call    cs:__imp_ExFreePoolWithTag
0x14000ab62  nop     dword ptr [rax+rax+00h]
0x14000ab67  jmp     loc_14000AA2F
0x14000ab6c  mov     rcx, rdi; P
0x14000ab6f  call    cs:__imp_ExFreePoolWithTag
0x14000ab76  nop     dword ptr [rax+rax+00h]
0x14000ab7b  xor     edx, edx; Tag
0x14000ab7d  mov     rcx, rsi; P
0x14000ab80  call    cs:__imp_ExFreePoolWithTag
0x14000ab87  nop     dword ptr [rax+rax+00h]
0x14000ab8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab93  lea     rdx, WPP_GLOBAL_Control
0x14000ab9a  cmp     rcx, rdx
0x14000ab9d  jz      loc_14000AC25
0x14000aba3  mov     eax, [rcx+2Ch]
0x14000aba6  test    al, 1
0x14000aba8  jz      short loc_14000AC25
0x14000abaa  mov     edx, 49h ; 'I'
0x14000abaf  jmp     short loc_14000AC19
0x14000abb1  xor     edx, edx; Tag
0x14000abb3  mov     rcx, rdi; P
0x14000abb6  call    cs:__imp_ExFreePoolWithTag
0x14000abbd  nop     dword ptr [rax+rax+00h]
0x14000abc2  xor     edx, edx; Tag
0x14000abc4  mov     rcx, rsi; P
0x14000abc7  call    cs:__imp_ExFreePoolWithTag
0x14000abce  nop     dword ptr [rax+rax+00h]
0x14000abd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000abda  lea     rdx, WPP_GLOBAL_Control
0x14000abe1  cmp     rcx, rdx
0x14000abe4  jz      short loc_14000AC25
0x14000abe6  mov     eax, [rcx+2Ch]
0x14000abe9  test    al, 1
0x14000abeb  jz      short loc_14000AC25
0x14000abed  cmp     byte ptr [rcx+29h], 1
0x14000abf1  jb      short loc_14000AC25
0x14000abf3  mov     edx, 48h ; 'H'
0x14000abf8  jmp     short loc_14000AC19
0x14000abfa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac01  lea     rdx, WPP_GLOBAL_Control
0x14000ac08  cmp     rcx, rdx
0x14000ac0b  jz      short loc_14000AC25
0x14000ac0d  mov     eax, [rcx+2Ch]
0x14000ac10  test    al, 1
0x14000ac12  jz      short loc_14000AC25
0x14000ac14  mov     edx, 47h ; 'G'
0x14000ac19  mov     rcx, [rcx+18h]
0x14000ac1d  mov     r9d, ebx
0x14000ac20  call    WPP_SF_L
0x14000ac25  mov     rdx, [rbp+var_18]
0x14000ac29  mov     rcx, [r15+98h]
0x14000ac30  call    CloseFileHandleOutsideExtensionMutexLock
0x14000ac35  mov     eax, ebx
0x14000ac37  add     rsp, 38h
0x14000ac3b  pop     r15
0x14000ac3d  pop     r14
0x14000ac3f  pop     r13
0x14000ac41  pop     r12
0x14000ac43  pop     rdi
0x14000ac44  pop     rsi
0x14000ac45  pop     rbx
0x14000ac46  pop     rbp
0x14000ac47  retn
```
