# PcDetachQoSClient

- ea: `0x14000fed0`
- end: `0x14000ff68`
- name: `PcDetachQoSClient`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000fed0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000ff2c`
- `NDIS!NdisReleaseRWLock` at `0x14000ff2c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000fefb`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000fefb`
- `NETIO!NmrProviderDetachClientComplete` at `0x14000ff49`
- `NETIO!NmrProviderDetachClientComplete` at `0x14000ff49`

## pseudocode

```c
__int64 __fastcall PcDetachQoSClient(volatile signed __int32 *a1)
{
  __int64 *v2; // rcx
  __int64 **v3; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *((_QWORD *)a1 + 5) = *((_QWORD *)a1 + 6);
  NdisAcquireRWLockWrite(PcgQoSClientListLock, &LockState, 0);
  v2 = *(__int64 **)a1;
  if ( *(volatile signed __int32 **)(*(_QWORD *)a1 + 8LL) != a1
    || (v3 = (__int64 **)*((_QWORD *)a1 + 1), *v3 != (__int64 *)a1) )
  {
    __fastfail(3u);
  }
  *v3 = v2;
  v2[1] = (__int64)v3;
  NdisReleaseRWLock(PcgQoSClientListLock, &LockState);
  if ( _InterlockedExchangeAdd(a1 + 8, 0xFFFFFFFF) == 1 )
    NmrProviderDetachClientComplete(*((HANDLE *)a1 + 5));
  return 259;
}

```

## disassembly

```asm
0x14000fed0  push    rbx
0x14000fed2  sub     rsp, 20h
0x14000fed6  xor     eax, eax
0x14000fed8  lea     rdx, [rsp+28h+LockState]; LockState
0x14000fedd  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000fee2  mov     rbx, rcx
0x14000fee5  mov     [rsp+28h+LockState.Flags], al
0x14000fee9  xor     r8d, r8d; Flags
0x14000feec  mov     rax, [rcx+30h]
0x14000fef0  mov     [rcx+28h], rax
0x14000fef4  mov     rcx, cs:PcgQoSClientListLock; Lock
0x14000fefb  call    cs:__imp_NdisAcquireRWLockWrite
0x14000ff02  nop     dword ptr [rax+rax+00h]
0x14000ff07  mov     rcx, [rbx]
0x14000ff0a  cmp     [rcx+8], rbx
0x14000ff0e  jnz     short loc_14000FF61
0x14000ff10  mov     rax, [rbx+8]
0x14000ff14  cmp     [rax], rbx
0x14000ff17  jnz     short loc_14000FF61
0x14000ff19  mov     [rax], rcx
0x14000ff1c  lea     rdx, [rsp+28h+LockState]; LockState
0x14000ff21  mov     [rcx+8], rax
0x14000ff25  mov     rcx, cs:PcgQoSClientListLock; Lock
0x14000ff2c  call    cs:__imp_NdisReleaseRWLock
0x14000ff33  nop     dword ptr [rax+rax+00h]
0x14000ff38  or      eax, 0FFFFFFFFh
0x14000ff3b  lock xadd [rbx+20h], eax
0x14000ff40  cmp     eax, 1
0x14000ff43  jnz     short loc_14000FF55
0x14000ff45  mov     rcx, [rbx+28h]; NmrBindingHandle
0x14000ff49  call    cs:__imp_NmrProviderDetachClientComplete
0x14000ff50  nop     dword ptr [rax+rax+00h]
0x14000ff55  mov     eax, 103h
0x14000ff5a  add     rsp, 20h
0x14000ff5e  pop     rbx
0x14000ff5f  retn
0x14000ff61  mov     ecx, 3
0x14000ff66  int     29h; Win8: RtlFailFast(ecx)
```
