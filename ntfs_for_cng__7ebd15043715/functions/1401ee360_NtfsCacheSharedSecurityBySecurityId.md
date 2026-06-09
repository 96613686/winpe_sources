# NtfsCacheSharedSecurityBySecurityId

- ea: `0x1401ee360`
- end: `0x1401eea6b`
- name: `NtfsCacheSharedSecurityBySecurityId`
- size: `1803`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002ec20`
- `0x1400e6a1c`
- `0x1400ee0f8`
- `0x140166514`
- `0x14017d914`
- `0x14018751c`
- `0x14018dd88`
- `0x1401941c0`
- `0x1401ecb70`
- `0x1401edd00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x140012e70`
- `0x1400410a8`
- `0x140059250`
- `0x1400593c0`
- `0x140059be0`
- `0x1401620c0`
- `0x1401ee360`
- `0x1401eecf0`
- `0x1401ef280`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1401ee615`
- `ntoskrnl!CcMapData` at `0x1401ee615`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ee661`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ee661`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401ee797`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401ee797`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1401ee7af`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1401ee7af`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401ee7de`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401ee7de`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee8b2`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee8d9`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee8b2`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee8d9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee3f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee431`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401eea24`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b190a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee3f7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee431`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401eea24`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b190a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee891`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee891`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ee741`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ee741`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee3af`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee46e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee3af`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee46e`
- `ntoskrnl!CcUnpinData` at `0x1401ee561`
- `ntoskrnl!CcUnpinData` at `0x1401ee9f6`
- `ntoskrnl!CcUnpinData` at `0x1402b18d1`
- `ntoskrnl!CcUnpinData` at `0x1401ee561`
- `ntoskrnl!CcUnpinData` at `0x1401ee9f6`
- `ntoskrnl!CcUnpinData` at `0x1402b18d1`
- `ntoskrnl!RtlCompareMemory` at `0x1401ee63c`
- `ntoskrnl!RtlCompareMemory` at `0x1401ee63c`
- `ntoskrnl!ExRaiseStatus` at `0x1401ee6ee`
- `ntoskrnl!ExRaiseStatus` at `0x1401ee6ee`

## pseudocode

```c
__int64 __fastcall NtfsCacheSharedSecurityBySecurityId(__int64 a1, __int64 a2, int a3)
{
  PVOID *v6; // r14
  volatile signed __int32 *PoolWithTag; // r14
  __int64 v9; // rdx
  __int64 v10; // r9
  ULONG v11; // r8d
  __int64 v12; // r13
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  _DWORD *v15; // r12
  int v16; // r13d
  size_t v17; // r8
  unsigned int v18; // r13d
  char *v19; // r13
  int v20; // r12d
  volatile signed __int32 **v21; // rdx
  volatile signed __int32 *v22; // r8
  signed __int32 v23; // eax
  bool v24; // cc
  signed __int32 v25; // eax
  unsigned __int8 DaclPresent; // [rsp+40h] [rbp-108h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+41h] [rbp-107h] BYREF
  int v28; // [rsp+44h] [rbp-104h]
  PVOID Source2; // [rsp+48h] [rbp-100h] BYREF
  PVOID v30; // [rsp+50h] [rbp-F8h] BYREF
  PACL Dacl; // [rsp+58h] [rbp-F0h] BYREF
  int v32; // [rsp+60h] [rbp-E8h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+68h] [rbp-E0h] BYREF
  volatile signed __int32 *v34; // [rsp+70h] [rbp-D8h]
  __int64 v35; // [rsp+78h] [rbp-D0h]
  __int64 v36; // [rsp+80h] [rbp-C8h]
  int v37[4]; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+98h] [rbp-B0h]
  int v39; // [rsp+A0h] [rbp-A8h]
  __int64 v40[2]; // [rsp+A8h] [rbp-A0h] BYREF
  PVOID Bcb[2]; // [rsp+B8h] [rbp-90h]
  __m256i v42; // [rsp+C8h] [rbp-80h] BYREF
  __int128 Source1; // [rsp+E8h] [rbp-60h] BYREF
  ULONG Length; // [rsp+F8h] [rbp-50h]

  v36 = a1;
  v35 = a2;
  v30 = 0;
  Source2 = 0;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
  v6 = *(PVOID **)(a2 + 8LL * (a3 & 0x7F) + 2448);
  if ( v6 )
  {
    PoolWithTag = (volatile signed __int32 *)*v6;
    if ( PoolWithTag )
    {
      if ( *((_DWORD *)PoolWithTag + 3) == a3 )
      {
        if ( _InterlockedIncrement(PoolWithTag) <= 1 )
          __fastfail(0xEu);
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
        return (__int64)PoolWithTag;
      }
    }
  }
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
  v9 = *(_QWORD *)(a2 + 104);
  if ( v9 )
  {
    PoolWithTag = 0;
    v30 = 0;
    NtfsAcquireSharedFcb(a1, *(_QWORD *)(v9 + 184), v9, 0);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
    v32 = a3;
    Source1 = 0;
    Length = 0;
    *(_OWORD *)v40 = 0;
    Bcb[0] = 0;
    memset(&v42, 0, 28);
    v37[1] = 0;
    v39 = 0;
    Bcb[1] = 0;
    v37[0] = 4;
    *(_QWORD *)&v37[2] = &v32;
    v38 = 0;
    if ( (unsigned int)NtOfsFindRecord(a1, *(_QWORD *)(a2 + 112), (int)v37, (__int64)v40, 0) != -1073741198 )
    {
      Source1 = *(_OWORD *)v42.m256i_i64[3];
      v11 = *(_DWORD *)(v42.m256i_i64[3] + 16);
      Length = v11;
      if ( Bcb[1] )
      {
        CcUnpinData(Bcb[1]);
        Bcb[1] = 0;
        v11 = Length;
      }
      if ( v42.m256i_i32[4] == 20 )
      {
        v12 = *(_QWORD *)(a2 + 104);
        v13 = *(_QWORD *)(v12 + 32);
        if ( *((_QWORD *)&Source1 + 1) <= v13 )
        {
          v14 = *((_QWORD *)&Source1 + 1) + v11;
          if ( v14 <= v13 && v11 >= 0x14 && ((*((_QWORD *)&Source1 + 1) ^ (v14 - 1)) & 0xFFFFFFFFFFFC0000uLL) == 0 )
          {
            FileOffset = *(union _LARGE_INTEGER *)((char *)&Source1 + 8);
            if ( Source1 < 0 || (signed __int64)(*((_QWORD *)&Source1 + 1) + v11) > *(_QWORD *)(v12 + 24) )
            {
              NtfsAttachCorruption_BadOrOrphanFRS(
                a1,
                2,
                328988,
                v10,
                (_DWORD *)(*(_QWORD *)(v12 + 184) + 8LL),
                *(_QWORD *)(v12 + 184),
                0);
              NtfsAttachRepairInfoPriv(a1, 256, 0, (struct _LIST_ENTRY *)0x620005051CLL);
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0x5051Cu);
              NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v12 + 184) + 8, *(_QWORD *)(v12 + 184), 328988);
            }
            if ( !CcMapData(*(PFILE_OBJECT *)(v12 + 280), &FileOffset, v11, 1u, &v30, &Source2) )
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 329015);
            if ( RtlCompareMemory(&Source1, Source2, 0x14u) == 20
              && SeValidSecurityDescriptor(*((_DWORD *)Source2 + 4) - 20, (char *)Source2 + 20) )
            {
              v15 = Source2;
              v16 = *((_DWORD *)Source2 + 4);
              PoolWithTag = *(volatile signed __int32 **)(a2 + 8LL * (*(_DWORD *)Source2 & 0x7F) + 3472);
              if ( PoolWithTag )
              {
                if ( *((_DWORD *)PoolWithTag + 2) == *(_DWORD *)Source2 )
                {
                  v17 = (unsigned int)(v16 - 20);
                  if ( *((unsigned int *)PoolWithTag + 6) - 20LL == v17 )
                  {
                    if ( memcmp((const void *)(PoolWithTag + 7), (char *)Source2 + 20, v17) )
                      PoolWithTag = 0;
                  }
                  else
                  {
                    PoolWithTag = 0;
                  }
                }
                else
                {
                  PoolWithTag = 0;
                }
              }
              v34 = PoolWithTag;
              if ( PoolWithTag )
              {
                *(_OWORD *)(PoolWithTag + 2) = *(_OWORD *)v15;
                *((_DWORD *)PoolWithTag + 6) = v15[4];
                if ( _InterlockedIncrement(PoolWithTag) <= 1 )
                  __fastfail(0xEu);
              }
              else
              {
                v18 = v16 + 8;
                if ( v18 < 8 )
                {
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 0xC0000183, 0x1F12DCu);
                  ExRaiseStatus(-1073741437);
                }
                PoolWithTag = (volatile signed __int32 *)ExAllocatePoolWithTag(
                                                           (POOL_TYPE)(PoolType | 0x10),
                                                           v18,
                                                           0x5346744Eu);
                v34 = PoolWithTag;
                *PoolWithTag = 1;
                v19 = (char *)Source2;
                Dacl = 0;
                DaclDefaulted[0] = 0;
                v20 = 0;
                v28 = 0;
                DaclPresent = 0;
                RtlGetDaclSecurityDescriptor((char *)Source2 + 20, &DaclPresent, &Dacl, DaclDefaulted);
                if ( !DaclPresent || !(unsigned __int8)RtlOwnerAcesPresent(Dacl) )
                {
                  v20 = 1;
                  v28 = 1;
                }
                DaclPresent = 0;
                RtlGetSaclSecurityDescriptor(v19 + 20, &DaclPresent, &Dacl, DaclDefaulted);
                if ( !DaclPresent || !RtlFindAceByType(Dacl, 17, 0) )
                {
                  v20 |= 2u;
                  v28 = v20;
                }
                if ( !DaclPresent || !RtlFindAceByType(Dacl, 21, 0) )
                {
                  v20 |= 4u;
                  v28 = v20;
                }
                *((_DWORD *)PoolWithTag + 1) = v20;
                memmove((void *)(PoolWithTag + 2), Source2, *((unsigned int *)Source2 + 4));
              }
              v21 = (volatile signed __int32 **)(a2 + 8 * ((PoolWithTag[2] & 0x7F) + 434LL));
              v22 = *v21;
              if ( PoolWithTag == *v21 )
              {
                *(_QWORD *)(a2 + 8LL * (PoolWithTag[3] & 0x7F) + 2448) = v21;
              }
              else
              {
                *v21 = PoolWithTag;
                if ( _InterlockedIncrement(PoolWithTag) <= 1 )
                  __fastfail(0xEu);
                *(_QWORD *)(a2 + 8LL * (PoolWithTag[3] & 0x7F) + 2448) = v21;
                if ( v22 )
                {
                  v23 = _InterlockedExchangeAdd(v22, 0xFFFFFFFF);
                  v24 = v23 <= 1;
                  v25 = v23 - 1;
                  if ( v24 )
                  {
                    if ( v25 )
                      __fastfail(0xEu);
                    ExFreePoolWithTag((PVOID)v22, 0);
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v30 )
    {
      CcUnpinData(v30);
      v30 = 0;
    }
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(a2 + 104) + 184LL), 0);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
    if ( !PoolWithTag )
      return NtfsCacheSharedSecurityByDescriptor(a1, SecurityDescriptor, ::Length, 1);
    return (__int64)PoolWithTag;
  }
  return 0;
}

```

## disassembly

```asm
0x1401ee360  push    rbx
0x1401ee362  push    rsi
0x1401ee363  push    rdi
0x1401ee364  push    r12
0x1401ee366  push    r13
0x1401ee368  push    r14
0x1401ee36a  push    r15
0x1401ee36c  sub     rsp, 110h
0x1401ee373  mov     rax, cs:__security_cookie
0x1401ee37a  xor     rax, rsp
0x1401ee37d  mov     [rsp+148h+var_48], rax
0x1401ee385  mov     edi, r8d
0x1401ee388  mov     rbx, rdx
0x1401ee38b  mov     r15, rcx
0x1401ee38e  mov     [rsp+148h+var_C8], rcx
0x1401ee396  mov     [rsp+148h+var_D0], rdx
0x1401ee39b  xor     r12d, r12d
0x1401ee39e  mov     [rsp+148h+var_F8], r12
0x1401ee3a3  mov     [rsp+148h+Source2], r12
0x1401ee3a8  lea     rcx, [rdx+298h]; Mutex
0x1401ee3af  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee3b6  nop     dword ptr [rax+rax+00h]
0x1401ee3bb  mov     eax, edi
0x1401ee3bd  and     eax, 7Fh
0x1401ee3c0  mov     r14, [rbx+rax*8+990h]
0x1401ee3c8  test    r14, r14
0x1401ee3cb  jz      short loc_1401EE42A
0x1401ee3cd  mov     r14, [r14]
0x1401ee3d0  test    r14, r14
0x1401ee3d3  jz      short loc_1401EE42A
0x1401ee3d5  cmp     [r14+0Ch], edi
0x1401ee3d9  jnz     short loc_1401EE42A
0x1401ee3db  mov     edi, 1
0x1401ee3e0  lock xadd [r14], edi
0x1401ee3e5  inc     edi
0x1401ee3e7  cmp     edi, 1
0x1401ee3ea  jle     loc_1401EEA5F
0x1401ee3f0  lea     rcx, [rbx+298h]; Mutex
0x1401ee3f7  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee3fe  nop     dword ptr [rax+rax+00h]
0x1401ee403  mov     rax, r14
0x1401ee406  mov     rcx, [rsp+148h+var_48]
0x1401ee40e  xor     rcx, rsp; StackCookie
0x1401ee411  call    __security_check_cookie
0x1401ee416  add     rsp, 110h
0x1401ee41d  pop     r15
0x1401ee41f  pop     r14
0x1401ee421  pop     r13
0x1401ee423  pop     r12
0x1401ee425  pop     rdi
0x1401ee426  pop     rsi
0x1401ee427  pop     rbx
0x1401ee428  retn
0x1401ee42a  lea     rcx, [rbx+298h]; Mutex
0x1401ee431  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee438  nop     dword ptr [rax+rax+00h]
0x1401ee43d  mov     rdx, [rbx+68h]
0x1401ee441  test    rdx, rdx
0x1401ee444  jnz     short loc_1401EE44A
0x1401ee446  xor     eax, eax
0x1401ee448  jmp     short loc_1401EE406
0x1401ee44a  mov     r14, r12
0x1401ee44d  mov     [rsp+148h+var_F8], r12
0x1401ee452  xor     r9d, r9d
0x1401ee455  mov     r8, rdx
0x1401ee458  mov     rdx, [rdx+0B8h]
0x1401ee45f  mov     rcx, r15
0x1401ee462  call    NtfsAcquireSharedFcb
0x1401ee467  lea     rcx, [rbx+298h]; Mutex
0x1401ee46e  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee475  nop     dword ptr [rax+rax+00h]
0x1401ee47a  nop
0x1401ee47b  mov     [rsp+148h+var_E8], edi
0x1401ee47f  xorps   xmm0, xmm0
0x1401ee482  xor     eax, eax
0x1401ee484  movups  [rsp+148h+Source1], xmm0
0x1401ee48c  mov     [rsp+148h+Length], eax
0x1401ee493  xorps   xmm1, xmm1
0x1401ee496  movups  xmmword ptr [rsp+148h+var_A0], xmm1
0x1401ee49e  movups  xmmword ptr [rsp+148h+Bcb], xmm1
0x1401ee4a6  mov     dword ptr [rsp+148h+var_80+4], eax
0x1401ee4ad  movups  [rsp+148h+var_80], xmm0
0x1401ee4b5  movups  [rsp+148h+var_80+0Ch], xmm0
0x1401ee4bd  mov     [rsp+148h+var_C0+4], eax
0x1401ee4c4  movups  xmmword ptr [rsp+148h+var_C0], xmm0
0x1401ee4cc  movups  xmmword ptr [rsp+148h+var_C0+0Ch], xmm0
0x1401ee4d4  mov     [rsp+148h+Bcb+8], r12
0x1401ee4dc  mov     [rsp+148h+var_C0], 4
0x1401ee4e7  lea     rax, [rsp+148h+var_E8]
0x1401ee4ec  mov     qword ptr [rsp+148h+var_C0+8], rax
0x1401ee4f4  mov     [rsp+148h+var_B0], r12
0x1401ee4fc  mov     [rsp+148h+Buffer], r12; __int64
0x1401ee501  lea     rax, [rsp+148h+var_A0]
0x1401ee509  mov     [rsp+148h+var_128], rax; __int64
0x1401ee50e  lea     r9, [rsp+148h+var_80]
0x1401ee516  lea     r8, [rsp+148h+var_C0]; int
0x1401ee51e  mov     rdx, [rbx+70h]; int
0x1401ee522  mov     rcx, r15; int
0x1401ee525  call    NtOfsFindRecord
0x1401ee52a  cmp     eax, 0C0000272h
0x1401ee52f  jz      loc_1401EE9EC
0x1401ee535  mov     rax, [rsp+148h+var_68]
0x1401ee53d  movups  xmm0, xmmword ptr [rax]
0x1401ee540  movups  [rsp+148h+Source1], xmm0
0x1401ee548  mov     r8d, [rax+10h]
0x1401ee54c  mov     [rsp+148h+Length], r8d
0x1401ee554  mov     rcx, [rsp+148h+Bcb+8]; Bcb
0x1401ee55c  test    rcx, rcx
0x1401ee55f  jz      short loc_1401EE57D
0x1401ee561  call    cs:__imp_CcUnpinData
0x1401ee568  nop     dword ptr [rax+rax+00h]
0x1401ee56d  mov     [rsp+148h+Bcb+8], r12
0x1401ee575  mov     r8d, [rsp+148h+Length]; Length
0x1401ee57d  cmp     [rsp+148h+var_70], 14h
0x1401ee585  jnz     loc_1401EE9EC
0x1401ee58b  mov     r13, [rbx+68h]
0x1401ee58f  mov     rcx, [r13+20h]
0x1401ee593  mov     rdx, qword ptr [rsp+148h+Source1+8]
0x1401ee59b  cmp     rdx, rcx
0x1401ee59e  ja      loc_1401EE9EC
0x1401ee5a4  mov     eax, r8d
0x1401ee5a7  add     rax, rdx
0x1401ee5aa  cmp     rax, rcx
0x1401ee5ad  ja      loc_1401EE9EC
0x1401ee5b3  cmp     r8d, 14h
0x1401ee5b7  jb      loc_1401EE9EC
0x1401ee5bd  dec     rax
0x1401ee5c0  xor     rax, rdx
0x1401ee5c3  test    rax, 0FFFFFFFFFFFC0000h
0x1401ee5c9  jnz     loc_1401EE9EC
0x1401ee5cf  mov     qword ptr [rsp+148h+FileOffset], rdx
0x1401ee5d4  test    rdx, rdx
0x1401ee5d7  js      loc_1401EE94D
0x1401ee5dd  mov     eax, r8d
0x1401ee5e0  add     rax, rdx
0x1401ee5e3  cmp     rax, [r13+18h]
0x1401ee5e7  jg      loc_1401EE94D
0x1401ee5ed  lea     rax, [rsp+148h+Source2]
0x1401ee5f2  mov     [rsp+148h+Buffer], rax; Buffer
0x1401ee5f7  lea     rax, [rsp+148h+var_F8]
0x1401ee5fc  mov     [rsp+148h+var_128], rax; Bcb
0x1401ee601  mov     edi, 1
0x1401ee606  mov     r9d, edi; Flags
0x1401ee609  lea     rdx, [rsp+148h+FileOffset]; FileOffset
0x1401ee60e  mov     rcx, [r13+118h]; FileObject
0x1401ee615  call    cs:__imp_CcMapData
0x1401ee61c  nop     dword ptr [rax+rax+00h]
0x1401ee621  test    al, al
0x1401ee623  jz      loc_1401EE929
0x1401ee629  mov     r8d, 14h; Length
0x1401ee62f  mov     rdx, [rsp+148h+Source2]; Source2
0x1401ee634  lea     rcx, [rsp+148h+Source1]; Source1
0x1401ee63c  call    cs:__imp_RtlCompareMemory
0x1401ee643  nop     dword ptr [rax+rax+00h]
0x1401ee648  cmp     rax, 14h
0x1401ee64c  jnz     loc_1401EE9EC
0x1401ee652  mov     rax, [rsp+148h+Source2]
0x1401ee657  lea     rdx, [rax+14h]; SecurityDescriptor
0x1401ee65b  mov     ecx, [rax+10h]
0x1401ee65e  sub     ecx, 14h; Length
0x1401ee661  call    cs:__imp_SeValidSecurityDescriptor
0x1401ee668  nop     dword ptr [rax+rax+00h]
0x1401ee66d  test    al, al
0x1401ee66f  jz      loc_1401EE9EC
0x1401ee675  mov     r12, [rsp+148h+Source2]
0x1401ee67a  mov     ecx, [r12]
0x1401ee67e  mov     r13d, [r12+10h]
0x1401ee683  mov     eax, ecx
0x1401ee685  and     eax, 7Fh
0x1401ee688  mov     r14, [rbx+rax*8+0D90h]
0x1401ee690  test    r14, r14
0x1401ee693  jz      short loc_1401EE6C6
0x1401ee695  cmp     [r14+8], ecx
0x1401ee699  jnz     short loc_1401EE6FA
0x1401ee69b  lea     r8d, [r13-14h]; Size
0x1401ee69f  mov     eax, [r14+18h]
0x1401ee6a3  sub     rax, 14h
0x1401ee6a7  cmp     rax, r8
0x1401ee6aa  jnz     loc_1401EE921
0x1401ee6b0  lea     rdx, [r12+14h]; Buf2
0x1401ee6b5  lea     rcx, [r14+1Ch]; Buf1
0x1401ee6b9  call    memcmp
0x1401ee6be  xor     ecx, ecx
0x1401ee6c0  test    eax, eax
0x1401ee6c2  cmovnz  r14, rcx
0x1401ee6c6  mov     [rsp+148h+var_D8], r14
0x1401ee6cb  test    r14, r14
0x1401ee6ce  jnz     short loc_1401EE6FF
0x1401ee6d0  add     r13d, 8
0x1401ee6d4  cmp     r13d, 8
0x1401ee6d8  jnb     short loc_1401EE72F
0x1401ee6da  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ee6e1  test    al, al
0x1401ee6e3  jnz     loc_1401EE8F3
0x1401ee6e9  mov     ecx, 0C0000183h; Status
0x1401ee6ee  call    cs:__imp_ExRaiseStatus
0x1401ee6fa  xor     r14d, r14d
0x1401ee6fd  jmp     short loc_1401EE6C6
0x1401ee6ff  movups  xmm0, xmmword ptr [r12]
0x1401ee704  movups  xmmword ptr [r14+8], xmm0
0x1401ee709  mov     eax, [r12+10h]
0x1401ee70e  mov     [r14+18h], eax
0x1401ee712  mov     eax, edi
0x1401ee714  lock xadd [r14], eax
0x1401ee719  inc     eax
0x1401ee71b  cmp     eax, edi
0x1401ee71d  jg      loc_1401EE828
0x1401ee723  mov     ecx, 0Eh
0x1401ee728  int     29h; Win8: RtlFailFast(ecx)
0x1401ee72a  jmp     loc_1401EE828
0x1401ee72f  mov     edx, r13d; NumberOfBytes
0x1401ee732  mov     ecx, cs:PoolType
0x1401ee738  or      ecx, 10h; PoolType
0x1401ee73b  mov     r8d, 5346744Eh; Tag
0x1401ee741  call    cs:__imp_ExAllocatePoolWithTag
0x1401ee748  nop     dword ptr [rax+rax+00h]
0x1401ee74d  mov     r14, rax
0x1401ee750  mov     [rsp+148h+var_D8], rax
0x1401ee755  mov     [rax], edi
0x1401ee757  mov     r13, [rsp+148h+Source2]
0x1401ee75c  mov     [rsp+148h+var_104], 0
0x1401ee764  mov     [rsp+148h+Dacl], 0
0x1401ee76d  mov     [rsp+148h+DaclPresent], 0
0x1401ee772  mov     [rsp+148h+DaclDefaulted], 0
0x1401ee777  xor     r12d, r12d
0x1401ee77a  mov     [rsp+148h+var_104], r12d
0x1401ee77f  mov     [rsp+148h+DaclPresent], r12b
0x1401ee784  lea     r9, [rsp+148h+DaclDefaulted]; DaclDefaulted
0x1401ee789  lea     r8, [rsp+148h+Dacl]; Dacl
0x1401ee78e  lea     rdx, [rsp+148h+DaclPresent]; DaclPresent
0x1401ee793  lea     rcx, [r13+14h]; SecurityDescriptor
0x1401ee797  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1401ee79e  nop     dword ptr [rax+rax+00h]
0x1401ee7a3  cmp     [rsp+148h+DaclPresent], r12b
0x1401ee7a8  jz      short loc_1401EE7BF
0x1401ee7aa  mov     rcx, [rsp+148h+Dacl]
0x1401ee7af  call    cs:__imp_RtlOwnerAcesPresent
0x1401ee7b6  nop     dword ptr [rax+rax+00h]
0x1401ee7bb  test    al, al
0x1401ee7bd  jnz     short loc_1401EE7C6
0x1401ee7bf  mov     r12d, edi
0x1401ee7c2  mov     [rsp+148h+var_104], edi
0x1401ee7c6  mov     [rsp+148h+DaclPresent], 0
0x1401ee7cb  lea     r9, [rsp+148h+DaclDefaulted]; SaclDefaulted
0x1401ee7d0  lea     r8, [rsp+148h+Dacl]; Sacl
0x1401ee7d5  lea     rdx, [rsp+148h+DaclPresent]; SaclPresent
0x1401ee7da  lea     rcx, [r13+14h]; SecurityDescriptor
0x1401ee7de  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1401ee7e5  nop     dword ptr [rax+rax+00h]
0x1401ee7ea  cmp     [rsp+148h+DaclPresent], 0
0x1401ee7ef  jnz     loc_1401EE8A5
0x1401ee7f5  or      r12d, 2
0x1401ee7f9  mov     [rsp+148h+var_104], r12d
0x1401ee7fe  cmp     [rsp+148h+DaclPresent], 0
0x1401ee803  jnz     loc_1401EE8CC
0x1401ee809  or      r12d, 4
0x1401ee80d  mov     [rsp+148h+var_104], r12d
0x1401ee812  mov     [r14+4], r12d
0x1401ee816  mov     rdx, [rsp+148h+Source2]; Src
0x1401ee81b  mov     r8d, [rdx+10h]; Size
0x1401ee81f  lea     rcx, [r14+8]; void *
0x1401ee823  call    memmove
0x1401ee828  mov     edx, [r14+8]
0x1401ee82c  and     edx, 7Fh
0x1401ee82f  add     rdx, 1B2h
0x1401ee836  lea     rdx, [rbx+rdx*8]
0x1401ee83a  mov     r8, [rdx]
0x1401ee83d  cmp     r14, r8
0x1401ee840  jz      loc_1401EE90A
0x1401ee846  mov     [rdx], r14
0x1401ee849  lock xadd [r14], edi
0x1401ee84e  inc     edi
0x1401ee850  cmp     edi, 1
0x1401ee853  jle     loc_1401EE9D6
0x1401ee859  mov     eax, [r14+0Ch]
0x1401ee85d  and     eax, 7Fh
0x1401ee860  mov     [rbx+rax*8+990h], rdx
0x1401ee868  test    r8, r8
0x1401ee86b  jz      loc_1401EE919
0x1401ee871  mov     eax, 0FFFFFFFFh
0x1401ee876  lock xadd [r8], eax
0x1401ee87b  sub     eax, 1
0x1401ee87e  jg      loc_1401EE919
0x1401ee884  test    eax, eax
0x1401ee886  jnz     loc_1401EE9E2
0x1401ee88c  xor     edx, edx; Tag
0x1401ee88e  mov     rcx, r8; P
0x1401ee891  call    cs:__imp_ExFreePoolWithTag
0x1401ee898  nop     dword ptr [rax+rax+00h]
0x1401ee89d  xor     r12d, r12d
0x1401ee8a0  jmp     loc_1401EE9EC
0x1401ee8a5  xor     r8d, r8d
0x1401ee8a8  mov     edx, 11h
0x1401ee8ad  mov     rcx, [rsp+148h+Dacl]
0x1401ee8b2  call    cs:__imp_RtlFindAceByType
0x1401ee8b9  nop     dword ptr [rax+rax+00h]
0x1401ee8be  test    rax, rax
0x1401ee8c1  jnz     loc_1401EE7FE
0x1401ee8c7  jmp     loc_1401EE7F5
0x1401ee8cc  xor     r8d, r8d
  ... truncated ...
```
