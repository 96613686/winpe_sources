# FTCache::Retrieve(_UNICODE_STRING *,_LSA_FOREST_TRUST_INFORMATION2 * *)

- ea: `0x18002aa14`
- end: `0x18002ae56`
- name: `?Retrieve@FTCache@@QEAAJPEAU_UNICODE_STRING@@PEAPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z`
- size: `1090`
- prototype: `int(FTCache *__hidden this, struct _UNICODE_STRING *, struct _LSA_FOREST_TRUST_INFORMATION2 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180027f28`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x180026940`
- `0x18002a43c`
- `0x18002a5ac`
- `0x18002a73c`
- `0x18002aa14`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aaf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ab3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aca5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ace4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aaf8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ab3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aca5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ace4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ade8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ade8`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002aaae`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002aaae`

## pseudocode

```c
__int64 __fastcall FTCache::Retrieve(
        FTCache *this,
        struct _UNICODE_STRING *a2,
        struct _LSA_FOREST_TRUST_INFORMATION2 **a3)
{
  FTCache *v5; // rbp
  unsigned int *v6; // r14
  unsigned int v7; // ebx
  _BYTE *v8; // rax
  _BYTE *v9; // rbp
  unsigned int *v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  HLOCAL v14; // rax
  FTCache *v15; // rcx
  __int64 *i; // r15
  struct _LSA_FOREST_TRUST_RECORD2 *v17; // rdx
  struct FTCache::DOMAIN_INFO_ENTRY *v18; // r15
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  struct _LSA_FOREST_TRUST_RECORD2 *v21; // rdx
  struct FTCache::SCANNER_INFO_ENTRY *v22; // r15
  struct _LSA_FOREST_TRUST_RECORD2 *v23; // rdx
  __int64 *v24; // r12
  __int64 *v25; // r15
  _QWORD *v26; // rax
  _QWORD *v27; // rbp
  HLOCAL v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx

  if ( !a2 || !a3 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    return 3221225485LL;
  }
  v5 = g_FTCache;
  v6 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, a2);
  *a3 = 0;
  if ( !*((_BYTE *)v5 + 2) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v7 = -1073741595;
    goto LABEL_72;
  }
  v8 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v5 + 8), a2);
  v9 = v8;
  if ( !v8 )
  {
LABEL_10:
    v7 = -1073741275;
    goto LABEL_72;
  }
  if ( v8[92] )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_10;
  }
  v10 = (unsigned int *)LocalAlloc(0x40u, 0x10u);
  v6 = v10;
  if ( !v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 147;
      goto LABEL_17;
    }
    goto LABEL_18;
  }
  *v10 = 0;
  v13 = *((_DWORD *)v9 + 22);
  v14 = LocalAlloc(0x40u, 8LL * v13);
  *((_QWORD *)v6 + 1) = v14;
  if ( !v14 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 148;
      goto LABEL_17;
    }
    goto LABEL_18;
  }
  for ( i = (__int64 *)*((_QWORD *)v9 + 3); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(v9 + 24) )
    {
      v18 = (struct FTCache::DOMAIN_INFO_ENTRY *)*((_QWORD *)v9 + 5);
      while ( 1 )
      {
        if ( v18 == (struct FTCache::DOMAIN_INFO_ENTRY *)(v9 + 40) )
        {
          v22 = (struct FTCache::SCANNER_INFO_ENTRY *)*((_QWORD *)v9 + 7);
          while ( v22 != (struct FTCache::SCANNER_INFO_ENTRY *)(v9 + 56) )
          {
            if ( !v13 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_71;
              v20 = 153;
              goto LABEL_70;
            }
            v23 = FTCache::RecordFromScannerInfoEntry(v15, v22);
            if ( !v23 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_18;
              v12 = 154;
              goto LABEL_17;
            }
            v15 = (FTCache *)*v6;
            *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * (_QWORD)v15) = v23;
            ++*v6;
            v22 = *(struct FTCache::SCANNER_INFO_ENTRY **)v22;
            --v13;
          }
          v24 = (__int64 *)(v9 + 72);
          v25 = (__int64 *)*((_QWORD *)v9 + 9);
          if ( v25 == (__int64 *)(v9 + 72) )
          {
LABEL_73:
            v7 = 0;
            *a3 = (struct _LSA_FOREST_TRUST_INFORMATION2 *)v6;
            goto LABEL_74;
          }
          while ( v13 )
          {
            v26 = LocalAlloc(0x40u, 0x38u);
            v27 = v26;
            if ( !v26 )
            {
              v29 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v30 = 218;
LABEL_65:
                WPP_SF_(v29[2], v30, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
              }
LABEL_66:
              LocalFree(v27);
              v11 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_18;
              v12 = 156;
              goto LABEL_17;
            }
            v26[1] = v25[2];
            *(_DWORD *)v26 = *((_DWORD *)v25 + 12);
            *((_DWORD *)v26 + 1) = 3;
            *((_DWORD *)v26 + 4) = *((_DWORD *)v25 + 8);
            if ( *((_DWORD *)v25 + 8) )
            {
              v28 = LocalAlloc(0x40u, *((unsigned int *)v25 + 8));
              v27[3] = v28;
              if ( !v28 )
              {
                v29 = WPP_GLOBAL_Control;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v30 = 219;
                  goto LABEL_65;
                }
                goto LABEL_66;
              }
              memcpy_0(v28, (const void *)v25[5], *((unsigned int *)v25 + 8));
            }
            else
            {
              v26[3] = 0;
            }
            *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * (*v6)++) = v27;
            v25 = (__int64 *)*v25;
            if ( v25 == v24 )
              goto LABEL_73;
            --v13;
          }
          v19 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_71;
          v20 = 155;
          goto LABEL_70;
        }
        if ( !v13 )
          break;
        v21 = FTCache::RecordFromDomainInfoEntry(v15, v18);
        if ( !v21 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_18;
          v12 = 152;
          goto LABEL_17;
        }
        v15 = (FTCache *)*v6;
        *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * (_QWORD)v15) = v21;
        ++*v6;
        v18 = *(struct FTCache::DOMAIN_INFO_ENTRY **)v18;
        --v13;
      }
      v19 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_71;
      v20 = 151;
      goto LABEL_70;
    }
    if ( *((_BYTE *)i + 40) || !i[7] )
      break;
LABEL_28:
    ;
  }
  if ( !v13 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_71:
      v7 = -2147483643;
      goto LABEL_72;
    }
    v20 = 149;
LABEL_70:
    WPP_SF_(v19[2], v20, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_71;
  }
  v17 = FTCache::RecordFromTopLevelNameEntry(v15, (struct FTCache::TLN_ENTRY *)i);
  if ( v17 )
  {
    v15 = (FTCache *)*v6;
    *(_QWORD *)(*((_QWORD *)v6 + 1) + 8LL * (_QWORD)v15) = v17;
    ++*v6;
    --v13;
    goto LABEL_28;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    goto LABEL_18;
  v12 = 150;
LABEL_17:
  WPP_SF_(v11[2], v12, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
LABEL_18:
  v7 = -1073741670;
LABEL_72:
  LsaDbpFreeForestTrustInfo2((struct _LSA_FOREST_TRUST_INFORMATION2 *)v6);
  LocalFree(v6);
LABEL_74:
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18002aa14  push    rbx
0x18002aa16  push    rbp
0x18002aa17  push    rsi
0x18002aa18  push    rdi
0x18002aa19  push    r12
0x18002aa1b  push    r13
0x18002aa1d  push    r14
0x18002aa1f  push    r15
0x18002aa21  sub     rsp, 28h
0x18002aa25  xor     r15d, r15d
0x18002aa28  mov     r13, r8
0x18002aa2b  mov     rbx, rdx
0x18002aa2e  test    rdx, rdx
0x18002aa31  jz      loc_18002AE1B
0x18002aa37  test    r8, r8
0x18002aa3a  jz      loc_18002AE1B
0x18002aa40  mov     rbp, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x18002aa47  mov     r14d, r15d
0x18002aa4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa51  lea     rsi, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002aa58  mov     dil, 8
0x18002aa5b  test    [rcx+1Ch], dil
0x18002aa5f  jz      short loc_18002AA75
0x18002aa61  mov     rcx, [rcx+10h]
0x18002aa65  mov     edx, 90h
0x18002aa6a  mov     r9, rbx
0x18002aa6d  mov     r8, rsi
0x18002aa70  call    WPP_SF_Z
0x18002aa75  mov     [r13+0], r15
0x18002aa79  cmp     [rbp+2], r15b
0x18002aa7d  jnz     short loc_18002AAA7
0x18002aa7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa86  test    [rcx+1Ch], dil
0x18002aa8a  jz      short loc_18002AA9D
0x18002aa8c  mov     rcx, [rcx+10h]
0x18002aa90  mov     edx, 91h
0x18002aa95  mov     r8, rsi
0x18002aa98  call    WPP_SF_
0x18002aa9d  mov     ebx, 0C00000E5h
0x18002aaa2  jmp     loc_18002ADDD
0x18002aaa7  lea     rcx, [rbp+8]; Table
0x18002aaab  mov     rdx, rbx; Buffer
0x18002aaae  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18002aab4  mov     rbp, rax
0x18002aab7  test    rax, rax
0x18002aaba  jnz     short loc_18002AAC6
0x18002aabc  mov     ebx, 0C0000225h
0x18002aac1  jmp     loc_18002ADDD
0x18002aac6  cmp     [rax+5Ch], r15b
0x18002aaca  jz      short loc_18002AAEC
0x18002aacc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aad3  test    [rcx+1Ch], dil
0x18002aad7  jz      short loc_18002AABC
0x18002aad9  mov     rcx, [rcx+10h]
0x18002aadd  mov     edx, 92h
0x18002aae2  mov     r8, rsi
0x18002aae5  call    WPP_SF_
0x18002aaea  jmp     short loc_18002AABC
0x18002aaec  mov     edx, 10h; uBytes
0x18002aaf1  lea     r12d, [rdx+30h]
0x18002aaf5  mov     ecx, r12d; uFlags
0x18002aaf8  call    cs:__imp_LocalAlloc
0x18002aafe  mov     r14, rax
0x18002ab01  test    rax, rax
0x18002ab04  jnz     short loc_18002AB2E
0x18002ab06  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab0d  test    [rcx+1Ch], dil
0x18002ab11  jz      short loc_18002AB24
0x18002ab13  lea     edx, [r12+53h]
0x18002ab18  mov     rcx, [rcx+10h]
0x18002ab1c  mov     r8, rsi
0x18002ab1f  call    WPP_SF_
0x18002ab24  mov     ebx, 0C000009Ah
0x18002ab29  jmp     loc_18002ADDD
0x18002ab2e  mov     [rax], r15d
0x18002ab31  mov     ecx, r12d; uFlags
0x18002ab34  mov     ebx, [rbp+58h]
0x18002ab37  mov     edx, ebx
0x18002ab39  shl     rdx, 3; uBytes
0x18002ab3d  call    cs:__imp_LocalAlloc
0x18002ab43  mov     [r14+8], rax
0x18002ab47  test    rax, rax
0x18002ab4a  jnz     short loc_18002AB60
0x18002ab4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab53  test    [rcx+1Ch], dil
0x18002ab57  jz      short loc_18002AB24
0x18002ab59  mov     edx, 94h
0x18002ab5e  jmp     short loc_18002AB18
0x18002ab60  lea     r12, [rbp+18h]
0x18002ab64  mov     r15, [r12]
0x18002ab68  jmp     short loc_18002AB9F
0x18002ab6a  cmp     byte ptr [r15+28h], 0
0x18002ab6f  jnz     short loc_18002AB78
0x18002ab71  cmp     qword ptr [r15+38h], 0
0x18002ab76  jnz     short loc_18002AB9C
0x18002ab78  test    ebx, ebx
0x18002ab7a  jz      short loc_18002ABC9
0x18002ab7c  mov     rdx, r15; struct FTCache::TLN_ENTRY *
0x18002ab7f  call    ?RecordFromTopLevelNameEntry@FTCache@@AEAAPEAU_LSA_FOREST_TRUST_RECORD2@@PEAUTLN_ENTRY@1@@Z; FTCache::RecordFromTopLevelNameEntry(FTCache::TLN_ENTRY *)
0x18002ab84  mov     rdx, rax
0x18002ab87  test    rax, rax
0x18002ab8a  jz      short loc_18002ABAE
0x18002ab8c  mov     ecx, [r14]; this
0x18002ab8f  mov     rax, [r14+8]
0x18002ab93  mov     [rax+rcx*8], rdx
0x18002ab97  inc     dword ptr [r14]
0x18002ab9a  dec     ebx
0x18002ab9c  mov     r15, [r15]
0x18002ab9f  cmp     r15, r12
0x18002aba2  jnz     short loc_18002AB6A
0x18002aba4  lea     r12, [rbp+28h]
0x18002aba8  mov     r15, [r12]
0x18002abac  jmp     short loc_18002AC0B
0x18002abae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abb5  test    [rcx+1Ch], dil
0x18002abb9  jz      loc_18002AB24
0x18002abbf  mov     edx, 96h
0x18002abc4  jmp     loc_18002AB18
0x18002abc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abd0  test    [rcx+1Ch], dil
0x18002abd4  jz      loc_18002ADD8
0x18002abda  mov     edx, 95h
0x18002abdf  jmp     loc_18002ADCC
0x18002abe4  test    ebx, ebx
0x18002abe6  jz      short loc_18002AC35
0x18002abe8  mov     rdx, r15; struct FTCache::DOMAIN_INFO_ENTRY *
0x18002abeb  call    ?RecordFromDomainInfoEntry@FTCache@@AEAAPEAU_LSA_FOREST_TRUST_RECORD2@@PEAUDOMAIN_INFO_ENTRY@1@@Z; FTCache::RecordFromDomainInfoEntry(FTCache::DOMAIN_INFO_ENTRY *)
0x18002abf0  mov     rdx, rax
0x18002abf3  test    rax, rax
0x18002abf6  jz      short loc_18002AC1A
0x18002abf8  mov     ecx, [r14]; this
0x18002abfb  mov     rax, [r14+8]
0x18002abff  mov     [rax+rcx*8], rdx
0x18002ac03  inc     dword ptr [r14]
0x18002ac06  mov     r15, [r15]
0x18002ac09  dec     ebx
0x18002ac0b  cmp     r15, r12
0x18002ac0e  jnz     short loc_18002ABE4
0x18002ac10  lea     r12, [rbp+38h]
0x18002ac14  mov     r15, [r12]
0x18002ac18  jmp     short loc_18002AC7F
0x18002ac1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac21  test    [rcx+1Ch], dil
0x18002ac25  jz      loc_18002AB24
0x18002ac2b  mov     edx, 98h
0x18002ac30  jmp     loc_18002AB18
0x18002ac35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac3c  test    [rcx+1Ch], dil
0x18002ac40  jz      loc_18002ADD8
0x18002ac46  mov     edx, 97h
0x18002ac4b  jmp     loc_18002ADCC
0x18002ac50  test    ebx, ebx
0x18002ac52  jz      loc_18002AD20
0x18002ac58  mov     rdx, r15; struct FTCache::SCANNER_INFO_ENTRY *
0x18002ac5b  call    ?RecordFromScannerInfoEntry@FTCache@@AEAAPEAU_LSA_FOREST_TRUST_RECORD2@@PEAUSCANNER_INFO_ENTRY@1@@Z; FTCache::RecordFromScannerInfoEntry(FTCache::SCANNER_INFO_ENTRY *)
0x18002ac60  mov     rdx, rax
0x18002ac63  test    rax, rax
0x18002ac66  jz      loc_18002AD05
0x18002ac6c  mov     ecx, [r14]; this
0x18002ac6f  mov     rax, [r14+8]
0x18002ac73  mov     [rax+rcx*8], rdx
0x18002ac77  inc     dword ptr [r14]
0x18002ac7a  mov     r15, [r15]
0x18002ac7d  dec     ebx
0x18002ac7f  cmp     r15, r12
0x18002ac82  jnz     short loc_18002AC50
0x18002ac84  lea     r12, [rbp+48h]
0x18002ac88  mov     r15, [r12]
0x18002ac8c  cmp     r15, r12
0x18002ac8f  jz      loc_18002ADF0
0x18002ac95  test    ebx, ebx
0x18002ac97  jz      loc_18002ADBA
0x18002ac9d  mov     edx, 38h ; '8'; uBytes
0x18002aca2  lea     ecx, [rdx+8]; uFlags
0x18002aca5  call    cs:__imp_LocalAlloc
0x18002acab  mov     rbp, rax
0x18002acae  test    rax, rax
0x18002acb1  jz      loc_18002AD78
0x18002acb7  mov     rax, [r15+10h]
0x18002acbb  mov     [rbp+8], rax
0x18002acbf  mov     eax, [r15+30h]
0x18002acc3  mov     [rbp+0], eax
0x18002acc6  mov     dword ptr [rbp+4], 3
0x18002accd  mov     eax, [r15+20h]
0x18002acd1  mov     [rbp+10h], eax
0x18002acd4  cmp     dword ptr [r15+20h], 0
0x18002acd9  jbe     short loc_18002AD3B
0x18002acdb  mov     edx, [r15+20h]; uBytes
0x18002acdf  mov     ecx, 40h ; '@'; uFlags
0x18002ace4  call    cs:__imp_LocalAlloc
0x18002acea  mov     [rbp+18h], rax
0x18002acee  test    rax, rax
0x18002acf1  jz      short loc_18002AD64
0x18002acf3  mov     r8d, [r15+20h]; Size
0x18002acf7  mov     rcx, rax; void *
0x18002acfa  mov     rdx, [r15+28h]; Src
0x18002acfe  call    memcpy_0
0x18002ad03  jmp     short loc_18002AD43
0x18002ad05  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad0c  test    [rcx+1Ch], dil
0x18002ad10  jz      loc_18002AB24
0x18002ad16  mov     edx, 9Ah
0x18002ad1b  jmp     loc_18002AB18
0x18002ad20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad27  test    [rcx+1Ch], dil
0x18002ad2b  jz      loc_18002ADD8
0x18002ad31  mov     edx, 99h
0x18002ad36  jmp     loc_18002ADCC
0x18002ad3b  mov     qword ptr [rbp+18h], 0
0x18002ad43  mov     ecx, [r14]
0x18002ad46  mov     rax, [r14+8]
0x18002ad4a  mov     [rax+rcx*8], rbp
0x18002ad4e  inc     dword ptr [r14]
0x18002ad51  mov     r15, [r15]
0x18002ad54  cmp     r15, r12
0x18002ad57  jz      loc_18002ADF0
0x18002ad5d  dec     ebx
0x18002ad5f  jmp     loc_18002AC95
0x18002ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad6b  test    [rcx+1Ch], dil
0x18002ad6f  jz      short loc_18002AD96
0x18002ad71  mov     edx, 0DBh
0x18002ad76  jmp     short loc_18002AD8A
0x18002ad78  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad7f  test    [rcx+1Ch], dil
0x18002ad83  jz      short loc_18002AD96
0x18002ad85  mov     edx, 0DAh
0x18002ad8a  mov     rcx, [rcx+10h]
0x18002ad8e  mov     r8, rsi
0x18002ad91  call    WPP_SF_
0x18002ad96  mov     rcx, rbp; hMem
0x18002ad99  call    cs:__imp_LocalFree
0x18002ad9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ada6  test    [rcx+1Ch], dil
0x18002adaa  jz      loc_18002AB24
0x18002adb0  mov     edx, 9Ch
0x18002adb5  jmp     loc_18002AB18
0x18002adba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adc1  test    [rcx+1Ch], dil
0x18002adc5  jz      short loc_18002ADD8
0x18002adc7  mov     edx, 9Bh
0x18002adcc  mov     rcx, [rcx+10h]
0x18002add0  mov     r8, rsi
0x18002add3  call    WPP_SF_
0x18002add8  mov     ebx, 80000005h
0x18002addd  mov     rcx, r14; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x18002ade0  call    ?LsaDbpFreeForestTrustInfo2@@YAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbpFreeForestTrustInfo2(_LSA_FOREST_TRUST_INFORMATION2 *)
0x18002ade5  mov     rcx, r14; hMem
0x18002ade8  call    cs:__imp_LocalFree
0x18002adee  jmp     short loc_18002ADF6
0x18002adf0  xor     ebx, ebx
0x18002adf2  mov     [r13+0], r14
0x18002adf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adfd  test    [rcx+1Ch], dil
0x18002ae01  jz      short loc_18002AE17
0x18002ae03  mov     rcx, [rcx+10h]
0x18002ae07  mov     edx, 9Dh
0x18002ae0c  mov     r9d, ebx
0x18002ae0f  mov     r8, rsi
0x18002ae12  call    WPP_SF_d
0x18002ae17  mov     eax, ebx
0x18002ae19  jmp     short loc_18002AE45
0x18002ae1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae22  mov     dil, 8
0x18002ae25  test    [rcx+1Ch], dil
0x18002ae29  jz      short loc_18002AE40
0x18002ae2b  mov     rcx, [rcx+10h]
0x18002ae2f  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002ae36  mov     edx, 8Fh
0x18002ae3b  call    WPP_SF_
0x18002ae40  mov     eax, 0C000000Dh
0x18002ae45  add     rsp, 28h
0x18002ae49  pop     r15
0x18002ae4b  pop     r14
0x18002ae4d  pop     r13
0x18002ae4f  pop     r12
0x18002ae51  pop     rdi
0x18002ae52  pop     rsi
0x18002ae53  pop     rbp
0x18002ae54  pop     rbx
0x18002ae55  retn
```
