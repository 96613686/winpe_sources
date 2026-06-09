# PcpCleanupFileHandle

- ea: `0x14000d708`
- end: `0x14000d8af`
- name: `PcpCleanupFileHandle`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140020a90`

## callees

- `0x140005578`
- `0x14000a910`
- `0x14000b584`
- `0x14000d708`
- `0x14000dbb8`
- `0x14000eb54`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d77b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d77b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d76b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000d76b`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14000d81d`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14000d81d`

## pseudocode

```c
__int64 __fastcall PcpCleanupFileHandle(__int64 a1)
{
  __int64 v1; // rax
  KSPIN_LOCK *v2; // rbx
  __int64 *v3; // rcx
  __int64 **v4; // rax
  KIRQL v5; // al
  __int64 *v6; // rdx
  unsigned int v7; // r14d
  __int64 v8; // rdx
  __int128 *v9; // rbx
  __int128 *v10; // r15
  GUID *v11; // rdi
  GUID *v12; // r13
  NTSTATUS v13; // eax
  __int128 v15; // [rsp+20h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v15 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = *(KSPIN_LOCK **)(v1 + 24);
  RtlAcquireWriteLock(&WPP_MAIN_CB.Queue.Wcb.DeviceObject, &LockHandle);
  v3 = (__int64 *)*v2;
  if ( *(KSPIN_LOCK **)(*v2 + 8) != v2 || (v4 = (__int64 **)v2[1], *v4 != (__int64 *)v2) )
    __fastfail(3u);
  *v4 = v3;
  v3[1] = (__int64)v4;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v5 = KeAcquireSpinLockRaiseToDpc(v2 + 4);
  *((_BYTE *)v2 + 52) = 1;
  v6 = (__int64 *)v2[2];
  if ( v6 == (__int64 *)(v2 + 2) )
  {
    *((_QWORD *)&v15 + 1) = &v15;
    *(_QWORD *)&v15 = &v15;
  }
  else
  {
    v15 = *((_OWORD *)v2 + 1);
    v6[1] = (__int64)&v15;
    **((_QWORD **)&v15 + 1) = &v15;
    v2[3] = (KSPIN_LOCK)(v2 + 2);
    v2[2] = (KSPIN_LOCK)(v2 + 2);
  }
  v7 = *((_DWORD *)v2 + 12);
  *((_DWORD *)v2 + 12) = 0;
  KeReleaseSpinLock(v2 + 4, v5);
  v9 = (__int128 *)v15;
  while ( v9 != &v15 )
  {
    v10 = v9 - 1;
    v9 = *(__int128 **)v9;
    v11 = (GUID *)*((_QWORD *)v10 + 71);
    while ( v11 != (GUID *)((char *)v10 + 568) )
    {
      v12 = v11;
      v11 = *(GUID **)&v11->Data1;
      v13 = FwpmFilterDeleteByKey0(PcgWfpEngineHandle, v12 + 1);
      if ( v13 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids,
          (unsigned int)v13);
      }
      PcpFreeFilter(v12);
    }
    PcpDeleteFlow((char *)v10, v8);
  }
  if ( v7 )
    PcpFilterDecrementIntercept(v7);
  return 0;
}

```

## disassembly

```asm
0x14000d708  push    rbp
0x14000d70a  push    rbx
0x14000d70b  push    rsi
0x14000d70c  push    rdi
0x14000d70d  push    r13
0x14000d70f  push    r14
0x14000d711  push    r15
0x14000d713  mov     rbp, rsp
0x14000d716  sub     rsp, 50h
0x14000d71a  xor     eax, eax
0x14000d71c  lea     rdx, [rbp+LockHandle]
0x14000d720  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000d724  xorps   xmm0, xmm0
0x14000d727  mov     rax, [rcx+30h]
0x14000d72b  xorps   xmm1, xmm1
0x14000d72e  movups  [rbp+var_30], xmm0
0x14000d732  lea     rcx, WPP_MAIN_CB.Queue+30h
0x14000d739  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm1
0x14000d73d  mov     rbx, [rax+18h]
0x14000d741  call    RtlAcquireWriteLock
0x14000d746  mov     rcx, [rbx]
0x14000d749  cmp     [rcx+8], rbx
0x14000d74d  jnz     loc_14000D8A8
0x14000d753  mov     rax, [rbx+8]
0x14000d757  cmp     [rax], rbx
0x14000d75a  jnz     loc_14000D8A8
0x14000d760  mov     [rax], rcx
0x14000d763  mov     [rcx+8], rax
0x14000d767  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000d76b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000d772  nop     dword ptr [rax+rax+00h]
0x14000d777  lea     rcx, [rbx+20h]; SpinLock
0x14000d77b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d782  nop     dword ptr [rax+rax+00h]
0x14000d787  lea     rcx, [rbx+10h]
0x14000d78b  mov     byte ptr [rbx+34h], 1
0x14000d78f  mov     rdx, [rcx]
0x14000d792  mov     r8b, al
0x14000d795  cmp     rdx, rcx
0x14000d798  jnz     short loc_14000D7AC
0x14000d79a  lea     rax, [rbp+var_30]
0x14000d79e  mov     qword ptr [rbp+var_30+8], rax
0x14000d7a2  lea     rax, [rbp+var_30]
0x14000d7a6  mov     qword ptr [rbp+var_30], rax
0x14000d7aa  jmp     short loc_14000D7D2
0x14000d7ac  mov     qword ptr [rbp+var_30], rdx
0x14000d7b0  mov     rax, [rcx+8]
0x14000d7b4  mov     qword ptr [rbp+var_30+8], rax
0x14000d7b8  lea     rax, [rbp+var_30]
0x14000d7bc  mov     [rdx+8], rax
0x14000d7c0  lea     rdx, [rbp+var_30]
0x14000d7c4  mov     rax, qword ptr [rbp+var_30+8]
0x14000d7c8  mov     [rax], rdx
0x14000d7cb  mov     [rcx+8], rcx
0x14000d7cf  mov     [rcx], rcx
0x14000d7d2  mov     r14d, [rbx+30h]
0x14000d7d6  lea     rcx, [rbx+20h]; SpinLock
0x14000d7da  mov     dl, r8b; NewIrql
0x14000d7dd  mov     dword ptr [rbx+30h], 0
0x14000d7e4  call    cs:__imp_KeReleaseSpinLock
0x14000d7eb  nop     dword ptr [rax+rax+00h]
0x14000d7f0  mov     rbx, qword ptr [rbp+var_30]
0x14000d7f4  jmp     loc_14000D87C
0x14000d7f9  lea     r15, [rbx-10h]
0x14000d7fd  mov     rbx, [rbx]
0x14000d800  lea     rsi, [r15+238h]
0x14000d807  mov     rdi, [rsi]
0x14000d80a  jmp     short loc_14000D86F
0x14000d80c  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14000d813  mov     r13, rdi
0x14000d816  mov     rdi, [rdi]
0x14000d819  lea     rdx, [r13+10h]; key
0x14000d81d  call    cs:__imp_FwpmFilterDeleteByKey0
0x14000d824  nop     dword ptr [rax+rax+00h]
0x14000d829  test    eax, eax
0x14000d82b  jns     short loc_14000D867
0x14000d82d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d834  lea     rdx, WPP_GLOBAL_Control
0x14000d83b  cmp     rcx, rdx
0x14000d83e  jz      short loc_14000D867
0x14000d840  cmp     byte ptr [rcx+29h], 3
0x14000d844  jb      short loc_14000D867
0x14000d846  test    dword ptr [rcx+2Ch], 800h
0x14000d84d  jz      short loc_14000D867
0x14000d84f  mov     rcx, [rcx+18h]
0x14000d853  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14000d85a  mov     edx, 11h
0x14000d85f  mov     r9d, eax
0x14000d862  call    WPP_SF_D
0x14000d867  mov     rcx, r13; P
0x14000d86a  call    PcpFreeFilter
0x14000d86f  cmp     rdi, rsi
0x14000d872  jnz     short loc_14000D80C
0x14000d874  mov     rcx, r15; P
0x14000d877  call    PcpDeleteFlow
0x14000d87c  lea     rax, [rbp+var_30]
0x14000d880  cmp     rbx, rax
0x14000d883  jnz     loc_14000D7F9
0x14000d889  test    r14d, r14d
0x14000d88c  jz      short loc_14000D896
0x14000d88e  mov     ecx, r14d
0x14000d891  call    PcpFilterDecrementIntercept
0x14000d896  xor     eax, eax
0x14000d898  add     rsp, 50h
0x14000d89c  pop     r15
0x14000d89e  pop     r14
0x14000d8a0  pop     r13
0x14000d8a2  pop     rdi
0x14000d8a3  pop     rsi
0x14000d8a4  pop     rbx
0x14000d8a5  pop     rbp
0x14000d8a6  retn
0x14000d8a8  mov     ecx, 3
0x14000d8ad  int     29h; Win8: RtlFailFast(ecx)
```
