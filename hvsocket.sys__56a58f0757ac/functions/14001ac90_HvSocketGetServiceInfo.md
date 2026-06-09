# HvSocketGetServiceInfo

- ea: `0x14001ac90`
- end: `0x14001ae3d`
- name: `HvSocketGetServiceInfo`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x1400190c8`
- `0x14001ac90`
- `0x14001d530`
- `0x1400221e8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ad14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ad14`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ad08`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001ad08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ae16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ae16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001acd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001acd6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ae00`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ae00`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ace9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14001ace9`

## string_xrefs

- `0x14001ad46`: `HvSocketGetServiceInfo`
- `0x14001ad82`: `HvSocketGetServiceInfo`
- `0x14001adb1`: `HvSocketGetServiceInfo`

## pseudocode

```c
__int64 __fastcall HvSocketGetServiceInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v7; // rax
  struct _FAST_MUTEX *v8; // rcx
  __int64 v9; // rdi
  unsigned int v10; // ebx
  int ServiceInfo; // eax
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  void (__fastcall *v15)(__int64); // rax
  __int128 v17; // [rsp+30h] [rbp-58h] BYREF
  __int128 v18; // [rsp+40h] [rbp-48h] BYREF

  v3 = *(_QWORD *)(a1 + 96);
  v18 = 0;
  v18 = *HvsocketAddressInfoToPartitionId(&v17, a1 + 104);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v3 + 16));
  v7 = HvSocketFindAndReferenceAnyPartition(v3, (__int64)&v18);
  v8 = (struct _FAST_MUTEX *)(v3 + 16);
  v9 = v7;
  ExReleaseFastMutexUnsafe(v8);
  KeLeaveCriticalRegion();
  if ( v9 )
  {
    ServiceInfo = VmbusTlGetServiceInfo(v9, a2, a3);
    v10 = ServiceInfo;
    if ( ServiceInfo < 0 && (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketGetServiceInfo", 320, (unsigned int)ServiceInfo, a1 + 120);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketGetServiceInfo",
        327,
        v9,
        *(_QWORD *)(v9 + 8),
        (__int64)"Dereference object");
    v12 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v9 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v13 = v12 <= 1;
    v14 = v12 - 1;
    if ( v13 )
    {
      if ( v14 )
        __fastfail(0xEu);
      v15 = *(void (__fastcall **)(__int64))(v9 + 80);
      if ( v15 )
        v15(v9);
      if ( *(_DWORD *)(v9 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v9, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v9 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v9 + 96), (PVOID)v9);
      }
    }
  }
  else
  {
    v10 = -1073741503;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceGuidError("HvSocketGetServiceInfo", 313, 3221225793LL, &v18);
  }
  return v10;
}

```

## disassembly

```asm
0x14001ac90  push    rbx
0x14001ac92  push    rbp
0x14001ac93  push    rsi
0x14001ac94  push    rdi
0x14001ac95  push    r14
0x14001ac97  sub     rsp, 60h
0x14001ac9b  mov     rax, cs:__security_cookie
0x14001aca2  xor     rax, rsp
0x14001aca5  mov     [rsp+88h+var_38], rax
0x14001acaa  mov     rdi, [rcx+60h]
0x14001acae  mov     rsi, rcx
0x14001acb1  xorps   xmm0, xmm0
0x14001acb4  mov     rbp, rdx
0x14001acb7  lea     rdx, [rcx+68h]
0x14001acbb  mov     r14, r8
0x14001acbe  lea     rcx, [rsp+88h+var_58]
0x14001acc3  movups  [rsp+88h+var_48], xmm0
0x14001acc8  call    HvsocketAddressInfoToPartitionId
0x14001accd  movups  xmm1, xmmword ptr [rax]
0x14001acd0  movdqu  [rsp+88h+var_48], xmm1
0x14001acd6  call    cs:__imp_KeEnterCriticalRegion
0x14001acdd  nop     dword ptr [rax+rax+00h]
0x14001ace2  lea     rbx, [rdi+10h]
0x14001ace6  mov     rcx, rbx; FastMutex
0x14001ace9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001acf0  nop     dword ptr [rax+rax+00h]
0x14001acf5  lea     rdx, [rsp+88h+var_48]
0x14001acfa  mov     rcx, rdi
0x14001acfd  call    HvSocketFindAndReferenceAnyPartition
0x14001ad02  mov     rcx, rbx; FastMutex
0x14001ad05  mov     rdi, rax
0x14001ad08  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001ad0f  nop     dword ptr [rax+rax+00h]
0x14001ad14  call    cs:__imp_KeLeaveCriticalRegion
0x14001ad1b  nop     dword ptr [rax+rax+00h]
0x14001ad20  test    rdi, rdi
0x14001ad23  jnz     short loc_14001AD57
0x14001ad25  mov     eax, cs:dword_140013058
0x14001ad2b  mov     ebx, 0C0000141h
0x14001ad30  cmp     eax, 2
0x14001ad33  jbe     loc_14001AE22
0x14001ad39  lea     r9, [rsp+88h+var_48]
0x14001ad3e  mov     r8d, ebx
0x14001ad41  mov     edx, 139h
0x14001ad46  lea     rcx, aHvsocketgetser; "HvSocketGetServiceInfo"
0x14001ad4d  call    HvsocketTraceGuidError
0x14001ad52  jmp     loc_14001AE22
0x14001ad57  mov     r8, r14
0x14001ad5a  mov     rdx, rbp
0x14001ad5d  mov     rcx, rdi
0x14001ad60  call    VmbusTlGetServiceInfo
0x14001ad65  mov     ebx, eax
0x14001ad67  test    eax, eax
0x14001ad69  jns     short loc_14001AD8E
0x14001ad6b  mov     ecx, cs:dword_140013058
0x14001ad71  cmp     ecx, 2
0x14001ad74  jbe     short loc_14001AD8E
0x14001ad76  lea     r9, [rsi+78h]
0x14001ad7a  mov     r8d, eax
0x14001ad7d  mov     edx, 140h
0x14001ad82  lea     rcx, aHvsocketgetser; "HvSocketGetServiceInfo"
0x14001ad89  call    HvsocketTraceGuidError
0x14001ad8e  mov     eax, cs:dword_140013058
0x14001ad94  cmp     eax, 5
0x14001ad97  jbe     short loc_14001ADBD
0x14001ad99  mov     r9, [rdi+8]
0x14001ad9d  lea     rax, aDereferenceObj; "Dereference object"
0x14001ada4  mov     r8, rdi
0x14001ada7  mov     [rsp+88h+var_68], rax
0x14001adac  mov     edx, 147h
0x14001adb1  lea     rcx, aHvsocketgetser; "HvSocketGetServiceInfo"
0x14001adb8  call    HvsocketTraceReferenceCount
0x14001adbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001adc1  lock xadd [rdi+8], rax
0x14001adc7  sub     rax, 1
0x14001adcb  jg      short loc_14001AE22
0x14001adcd  test    rax, rax
0x14001add0  jz      short loc_14001ADDB
0x14001add2  mov     ecx, 0Eh
0x14001add7  int     29h; Win8: RtlFailFast(ecx)
0x14001add9  jmp     short loc_14001AE22
0x14001addb  mov     rax, [rdi+50h]
0x14001addf  test    rax, rax
0x14001ade2  jz      short loc_14001ADEC
0x14001ade4  mov     rcx, rdi
0x14001ade7  call    _guard_dispatch_icall
0x14001adec  mov     ecx, [rdi+58h]
0x14001adef  sub     ecx, 1
0x14001adf2  jz      short loc_14001AE0E
0x14001adf4  cmp     ecx, 1
0x14001adf7  jnz     short loc_14001AE22
0x14001adf9  mov     rcx, [rdi+60h]; Lookaside
0x14001adfd  mov     rdx, rdi; Entry
0x14001ae00  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001ae07  nop     dword ptr [rax+rax+00h]
0x14001ae0c  jmp     short loc_14001AE22
0x14001ae0e  mov     edx, 69706E56h; Tag
0x14001ae13  mov     rcx, rdi; P
0x14001ae16  call    cs:__imp_ExFreePoolWithTag
0x14001ae1d  nop     dword ptr [rax+rax+00h]
0x14001ae22  mov     eax, ebx
0x14001ae24  mov     rcx, [rsp+88h+var_38]
0x14001ae29  xor     rcx, rsp; StackCookie
0x14001ae2c  call    __security_check_cookie
0x14001ae31  add     rsp, 60h
0x14001ae35  pop     r14
0x14001ae37  pop     rdi
0x14001ae38  pop     rsi
0x14001ae39  pop     rbp
0x14001ae3a  pop     rbx
0x14001ae3b  retn
```
