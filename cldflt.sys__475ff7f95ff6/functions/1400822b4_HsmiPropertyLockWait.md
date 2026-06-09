# HsmiPropertyLockWait

- ea: `0x1400822b4`
- end: `0x140082442`
- name: `HsmiPropertyLockWait`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14006e898`

## callees

- `0x140003c50`
- `0x1400822b4`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400822fd`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400822fd`
- `ntoskrnl!KeReadStateEvent` at `0x1400823a0`
- `ntoskrnl!KeReadStateEvent` at `0x1400823a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082348`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082401`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082348`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140082401`
- `ntoskrnl!KeClearEvent` at `0x140082325`
- `ntoskrnl!KeClearEvent` at `0x140082325`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008233c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400823f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008233c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400823f5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008238e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008238e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008237c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008237c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008236c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008236c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082415`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082415`

## pseudocode

```c
__int64 __fastcall HsmiPropertyLockWait(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rdx
  __int64 v4; // rbp
  signed __int64 UnbiasedInterruptTime; // rax
  signed __int64 v6; // rcx
  char v7; // si
  unsigned int v8; // edi
  __int64 **v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  v3 = *(_QWORD **)(a1 + 104);
  if ( *v3 != a1 + 96 )
    goto LABEL_13;
  v4 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a2 + 64) = a1 + 96;
  *(_QWORD *)(a2 + 72) = v3;
  *v3 = a2 + 64;
  *(_QWORD *)(a1 + 104) = a2 + 64;
  while ( 1 )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v6 = *(_QWORD *)(a2 + 56);
    if ( UnbiasedInterruptTime >= v6 )
      break;
    Timeout.QuadPart = UnbiasedInterruptTime - v6;
    KeClearEvent((PRKEVENT)(a2 + 24));
    *(_DWORD *)(a2 + 48) = 259;
    ExReleaseResourceLite((PERESOURCE)(v4 + 120));
    KeLeaveCriticalRegion();
    v7 = 0;
    if ( KeWaitForSingleObject((PVOID)(a2 + 24), Executive, 0, 1u, &Timeout) )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 120), 1u);
      v7 = 1;
      if ( !KeReadStateEvent((PRKEVENT)(a2 + 24)) )
        continue;
    }
    v8 = *(_DWORD *)(a2 + 48);
    goto LABEL_10;
  }
  v9 = *(__int64 ***)(a2 + 72);
  v10 = *v9;
  if ( (__int64 **)(*v9)[1] != v9 || (v11 = (__int64 *)*v10, *(__int64 **)(*v10 + 8) != v10) )
LABEL_13:
    __fastfail(3u);
  *v9 = v11;
  v7 = 1;
  v11[1] = (__int64)v9;
  *(_QWORD *)(a2 + 72) = a2 + 64;
  *(_QWORD *)(a2 + 64) = a2 + 64;
  v8 = -1073688806;
LABEL_10:
  HsmDbgBreakOnStatus(v8);
  if ( v7 )
  {
    ExReleaseResourceLite((PERESOURCE)(v4 + 120));
    KeLeaveCriticalRegion();
  }
  ExFreePoolWithTag((PVOID)a2, 0x72507348u);
  return v8;
}

```

## disassembly

```asm
0x1400822b4  mov     [rsp+arg_8], rbx
0x1400822b9  mov     [rsp+arg_10], rbp
0x1400822be  push    rsi
0x1400822bf  push    rdi
0x1400822c0  push    r12
0x1400822c2  push    r14
0x1400822c4  push    r15
0x1400822c6  sub     rsp, 30h
0x1400822ca  lea     rax, [rcx+60h]
0x1400822ce  mov     qword ptr [rsp+58h+arg_0], 0
0x1400822d7  mov     rbx, rdx
0x1400822da  mov     rdx, [rax+8]
0x1400822de  cmp     [rdx], rax
0x1400822e1  jnz     loc_14008243B
0x1400822e7  mov     rbp, [rcx+8]
0x1400822eb  lea     rdi, [rbx+40h]
0x1400822ef  mov     [rdi], rax
0x1400822f2  mov     [rdi+8], rdx
0x1400822f6  mov     [rdx], rdi
0x1400822f9  mov     [rax+8], rdi
0x1400822fd  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140082304  nop     dword ptr [rax+rax+00h]
0x140082309  mov     rcx, [rbx+38h]
0x14008230d  cmp     rax, rcx
0x140082310  jge     loc_1400823B9
0x140082316  sub     rax, rcx
0x140082319  lea     r15, [rbx+18h]
0x14008231d  mov     rcx, r15; Event
0x140082320  mov     qword ptr [rsp+58h+arg_0], rax
0x140082325  call    cs:__imp_KeClearEvent
0x14008232c  nop     dword ptr [rax+rax+00h]
0x140082331  lea     rcx, [rbp+78h]; Resource
0x140082335  mov     dword ptr [rbx+30h], 103h
0x14008233c  call    cs:__imp_ExReleaseResourceLite
0x140082343  nop     dword ptr [rax+rax+00h]
0x140082348  call    cs:__imp_KeLeaveCriticalRegion
0x14008234f  nop     dword ptr [rax+rax+00h]
0x140082354  lea     rax, [rsp+58h+arg_0]
0x140082359  mov     r9b, 1; Alertable
0x14008235c  xor     r8d, r8d; WaitMode
0x14008235f  mov     [rsp+58h+Timeout], rax; Timeout
0x140082364  xor     edx, edx; WaitReason
0x140082366  mov     rcx, r15; Object
0x140082369  xor     sil, sil
0x14008236c  call    cs:__imp_KeWaitForSingleObject
0x140082373  nop     dword ptr [rax+rax+00h]
0x140082378  test    eax, eax
0x14008237a  jz      short loc_1400823B4
0x14008237c  call    cs:__imp_KeEnterCriticalRegion
0x140082383  nop     dword ptr [rax+rax+00h]
0x140082388  mov     dl, 1; Wait
0x14008238a  lea     rcx, [rbp+78h]; Resource
0x14008238e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140082395  nop     dword ptr [rax+rax+00h]
0x14008239a  mov     rcx, r15; Event
0x14008239d  mov     sil, 1
0x1400823a0  call    cs:__imp_KeReadStateEvent
0x1400823a7  nop     dword ptr [rax+rax+00h]
0x1400823ac  test    eax, eax
0x1400823ae  jz      loc_1400822FD
0x1400823b4  mov     edi, [rbx+30h]
0x1400823b7  jmp     short loc_1400823E5
0x1400823b9  mov     rax, [rbx+48h]
0x1400823bd  mov     rcx, [rax]
0x1400823c0  cmp     [rcx+8], rax
0x1400823c4  jnz     short loc_14008243B
0x1400823c6  mov     rdx, [rcx]
0x1400823c9  cmp     [rdx+8], rcx
0x1400823cd  jnz     short loc_14008243B
0x1400823cf  mov     [rax], rdx
0x1400823d2  mov     sil, 1
0x1400823d5  mov     [rdx+8], rax
0x1400823d9  mov     [rdi+8], rdi
0x1400823dd  mov     [rdi], rdi
0x1400823e0  mov     edi, 0C000CF1Ah
0x1400823e5  mov     ecx, edi
0x1400823e7  call    HsmDbgBreakOnStatus
0x1400823ec  test    sil, sil
0x1400823ef  jz      short loc_14008240D
0x1400823f1  lea     rcx, [rbp+78h]; Resource
0x1400823f5  call    cs:__imp_ExReleaseResourceLite
0x1400823fc  nop     dword ptr [rax+rax+00h]
0x140082401  call    cs:__imp_KeLeaveCriticalRegion
0x140082408  nop     dword ptr [rax+rax+00h]
0x14008240d  mov     edx, 72507348h; Tag
0x140082412  mov     rcx, rbx; P
0x140082415  call    cs:__imp_ExFreePoolWithTag
0x14008241c  nop     dword ptr [rax+rax+00h]
0x140082421  mov     rbx, [rsp+58h+arg_8]
0x140082426  mov     eax, edi
0x140082428  mov     rbp, [rsp+58h+arg_10]
0x14008242d  add     rsp, 30h
0x140082431  pop     r15
0x140082433  pop     r14
0x140082435  pop     r12
0x140082437  pop     rdi
0x140082438  pop     rsi
0x140082439  retn
0x14008243b  mov     ecx, 3
0x140082440  int     29h; Win8: RtlFailFast(ecx)
```
