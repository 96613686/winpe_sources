# TxfFsctlCreateMiniversion

- ea: `0x1400faa0c`
- end: `0x1400fb0bf`
- name: `TxfFsctlCreateMiniversion`
- size: `1715`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1402491a8`

## callees

- `0x140007ea0`
- `0x14000cb00`
- `0x140012e70`
- `0x140021590`
- `0x140034560`
- `0x1400596c0`
- `0x1400faa0c`
- `0x140188ce4`
- `0x1401891f4`
- `0x14018dc4c`
- `0x1401ac080`
- `0x1401c00e0`
- `0x140243c00`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400fad38`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400fad38`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c413a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c413a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400faddd`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400faddd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fab5c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fac7a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fab5c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fac7a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fab79`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fb00d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c416a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fab79`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fb00d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c416a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400fad23`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400fad23`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400fad54`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400fad54`
- `ntoskrnl!ExRaiseStatus` at `0x1400fafd9`
- `ntoskrnl!ExRaiseStatus` at `0x1400fafd9`

## pseudocode

```c
__int64 __fastcall TxfFsctlCreateMiniversion(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // r14
  __int64 v8; // r9
  unsigned int v9; // r8d
  __int64 TxfVscb; // r13
  char v11; // bl
  _QWORD *v12; // r15
  __int64 v13; // r12
  signed int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // r8
  unsigned int j; // eax
  __int64 v21; // rcx
  unsigned int v22; // r8d
  __int64 v23; // rax
  __int64 v24; // r14
  BOOLEAN k; // dl
  __int64 v26; // rcx
  _QWORD *v27; // r14
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 i; // rcx
  int v34; // [rsp+20h] [rbp-98h]
  char v35; // [rsp+50h] [rbp-68h]
  char v36; // [rsp+51h] [rbp-67h]
  char v37; // [rsp+52h] [rbp-66h]
  char v38; // [rsp+53h] [rbp-65h]
  _QWORD v39[2]; // [rsp+60h] [rbp-58h] BYREF
  _QWORD *v40; // [rsp+70h] [rbp-48h]
  __int64 v41; // [rsp+78h] [rbp-40h]
  __int64 v42; // [rsp+80h] [rbp-38h]

  v39[0] = 0;
  if ( !a4 || a3 < 0xC )
  {
    if ( NtfsStatusDebugFlags )
    {
      v9 = 2692725;
      goto LABEL_13;
    }
    return (unsigned int)-1073741811;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL) & 0x2000000) == 0 )
  {
    v7 = *(_QWORD *)(a2 + 32);
    v8 = *(_QWORD *)(v7 + 80);
    if ( !v8 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v9 = 2692751;
LABEL_13:
        v14 = -1073741811;
        NtfsStatusTraceAndDebugInternal(0, 0xC000000D, v9);
        return (unsigned int)v14;
      }
      return (unsigned int)-1073741811;
    }
    TxfVscb = 0;
    v38 = 0;
    v36 = 0;
    v37 = 0;
    v40 = 0;
    v11 = 0;
    v35 = 0;
    v12 = *(_QWORD **)(a2 + 24);
    v39[1] = v12;
    v13 = v12[23];
    v42 = v13;
    if ( !*(_QWORD *)(v13 + 328) )
    {
      if ( NtfsStatusDebugFlags )
      {
        v9 = 2692756;
        goto LABEL_13;
      }
      return (unsigned int)-1073741811;
    }
    v14 = TxfReferenceTransaction(0, *(_QWORD *)(v13 + 320), 0, *(_QWORD *)(v8 + 56), 1, 0, 0, 0, (__int64)v39);
    if ( v14 < 0 )
    {
LABEL_67:
      if ( v36 )
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v13 + 328) + 136LL));
      if ( v37 )
        NtfsReleaseFcbEx(a1, v12[23], 0);
      if ( v11 )
      {
        NtfsReleasePagingResourcePriv(v16, v12[23]);
        if ( a1 )
        {
          for ( i = 0; i != 2; ++i )
          {
            if ( *(_QWORD *)(a1 + 8 * i + 48) == v12[23] )
              *(_QWORD *)(a1 + 8 * i + 48) = 0;
          }
        }
      }
      if ( v38 )
      {
        LOBYTE(v15) = 1;
        TxfDereferenceTransaction(v39, v15);
      }
      return (unsigned int)v14;
    }
    v38 = 1;
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v39[0] + 24LL) + 80LL), 1u);
    v17 = *(_QWORD *)(v39[0] + 40LL);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v39[0] + 24LL) + 80LL));
    v18 = v12[23];
    v19 = 0;
    if ( *(_QWORD *)(v18 + 112) )
    {
      LOBYTE(v19) = 1;
      if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v12[23], v19) )
      {
        for ( j = 0; j < 2; ++j )
        {
          v21 = *(_QWORD *)(a1 + 8LL * j + 48);
          if ( !v21 || v21 == v18 )
          {
            *(_QWORD *)(a1 + 8LL * j + 48) = v18;
            break;
          }
        }
      }
      v35 = 1;
    }
    LOBYTE(v34) = 0;
    v14 = NtfsFlushUserStream(a1, v12, 0, 0, v34);
    v15 = *(unsigned int *)(*(_QWORD *)(a1 + 144) + 24LL);
    if ( (_DWORD)v15 == -1073741432 || (_DWORD)v15 == -1073741608 )
    {
      if ( NtfsStatusDebugFlags
        && (((_DWORD)v15 - 294) & 0xFFFFFFFA) != 0
        && (_DWORD)v15 != -1073741608
        && (unsigned int)(v15 + 2147483643) > 1 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v15, 0x2916DBu);
      }
      ExRaiseStatus(*(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL));
    }
    if ( v14 >= 0 )
    {
      NtfsAcquireExclusiveScbEx(a1, (__int64)v12, 0);
      v37 = 1;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v13 + 328) + 136LL), 1u);
      v15 = 1;
      v36 = 1;
      v23 = *(_QWORD *)(*(_QWORD *)(v13 + 328) + 24LL);
      if ( v23
        && (v16 = *(_QWORD *)(v7 + 80), *(_QWORD *)(v16 + 56) == *(_QWORD *)(v23 + 232))
        && !*(_DWORD *)(v16 + 36) )
      {
        v16 = *(_QWORD *)(v12[66] + 56LL);
        if ( !v16 || (*(_DWORD *)(v16 + 8) & 1) != 0 )
        {
          v14 = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_66;
          v22 = 2692881;
        }
        else
        {
          if ( *(_WORD *)(v16 + 304) < 0x3E8u )
          {
            v24 = TxfCurrentWritableVersion(v12[66], 1, 0);
            ExAcquireFastMutex(*(PFAST_MUTEX *)(v24 + 256));
            for ( k = 1; RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(v24 + 152), k); k = 0 )
              ;
            ExReleaseFastMutex(*(PFAST_MUTEX *)(v24 + 256));
            if ( !*(_QWORD *)(v24 + 120) && *(_QWORD *)(v24 + 48) == v24 + 48 && (*(_DWORD *)(v24 + 8) & 0x10000) != 0 )
            {
              v26 = *(_QWORD *)(v24 + 264);
              if ( *(_QWORD *)(v26 + 16) == v12[5] && *(_QWORD *)(v26 + 8) == v12[4] && *(_WORD *)(v24 + 304) )
              {
                v14 = 0;
                TxfVscb = v24;
              }
            }
            if ( !TxfVscb )
            {
              v41 = TxfSearchAddTxfFcbCleanupList(a1, *(_QWORD *)(v13 + 328), 1, 0, 0);
              v27 = ExAllocateFromLookasideListEx(&TxfFcbInfoLookasideList);
              v40 = v27;
              memset(v27, 0, 0x50u);
              *((_OWORD *)v27 + 1) = *(_OWORD *)(v13 + 128);
              *((_OWORD *)v27 + 2) = *(_OWORD *)(v13 + 144);
              *((_OWORD *)v27 + 3) = *(_OWORD *)(v13 + 160);
              v27[8] = *(_QWORD *)(v13 + 176);
              *((_DWORD *)v27 + 18) = *(_DWORD *)(v13 + 280);
              *((_WORD *)v27 + 39) |= 8u;
              v29 = *(_QWORD *)(v13 + 328) + 88LL;
              v30 = *(_QWORD *)v29;
              if ( *(_QWORD *)(*(_QWORD *)v29 + 8LL) != v29 )
                __fastfail(3u);
              *v27 = v30;
              v27[1] = v29;
              *(_QWORD *)(v30 + 8) = v27;
              *(_QWORD *)v29 = v27;
              *(_DWORD *)(*(_QWORD *)(v13 + 328) + 4LL) |= 8u;
              LOBYTE(v28) = 1;
              TxfVscb = TxfCreateTxfVscb(a1, v12, 1, v28);
              v31 = v41;
              *(_QWORD *)(v41 + 24) = TxfVscb;
              *(_DWORD *)(v31 + 16) |= 0x400u;
              _InterlockedOr((volatile signed __int32 *)(TxfVscb + 8), 0x8002u);
              _InterlockedAdd((volatile signed __int32 *)(TxfVscb + 4), 1u);
              v32 = *(_QWORD *)(TxfVscb + 32);
              *(_WORD *)(TxfVscb + 304) = *(_WORD *)(v32 + 304) + 1;
              _InterlockedOr((volatile signed __int32 *)(TxfVscb + 8), *(_DWORD *)(v32 + 8) & 0x100);
              _InterlockedOr((volatile signed __int32 *)(TxfVscb + 8), 0x400u);
              *(_QWORD *)(TxfVscb + 280) = v17;
            }
            v15 = a4;
            *(_DWORD *)a4 = 786433;
            *(_WORD *)(a4 + 8) = *(_WORD *)(TxfVscb + 304);
            v16 = *(unsigned int *)(*(_QWORD *)(TxfVscb + 16) + 40LL);
            *(_DWORD *)(a4 + 4) = v16;
            *a5 = 12;
            goto LABEL_66;
          }
          v14 = -1072103386;
          if ( !NtfsStatusDebugFlags )
          {
LABEL_66:
            v11 = v35;
            goto LABEL_67;
          }
          v22 = 2692890;
        }
      }
      else
      {
        v14 = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_66;
        v22 = 2692870;
      }
    }
    else
    {
      if ( v14 != -1073741740 )
        goto LABEL_66;
      v14 = -1073741670;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_66;
      v22 = 2692842;
    }
    NtfsStatusTraceAndDebugInternal(0, v14, v22);
    goto LABEL_66;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC00000A2, 0x29167Eu);
  return 3221225634LL;
}

```

## disassembly

```asm
0x1400faa0c  mov     rax, rsp
0x1400faa0f  mov     [rax+10h], rbx
0x1400faa13  mov     [rax+18h], rsi
0x1400faa17  mov     [rax+20h], r9
0x1400faa1b  mov     [rax+8], rcx
0x1400faa1f  push    rdi
0x1400faa20  push    r12
0x1400faa22  push    r13
0x1400faa24  push    r14
0x1400faa26  push    r15
0x1400faa28  sub     rsp, 90h
0x1400faa2f  mov     rsi, rcx
0x1400faa32  xor     ecx, ecx
0x1400faa34  mov     [rax-58h], rcx
0x1400faa38  test    r9, r9
0x1400faa3b  jz      loc_1400FB085
0x1400faa41  cmp     r8d, 0Ch
0x1400faa45  jb      loc_1400FB085
0x1400faa4b  mov     rax, [rsi+68h]
0x1400faa4f  test    dword ptr [rax+4], 2000000h
0x1400faa56  jz      short loc_1400FAA7C
0x1400faa58  mov     al, cs:NtfsStatusDebugFlags
0x1400faa5e  test    al, al
0x1400faa60  jz      short loc_1400FAA72
0x1400faa62  mov     edx, 0C00000A2h
0x1400faa67  mov     r8d, 29167Eh
0x1400faa6d  call    NtfsStatusTraceAndDebugInternal
0x1400faa72  mov     eax, 0C00000A2h
0x1400faa77  jmp     loc_1400FB0A1
0x1400faa7c  mov     r14, [rdx+20h]
0x1400faa80  mov     r9, [r14+50h]
0x1400faa84  test    r9, r9
0x1400faa87  jnz     short loc_1400FAA9F
0x1400faa89  mov     al, cs:NtfsStatusDebugFlags
0x1400faa8f  test    al, al
0x1400faa91  jz      loc_1400FB09A
0x1400faa97  mov     r8d, 29168Fh
0x1400faa9d  jmp     short loc_1400FAAEF
0x1400faa9f  mov     r13, rcx
0x1400faaa2  mov     [rsp+0B8h+var_65], cl
0x1400faaa6  mov     [rsp+0B8h+var_67], cl
0x1400faaaa  mov     [rsp+0B8h+var_66], cl
0x1400faaae  mov     [rsp+0B8h+var_48], rcx
0x1400faab3  mov     bl, cl
0x1400faab5  mov     [rsp+0B8h+var_68], cl
0x1400faab9  mov     r15, [rdx+18h]
0x1400faabd  mov     [rsp+0B8h+var_50], r15
0x1400faac2  mov     r12, [r15+0B8h]
0x1400faac9  mov     [rsp+0B8h+var_38], r12
0x1400faad1  cmp     [r12+148h], rcx
0x1400faad9  jnz     short loc_1400FAB00
0x1400faadb  mov     al, cs:NtfsStatusDebugFlags
0x1400faae1  test    al, al
0x1400faae3  jz      loc_1400FB09A
0x1400faae9  mov     r8d, 291694h
0x1400faaef  mov     edi, 0C000000Dh
0x1400faaf4  mov     edx, edi
0x1400faaf6  call    NtfsStatusTraceAndDebugInternal
0x1400faafb  jmp     loc_1400FB09F
0x1400fab00  lea     rax, [rsp+0B8h+var_58]
0x1400fab05  mov     [rsp+0B8h+var_78], rax
0x1400fab0a  mov     [rsp+0B8h+var_80], cl
0x1400fab0e  mov     [rsp+0B8h+var_88], cl
0x1400fab12  mov     [rsp+0B8h+var_90], cl
0x1400fab16  mov     [rsp+0B8h+var_98], 1
0x1400fab1b  mov     r9, [r9+38h]
0x1400fab1f  xor     r8d, r8d
0x1400fab22  mov     rdx, [r12+140h]
0x1400fab2a  xor     ecx, ecx
0x1400fab2c  call    TxfReferenceTransaction
0x1400fab31  mov     edi, eax
0x1400fab33  mov     [rsp+0B8h+var_64], eax
0x1400fab37  xor     r8d, r8d
0x1400fab3a  test    eax, eax
0x1400fab3c  js      loc_1400FAFE5
0x1400fab42  mov     [rsp+0B8h+var_64], r8d
0x1400fab47  lea     edx, [r8+1]; Wait
0x1400fab4b  mov     [rsp+0B8h+var_65], dl
0x1400fab4f  mov     rax, [rsp+0B8h+var_58]
0x1400fab54  mov     rcx, [rax+18h]
0x1400fab58  add     rcx, 50h ; 'P'; Resource
0x1400fab5c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fab63  nop     dword ptr [rax+rax+00h]
0x1400fab68  mov     rax, [rsp+0B8h+var_58]
0x1400fab6d  mov     rbx, [rax+28h]
0x1400fab71  mov     rcx, [rax+18h]
0x1400fab75  add     rcx, 50h ; 'P'; Resource
0x1400fab79  call    cs:__imp_ExReleaseResourceLite
0x1400fab80  nop     dword ptr [rax+rax+00h]
0x1400fab85  mov     rdi, [r15+0B8h]
0x1400fab8c  xor     r8d, r8d
0x1400fab8f  cmp     [rdi+70h], r8
0x1400fab93  jz      short loc_1400FABDA
0x1400fab95  mov     r8b, 1
0x1400fab98  mov     rdx, rdi
0x1400fab9b  mov     rcx, rsi
0x1400fab9e  call    NtfsAcquirePagingResourceExclusive
0x1400faba3  xor     r8d, r8d
0x1400faba6  test    al, al
0x1400faba8  jz      short loc_1400FABD5
0x1400fabaa  mov     [rsp+0B8h+var_60], r8d
0x1400fabaf  mov     eax, r8d
0x1400fabb2  mov     [rsp+0B8h+var_60], eax
0x1400fabb6  cmp     eax, 2
0x1400fabb9  jnb     short loc_1400FABD5
0x1400fabbb  mov     edx, eax
0x1400fabbd  mov     rcx, [rsi+rdx*8+30h]
0x1400fabc2  test    rcx, rcx
0x1400fabc5  jz      short loc_1400FABD0
0x1400fabc7  cmp     rcx, rdi
0x1400fabca  jz      short loc_1400FABD0
0x1400fabcc  inc     eax
0x1400fabce  jmp     short loc_1400FABB2
0x1400fabd0  mov     [rsi+rdx*8+30h], rdi
0x1400fabd5  mov     [rsp+0B8h+var_68], 1
0x1400fabda  mov     [rsp+0B8h+var_98], r8b
0x1400fabdf  xor     r9d, r9d
0x1400fabe2  xor     r8d, r8d
0x1400fabe5  mov     rdx, r15
0x1400fabe8  mov     rcx, rsi
0x1400fabeb  call    NtfsFlushUserStream
0x1400fabf0  mov     edi, eax
0x1400fabf2  mov     [rsp+0B8h+var_64], eax
0x1400fabf6  mov     rax, [rsi+90h]
0x1400fabfd  mov     edx, [rax+18h]
0x1400fac00  cmp     edx, 0C0000188h
0x1400fac06  jz      loc_1400FAF6E
0x1400fac0c  cmp     edx, 0C00000D8h
0x1400fac12  jz      loc_1400FAF6E
0x1400fac18  xor     r8d, r8d
0x1400fac1b  test    edi, edi
0x1400fac1d  jns     short loc_1400FAC55
0x1400fac1f  cmp     edi, 0C0000054h
0x1400fac25  jnz     loc_1400FAFED
0x1400fac2b  mov     al, cs:NtfsStatusDebugFlags
0x1400fac31  mov     edi, 0C000009Ah
0x1400fac36  test    al, al
0x1400fac38  jz      short loc_1400FAC4C
0x1400fac3a  mov     r8d, 2916EAh
0x1400fac40  mov     edx, edi
0x1400fac42  xor     ecx, ecx
0x1400fac44  call    NtfsStatusTraceAndDebugInternal
0x1400fac49  xor     r8d, r8d
0x1400fac4c  mov     [rsp+0B8h+var_64], edi
0x1400fac50  jmp     loc_1400FAFED
0x1400fac55  mov     rdx, r15
0x1400fac58  mov     rcx, rsi
0x1400fac5b  call    NtfsAcquireExclusiveScbEx
0x1400fac60  mov     eax, 1
0x1400fac65  mov     [rsp+0B8h+var_66], al
0x1400fac69  mov     rcx, [r12+148h]
0x1400fac71  mov     dl, al; Wait
0x1400fac73  mov     rcx, [rcx+88h]; Resource
0x1400fac7a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fac81  nop     dword ptr [rax+rax+00h]
0x1400fac86  mov     edx, 1
0x1400fac8b  mov     [rsp+0B8h+var_67], dl
0x1400fac8f  mov     rax, [r12+148h]
0x1400fac97  mov     rax, [rax+18h]
0x1400fac9b  xor     r8d, r8d
0x1400fac9e  test    rax, rax
0x1400faca1  jz      loc_1400FAF50
0x1400faca7  mov     rcx, [r14+50h]
0x1400facab  mov     rax, [rax+0E8h]
0x1400facb2  cmp     [rcx+38h], rax
0x1400facb6  jnz     loc_1400FAF50
0x1400facbc  cmp     [rcx+24h], r8d
0x1400facc0  jnz     loc_1400FAF50
0x1400facc6  mov     r9, [r15+210h]
0x1400faccd  mov     rcx, [r9+38h]
0x1400facd1  test    rcx, rcx
0x1400facd4  jz      loc_1400FAF32
0x1400facda  mov     eax, [rcx+8]
0x1400facdd  test    dl, al
0x1400facdf  jnz     loc_1400FAF32
0x1400face5  mov     eax, 3E8h
0x1400facea  cmp     [rcx+130h], ax
0x1400facf1  jb      short loc_1400FAD11
0x1400facf3  mov     al, cs:NtfsStatusDebugFlags
0x1400facf9  mov     edi, 0C0190026h
0x1400facfe  test    al, al
0x1400fad00  jz      loc_1400FAC4C
0x1400fad06  mov     r8d, 29171Ah
0x1400fad0c  jmp     loc_1400FAC40
0x1400fad11  mov     rcx, r9
0x1400fad14  call    TxfCurrentWritableVersion
0x1400fad19  mov     r14, rax
0x1400fad1c  mov     rcx, [rax+100h]; FastMutex
0x1400fad23  call    cs:__imp_ExAcquireFastMutex
0x1400fad2a  nop     dword ptr [rax+rax+00h]
0x1400fad2f  mov     dl, 1; Restart
0x1400fad31  lea     rcx, [r14+98h]; Table
0x1400fad38  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400fad3f  nop     dword ptr [rax+rax+00h]
0x1400fad44  test    rax, rax
0x1400fad47  jz      short loc_1400FAD4D
0x1400fad49  xor     edx, edx
0x1400fad4b  jmp     short loc_1400FAD31
0x1400fad4d  mov     rcx, [r14+100h]; FastMutex
0x1400fad54  call    cs:__imp_ExReleaseFastMutex
0x1400fad5b  nop     dword ptr [rax+rax+00h]
0x1400fad60  xor     r8d, r8d
0x1400fad63  cmp     [r14+78h], r8
0x1400fad67  jnz     short loc_1400FADAC
0x1400fad69  lea     rax, [r14+30h]
0x1400fad6d  cmp     [rax], rax
0x1400fad70  jnz     short loc_1400FADAC
0x1400fad72  test    dword ptr [r14+8], 10000h
0x1400fad7a  jz      short loc_1400FADAC
0x1400fad7c  mov     rcx, [r14+108h]
0x1400fad83  mov     rax, [r15+28h]
0x1400fad87  cmp     [rcx+10h], rax
0x1400fad8b  jnz     short loc_1400FADAC
0x1400fad8d  mov     rax, [r15+20h]
0x1400fad91  cmp     [rcx+8], rax
0x1400fad95  jnz     short loc_1400FADAC
0x1400fad97  cmp     [r14+130h], r8w
0x1400fad9f  jz      short loc_1400FADAC
0x1400fada1  mov     edi, r8d
0x1400fada4  mov     [rsp+0B8h+var_64], r8d
0x1400fada9  mov     r13, r14
0x1400fadac  test    r13, r13
0x1400fadaf  jnz     loc_1400FAEF2
0x1400fadb5  mov     [rsp+0B8h+var_98], r8b
0x1400fadba  xor     r9d, r9d
0x1400fadbd  lea     r8d, [r13+1]
0x1400fadc1  mov     rdx, [r12+148h]
0x1400fadc9  mov     rcx, rsi
0x1400fadcc  call    TxfSearchAddTxfFcbCleanupList
0x1400fadd1  mov     [rsp+0B8h+var_40], rax
0x1400fadd6  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x1400faddd  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400fade4  nop     dword ptr [rax+rax+00h]
0x1400fade9  mov     r14, rax
0x1400fadec  mov     [rsp+0B8h+var_48], rax
0x1400fadf1  xor     edx, edx; Val
0x1400fadf3  lea     r8d, [r13+50h]; Size
0x1400fadf7  mov     rcx, rax; void *
0x1400fadfa  call    memset
0x1400fadff  movups  xmm0, xmmword ptr [r12+80h]
0x1400fae08  movups  xmmword ptr [r14+10h], xmm0
0x1400fae0d  movups  xmm1, xmmword ptr [r12+90h]
0x1400fae16  movups  xmmword ptr [r14+20h], xmm1
0x1400fae1b  movups  xmm0, xmmword ptr [r12+0A0h]
0x1400fae24  movups  xmmword ptr [r14+30h], xmm0
0x1400fae29  movsd   xmm1, qword ptr [r12+0B0h]
0x1400fae33  movsd   qword ptr [r14+40h], xmm1
0x1400fae39  mov     eax, [r12+118h]
0x1400fae41  mov     [r14+48h], eax
0x1400fae45  lea     edx, [r13+8]
0x1400fae49  or      [r14+4Eh], dx
0x1400fae4e  mov     rax, [r12+148h]
0x1400fae56  add     rax, 58h ; 'X'
0x1400fae5a  mov     rcx, [rax]
0x1400fae5d  cmp     [rcx+8], rax
0x1400fae61  jz      short loc_1400FAE68
0x1400fae63  lea     ecx, [rdx-5]
0x1400fae66  int     29h; Win8: RtlFailFast(ecx)
0x1400fae68  mov     [r14], rcx
0x1400fae6b  mov     [r14+8], rax
0x1400fae6f  mov     [rcx+8], r14
0x1400fae73  mov     [rax], r14
0x1400fae76  mov     rax, [r12+148h]
0x1400fae7e  or      [rax+4], edx
0x1400fae81  mov     r14d, 1
0x1400fae87  mov     r9b, r14b
0x1400fae8a  mov     r8d, r14d
0x1400fae8d  mov     rdx, r15
0x1400fae90  mov     rcx, rsi
0x1400fae93  call    TxfCreateTxfVscb
0x1400fae98  mov     r13, rax
0x1400fae9b  mov     rax, [rsp+0B8h+var_40]
0x1400faea0  mov     [rax+18h], r13
0x1400faea4  mov     r8d, 400h
0x1400faeaa  or      [rax+10h], r8d
0x1400faeae  lock or dword ptr [r13+8], 8002h
0x1400faeb7  lock add [r13+4], r14d
0x1400faebc  mov     rdx, [r13+20h]
0x1400faec0  movzx   ecx, word ptr [rdx+130h]
0x1400faec7  add     cx, r14w
0x1400faecb  mov     [r13+130h], cx
0x1400faed3  mov     ecx, [rdx+8]
0x1400faed6  and     ecx, 100h
0x1400faedc  lock or [r13+8], ecx
0x1400faee1  lock or [r13+8], r8d
0x1400faee6  mov     [r13+118h], rbx
0x1400faeed  xor     r8d, r8d
0x1400faef0  jmp     short loc_1400FAEF8
0x1400faef2  mov     r14d, 1
0x1400faef8  mov     rdx, [rsp+0B8h+arg_18]
0x1400faf00  mov     r9d, 0Ch
0x1400faf06  mov     dword ptr [rdx], 0C0001h
0x1400faf0c  movzx   eax, word ptr [r13+130h]
0x1400faf14  mov     [rdx+8], ax
0x1400faf18  mov     rax, [r13+10h]
0x1400faf1c  mov     ecx, [rax+28h]
0x1400faf1f  mov     [rdx+4], ecx
0x1400faf22  mov     rax, [rsp+0B8h+arg_20]
0x1400faf2a  mov     [rax], r9d
0x1400faf2d  jmp     loc_1400FAFF3
  ... truncated ...
```
