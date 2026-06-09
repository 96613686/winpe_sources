# TxfFsctlCreateMiniversion

- ea: `0x1400faa5c`
- end: `0x1400fb10f`
- name: `TxfFsctlCreateMiniversion`
- size: `1715`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1402491f8`

## callees

- `0x140007ea0`
- `0x14000cb00`
- `0x140012e70`
- `0x140021590`
- `0x140034560`
- `0x140059740`
- `0x1400faa5c`
- `0x140188d34`
- `0x140189244`
- `0x14018dc9c`
- `0x1401ac0d0`
- `0x1401c0130`
- `0x140243c50`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400fad88`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400fad88`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c418a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c418a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fae2d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fae2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fabac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400facca`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fabac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400facca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fabc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fb05d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c41ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fabc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fb05d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c41ba`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400fad73`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400fad73`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400fada4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400fada4`
- `ntoskrnl!ExRaiseStatus` at `0x1400fb029`
- `ntoskrnl!ExRaiseStatus` at `0x1400fb029`

## pseudocode

```c
__int64 __fastcall TxfFsctlCreateMiniversion(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 v7; // r14
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 TxfVscb; // r13
  char v11; // bl
  _QWORD *v12; // r15
  __int64 v13; // r12
  int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // r9
  __int64 v19; // rdi
  __int64 v20; // r8
  unsigned int j; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  BOOLEAN k; // dl
  __int64 v27; // rcx
  _QWORD *v28; // r14
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 i; // rcx
  int v35; // [rsp+20h] [rbp-98h]
  char v36; // [rsp+50h] [rbp-68h]
  char v37; // [rsp+51h] [rbp-67h]
  char v38; // [rsp+52h] [rbp-66h]
  char v39; // [rsp+53h] [rbp-65h]
  _QWORD v40[2]; // [rsp+60h] [rbp-58h] BYREF
  _QWORD *v41; // [rsp+70h] [rbp-48h]
  __int64 v42; // [rsp+78h] [rbp-40h]
  __int64 v43; // [rsp+80h] [rbp-38h]

  v40[0] = 0;
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
        NtfsStatusTraceAndDebugInternal(0, 3221225485LL, v9);
        return (unsigned int)v14;
      }
      return (unsigned int)-1073741811;
    }
    TxfVscb = 0;
    v39 = 0;
    v37 = 0;
    v38 = 0;
    v41 = 0;
    v11 = 0;
    v36 = 0;
    v12 = *(_QWORD **)(a2 + 24);
    v40[1] = v12;
    v13 = v12[23];
    v43 = v13;
    if ( !*(_QWORD *)(v13 + 328) )
    {
      if ( NtfsStatusDebugFlags )
      {
        v9 = 2692756;
        goto LABEL_13;
      }
      return (unsigned int)-1073741811;
    }
    v14 = TxfReferenceTransaction(0, *(_QWORD *)(v13 + 320), 0, *(_QWORD *)(v8 + 56), 1, 0, 0, 0, (__int64)v40);
    if ( v14 < 0 )
    {
LABEL_67:
      if ( v37 )
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v13 + 328) + 136LL));
      if ( v38 )
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
      if ( v39 )
      {
        LOBYTE(v15) = 1;
        TxfDereferenceTransaction(v40, v15);
      }
      return (unsigned int)v14;
    }
    v39 = 1;
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v40[0] + 24LL) + 80LL), 1u);
    v17 = *(_QWORD *)(v40[0] + 40LL);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v40[0] + 24LL) + 80LL));
    v19 = v12[23];
    v20 = 0;
    if ( *(_QWORD *)(v19 + 112) )
    {
      LOBYTE(v20) = 1;
      if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v12[23], v20, v18) )
      {
        for ( j = 0; j < 2; ++j )
        {
          v22 = *(_QWORD *)(a1 + 8LL * j + 48);
          if ( !v22 || v22 == v19 )
          {
            *(_QWORD *)(a1 + 8LL * j + 48) = v19;
            break;
          }
        }
      }
      v36 = 1;
    }
    LOBYTE(v35) = 0;
    v14 = NtfsFlushUserStream(a1, v12, 0, 0, v35);
    v15 = *(unsigned int *)(*(_QWORD *)(a1 + 144) + 24LL);
    if ( (_DWORD)v15 == -1073741432 || (_DWORD)v15 == -1073741608 )
    {
      if ( NtfsStatusDebugFlags
        && (((_DWORD)v15 - 294) & 0xFFFFFFFA) != 0
        && (_DWORD)v15 != -1073741608
        && (unsigned int)(v15 + 2147483643) > 1 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v15, 2692827);
      }
      ExRaiseStatus(*(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL));
    }
    if ( v14 >= 0 )
    {
      NtfsAcquireExclusiveScbEx(a1, v12, 0);
      v38 = 1;
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v13 + 328) + 136LL), 1u);
      v15 = 1;
      v37 = 1;
      v24 = *(_QWORD *)(*(_QWORD *)(v13 + 328) + 24LL);
      if ( v24
        && (v16 = *(_QWORD *)(v7 + 80), *(_QWORD *)(v16 + 56) == *(_QWORD *)(v24 + 232))
        && !*(_DWORD *)(v16 + 36) )
      {
        v16 = *(_QWORD *)(v12[66] + 56LL);
        if ( !v16 || (*(_DWORD *)(v16 + 8) & 1) != 0 )
        {
          v14 = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_66;
          v23 = 2692881;
        }
        else
        {
          if ( *(_WORD *)(v16 + 304) < 0x3E8u )
          {
            v25 = TxfCurrentWritableVersion(v12[66], 1, 0);
            ExAcquireFastMutex(*(PFAST_MUTEX *)(v25 + 256));
            for ( k = 1; RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)(v25 + 152), k); k = 0 )
              ;
            ExReleaseFastMutex(*(PFAST_MUTEX *)(v25 + 256));
            if ( !*(_QWORD *)(v25 + 120) && *(_QWORD *)(v25 + 48) == v25 + 48 && (*(_DWORD *)(v25 + 8) & 0x10000) != 0 )
            {
              v27 = *(_QWORD *)(v25 + 264);
              if ( *(_QWORD *)(v27 + 16) == v12[5] && *(_QWORD *)(v27 + 8) == v12[4] && *(_WORD *)(v25 + 304) )
              {
                v14 = 0;
                TxfVscb = v25;
              }
            }
            if ( !TxfVscb )
            {
              v42 = TxfSearchAddTxfFcbCleanupList(a1, *(_QWORD *)(v13 + 328), 1, 0, 0);
              v28 = ExAllocateFromLookasideListEx(&TxfFcbInfoLookasideList);
              v41 = v28;
              memset(v28, 0, 0x50u);
              *((_OWORD *)v28 + 1) = *(_OWORD *)(v13 + 128);
              *((_OWORD *)v28 + 2) = *(_OWORD *)(v13 + 144);
              *((_OWORD *)v28 + 3) = *(_OWORD *)(v13 + 160);
              v28[8] = *(_QWORD *)(v13 + 176);
              *((_DWORD *)v28 + 18) = *(_DWORD *)(v13 + 280);
              *((_WORD *)v28 + 39) |= 8u;
              v30 = *(_QWORD *)(v13 + 328) + 88LL;
              v31 = *(_QWORD *)v30;
              if ( *(_QWORD *)(*(_QWORD *)v30 + 8LL) != v30 )
                __fastfail(3u);
              *v28 = v31;
              v28[1] = v30;
              *(_QWORD *)(v31 + 8) = v28;
              *(_QWORD *)v30 = v28;
              *(_DWORD *)(*(_QWORD *)(v13 + 328) + 4LL) |= 8u;
              LOBYTE(v29) = 1;
              TxfVscb = TxfCreateTxfVscb(a1, v12, 1, v29);
              v32 = v42;
              *(_QWORD *)(v42 + 24) = TxfVscb;
              *(_DWORD *)(v32 + 16) |= 0x400u;
              _InterlockedOr((volatile signed __int32 *)(TxfVscb + 8), 0x8002u);
              _InterlockedAdd((volatile signed __int32 *)(TxfVscb + 4), 1u);
              v33 = *(_QWORD *)(TxfVscb + 32);
              *(_WORD *)(TxfVscb + 304) = *(_WORD *)(v33 + 304) + 1;
              _InterlockedOr((volatile signed __int32 *)(TxfVscb + 8), *(_DWORD *)(v33 + 8) & 0x100);
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
            v11 = v36;
            goto LABEL_67;
          }
          v23 = 2692890;
        }
      }
      else
      {
        v14 = -1073741811;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_66;
        v23 = 2692870;
      }
    }
    else
    {
      if ( v14 != -1073741740 )
        goto LABEL_66;
      v14 = -1073741670;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_66;
      v23 = 2692842;
    }
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v14, v23);
    goto LABEL_66;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225634LL, 2692734);
  return 3221225634LL;
}

```

## disassembly

```asm
0x1400faa5c  mov     rax, rsp
0x1400faa5f  mov     [rax+10h], rbx
0x1400faa63  mov     [rax+18h], rsi
0x1400faa67  mov     [rax+20h], r9
0x1400faa6b  mov     [rax+8], rcx
0x1400faa6f  push    rdi
0x1400faa70  push    r12
0x1400faa72  push    r13
0x1400faa74  push    r14
0x1400faa76  push    r15
0x1400faa78  sub     rsp, 90h
0x1400faa7f  mov     rsi, rcx
0x1400faa82  xor     ecx, ecx
0x1400faa84  mov     [rax-58h], rcx
0x1400faa88  test    r9, r9
0x1400faa8b  jz      loc_1400FB0D5
0x1400faa91  cmp     r8d, 0Ch
0x1400faa95  jb      loc_1400FB0D5
0x1400faa9b  mov     rax, [rsi+68h]
0x1400faa9f  test    dword ptr [rax+4], 2000000h
0x1400faaa6  jz      short loc_1400FAACC
0x1400faaa8  mov     al, cs:NtfsStatusDebugFlags
0x1400faaae  test    al, al
0x1400faab0  jz      short loc_1400FAAC2
0x1400faab2  mov     edx, 0C00000A2h
0x1400faab7  mov     r8d, 29167Eh
0x1400faabd  call    NtfsStatusTraceAndDebugInternal
0x1400faac2  mov     eax, 0C00000A2h
0x1400faac7  jmp     loc_1400FB0F1
0x1400faacc  mov     r14, [rdx+20h]
0x1400faad0  mov     r9, [r14+50h]
0x1400faad4  test    r9, r9
0x1400faad7  jnz     short loc_1400FAAEF
0x1400faad9  mov     al, cs:NtfsStatusDebugFlags
0x1400faadf  test    al, al
0x1400faae1  jz      loc_1400FB0EA
0x1400faae7  mov     r8d, 29168Fh
0x1400faaed  jmp     short loc_1400FAB3F
0x1400faaef  mov     r13, rcx
0x1400faaf2  mov     [rsp+0B8h+var_65], cl
0x1400faaf6  mov     [rsp+0B8h+var_67], cl
0x1400faafa  mov     [rsp+0B8h+var_66], cl
0x1400faafe  mov     [rsp+0B8h+var_48], rcx
0x1400fab03  mov     bl, cl
0x1400fab05  mov     [rsp+0B8h+var_68], cl
0x1400fab09  mov     r15, [rdx+18h]
0x1400fab0d  mov     [rsp+0B8h+var_50], r15
0x1400fab12  mov     r12, [r15+0B8h]
0x1400fab19  mov     [rsp+0B8h+var_38], r12
0x1400fab21  cmp     [r12+148h], rcx
0x1400fab29  jnz     short loc_1400FAB50
0x1400fab2b  mov     al, cs:NtfsStatusDebugFlags
0x1400fab31  test    al, al
0x1400fab33  jz      loc_1400FB0EA
0x1400fab39  mov     r8d, 291694h
0x1400fab3f  mov     edi, 0C000000Dh
0x1400fab44  mov     edx, edi
0x1400fab46  call    NtfsStatusTraceAndDebugInternal
0x1400fab4b  jmp     loc_1400FB0EF
0x1400fab50  lea     rax, [rsp+0B8h+var_58]
0x1400fab55  mov     [rsp+0B8h+var_78], rax
0x1400fab5a  mov     [rsp+0B8h+var_80], cl
0x1400fab5e  mov     [rsp+0B8h+var_88], cl
0x1400fab62  mov     [rsp+0B8h+var_90], cl
0x1400fab66  mov     [rsp+0B8h+var_98], 1
0x1400fab6b  mov     r9, [r9+38h]
0x1400fab6f  xor     r8d, r8d
0x1400fab72  mov     rdx, [r12+140h]
0x1400fab7a  xor     ecx, ecx
0x1400fab7c  call    TxfReferenceTransaction
0x1400fab81  mov     edi, eax
0x1400fab83  mov     [rsp+0B8h+var_64], eax
0x1400fab87  xor     r8d, r8d
0x1400fab8a  test    eax, eax
0x1400fab8c  js      loc_1400FB035
0x1400fab92  mov     [rsp+0B8h+var_64], r8d
0x1400fab97  lea     edx, [r8+1]; Wait
0x1400fab9b  mov     [rsp+0B8h+var_65], dl
0x1400fab9f  mov     rax, [rsp+0B8h+var_58]
0x1400faba4  mov     rcx, [rax+18h]
0x1400faba8  add     rcx, 50h ; 'P'; Resource
0x1400fabac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fabb3  nop     dword ptr [rax+rax+00h]
0x1400fabb8  mov     rax, [rsp+0B8h+var_58]
0x1400fabbd  mov     rbx, [rax+28h]
0x1400fabc1  mov     rcx, [rax+18h]
0x1400fabc5  add     rcx, 50h ; 'P'; Resource
0x1400fabc9  call    cs:__imp_ExReleaseResourceLite
0x1400fabd0  nop     dword ptr [rax+rax+00h]
0x1400fabd5  mov     rdi, [r15+0B8h]
0x1400fabdc  xor     r8d, r8d
0x1400fabdf  cmp     [rdi+70h], r8
0x1400fabe3  jz      short loc_1400FAC2A
0x1400fabe5  mov     r8b, 1
0x1400fabe8  mov     rdx, rdi
0x1400fabeb  mov     rcx, rsi
0x1400fabee  call    NtfsAcquirePagingResourceExclusive
0x1400fabf3  xor     r8d, r8d
0x1400fabf6  test    al, al
0x1400fabf8  jz      short loc_1400FAC25
0x1400fabfa  mov     [rsp+0B8h+var_60], r8d
0x1400fabff  mov     eax, r8d
0x1400fac02  mov     [rsp+0B8h+var_60], eax
0x1400fac06  cmp     eax, 2
0x1400fac09  jnb     short loc_1400FAC25
0x1400fac0b  mov     edx, eax
0x1400fac0d  mov     rcx, [rsi+rdx*8+30h]
0x1400fac12  test    rcx, rcx
0x1400fac15  jz      short loc_1400FAC20
0x1400fac17  cmp     rcx, rdi
0x1400fac1a  jz      short loc_1400FAC20
0x1400fac1c  inc     eax
0x1400fac1e  jmp     short loc_1400FAC02
0x1400fac20  mov     [rsi+rdx*8+30h], rdi
0x1400fac25  mov     [rsp+0B8h+var_68], 1
0x1400fac2a  mov     [rsp+0B8h+var_98], r8b
0x1400fac2f  xor     r9d, r9d
0x1400fac32  xor     r8d, r8d
0x1400fac35  mov     rdx, r15
0x1400fac38  mov     rcx, rsi
0x1400fac3b  call    NtfsFlushUserStream
0x1400fac40  mov     edi, eax
0x1400fac42  mov     [rsp+0B8h+var_64], eax
0x1400fac46  mov     rax, [rsi+90h]
0x1400fac4d  mov     edx, [rax+18h]
0x1400fac50  cmp     edx, 0C0000188h
0x1400fac56  jz      loc_1400FAFBE
0x1400fac5c  cmp     edx, 0C00000D8h
0x1400fac62  jz      loc_1400FAFBE
0x1400fac68  xor     r8d, r8d
0x1400fac6b  test    edi, edi
0x1400fac6d  jns     short loc_1400FACA5
0x1400fac6f  cmp     edi, 0C0000054h
0x1400fac75  jnz     loc_1400FB03D
0x1400fac7b  mov     al, cs:NtfsStatusDebugFlags
0x1400fac81  mov     edi, 0C000009Ah
0x1400fac86  test    al, al
0x1400fac88  jz      short loc_1400FAC9C
0x1400fac8a  mov     r8d, 2916EAh
0x1400fac90  mov     edx, edi
0x1400fac92  xor     ecx, ecx
0x1400fac94  call    NtfsStatusTraceAndDebugInternal
0x1400fac99  xor     r8d, r8d
0x1400fac9c  mov     [rsp+0B8h+var_64], edi
0x1400faca0  jmp     loc_1400FB03D
0x1400faca5  mov     rdx, r15
0x1400faca8  mov     rcx, rsi
0x1400facab  call    NtfsAcquireExclusiveScbEx
0x1400facb0  mov     eax, 1
0x1400facb5  mov     [rsp+0B8h+var_66], al
0x1400facb9  mov     rcx, [r12+148h]
0x1400facc1  mov     dl, al; Wait
0x1400facc3  mov     rcx, [rcx+88h]; Resource
0x1400facca  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400facd1  nop     dword ptr [rax+rax+00h]
0x1400facd6  mov     edx, 1
0x1400facdb  mov     [rsp+0B8h+var_67], dl
0x1400facdf  mov     rax, [r12+148h]
0x1400face7  mov     rax, [rax+18h]
0x1400faceb  xor     r8d, r8d
0x1400facee  test    rax, rax
0x1400facf1  jz      loc_1400FAFA0
0x1400facf7  mov     rcx, [r14+50h]
0x1400facfb  mov     rax, [rax+0E8h]
0x1400fad02  cmp     [rcx+38h], rax
0x1400fad06  jnz     loc_1400FAFA0
0x1400fad0c  cmp     [rcx+24h], r8d
0x1400fad10  jnz     loc_1400FAFA0
0x1400fad16  mov     r9, [r15+210h]
0x1400fad1d  mov     rcx, [r9+38h]
0x1400fad21  test    rcx, rcx
0x1400fad24  jz      loc_1400FAF82
0x1400fad2a  mov     eax, [rcx+8]
0x1400fad2d  test    dl, al
0x1400fad2f  jnz     loc_1400FAF82
0x1400fad35  mov     eax, 3E8h
0x1400fad3a  cmp     [rcx+130h], ax
0x1400fad41  jb      short loc_1400FAD61
0x1400fad43  mov     al, cs:NtfsStatusDebugFlags
0x1400fad49  mov     edi, 0C0190026h
0x1400fad4e  test    al, al
0x1400fad50  jz      loc_1400FAC9C
0x1400fad56  mov     r8d, 29171Ah
0x1400fad5c  jmp     loc_1400FAC90
0x1400fad61  mov     rcx, r9
0x1400fad64  call    TxfCurrentWritableVersion
0x1400fad69  mov     r14, rax
0x1400fad6c  mov     rcx, [rax+100h]; FastMutex
0x1400fad73  call    cs:__imp_ExAcquireFastMutex
0x1400fad7a  nop     dword ptr [rax+rax+00h]
0x1400fad7f  mov     dl, 1; Restart
0x1400fad81  lea     rcx, [r14+98h]; Table
0x1400fad88  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400fad8f  nop     dword ptr [rax+rax+00h]
0x1400fad94  test    rax, rax
0x1400fad97  jz      short loc_1400FAD9D
0x1400fad99  xor     edx, edx
0x1400fad9b  jmp     short loc_1400FAD81
0x1400fad9d  mov     rcx, [r14+100h]; FastMutex
0x1400fada4  call    cs:__imp_ExReleaseFastMutex
0x1400fadab  nop     dword ptr [rax+rax+00h]
0x1400fadb0  xor     r8d, r8d
0x1400fadb3  cmp     [r14+78h], r8
0x1400fadb7  jnz     short loc_1400FADFC
0x1400fadb9  lea     rax, [r14+30h]
0x1400fadbd  cmp     [rax], rax
0x1400fadc0  jnz     short loc_1400FADFC
0x1400fadc2  test    dword ptr [r14+8], 10000h
0x1400fadca  jz      short loc_1400FADFC
0x1400fadcc  mov     rcx, [r14+108h]
0x1400fadd3  mov     rax, [r15+28h]
0x1400fadd7  cmp     [rcx+10h], rax
0x1400faddb  jnz     short loc_1400FADFC
0x1400faddd  mov     rax, [r15+20h]
0x1400fade1  cmp     [rcx+8], rax
0x1400fade5  jnz     short loc_1400FADFC
0x1400fade7  cmp     [r14+130h], r8w
0x1400fadef  jz      short loc_1400FADFC
0x1400fadf1  mov     edi, r8d
0x1400fadf4  mov     [rsp+0B8h+var_64], r8d
0x1400fadf9  mov     r13, r14
0x1400fadfc  test    r13, r13
0x1400fadff  jnz     loc_1400FAF42
0x1400fae05  mov     [rsp+0B8h+var_98], r8b
0x1400fae0a  xor     r9d, r9d
0x1400fae0d  lea     r8d, [r13+1]
0x1400fae11  mov     rdx, [r12+148h]
0x1400fae19  mov     rcx, rsi
0x1400fae1c  call    TxfSearchAddTxfFcbCleanupList
0x1400fae21  mov     [rsp+0B8h+var_40], rax
0x1400fae26  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x1400fae2d  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400fae34  nop     dword ptr [rax+rax+00h]
0x1400fae39  mov     r14, rax
0x1400fae3c  mov     [rsp+0B8h+var_48], rax
0x1400fae41  xor     edx, edx; Val
0x1400fae43  lea     r8d, [r13+50h]; Size
0x1400fae47  mov     rcx, rax; void *
0x1400fae4a  call    memset
0x1400fae4f  movups  xmm0, xmmword ptr [r12+80h]
0x1400fae58  movups  xmmword ptr [r14+10h], xmm0
0x1400fae5d  movups  xmm1, xmmword ptr [r12+90h]
0x1400fae66  movups  xmmword ptr [r14+20h], xmm1
0x1400fae6b  movups  xmm0, xmmword ptr [r12+0A0h]
0x1400fae74  movups  xmmword ptr [r14+30h], xmm0
0x1400fae79  movsd   xmm1, qword ptr [r12+0B0h]
0x1400fae83  movsd   qword ptr [r14+40h], xmm1
0x1400fae89  mov     eax, [r12+118h]
0x1400fae91  mov     [r14+48h], eax
0x1400fae95  lea     edx, [r13+8]
0x1400fae99  or      [r14+4Eh], dx
0x1400fae9e  mov     rax, [r12+148h]
0x1400faea6  add     rax, 58h ; 'X'
0x1400faeaa  mov     rcx, [rax]
0x1400faead  cmp     [rcx+8], rax
0x1400faeb1  jz      short loc_1400FAEB8
0x1400faeb3  lea     ecx, [rdx-5]
0x1400faeb6  int     29h; Win8: RtlFailFast(ecx)
0x1400faeb8  mov     [r14], rcx
0x1400faebb  mov     [r14+8], rax
0x1400faebf  mov     [rcx+8], r14
0x1400faec3  mov     [rax], r14
0x1400faec6  mov     rax, [r12+148h]
0x1400faece  or      [rax+4], edx
0x1400faed1  mov     r14d, 1
0x1400faed7  mov     r9b, r14b
0x1400faeda  mov     r8d, r14d
0x1400faedd  mov     rdx, r15
0x1400faee0  mov     rcx, rsi
0x1400faee3  call    TxfCreateTxfVscb
0x1400faee8  mov     r13, rax
0x1400faeeb  mov     rax, [rsp+0B8h+var_40]
0x1400faef0  mov     [rax+18h], r13
0x1400faef4  mov     r8d, 400h
0x1400faefa  or      [rax+10h], r8d
0x1400faefe  lock or dword ptr [r13+8], 8002h
0x1400faf07  lock add [r13+4], r14d
0x1400faf0c  mov     rdx, [r13+20h]
0x1400faf10  movzx   ecx, word ptr [rdx+130h]
0x1400faf17  add     cx, r14w
0x1400faf1b  mov     [r13+130h], cx
0x1400faf23  mov     ecx, [rdx+8]
0x1400faf26  and     ecx, 100h
0x1400faf2c  lock or [r13+8], ecx
0x1400faf31  lock or [r13+8], r8d
0x1400faf36  mov     [r13+118h], rbx
0x1400faf3d  xor     r8d, r8d
0x1400faf40  jmp     short loc_1400FAF48
0x1400faf42  mov     r14d, 1
0x1400faf48  mov     rdx, [rsp+0B8h+arg_18]
0x1400faf50  mov     r9d, 0Ch
0x1400faf56  mov     dword ptr [rdx], 0C0001h
0x1400faf5c  movzx   eax, word ptr [r13+130h]
0x1400faf64  mov     [rdx+8], ax
0x1400faf68  mov     rax, [r13+10h]
0x1400faf6c  mov     ecx, [rax+28h]
0x1400faf6f  mov     [rdx+4], ecx
0x1400faf72  mov     rax, [rsp+0B8h+arg_20]
0x1400faf7a  mov     [rax], r9d
0x1400faf7d  jmp     loc_1400FB043
  ... truncated ...
```
