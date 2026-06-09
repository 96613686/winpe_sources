# ProcessFilterData

- ea: `0x14000da84`
- end: `0x14000db57`
- name: `ProcessFilterData`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d770`

## callees

- `0x14000da84`
- `0x14000de38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000db3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000db3f`
- `ntoskrnl!ExAllocatePool2` at `0x14000dac7`
- `ntoskrnl!ExAllocatePool2` at `0x14000dac7`
- `NDIS!NdisReleaseRWLock` at `0x14000db24`
- `NDIS!NdisReleaseRWLock` at `0x14000db24`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000dafe`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000dafe`

## pseudocode

```c
void __fastcall ProcessFilterData(__int64 a1)
{
  __int64 Pool2; // rax
  void *v3; // rbx
  PVOID v4; // rdi
  void *v5; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( (int)TraceFilterEngineValidateAndStoreRules(a1, 0, &v7) >= 0 )
  {
    Pool2 = ExAllocatePool2(64, v7, 1366188375);
    v3 = (void *)Pool2;
    if ( Pool2 )
    {
      if ( (int)TraceFilterEngineValidateAndStoreRules(a1, Pool2, &v7) < 0 )
      {
        v5 = v3;
      }
      else
      {
        NdisAcquireRWLockWrite(NdisWanPacketCapFilterLock, &LockState, 0);
        v4 = NDISWanPacketCapRules;
        NDISWanPacketCapRules = v3;
        NdisReleaseRWLock(NdisWanPacketCapFilterLock, &LockState);
        if ( !v4 )
          return;
        v5 = v4;
      }
      ExFreePoolWithTag(v5, 0);
    }
  }
}

```

## disassembly

```asm
0x14000da84  mov     [rsp+arg_0], rbx
0x14000da89  push    rdi
0x14000da8a  sub     rsp, 20h
0x14000da8e  xor     eax, eax
0x14000da90  mov     [rsp+28h+arg_10], 0
0x14000da98  lea     r8, [rsp+28h+arg_10]
0x14000da9d  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000daa2  xor     edx, edx
0x14000daa4  mov     [rsp+28h+LockState.Flags], al
0x14000daa8  mov     rdi, rcx
0x14000daab  call    TraceFilterEngineValidateAndStoreRules
0x14000dab0  test    eax, eax
0x14000dab2  js      loc_14000DB4B
0x14000dab8  mov     edx, [rsp+28h+arg_10]
0x14000dabc  mov     ecx, 40h ; '@'
0x14000dac1  mov     r8d, 516E6157h
0x14000dac7  call    cs:__imp_ExAllocatePool2
0x14000dace  nop     dword ptr [rax+rax+00h]
0x14000dad3  mov     rbx, rax
0x14000dad6  test    rax, rax
0x14000dad9  jz      short loc_14000DB4B
0x14000dadb  lea     r8, [rsp+28h+arg_10]
0x14000dae0  mov     rdx, rax
0x14000dae3  mov     rcx, rdi
0x14000dae6  call    TraceFilterEngineValidateAndStoreRules
0x14000daeb  test    eax, eax
0x14000daed  js      short loc_14000DB3A
0x14000daef  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000daf6  lea     rdx, [rsp+28h+LockState]; LockState
0x14000dafb  xor     r8d, r8d; Flags
0x14000dafe  call    cs:__imp_NdisAcquireRWLockWrite
0x14000db05  nop     dword ptr [rax+rax+00h]
0x14000db0a  mov     rdi, cs:NDISWanPacketCapRules
0x14000db11  lea     rdx, [rsp+28h+LockState]; LockState
0x14000db16  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000db1d  mov     cs:NDISWanPacketCapRules, rbx
0x14000db24  call    cs:__imp_NdisReleaseRWLock
0x14000db2b  nop     dword ptr [rax+rax+00h]
0x14000db30  test    rdi, rdi
0x14000db33  jz      short loc_14000DB4B
0x14000db35  mov     rcx, rdi
0x14000db38  jmp     short loc_14000DB3D
0x14000db3a  mov     rcx, rbx; P
0x14000db3d  xor     edx, edx; Tag
0x14000db3f  call    cs:__imp_ExFreePoolWithTag
0x14000db46  nop     dword ptr [rax+rax+00h]
0x14000db4b  mov     rbx, [rsp+28h+arg_0]
0x14000db50  add     rsp, 20h
0x14000db54  pop     rdi
0x14000db55  retn
```
