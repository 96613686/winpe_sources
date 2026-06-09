# UlpLockRequestQueueAndCoupling

- ea: `0x1c0102ea4`
- end: `0x1c0103085`
- name: `UlpLockRequestQueueAndCoupling`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1c0101ef4`

## callees

- `0x1c001a5f0`
- `0x1c008f680`
- `0x1c00903a4`
- `0x1c0102ea4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0102f9e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0102f9e`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0102f43`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0102f43`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0102f12`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0102f81`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0103002`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0102f12`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0102f81`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0103002`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0102f63`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0102fe1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0103077`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0102f63`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0102fe1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0103077`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102f1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102f8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102fae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010300e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102f1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102f8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0102fae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010300e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102ef2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102f2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102f52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102fd0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103065`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102ef2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102f2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102f52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0102fd0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103065`

## pseudocode

```c
__int64 __fastcall UlpLockRequestQueueAndCoupling(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r9
  __int64 v5; // rbx
  __int64 v6; // rdi

  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    if ( a1 )
      v4 = *(_QWORD *)(a1 + 64);
    else
      v4 = 0;
    WPP_SF_qqq(38, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, v4, a2);
  }
  *a2 = 0;
  KeEnterCriticalRegion();
  while ( 1 )
  {
    ExAcquirePushLockExclusiveEx(a1 + 1688, 0);
    v6 = *(_QWORD *)(a1 + 1696);
    if ( !v6 )
    {
      ExReleasePushLockExclusiveEx(a1 + 1688, 0);
      KeLeaveCriticalRegion();
      goto LABEL_13;
    }
    _InterlockedIncrement((volatile signed __int32 *)v6);
    ExReleasePushLockExclusiveEx(a1 + 1688, 0);
    KeLeaveCriticalRegion();
    v5 = *(_QWORD *)(v6 + 48);
    KeEnterCriticalRegion();
    *a2 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v5 + 280), 0);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 1688, 0);
    if ( *(_QWORD *)(a1 + 1696) == v6 )
      break;
    ExReleasePushLockExclusiveEx(a1 + 1688, 0);
    KeLeaveCriticalRegion();
    ExReleaseCacheAwarePushLockSharedEx(*a2, 0);
    *a2 = 0;
    KeLeaveCriticalRegion();
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
      UlpFreeCoupling((PVOID)v6);
    KeEnterCriticalRegion();
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
    UlpFreeCoupling((PVOID)v6);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6 + 56, 0);
LABEL_13:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(39, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1c0102ea4  mov     [rsp+arg_8], rbx
0x1c0102ea9  mov     [rsp+arg_10], rbp
0x1c0102eae  push    rsi
0x1c0102eaf  push    rdi
0x1c0102eb0  push    r14
0x1c0102eb2  sub     rsp, 30h
0x1c0102eb6  mov     r14, rdx
0x1c0102eb9  mov     rsi, rcx
0x1c0102ebc  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0102ec2  test    al, al
0x1c0102ec4  jns     short loc_1C0102EED
0x1c0102ec6  test    rcx, rcx
0x1c0102ec9  jz      short loc_1C0102ED1
0x1c0102ecb  mov     r9, [rcx+40h]
0x1c0102ecf  jmp     short loc_1C0102ED4
0x1c0102ed1  xor     r9d, r9d
0x1c0102ed4  mov     ecx, 26h ; '&'
0x1c0102ed9  mov     [rsp+48h+var_28], r14
0x1c0102ede  mov     r8, rsi
0x1c0102ee1  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0102ee8  call    WPP_SF_qqq
0x1c0102eed  xor     eax, eax
0x1c0102eef  mov     [r14], rax
0x1c0102ef2  call    cs:__imp_KeEnterCriticalRegion
0x1c0102ef9  nop     dword ptr [rax+rax+00h]
0x1c0102efe  lea     rbp, [rsi+698h]
0x1c0102f05  jmp     loc_1C0102FDC
0x1c0102f0a  lock inc dword ptr [rdi]
0x1c0102f0d  xor     edx, edx
0x1c0102f0f  mov     rcx, rbp
0x1c0102f12  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0102f19  nop     dword ptr [rax+rax+00h]
0x1c0102f1e  call    cs:__imp_KeLeaveCriticalRegion
0x1c0102f25  nop     dword ptr [rax+rax+00h]
0x1c0102f2a  mov     rbx, [rdi+30h]
0x1c0102f2e  call    cs:__imp_KeEnterCriticalRegion
0x1c0102f35  nop     dword ptr [rax+rax+00h]
0x1c0102f3a  mov     rcx, [rbx+118h]
0x1c0102f41  xor     edx, edx
0x1c0102f43  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c0102f4a  nop     dword ptr [rax+rax+00h]
0x1c0102f4f  mov     [r14], rax
0x1c0102f52  call    cs:__imp_KeEnterCriticalRegion
0x1c0102f59  nop     dword ptr [rax+rax+00h]
0x1c0102f5e  xor     edx, edx
0x1c0102f60  mov     rcx, rbp
0x1c0102f63  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c0102f6a  nop     dword ptr [rax+rax+00h]
0x1c0102f6f  cmp     [rsi+6A0h], rdi
0x1c0102f76  jz      loc_1C010304F
0x1c0102f7c  xor     edx, edx
0x1c0102f7e  mov     rcx, rbp
0x1c0102f81  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0102f88  nop     dword ptr [rax+rax+00h]
0x1c0102f8d  call    cs:__imp_KeLeaveCriticalRegion
0x1c0102f94  nop     dword ptr [rax+rax+00h]
0x1c0102f99  mov     rcx, [r14]
0x1c0102f9c  xor     edx, edx
0x1c0102f9e  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c0102fa5  nop     dword ptr [rax+rax+00h]
0x1c0102faa  and     qword ptr [r14], 0
0x1c0102fae  call    cs:__imp_KeLeaveCriticalRegion
0x1c0102fb5  nop     dword ptr [rax+rax+00h]
0x1c0102fba  or      eax, 0FFFFFFFFh
0x1c0102fbd  lock xadd [rdi], eax
0x1c0102fc1  cmp     eax, 1
0x1c0102fc4  jnz     short loc_1C0102FD0
0x1c0102fc6  xor     edx, edx
0x1c0102fc8  mov     rcx, rdi; P
0x1c0102fcb  call    UlpFreeCoupling
0x1c0102fd0  call    cs:__imp_KeEnterCriticalRegion
0x1c0102fd7  nop     dword ptr [rax+rax+00h]
0x1c0102fdc  xor     edx, edx
0x1c0102fde  mov     rcx, rbp
0x1c0102fe1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c0102fe8  nop     dword ptr [rax+rax+00h]
0x1c0102fed  mov     rdi, [rsi+6A0h]
0x1c0102ff4  test    rdi, rdi
0x1c0102ff7  jnz     loc_1C0102F0A
0x1c0102ffd  xor     edx, edx
0x1c0102fff  mov     rcx, rbp
0x1c0103002  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0103009  nop     dword ptr [rax+rax+00h]
0x1c010300e  call    cs:__imp_KeLeaveCriticalRegion
0x1c0103015  nop     dword ptr [rax+rax+00h]
0x1c010301a  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0103020  test    al, al
0x1c0103022  jns     short loc_1C0103038
0x1c0103024  mov     ecx, 27h ; '''
0x1c0103029  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0103030  mov     r8, rdi
0x1c0103033  call    WPP_SF_q
0x1c0103038  mov     rbx, [rsp+48h+arg_8]
0x1c010303d  mov     rax, rdi
0x1c0103040  mov     rbp, [rsp+48h+arg_10]
0x1c0103045  add     rsp, 30h
0x1c0103049  pop     r14
0x1c010304b  pop     rdi
0x1c010304c  pop     rsi
0x1c010304d  retn
0x1c010304f  or      eax, 0FFFFFFFFh
0x1c0103052  lock xadd [rdi], eax
0x1c0103056  cmp     eax, 1
0x1c0103059  jnz     short loc_1C0103065
0x1c010305b  xor     edx, edx
0x1c010305d  mov     rcx, rdi; P
0x1c0103060  call    UlpFreeCoupling
0x1c0103065  call    cs:__imp_KeEnterCriticalRegion
0x1c010306c  nop     dword ptr [rax+rax+00h]
0x1c0103071  lea     rcx, [rdi+38h]
0x1c0103075  xor     edx, edx
0x1c0103077  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c010307e  nop     dword ptr [rax+rax+00h]
0x1c0103083  jmp     short loc_1C010301A
```
