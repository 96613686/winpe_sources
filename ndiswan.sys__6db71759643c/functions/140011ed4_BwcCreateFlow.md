# BwcCreateFlow

- ea: `0x140011ed4`
- end: `0x140011fd3`
- name: `BwcCreateFlow`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140011064`
- `0x140013940`

## callees

- `0x140011ed4`
- `0x1400134d8`
- `0x140013570`
- `0x1400154bc`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140011f72`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011f72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fb6`
- `ntoskrnl!ExAllocatePool2` at `0x140011ef3`
- `ntoskrnl!ExAllocatePool2` at `0x140011ef3`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140011f55`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140011f55`

## pseudocode

```c
__int64 __fastcall BwcCreateFlow(_QWORD *a1, __int64 *a2)
{
  _DWORD *Pool2; // rax
  __int64 v5; // rdi
  __int64 v7; // rcx
  int updated; // ebx

  Pool2 = (_DWORD *)ExAllocatePool2(64, 496, 1835235138);
  v5 = (__int64)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Pool2[122] = 2;
  v7 = _InterlockedExchangeAdd(&BwcTimerUnitAssignmentIndex, 1u) % (unsigned int)BwcNumberOfProcessors;
  *Pool2 = v7;
  RtlInitializeTimerWheelEntry(*((_QWORD *)BwcTimerUnits + 24 * v7 + 20), Pool2 + 2, 0, 0);
  *(_DWORD *)(v5 + 464) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(v5 + 472));
  memset((void *)(v5 + 40), 0, 0x1A8u);
  QosTbcFlowInitialize(v5 + 40);
  updated = BwcUpdateFlow(a1, v5);
  if ( updated < 0 )
  {
    BwcUninitializeFlow(v5);
    ExFreePoolWithTag((PVOID)v5, 0);
    v5 = 0;
  }
  *a2 = v5;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140011ed4  push    rbx
0x140011ed6  push    rbp
0x140011ed7  push    rsi
0x140011ed8  push    rdi
0x140011ed9  sub     rsp, 28h
0x140011edd  mov     rsi, rdx
0x140011ee0  mov     rbp, rcx
0x140011ee3  mov     edx, 1F0h
0x140011ee8  mov     ecx, 40h ; '@'
0x140011eed  mov     r8d, 6D637742h
0x140011ef3  call    cs:__imp_ExAllocatePool2
0x140011efa  nop     dword ptr [rax+rax+00h]
0x140011eff  mov     rdi, rax
0x140011f02  test    rax, rax
0x140011f05  jnz     short loc_140011F11
0x140011f07  mov     eax, 0C000009Ah
0x140011f0c  jmp     loc_140011FC9
0x140011f11  mov     dword ptr [rax+1E8h], 2
0x140011f1b  mov     eax, 1
0x140011f20  lock xadd cs:BwcTimerUnitAssignmentIndex, eax
0x140011f28  xor     edx, edx
0x140011f2a  xor     r9d, r9d
0x140011f2d  div     cs:BwcNumberOfProcessors
0x140011f33  xor     r8d, r8d
0x140011f36  mov     ecx, edx
0x140011f38  lea     rdx, [rdi+8]
0x140011f3c  mov     [rdi], ecx
0x140011f3e  lea     rax, [rcx+rcx*2]
0x140011f42  mov     rcx, cs:BwcTimerUnits
0x140011f49  shl     rax, 6
0x140011f4d  mov     rcx, [rax+rcx+0A0h]
0x140011f55  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140011f5c  nop     dword ptr [rax+rax+00h]
0x140011f61  lea     rcx, [rdi+1D8h]; SpinLock
0x140011f68  mov     dword ptr [rdi+1D0h], 0
0x140011f72  call    cs:__imp_KeInitializeSpinLock
0x140011f79  nop     dword ptr [rax+rax+00h]
0x140011f7e  xor     edx, edx; Val
0x140011f80  lea     rcx, [rdi+28h]; void *
0x140011f84  mov     r8d, 1A8h; Size
0x140011f8a  call    memset
0x140011f8f  lea     rcx, [rdi+28h]
0x140011f93  call    QosTbcFlowInitialize
0x140011f98  mov     rdx, rdi
0x140011f9b  mov     rcx, rbp
0x140011f9e  call    BwcUpdateFlow
0x140011fa3  mov     ebx, eax
0x140011fa5  test    eax, eax
0x140011fa7  jns     short loc_140011FC4
0x140011fa9  mov     rcx, rdi
0x140011fac  call    BwcUninitializeFlow
0x140011fb1  xor     edx, edx; Tag
0x140011fb3  mov     rcx, rdi; P
0x140011fb6  call    cs:__imp_ExFreePoolWithTag
0x140011fbd  nop     dword ptr [rax+rax+00h]
0x140011fc2  xor     edi, edi
0x140011fc4  mov     [rsi], rdi
0x140011fc7  mov     eax, ebx
0x140011fc9  add     rsp, 28h
0x140011fcd  pop     rdi
0x140011fce  pop     rsi
0x140011fcf  pop     rbp
0x140011fd0  pop     rbx
0x140011fd1  retn
```
