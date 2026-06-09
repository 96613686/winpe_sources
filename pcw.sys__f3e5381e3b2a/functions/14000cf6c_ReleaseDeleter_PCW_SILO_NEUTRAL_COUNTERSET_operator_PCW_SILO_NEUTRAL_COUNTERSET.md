# ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)

- ea: `0x14000cf6c`
- end: `0x14000d043`
- name: `??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000cddc`
- `0x14000ce18`
- `0x14000ce54`
- `0x14000d2e0`
- `0x14000d460`
- `0x14000ddf4`
- `0x14000e3e8`
- `0x14000e8c0`
- `0x14000ed84`

## callees

- `0x14000cf6c`
- `0x14000ecc0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf93`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cfd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cfd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d012`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cfa8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cfa8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cfcd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d006`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cfcd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000d006`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d030`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d030`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000cff1`
- `ntoskrnl!RtlRbRemoveNode` at `0x14000cff1`

## pseudocode

```c
void __fastcall ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(__int64 a1, volatile signed __int32 *a2)
{
  signed __int32 v2; // eax
  signed __int32 v4; // ett

  v2 = *((_DWORD *)a2 + 33);
  while ( v2 > 1 )
  {
    v4 = v2;
    v2 = _InterlockedCompareExchange(a2 + 33, v2 - 1, v2);
    if ( v4 == v2 )
      return;
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&qword_1400114A8, 0);
  if ( _InterlockedExchangeAdd(a2 + 33, 0xFFFFFFFF) == 1 )
  {
    RtlRbRemoveNode(qword_1400114B0, a2);
    ExReleasePushLockExclusiveEx(&qword_1400114A8, 0);
    KeLeaveCriticalRegion();
    if ( a2 )
    {
      PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET((PCW_SILO_NEUTRAL_COUNTERSET *)a2);
      ExFreePoolWithTag((PVOID)a2, 0);
    }
  }
  else
  {
    ExReleasePushLockExclusiveEx(&qword_1400114A8, 0);
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14000cf6c  push    rbx
0x14000cf6e  sub     rsp, 20h
0x14000cf72  mov     eax, [rdx+84h]
0x14000cf78  mov     rbx, rdx
0x14000cf7b  jmp     short loc_14000CF8E
0x14000cf7d  lea     ecx, [rax-1]
0x14000cf80  lock cmpxchg [rdx+84h], ecx
0x14000cf88  jz      loc_14000D03C
0x14000cf8e  cmp     eax, 1
0x14000cf91  jg      short loc_14000CF7D
0x14000cf93  call    cs:__imp_KeEnterCriticalRegion
0x14000cf9a  nop     dword ptr [rax+rax+00h]
0x14000cf9f  xor     edx, edx
0x14000cfa1  lea     rcx, qword_1400114A8
0x14000cfa8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000cfaf  nop     dword ptr [rax+rax+00h]
0x14000cfb4  or      eax, 0FFFFFFFFh
0x14000cfb7  lock xadd [rbx+84h], eax
0x14000cfbf  cmp     eax, 1
0x14000cfc2  jz      short loc_14000CFE7
0x14000cfc4  xor     edx, edx
0x14000cfc6  lea     rcx, qword_1400114A8
0x14000cfcd  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000cfd4  nop     dword ptr [rax+rax+00h]
0x14000cfd9  call    cs:__imp_KeLeaveCriticalRegion
0x14000cfe0  nop     dword ptr [rax+rax+00h]
0x14000cfe5  jmp     short loc_14000D03C
0x14000cfe7  mov     rdx, rbx
0x14000cfea  lea     rcx, qword_1400114B0
0x14000cff1  call    cs:__imp_RtlRbRemoveNode
0x14000cff8  nop     dword ptr [rax+rax+00h]
0x14000cffd  xor     edx, edx
0x14000cfff  lea     rcx, qword_1400114A8
0x14000d006  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000d00d  nop     dword ptr [rax+rax+00h]
0x14000d012  call    cs:__imp_KeLeaveCriticalRegion
0x14000d019  nop     dword ptr [rax+rax+00h]
0x14000d01e  test    rbx, rbx
0x14000d021  jz      short loc_14000D03C
0x14000d023  mov     rcx, rbx; this
0x14000d026  call    ??1PCW_SILO_NEUTRAL_COUNTERSET@@AEAA@XZ; PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET(void)
0x14000d02b  xor     edx, edx; Tag
0x14000d02d  mov     rcx, rbx; P
0x14000d030  call    cs:__imp_ExFreePoolWithTag
0x14000d037  nop     dword ptr [rax+rax+00h]
0x14000d03c  add     rsp, 20h
0x14000d040  pop     rbx
0x14000d041  retn
```
