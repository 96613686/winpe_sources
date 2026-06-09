# NtfsCacheSharedSecurityBySecurityId

- ea: `0x1401ee3b0`
- end: `0x1401eeabb`
- name: `NtfsCacheSharedSecurityBySecurityId`
- size: `1803`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002ec20`
- `0x1400e6a6c`
- `0x1400ee148`
- `0x140166564`
- `0x14017d964`
- `0x14018756c`
- `0x14018ddd8`
- `0x140194210`
- `0x1401ecbc0`
- `0x1401edd50`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x140012e70`
- `0x1400410a8`
- `0x1400592c0`
- `0x140059440`
- `0x140059c60`
- `0x140162110`
- `0x1401ee3b0`
- `0x1401eed40`
- `0x1401ef2d0`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1401ee665`
- `ntoskrnl!CcMapData` at `0x1401ee665`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ee6b1`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1401ee6b1`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401ee7e7`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401ee7e7`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1401ee7ff`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1401ee7ff`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401ee82e`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401ee82e`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee902`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee929`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee902`
- `ntoskrnl!RtlFindAceByType` at `0x1401ee929`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee447`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee481`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401eea74`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b195a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee447`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401ee481`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401eea74`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402b195a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee8e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee8e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ee791`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401ee791`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee3ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee4be`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee3ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401ee4be`
- `ntoskrnl!CcUnpinData` at `0x1401ee5b1`
- `ntoskrnl!CcUnpinData` at `0x1401eea46`
- `ntoskrnl!CcUnpinData` at `0x1402b1921`
- `ntoskrnl!CcUnpinData` at `0x1401ee5b1`
- `ntoskrnl!CcUnpinData` at `0x1401eea46`
- `ntoskrnl!CcUnpinData` at `0x1402b1921`
- `ntoskrnl!RtlCompareMemory` at `0x1401ee68c`
- `ntoskrnl!RtlCompareMemory` at `0x1401ee68c`
- `ntoskrnl!ExRaiseStatus` at `0x1401ee73e`
- `ntoskrnl!ExRaiseStatus` at `0x1401ee73e`

## pseudocode

```c
__int64 __fastcall NtfsCacheSharedSecurityBySecurityId(__int64 a1, __int64 a2, int a3)
{
  PVOID *v6; // r14
  volatile signed __int32 *PoolWithTag; // r14
  __int64 v9; // rdx
  int v10; // r9d
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
                *(_QWORD *)(v12 + 184) + 8LL,
                *(_QWORD *)(v12 + 184),
                0);
              NtfsAttachRepairInfoPriv(a1, 256, 0, 0x620005051CLL);
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 328988);
              NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v12 + 184) + 8, *(_QWORD *)(v12 + 184), 328988);
              __debugbreak();
            }
            if ( !CcMapData(*(PFILE_OBJECT *)(v12 + 280), &FileOffset, v11, 1u, &v30, &Source2) )
            {
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 329015);
              __debugbreak();
            }
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
                    NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 2036444);
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
0x1401ee3b0  push    rbx
0x1401ee3b2  push    rsi
0x1401ee3b3  push    rdi
0x1401ee3b4  push    r12
0x1401ee3b6  push    r13
0x1401ee3b8  push    r14
0x1401ee3ba  push    r15
0x1401ee3bc  sub     rsp, 110h
0x1401ee3c3  mov     rax, cs:__security_cookie
0x1401ee3ca  xor     rax, rsp
0x1401ee3cd  mov     [rsp+148h+var_48], rax
0x1401ee3d5  mov     edi, r8d
0x1401ee3d8  mov     rbx, rdx
0x1401ee3db  mov     r15, rcx
0x1401ee3de  mov     [rsp+148h+var_C8], rcx
0x1401ee3e6  mov     [rsp+148h+var_D0], rdx
0x1401ee3eb  xor     r12d, r12d
0x1401ee3ee  mov     [rsp+148h+var_F8], r12
0x1401ee3f3  mov     [rsp+148h+Source2], r12
0x1401ee3f8  lea     rcx, [rdx+298h]; Mutex
0x1401ee3ff  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee406  nop     dword ptr [rax+rax+00h]
0x1401ee40b  mov     eax, edi
0x1401ee40d  and     eax, 7Fh
0x1401ee410  mov     r14, [rbx+rax*8+990h]
0x1401ee418  test    r14, r14
0x1401ee41b  jz      short loc_1401EE47A
0x1401ee41d  mov     r14, [r14]
0x1401ee420  test    r14, r14
0x1401ee423  jz      short loc_1401EE47A
0x1401ee425  cmp     [r14+0Ch], edi
0x1401ee429  jnz     short loc_1401EE47A
0x1401ee42b  mov     edi, 1
0x1401ee430  lock xadd [r14], edi
0x1401ee435  inc     edi
0x1401ee437  cmp     edi, 1
0x1401ee43a  jle     loc_1401EEAAF
0x1401ee440  lea     rcx, [rbx+298h]; Mutex
0x1401ee447  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee44e  nop     dword ptr [rax+rax+00h]
0x1401ee453  mov     rax, r14
0x1401ee456  mov     rcx, [rsp+148h+var_48]
0x1401ee45e  xor     rcx, rsp; StackCookie
0x1401ee461  call    __security_check_cookie
0x1401ee466  add     rsp, 110h
0x1401ee46d  pop     r15
0x1401ee46f  pop     r14
0x1401ee471  pop     r13
0x1401ee473  pop     r12
0x1401ee475  pop     rdi
0x1401ee476  pop     rsi
0x1401ee477  pop     rbx
0x1401ee478  retn
0x1401ee47a  lea     rcx, [rbx+298h]; Mutex
0x1401ee481  call    cs:__imp_KeReleaseGuardedMutex
0x1401ee488  nop     dword ptr [rax+rax+00h]
0x1401ee48d  mov     rdx, [rbx+68h]
0x1401ee491  test    rdx, rdx
0x1401ee494  jnz     short loc_1401EE49A
0x1401ee496  xor     eax, eax
0x1401ee498  jmp     short loc_1401EE456
0x1401ee49a  mov     r14, r12
0x1401ee49d  mov     [rsp+148h+var_F8], r12
0x1401ee4a2  xor     r9d, r9d
0x1401ee4a5  mov     r8, rdx
0x1401ee4a8  mov     rdx, [rdx+0B8h]
0x1401ee4af  mov     rcx, r15
0x1401ee4b2  call    NtfsAcquireSharedFcb
0x1401ee4b7  lea     rcx, [rbx+298h]; Mutex
0x1401ee4be  call    cs:__imp_KeAcquireGuardedMutex
0x1401ee4c5  nop     dword ptr [rax+rax+00h]
0x1401ee4ca  nop
0x1401ee4cb  mov     [rsp+148h+var_E8], edi
0x1401ee4cf  xorps   xmm0, xmm0
0x1401ee4d2  xor     eax, eax
0x1401ee4d4  movups  [rsp+148h+Source1], xmm0
0x1401ee4dc  mov     [rsp+148h+Length], eax
0x1401ee4e3  xorps   xmm1, xmm1
0x1401ee4e6  movups  xmmword ptr [rsp+148h+var_A0], xmm1
0x1401ee4ee  movups  xmmword ptr [rsp+148h+Bcb], xmm1
0x1401ee4f6  mov     dword ptr [rsp+148h+var_80+4], eax
0x1401ee4fd  movups  [rsp+148h+var_80], xmm0
0x1401ee505  movups  [rsp+148h+var_80+0Ch], xmm0
0x1401ee50d  mov     [rsp+148h+var_C0+4], eax
0x1401ee514  movups  xmmword ptr [rsp+148h+var_C0], xmm0
0x1401ee51c  movups  xmmword ptr [rsp+148h+var_C0+0Ch], xmm0
0x1401ee524  mov     [rsp+148h+Bcb+8], r12
0x1401ee52c  mov     [rsp+148h+var_C0], 4
0x1401ee537  lea     rax, [rsp+148h+var_E8]
0x1401ee53c  mov     qword ptr [rsp+148h+var_C0+8], rax
0x1401ee544  mov     [rsp+148h+var_B0], r12
0x1401ee54c  mov     [rsp+148h+Buffer], r12; __int64
0x1401ee551  lea     rax, [rsp+148h+var_A0]
0x1401ee559  mov     [rsp+148h+var_128], rax; __int64
0x1401ee55e  lea     r9, [rsp+148h+var_80]
0x1401ee566  lea     r8, [rsp+148h+var_C0]; int
0x1401ee56e  mov     rdx, [rbx+70h]; int
0x1401ee572  mov     rcx, r15; int
0x1401ee575  call    NtOfsFindRecord
0x1401ee57a  cmp     eax, 0C0000272h
0x1401ee57f  jz      loc_1401EEA3C
0x1401ee585  mov     rax, [rsp+148h+var_68]
0x1401ee58d  movups  xmm0, xmmword ptr [rax]
0x1401ee590  movups  [rsp+148h+Source1], xmm0
0x1401ee598  mov     r8d, [rax+10h]
0x1401ee59c  mov     [rsp+148h+Length], r8d
0x1401ee5a4  mov     rcx, [rsp+148h+Bcb+8]; Bcb
0x1401ee5ac  test    rcx, rcx
0x1401ee5af  jz      short loc_1401EE5CD
0x1401ee5b1  call    cs:__imp_CcUnpinData
0x1401ee5b8  nop     dword ptr [rax+rax+00h]
0x1401ee5bd  mov     [rsp+148h+Bcb+8], r12
0x1401ee5c5  mov     r8d, [rsp+148h+Length]; Length
0x1401ee5cd  cmp     [rsp+148h+var_70], 14h
0x1401ee5d5  jnz     loc_1401EEA3C
0x1401ee5db  mov     r13, [rbx+68h]
0x1401ee5df  mov     rcx, [r13+20h]
0x1401ee5e3  mov     rdx, qword ptr [rsp+148h+Source1+8]
0x1401ee5eb  cmp     rdx, rcx
0x1401ee5ee  ja      loc_1401EEA3C
0x1401ee5f4  mov     eax, r8d
0x1401ee5f7  add     rax, rdx
0x1401ee5fa  cmp     rax, rcx
0x1401ee5fd  ja      loc_1401EEA3C
0x1401ee603  cmp     r8d, 14h
0x1401ee607  jb      loc_1401EEA3C
0x1401ee60d  dec     rax
0x1401ee610  xor     rax, rdx
0x1401ee613  test    rax, 0FFFFFFFFFFFC0000h
0x1401ee619  jnz     loc_1401EEA3C
0x1401ee61f  mov     qword ptr [rsp+148h+FileOffset], rdx
0x1401ee624  test    rdx, rdx
0x1401ee627  js      loc_1401EE99D
0x1401ee62d  mov     eax, r8d
0x1401ee630  add     rax, rdx
0x1401ee633  cmp     rax, [r13+18h]
0x1401ee637  jg      loc_1401EE99D
0x1401ee63d  lea     rax, [rsp+148h+Source2]
0x1401ee642  mov     [rsp+148h+Buffer], rax; Buffer
0x1401ee647  lea     rax, [rsp+148h+var_F8]
0x1401ee64c  mov     [rsp+148h+var_128], rax; Bcb
0x1401ee651  mov     edi, 1
0x1401ee656  mov     r9d, edi; Flags
0x1401ee659  lea     rdx, [rsp+148h+FileOffset]; FileOffset
0x1401ee65e  mov     rcx, [r13+118h]; FileObject
0x1401ee665  call    cs:__imp_CcMapData
0x1401ee66c  nop     dword ptr [rax+rax+00h]
0x1401ee671  test    al, al
0x1401ee673  jz      loc_1401EE979
0x1401ee679  mov     r8d, 14h; Length
0x1401ee67f  mov     rdx, [rsp+148h+Source2]; Source2
0x1401ee684  lea     rcx, [rsp+148h+Source1]; Source1
0x1401ee68c  call    cs:__imp_RtlCompareMemory
0x1401ee693  nop     dword ptr [rax+rax+00h]
0x1401ee698  cmp     rax, 14h
0x1401ee69c  jnz     loc_1401EEA3C
0x1401ee6a2  mov     rax, [rsp+148h+Source2]
0x1401ee6a7  lea     rdx, [rax+14h]; SecurityDescriptor
0x1401ee6ab  mov     ecx, [rax+10h]
0x1401ee6ae  sub     ecx, 14h; Length
0x1401ee6b1  call    cs:__imp_SeValidSecurityDescriptor
0x1401ee6b8  nop     dword ptr [rax+rax+00h]
0x1401ee6bd  test    al, al
0x1401ee6bf  jz      loc_1401EEA3C
0x1401ee6c5  mov     r12, [rsp+148h+Source2]
0x1401ee6ca  mov     ecx, [r12]
0x1401ee6ce  mov     r13d, [r12+10h]
0x1401ee6d3  mov     eax, ecx
0x1401ee6d5  and     eax, 7Fh
0x1401ee6d8  mov     r14, [rbx+rax*8+0D90h]
0x1401ee6e0  test    r14, r14
0x1401ee6e3  jz      short loc_1401EE716
0x1401ee6e5  cmp     [r14+8], ecx
0x1401ee6e9  jnz     short loc_1401EE74A
0x1401ee6eb  lea     r8d, [r13-14h]; Size
0x1401ee6ef  mov     eax, [r14+18h]
0x1401ee6f3  sub     rax, 14h
0x1401ee6f7  cmp     rax, r8
0x1401ee6fa  jnz     loc_1401EE971
0x1401ee700  lea     rdx, [r12+14h]; Buf2
0x1401ee705  lea     rcx, [r14+1Ch]; Buf1
0x1401ee709  call    memcmp
0x1401ee70e  xor     ecx, ecx
0x1401ee710  test    eax, eax
0x1401ee712  cmovnz  r14, rcx
0x1401ee716  mov     [rsp+148h+var_D8], r14
0x1401ee71b  test    r14, r14
0x1401ee71e  jnz     short loc_1401EE74F
0x1401ee720  add     r13d, 8
0x1401ee724  cmp     r13d, 8
0x1401ee728  jnb     short loc_1401EE77F
0x1401ee72a  movzx   eax, cs:NtfsStatusDebugFlags
0x1401ee731  test    al, al
0x1401ee733  jnz     loc_1401EE943
0x1401ee739  mov     ecx, 0C0000183h; Status
0x1401ee73e  call    cs:__imp_ExRaiseStatus
0x1401ee74a  xor     r14d, r14d
0x1401ee74d  jmp     short loc_1401EE716
0x1401ee74f  movups  xmm0, xmmword ptr [r12]
0x1401ee754  movups  xmmword ptr [r14+8], xmm0
0x1401ee759  mov     eax, [r12+10h]
0x1401ee75e  mov     [r14+18h], eax
0x1401ee762  mov     eax, edi
0x1401ee764  lock xadd [r14], eax
0x1401ee769  inc     eax
0x1401ee76b  cmp     eax, edi
0x1401ee76d  jg      loc_1401EE878
0x1401ee773  mov     ecx, 0Eh
0x1401ee778  int     29h; Win8: RtlFailFast(ecx)
0x1401ee77a  jmp     loc_1401EE878
0x1401ee77f  mov     edx, r13d; NumberOfBytes
0x1401ee782  mov     ecx, cs:PoolType
0x1401ee788  or      ecx, 10h; PoolType
0x1401ee78b  mov     r8d, 5346744Eh; Tag
0x1401ee791  call    cs:__imp_ExAllocatePoolWithTag
0x1401ee798  nop     dword ptr [rax+rax+00h]
0x1401ee79d  mov     r14, rax
0x1401ee7a0  mov     [rsp+148h+var_D8], rax
0x1401ee7a5  mov     [rax], edi
0x1401ee7a7  mov     r13, [rsp+148h+Source2]
0x1401ee7ac  mov     [rsp+148h+var_104], 0
0x1401ee7b4  mov     [rsp+148h+Dacl], 0
0x1401ee7bd  mov     [rsp+148h+DaclPresent], 0
0x1401ee7c2  mov     [rsp+148h+DaclDefaulted], 0
0x1401ee7c7  xor     r12d, r12d
0x1401ee7ca  mov     [rsp+148h+var_104], r12d
0x1401ee7cf  mov     [rsp+148h+DaclPresent], r12b
0x1401ee7d4  lea     r9, [rsp+148h+DaclDefaulted]; DaclDefaulted
0x1401ee7d9  lea     r8, [rsp+148h+Dacl]; Dacl
0x1401ee7de  lea     rdx, [rsp+148h+DaclPresent]; DaclPresent
0x1401ee7e3  lea     rcx, [r13+14h]; SecurityDescriptor
0x1401ee7e7  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1401ee7ee  nop     dword ptr [rax+rax+00h]
0x1401ee7f3  cmp     [rsp+148h+DaclPresent], r12b
0x1401ee7f8  jz      short loc_1401EE80F
0x1401ee7fa  mov     rcx, [rsp+148h+Dacl]
0x1401ee7ff  call    cs:__imp_RtlOwnerAcesPresent
0x1401ee806  nop     dword ptr [rax+rax+00h]
0x1401ee80b  test    al, al
0x1401ee80d  jnz     short loc_1401EE816
0x1401ee80f  mov     r12d, edi
0x1401ee812  mov     [rsp+148h+var_104], edi
0x1401ee816  mov     [rsp+148h+DaclPresent], 0
0x1401ee81b  lea     r9, [rsp+148h+DaclDefaulted]; SaclDefaulted
0x1401ee820  lea     r8, [rsp+148h+Dacl]; Sacl
0x1401ee825  lea     rdx, [rsp+148h+DaclPresent]; SaclPresent
0x1401ee82a  lea     rcx, [r13+14h]; SecurityDescriptor
0x1401ee82e  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1401ee835  nop     dword ptr [rax+rax+00h]
0x1401ee83a  cmp     [rsp+148h+DaclPresent], 0
0x1401ee83f  jnz     loc_1401EE8F5
0x1401ee845  or      r12d, 2
0x1401ee849  mov     [rsp+148h+var_104], r12d
0x1401ee84e  cmp     [rsp+148h+DaclPresent], 0
0x1401ee853  jnz     loc_1401EE91C
0x1401ee859  or      r12d, 4
0x1401ee85d  mov     [rsp+148h+var_104], r12d
0x1401ee862  mov     [r14+4], r12d
0x1401ee866  mov     rdx, [rsp+148h+Source2]; Src
0x1401ee86b  mov     r8d, [rdx+10h]; Size
0x1401ee86f  lea     rcx, [r14+8]; void *
0x1401ee873  call    memmove
0x1401ee878  mov     edx, [r14+8]
0x1401ee87c  and     edx, 7Fh
0x1401ee87f  add     rdx, 1B2h
0x1401ee886  lea     rdx, [rbx+rdx*8]
0x1401ee88a  mov     r8, [rdx]
0x1401ee88d  cmp     r14, r8
0x1401ee890  jz      loc_1401EE95A
0x1401ee896  mov     [rdx], r14
0x1401ee899  lock xadd [r14], edi
0x1401ee89e  inc     edi
0x1401ee8a0  cmp     edi, 1
0x1401ee8a3  jle     loc_1401EEA26
0x1401ee8a9  mov     eax, [r14+0Ch]
0x1401ee8ad  and     eax, 7Fh
0x1401ee8b0  mov     [rbx+rax*8+990h], rdx
0x1401ee8b8  test    r8, r8
0x1401ee8bb  jz      loc_1401EE969
0x1401ee8c1  mov     eax, 0FFFFFFFFh
0x1401ee8c6  lock xadd [r8], eax
0x1401ee8cb  sub     eax, 1
0x1401ee8ce  jg      loc_1401EE969
0x1401ee8d4  test    eax, eax
0x1401ee8d6  jnz     loc_1401EEA32
0x1401ee8dc  xor     edx, edx; Tag
0x1401ee8de  mov     rcx, r8; P
0x1401ee8e1  call    cs:__imp_ExFreePoolWithTag
0x1401ee8e8  nop     dword ptr [rax+rax+00h]
0x1401ee8ed  xor     r12d, r12d
0x1401ee8f0  jmp     loc_1401EEA3C
0x1401ee8f5  xor     r8d, r8d
0x1401ee8f8  mov     edx, 11h
0x1401ee8fd  mov     rcx, [rsp+148h+Dacl]
0x1401ee902  call    cs:__imp_RtlFindAceByType
0x1401ee909  nop     dword ptr [rax+rax+00h]
0x1401ee90e  test    rax, rax
0x1401ee911  jnz     loc_1401EE84E
0x1401ee917  jmp     loc_1401EE845
0x1401ee91c  xor     r8d, r8d
  ... truncated ...
```
