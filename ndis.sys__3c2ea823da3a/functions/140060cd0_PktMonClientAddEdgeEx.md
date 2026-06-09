# PktMonClientAddEdgeEx

- ea: `0x140060cd0`
- end: `0x140060df5`
- name: `PktMonClientAddEdgeEx`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140060b20`

## callees

- `0x140060cd0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140060d8a`
- `ntoskrnl!KeReleaseMutex` at `0x140060d8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060d20`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060d20`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060d33`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140060d33`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060d75`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060d75`

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
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int16 *, __int64 *))(*((_QWORD *)&xmmword_14011D750 + 1) + 32LL))(
           xmmword_14011D750,
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
0x140060cd0  mov     [rsp+arg_0], rbx
0x140060cd5  push    rdi
0x140060cd6  sub     rsp, 50h
0x140060cda  mov     rdi, rcx
0x140060cdd  mov     [rsp+58h+var_20], rdx
0x140060ce2  xor     ecx, ecx
0x140060ce4  mov     [rsp+58h+var_18], 3
0x140060cec  mov     [rsp+58h+var_26], ecx
0x140060cf0  mov     eax, 18h
0x140060cf5  mov     [rsp+58h+var_22], cx
0x140060cfa  xor     r9d, r9d; Alertable
0x140060cfd  mov     [rsp+58h+arg_8], rcx
0x140060d02  xor     r8d, r8d; WaitMode
0x140060d05  mov     [rsp+58h+Timeout], rcx; Timeout
0x140060d0a  xor     edx, edx; WaitReason
0x140060d0c  lea     rcx, PktMonCompMutex; Object
0x140060d13  mov     [rsp+58h+var_28], ax
0x140060d18  mov     [rsp+58h+var_14], 4
0x140060d20  call    cs:__imp_KeWaitForSingleObject
0x140060d27  nop     dword ptr [rax+rax+00h]
0x140060d2c  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140060d33  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140060d3a  nop     dword ptr [rax+rax+00h]
0x140060d3f  test    al, al
0x140060d41  jz      short loc_140060DA4
0x140060d43  mov     rax, qword ptr cs:xmmword_14011D750+8
0x140060d4a  lea     r9, [rsp+58h+arg_8]
0x140060d4f  mov     rdx, [rdi+28h]
0x140060d53  lea     r8, [rsp+58h+var_28]
0x140060d58  mov     rcx, qword ptr cs:xmmword_14011D750
0x140060d5f  mov     rax, [rax+20h]
0x140060d63  call    _guard_dispatch_icall
0x140060d68  mov     ebx, eax
0x140060d6a  test    eax, eax
0x140060d6c  jz      short loc_140060DAB
0x140060d6e  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140060d75  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140060d7c  nop     dword ptr [rax+rax+00h]
0x140060d81  xor     edx, edx; Wait
0x140060d83  lea     rcx, PktMonCompMutex; Mutex
0x140060d8a  call    cs:__imp_KeReleaseMutex
0x140060d91  nop     dword ptr [rax+rax+00h]
0x140060d96  mov     eax, ebx
0x140060d98  mov     rbx, [rsp+58h+arg_0]
0x140060d9d  add     rsp, 50h
0x140060da1  pop     rdi
0x140060da2  retn
0x140060da4  mov     ebx, 0C00000A3h
0x140060da9  jmp     short loc_140060D81
0x140060dab  mov     r8, [rdi+10h]
0x140060daf  lea     rax, [rdi+10h]
0x140060db3  cmp     [r8+8], rax
0x140060db7  jz      short loc_140060DC0
0x140060db9  mov     ecx, 3
0x140060dbe  int     29h; Win8: RtlFailFast(ecx)
0x140060dc0  mov     rdx, [rsp+58h+arg_28]
0x140060dc8  mov     [rdx+8], rax
0x140060dcc  mov     [rdx], r8
0x140060dcf  mov     [r8+8], rdx
0x140060dd3  mov     [rax], rdx
0x140060dd6  inc     dword ptr [rdi+20h]
0x140060dd9  mov     rax, [rsp+58h+arg_8]
0x140060dde  mov     [rdx+10h], rax
0x140060de2  mov     eax, [rsp+58h+arg_20]
0x140060de9  mov     [rdx+20h], eax
0x140060dec  mov     [rdx+18h], rdi
0x140060df0  jmp     loc_140060D6E
```
