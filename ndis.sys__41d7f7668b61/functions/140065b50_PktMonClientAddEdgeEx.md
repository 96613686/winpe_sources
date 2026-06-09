# PktMonClientAddEdgeEx

- ea: `0x140065b50`
- end: `0x140065c75`
- name: `PktMonClientAddEdgeEx`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400659a0`

## callees

- `0x140065b50`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140065c0a`
- `ntoskrnl!KeReleaseMutex` at `0x140065c0a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065ba0`
- `ntoskrnl!KeWaitForSingleObject` at `0x140065ba0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140065bb3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140065bb3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140065bf5`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140065bf5`

## pseudocode

```c
__int64 __fastcall PktMonClientAddEdgeEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  unsigned int v7; // ebx
  __int64 v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rdx
  __int16 v12; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+32h] [rbp-26h]
  __int16 v14; // [rsp+36h] [rbp-22h]
  __int64 v15; // [rsp+38h] [rbp-20h]
  int v16; // [rsp+40h] [rbp-18h]
  int v17; // [rsp+44h] [rbp-14h]
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v15 = a2;
  v16 = 3;
  v13 = 0;
  v14 = 0;
  v18 = 0;
  v12 = 24;
  v17 = 4;
  KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
  if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int16 *, __int64 *))(*((_QWORD *)&xmmword_140123740 + 1) + 32LL))(
           xmmword_140123740,
           *(_QWORD *)(a1 + 40),
           &v12,
           &v18);
    if ( !v7 )
    {
      v9 = *(_QWORD *)(a1 + 16);
      v10 = (__int64 *)(a1 + 16);
      if ( *(_QWORD *)(v9 + 8) != a1 + 16 )
        __fastfail(3u);
      v11 = a6;
      *(_QWORD *)(a6 + 8) = v10;
      *(_QWORD *)v11 = v9;
      *(_QWORD *)(v9 + 8) = v11;
      *v10 = v11;
      ++*(_DWORD *)(a1 + 32);
      *(_QWORD *)(v11 + 16) = v18;
      *(_DWORD *)(v11 + 32) = a5;
      *(_QWORD *)(v11 + 24) = a1;
    }
    ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
  }
  else
  {
    v7 = -1073741661;
  }
  KeReleaseMutex(&PktMonCompMutex, 0);
  return v7;
}

```

## disassembly

```asm
0x140065b50  mov     [rsp+arg_0], rbx
0x140065b55  push    rdi
0x140065b56  sub     rsp, 50h
0x140065b5a  mov     rdi, rcx
0x140065b5d  mov     [rsp+58h+var_20], rdx
0x140065b62  xor     ecx, ecx
0x140065b64  mov     [rsp+58h+var_18], 3
0x140065b6c  mov     [rsp+58h+var_26], ecx
0x140065b70  mov     eax, 18h
0x140065b75  mov     [rsp+58h+var_22], cx
0x140065b7a  xor     r9d, r9d; Alertable
0x140065b7d  mov     [rsp+58h+arg_8], rcx
0x140065b82  xor     r8d, r8d; WaitMode
0x140065b85  mov     [rsp+58h+Timeout], rcx; Timeout
0x140065b8a  xor     edx, edx; WaitReason
0x140065b8c  lea     rcx, PktMonCompMutex; Object
0x140065b93  mov     [rsp+58h+var_28], ax
0x140065b98  mov     [rsp+58h+var_14], 4
0x140065ba0  call    cs:__imp_KeWaitForSingleObject
0x140065ba7  nop     dword ptr [rax+rax+00h]
0x140065bac  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140065bb3  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140065bba  nop     dword ptr [rax+rax+00h]
0x140065bbf  test    al, al
0x140065bc1  jz      short loc_140065C24
0x140065bc3  mov     rax, qword ptr cs:xmmword_140123740+8
0x140065bca  lea     r9, [rsp+58h+arg_8]
0x140065bcf  mov     rdx, [rdi+28h]
0x140065bd3  lea     r8, [rsp+58h+var_28]
0x140065bd8  mov     rcx, qword ptr cs:xmmword_140123740
0x140065bdf  mov     rax, [rax+20h]
0x140065be3  call    _guard_dispatch_icall
0x140065be8  mov     ebx, eax
0x140065bea  test    eax, eax
0x140065bec  jz      short loc_140065C2B
0x140065bee  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140065bf5  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140065bfc  nop     dword ptr [rax+rax+00h]
0x140065c01  xor     edx, edx; Wait
0x140065c03  lea     rcx, PktMonCompMutex; Mutex
0x140065c0a  call    cs:__imp_KeReleaseMutex
0x140065c11  nop     dword ptr [rax+rax+00h]
0x140065c16  mov     eax, ebx
0x140065c18  mov     rbx, [rsp+58h+arg_0]
0x140065c1d  add     rsp, 50h
0x140065c21  pop     rdi
0x140065c22  retn
0x140065c24  mov     ebx, 0C00000A3h
0x140065c29  jmp     short loc_140065C01
0x140065c2b  mov     r8, [rdi+10h]
0x140065c2f  lea     rax, [rdi+10h]
0x140065c33  cmp     [r8+8], rax
0x140065c37  jz      short loc_140065C40
0x140065c39  mov     ecx, 3
0x140065c3e  int     29h; Win8: RtlFailFast(ecx)
0x140065c40  mov     rdx, [rsp+58h+arg_28]
0x140065c48  mov     [rdx+8], rax
0x140065c4c  mov     [rdx], r8
0x140065c4f  mov     [r8+8], rdx
0x140065c53  mov     [rax], rdx
0x140065c56  inc     dword ptr [rdi+20h]
0x140065c59  mov     rax, [rsp+58h+arg_8]
0x140065c5e  mov     [rdx+10h], rax
0x140065c62  mov     eax, [rsp+58h+arg_20]
0x140065c69  mov     [rdx+20h], eax
0x140065c6c  mov     [rdx+18h], rdi
0x140065c70  jmp     loc_140065BEE
```
