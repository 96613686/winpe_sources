# FTCache::RebuildCachesIfNecessary(int,int)

- ea: `0x18002a15c`
- end: `0x18002a319`
- name: `?RebuildCachesIfNecessary@FTCache@@AEAAJHH@Z`
- size: `445`
- prototype: `__int64 __fastcall(FTCache *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180021728`
- `0x180021b94`
- `0x18002901c`

## callees

- `0x180009ec4`
- `0x18000fd18`
- `0x18000fd40`
- `0x180026594`
- `0x1800266b0`
- `0x180026cf0`
- `0x18002a15c`

## import_xrefs

- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x18002a19f`
- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x18002a268`
- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x18002a19f`
- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x18002a268`
- `LSASRV!LsapDbExpConvertWriteLockTrustedDomainListToShared` at `0x18002a1ac`
- `LSASRV!LsapDbExpConvertWriteLockTrustedDomainListToShared` at `0x18002a2be`
- `LSASRV!LsapDbExpConvertWriteLockTrustedDomainListToShared` at `0x18002a1ac`
- `LSASRV!LsapDbExpConvertWriteLockTrustedDomainListToShared` at `0x18002a2be`
- `NTDSA!SamIAmIGC` at `0x18002a25a`
- `NTDSA!SamIAmIGC` at `0x18002a25a`

## pseudocode

```c
__int64 __fastcall FTCache::RebuildCachesIfNecessary(FTCache *this, int a2, int a3)
{
  int inserted; // ebx
  _QWORD *v6; // rcx
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx

  if ( !a2 || *((_BYTE *)this + 1) )
    goto LABEL_10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  LsapDbExpConvertReadLockTrustedDomainListToExclusive();
  inserted = LsaDbpForestTrustInsertLocalInfo();
  LsapDbExpConvertWriteLockTrustedDomainListToShared();
  if ( inserted < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        196,
        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (unsigned int)inserted);
    return (unsigned int)inserted;
  }
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 || *((_BYTE *)this + 2) )
    return 0;
  if ( (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(v6[2], 198, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  if ( DcInRootDomain )
  {
    LOBYTE(v6) = 1;
    v7 = LsaDbpBuildTrustedDomainCacheIfNecessary((__int64)v6, 0);
    inserted = v7;
    if ( v7 >= 0 )
      goto LABEL_27;
    v8 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_27;
    v9 = 199;
    goto LABEL_26;
  }
  if ( (unsigned __int8)SamIAmIGC() )
  {
    LsapDbExpConvertReadLockTrustedDomainListToExclusive();
    LsaDbpForestTrustCacheSetInvalid();
    v7 = LsaDbpForestTrustInsertLocalInfo();
    inserted = v7;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      {
LABEL_27:
        LsapDbExpConvertWriteLockTrustedDomainListToShared();
        if ( inserted < 0 )
          return (unsigned int)inserted;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
        return 0;
      }
      v9 = 201;
    }
    else
    {
      v7 = LsaDbpRebuildFtCacheGC();
      inserted = v7;
      if ( v7 >= 0 )
        goto LABEL_27;
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_27;
      v9 = 200;
    }
LABEL_26:
    WPP_SF_d(v8[2], v9, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v7);
    goto LABEL_27;
  }
  inserted = -1073741603;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002a15c  push    rbx
0x18002a15e  push    rsi
0x18002a15f  push    rdi
0x18002a160  push    r15
0x18002a162  sub     rsp, 28h
0x18002a166  lea     r15, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a16d  mov     esi, r8d
0x18002a170  mov     rdi, rcx
0x18002a173  test    edx, edx
0x18002a175  jz      loc_18002A1FE
0x18002a17b  cmp     byte ptr [rcx+1], 0
0x18002a17f  jnz     short loc_18002A1FE
0x18002a181  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a188  test    byte ptr [rcx+1Ch], 8
0x18002a18c  jz      short loc_18002A19F
0x18002a18e  mov     rcx, [rcx+10h]
0x18002a192  mov     edx, 0C3h
0x18002a197  mov     r8, r15
0x18002a19a  call    WPP_SF_
0x18002a19f  call    cs:__imp_LsapDbExpConvertReadLockTrustedDomainListToExclusive
0x18002a1a5  call    ?LsaDbpForestTrustInsertLocalInfo@@YAJXZ; LsaDbpForestTrustInsertLocalInfo(void)
0x18002a1aa  mov     ebx, eax
0x18002a1ac  call    cs:__imp_LsapDbExpConvertWriteLockTrustedDomainListToShared
0x18002a1b2  test    ebx, ebx
0x18002a1b4  jns     short loc_18002A1E0
0x18002a1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1bd  test    byte ptr [rcx+1Ch], 8
0x18002a1c1  jz      loc_18002A2E8
0x18002a1c7  mov     rcx, [rcx+10h]
0x18002a1cb  mov     edx, 0C4h
0x18002a1d0  mov     r9d, ebx
0x18002a1d3  mov     r8, r15
0x18002a1d6  call    WPP_SF_d
0x18002a1db  jmp     loc_18002A2E8
0x18002a1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1e7  test    byte ptr [rcx+1Ch], 8
0x18002a1eb  jz      short loc_18002A205
0x18002a1ed  mov     rcx, [rcx+10h]
0x18002a1f1  mov     edx, 0C5h
0x18002a1f6  mov     r8, r15
0x18002a1f9  call    WPP_SF_
0x18002a1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a205  test    esi, esi
0x18002a207  jz      loc_18002A2E6
0x18002a20d  cmp     byte ptr [rdi+2], 0
0x18002a211  jnz     loc_18002A2E6
0x18002a217  test    byte ptr [rcx+1Ch], 8
0x18002a21b  jz      short loc_18002A22E
0x18002a21d  mov     rcx, [rcx+10h]
0x18002a221  mov     edx, 0C6h
0x18002a226  mov     r8, r15
0x18002a229  call    WPP_SF_
0x18002a22e  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x18002a235  jz      short loc_18002A25A
0x18002a237  xor     edx, edx; unsigned __int8
0x18002a239  mov     cl, 1; unsigned __int8
0x18002a23b  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x18002a240  mov     ebx, eax
0x18002a242  test    eax, eax
0x18002a244  jns     short loc_18002A2BE
0x18002a246  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a24d  test    byte ptr [rcx+1Ch], 8
0x18002a251  jz      short loc_18002A2BE
0x18002a253  mov     edx, 0C7h
0x18002a258  jmp     short loc_18002A2AF
0x18002a25a  call    cs:__imp_SamIAmIGC
0x18002a260  test    al, al
0x18002a262  jz      loc_18002A2F4
0x18002a268  call    cs:__imp_LsapDbExpConvertReadLockTrustedDomainListToExclusive
0x18002a26e  call    ?LsaDbpForestTrustCacheSetInvalid@@YAXXZ; LsaDbpForestTrustCacheSetInvalid(void)
0x18002a273  call    ?LsaDbpForestTrustInsertLocalInfo@@YAJXZ; LsaDbpForestTrustInsertLocalInfo(void)
0x18002a278  mov     ebx, eax
0x18002a27a  test    eax, eax
0x18002a27c  js      short loc_18002A29D
0x18002a27e  call    ?LsaDbpRebuildFtCacheGC@@YAJXZ; LsaDbpRebuildFtCacheGC(void)
0x18002a283  mov     ebx, eax
0x18002a285  test    eax, eax
0x18002a287  jns     short loc_18002A2BE
0x18002a289  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a290  test    byte ptr [rcx+1Ch], 8
0x18002a294  jz      short loc_18002A2BE
0x18002a296  mov     edx, 0C8h
0x18002a29b  jmp     short loc_18002A2AF
0x18002a29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2a4  test    byte ptr [rcx+1Ch], 8
0x18002a2a8  jz      short loc_18002A2BE
0x18002a2aa  mov     edx, 0C9h
0x18002a2af  mov     rcx, [rcx+10h]
0x18002a2b3  mov     r9d, eax
0x18002a2b6  mov     r8, r15
0x18002a2b9  call    WPP_SF_d
0x18002a2be  call    cs:__imp_LsapDbExpConvertWriteLockTrustedDomainListToShared
0x18002a2c4  test    ebx, ebx
0x18002a2c6  js      short loc_18002A2E8
0x18002a2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2cf  test    byte ptr [rcx+1Ch], 8
0x18002a2d3  jz      short loc_18002A2E6
0x18002a2d5  mov     rcx, [rcx+10h]
0x18002a2d9  mov     edx, 0CBh
0x18002a2de  mov     r8, r15
0x18002a2e1  call    WPP_SF_
0x18002a2e6  xor     ebx, ebx
0x18002a2e8  mov     eax, ebx
0x18002a2ea  add     rsp, 28h
0x18002a2ee  pop     r15
0x18002a2f0  pop     rdi
0x18002a2f1  pop     rsi
0x18002a2f2  pop     rbx
0x18002a2f3  retn
0x18002a2f4  mov     ebx, 0C00000DDh
0x18002a2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a300  test    byte ptr [rcx+1Ch], 8
0x18002a304  jz      short loc_18002A2E8
0x18002a306  mov     rcx, [rcx+10h]
0x18002a30a  mov     edx, 0CAh
0x18002a30f  mov     r8, r15
0x18002a312  call    WPP_SF_
0x18002a317  jmp     short loc_18002A2E8
```
