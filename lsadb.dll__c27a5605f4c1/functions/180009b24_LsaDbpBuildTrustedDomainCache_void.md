# LsaDbpBuildTrustedDomainCache(void)

- ea: `0x180009b24`
- end: `0x180009ebe`
- name: `?LsaDbpBuildTrustedDomainCache@@YAJXZ`
- size: `922`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180009ec4`

## callees

- `0x18000988c`
- `0x180009b24`
- `0x18000bae8`
- `0x18000c400`
- `0x18000fd18`
- `0x18000fd40`
- `0x180018938`
- `0x18001f3b4`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x1800266b0`
- `0x180026cf0`
- `0x180027338`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d38`
- `LSASRV!LsapDbExpMakeCacheValid` at `0x180009e0a`
- `LSASRV!LsapDbExpMakeCacheValid` at `0x180009e0a`
- `LSASRV!_fgs__LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2` at `0x180009d27`
- `LSASRV!_fgs__LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2` at `0x180009d27`
- `LSASRV!_fgs__LSAPR_TRUSTED_DOMAIN_FULL_INFORMATION2` at `0x180009d03`
- `LSASRV!_fgs__LSAPR_TRUSTED_DOMAIN_FULL_INFORMATION2` at `0x180009d03`
- `LSASRV!LsapDbSlowEnumerateTrustedDomains` at `0x180009c8a`
- `LSASRV!LsapDbSlowEnumerateTrustedDomains` at `0x180009c8a`
- `LSASRV!LsapDbExpMakeCacheBuilding` at `0x180009bcd`
- `LSASRV!LsapDbExpMakeCacheBuilding` at `0x180009bcd`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180009eae`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180009eae`
- `NTDSA!SamIAmIGC` at `0x180009e6f`
- `NTDSA!SamIAmIGC` at `0x180009e6f`

## pseudocode

```c
__int64 LsaDbpBuildTrustedDomainCache(void)
{
  char v0; // al
  char v1; // r12
  char v2; // r15
  int inited; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int inserted; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  int v11; // esi
  int v12; // r14d
  int v13; // eax
  unsigned int v14; // edi
  char *v15; // rcx
  unsigned int v16; // edx
  unsigned int v17; // edi
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  __int64 v20; // r8
  HLOCAL hMem[2]; // [rsp+30h] [rbp-10h] BYREF
  char v23; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v24; // [rsp+78h] [rbp+38h] BYREF

  v0 = HIBYTE(word_18004706B);
  v1 = 0;
  v24 = 0;
  *(_OWORD *)hMem = 0;
  v2 = HIBYTE(word_18004706B);
  v23 = 0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    v0 = HIBYTE(word_18004706B);
  }
  if ( v0 )
  {
    inited = LsaDbpDsInitAllocAsNeededEx(33554434, 2, &v23);
    if ( inited < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        v5 = 40;
LABEL_58:
        WPP_SF_d(v4[2], v5, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, (unsigned int)inited);
        return (unsigned int)inited;
      }
      return (unsigned int)inited;
    }
    v1 = v23;
  }
  LsapDbExpMakeCacheBuilding(2);
  LsaDbpPurgeTrustedDomainCache();
  if ( byte_18004706E )
  {
    inserted = LsaDbpRegisterForUpnListNotifications();
    inited = inserted;
    if ( inserted < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        goto LABEL_64;
      v8 = 41;
      goto LABEL_12;
    }
    LsaDbpDsContinueTransaction();
  }
  inserted = LsaDbpForestTrustInsertLocalInfo();
  inited = inserted;
  if ( inserted < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_64;
    v8 = 42;
LABEL_12:
    v9 = (unsigned int)inserted;
LABEL_13:
    WPP_SF_d(v7[2], v8, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids, v9);
    goto LABEL_64;
  }
  while ( 1 )
  {
    if ( v2 )
    {
      v10 = LsaDbpDsEnumerateTrustedDomainsEx(
              &v24,
              TrustedDomainFullInformation2Internal,
              (union _LSAPR_TRUSTED_DOMAIN_INFO **)&hMem[1],
              0x6400u,
              (unsigned int *)hMem,
              0);
      v11 = 12;
    }
    else
    {
      v10 = LsapDbSlowEnumerateTrustedDomains(LsaDbpPolicyHandle, &v24, 11, hMem, 256);
      v11 = 11;
    }
    inited = v10;
    v12 = v10;
    if ( v10 < 0 )
    {
      if ( v10 != -2147483622 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
          goto LABEL_64;
        v8 = 43;
        v9 = (unsigned int)v10;
        goto LABEL_13;
      }
      inited = 0;
    }
    v13 = (int)hMem[0];
    if ( !LODWORD(hMem[0]) )
      break;
    v14 = 0;
    do
    {
      if ( inited < 0 )
        break;
      if ( v2 )
      {
        v15 = (char *)hMem[1] + 120 * v14;
        v16 = *((_DWORD *)v15 + 16);
      }
      else
      {
        v15 = (char *)hMem[1] + 64 * (unsigned __int64)v14;
        v16 = 0;
      }
      inited = LsaDbpInsertTrustedDomainList((struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)v15, v16);
      ++v14;
      v13 = (int)hMem[0];
    }
    while ( v14 < LODWORD(hMem[0]) );
    if ( v11 == 12 )
    {
      v17 = 0;
      if ( v13 )
      {
        do
          _fgs__LSAPR_TRUSTED_DOMAIN_FULL_INFORMATION2((char *)hMem[1] + 120 * v17++);
        while ( v17 < LODWORD(hMem[0]) );
      }
    }
    else
    {
      v18 = 0;
      if ( v13 )
      {
        do
          _fgs__LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2((char *)hMem[1] + 64 * (unsigned __int64)v18++);
        while ( v18 < LODWORD(hMem[0]) );
      }
    }
    LocalFree(hMem[1]);
    if ( inited < 0 )
    {
      if ( inited != -2147483622 )
        goto LABEL_64;
      inited = 0;
LABEL_46:
      v19 = WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    if ( v12 == -2147483622 )
      goto LABEL_46;
  }
  v19 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
    goto LABEL_46;
  }
LABEL_47:
  if ( DcInRootDomain )
  {
    if ( (*((_DWORD *)v19 + 7) & 0x100) != 0 )
    {
      WPP_SF_(v19[2], 45, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v19 + 28) & 8) != 0 )
      WPP_SF_(v19[2], 42, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    *((_BYTE *)g_FTCache + 2) = 1;
LABEL_53:
    LsapDbExpMakeCacheValid(2);
    goto LABEL_54;
  }
  if ( !(unsigned __int8)SamIAmIGC() )
    goto LABEL_53;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_d732922acb273e81328a1f77e1e7700c_Traceguids);
  inited = LsaDbpRebuildFtCacheGC();
  if ( inited >= 0 )
    goto LABEL_53;
LABEL_64:
  LsapDbExpMakeCacheInvalid(2);
  LsaDbpPurgeTrustedDomainCache();
LABEL_54:
  if ( HIBYTE(word_18004706B) )
  {
    LOBYTE(v20) = v1;
    LsaDbpDsDeleteAllocAsNeededEx(33554434, 2, v20);
  }
  LsaDbLogInfoTrustedDomainList();
  v4 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v5 = 47;
    goto LABEL_58;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009b24  mov     [rsp-28h+arg_10], rbx
0x180009b29  mov     [rsp-28h+arg_18], rsi
0x180009b2e  push    rbp
0x180009b2f  push    rdi
0x180009b30  push    r12
0x180009b32  push    r14
0x180009b34  push    r15
0x180009b36  mov     rbp, rsp
0x180009b39  sub     rsp, 40h
0x180009b3d  mov     al, byte ptr cs:word_18004706B+1
0x180009b43  xorps   xmm0, xmm0
0x180009b46  xor     r12b, r12b
0x180009b49  mov     [rbp+arg_8], 0
0x180009b50  movups  xmmword ptr [rbp+hMem], xmm0
0x180009b54  mov     r15b, al
0x180009b57  mov     [rbp+arg_0], r12b
0x180009b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b62  lea     rsi, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009b69  mov     edi, 100h
0x180009b6e  test    [rcx+1Ch], edi
0x180009b71  jz      short loc_180009B8A
0x180009b73  mov     rcx, [rcx+10h]
0x180009b77  mov     edx, 27h ; '''
0x180009b7c  mov     r8, rsi
0x180009b7f  call    WPP_SF_
0x180009b84  mov     al, byte ptr cs:word_18004706B+1
0x180009b8a  test    al, al
0x180009b8c  jz      short loc_180009BC8
0x180009b8e  lea     r8, [rbp+arg_0]
0x180009b92  mov     edx, 2
0x180009b97  mov     ecx, 2000002h
0x180009b9c  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x180009ba1  mov     ebx, eax
0x180009ba3  test    eax, eax
0x180009ba5  jns     short loc_180009BC4
0x180009ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bae  test    [rcx+1Ch], edi
0x180009bb1  jz      loc_180009E54
0x180009bb7  mov     edx, 28h ; '('
0x180009bbc  mov     r8, rsi
0x180009bbf  jmp     loc_180009E48
0x180009bc4  mov     r12b, [rbp+arg_0]
0x180009bc8  mov     ecx, 2
0x180009bcd  call    cs:__imp_LsapDbExpMakeCacheBuilding
0x180009bd3  call    ?LsaDbpPurgeTrustedDomainCache@@YAXXZ; LsaDbpPurgeTrustedDomainCache(void)
0x180009bd8  cmp     cs:byte_18004706E, 0
0x180009bdf  jz      short loc_180009C1A
0x180009be1  call    ?LsaDbpRegisterForUpnListNotifications@@YAJXZ; LsaDbpRegisterForUpnListNotifications(void)
0x180009be6  mov     ebx, eax
0x180009be8  test    eax, eax
0x180009bea  jns     short loc_180009C15
0x180009bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bf3  test    [rcx+1Ch], edi
0x180009bf6  jz      loc_180009EA9
0x180009bfc  mov     edx, 29h ; ')'
0x180009c01  mov     r9d, eax
0x180009c04  mov     r8, rsi
0x180009c07  mov     rcx, [rcx+10h]
0x180009c0b  call    WPP_SF_d
0x180009c10  jmp     loc_180009EA9
0x180009c15  call    ?LsaDbpDsContinueTransaction@@YAXXZ; LsaDbpDsContinueTransaction(void)
0x180009c1a  call    ?LsaDbpForestTrustInsertLocalInfo@@YAJXZ; LsaDbpForestTrustInsertLocalInfo(void)
0x180009c1f  mov     ebx, eax
0x180009c21  test    eax, eax
0x180009c23  jns     short loc_180009C3C
0x180009c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c2c  test    [rcx+1Ch], edi
0x180009c2f  jz      loc_180009EA9
0x180009c35  mov     edx, 2Ah ; '*'
0x180009c3a  jmp     short loc_180009C01
0x180009c3c  test    r15b, r15b
0x180009c3f  jz      short loc_180009C71
0x180009c41  lea     rax, [rbp+hMem]
0x180009c45  mov     [rsp+40h+var_18], 0; unsigned int
0x180009c4d  mov     r9d, 6400h; unsigned int
0x180009c53  mov     [rsp+40h+var_20], rax; unsigned int *
0x180009c58  lea     r8, [rbp+hMem+8]; union _LSAPR_TRUSTED_DOMAIN_INFO **
0x180009c5c  mov     edx, 0Ch; enum _TRUSTED_INFORMATION_CLASS
0x180009c61  lea     rcx, [rbp+arg_8]; unsigned int *
0x180009c65  call    ?LsaDbpDsEnumerateTrustedDomainsEx@@YAJPEAKW4_TRUSTED_INFORMATION_CLASS@@PEAPEAT_LSAPR_TRUSTED_DOMAIN_INFO@@K0K@Z; LsaDbpDsEnumerateTrustedDomainsEx(ulong *,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO * *,ulong,ulong *,ulong)
0x180009c6a  mov     esi, 0Ch
0x180009c6f  jmp     short loc_180009C95
0x180009c71  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x180009c78  lea     r9, [rbp+hMem]
0x180009c7c  mov     r8d, 0Bh
0x180009c82  mov     dword ptr [rsp+40h+var_20], edi
0x180009c86  lea     rdx, [rbp+arg_8]
0x180009c8a  call    cs:__imp_LsapDbSlowEnumerateTrustedDomains
0x180009c90  mov     esi, 0Bh
0x180009c95  mov     ebx, eax
0x180009c97  mov     r14d, eax
0x180009c9a  test    eax, eax
0x180009c9c  jns     short loc_180009CAB
0x180009c9e  cmp     eax, 8000001Ah
0x180009ca3  jnz     loc_180009D55
0x180009ca9  xor     ebx, ebx
0x180009cab  mov     eax, dword ptr [rbp+hMem]
0x180009cae  test    eax, eax
0x180009cb0  jz      loc_180009D89
0x180009cb6  xor     edi, edi
0x180009cb8  test    eax, eax
0x180009cba  jz      short loc_180009CEE
0x180009cbc  test    ebx, ebx
0x180009cbe  js      short loc_180009CEE
0x180009cc0  mov     ecx, edi
0x180009cc2  test    r15b, r15b
0x180009cc5  jz      short loc_180009CD4
0x180009cc7  imul    rcx, 78h ; 'x'
0x180009ccb  add     rcx, [rbp+hMem+8]
0x180009ccf  mov     edx, [rcx+40h]
0x180009cd2  jmp     short loc_180009CDE
0x180009cd4  shl     rcx, 6
0x180009cd8  add     rcx, [rbp+hMem+8]; struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *
0x180009cdc  xor     edx, edx; unsigned int
0x180009cde  call    ?LsaDbpInsertTrustedDomainList@@YAJPEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@K@Z; LsaDbpInsertTrustedDomainList(_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong)
0x180009ce3  mov     ebx, eax
0x180009ce5  inc     edi
0x180009ce7  mov     eax, dword ptr [rbp+hMem]
0x180009cea  cmp     edi, eax
0x180009cec  jb      short loc_180009CBC
0x180009cee  cmp     esi, 0Ch
0x180009cf1  jnz     short loc_180009D12
0x180009cf3  xor     edi, edi
0x180009cf5  test    eax, eax
0x180009cf7  jz      short loc_180009D34
0x180009cf9  mov     eax, edi
0x180009cfb  imul    rcx, rax, 78h ; 'x'
0x180009cff  add     rcx, [rbp+hMem+8]
0x180009d03  call    cs:__imp__fgs__LSAPR_TRUSTED_DOMAIN_FULL_INFORMATION2
0x180009d09  inc     edi
0x180009d0b  cmp     edi, dword ptr [rbp+hMem]
0x180009d0e  jb      short loc_180009CF9
0x180009d10  jmp     short loc_180009D34
0x180009d12  cmp     esi, 0Bh
0x180009d15  jnz     short loc_180009D34
0x180009d17  xor     edi, edi
0x180009d19  test    eax, eax
0x180009d1b  jz      short loc_180009D34
0x180009d1d  mov     ecx, edi
0x180009d1f  shl     rcx, 6
0x180009d23  add     rcx, [rbp+hMem+8]
0x180009d27  call    cs:__imp__fgs__LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2
0x180009d2d  inc     edi
0x180009d2f  cmp     edi, dword ptr [rbp+hMem]
0x180009d32  jb      short loc_180009D1D
0x180009d34  mov     rcx, [rbp+hMem+8]; hMem
0x180009d38  call    cs:__imp_LocalFree
0x180009d3e  mov     edi, 100h
0x180009d43  test    ebx, ebx
0x180009d45  js      short loc_180009D79
0x180009d47  cmp     r14d, 8000001Ah
0x180009d4e  jz      short loc_180009DAA
0x180009d50  jmp     loc_180009C3C
0x180009d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d5c  test    [rcx+1Ch], edi
0x180009d5f  jz      loc_180009EA9
0x180009d65  mov     edx, 2Bh ; '+'
0x180009d6a  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009d71  mov     r9d, ebx
0x180009d74  jmp     loc_180009C07
0x180009d79  cmp     ebx, 8000001Ah
0x180009d7f  jnz     loc_180009EA9
0x180009d85  xor     ebx, ebx
0x180009d87  jmp     short loc_180009DAA
0x180009d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d90  test    [rcx+1Ch], edi
0x180009d93  jz      short loc_180009DB1
0x180009d95  mov     rcx, [rcx+10h]
0x180009d99  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009da0  mov     edx, 2Ch ; ','
0x180009da5  call    WPP_SF_
0x180009daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009db1  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x180009db8  jz      loc_180009E6F
0x180009dbe  test    [rcx+1Ch], edi
0x180009dc1  jz      short loc_180009DDF
0x180009dc3  mov     rcx, [rcx+10h]
0x180009dc7  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009dce  mov     edx, 2Dh ; '-'
0x180009dd3  call    WPP_SF_
0x180009dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ddf  test    byte ptr [rcx+1Ch], 8
0x180009de3  jz      short loc_180009DFA
0x180009de5  mov     rcx, [rcx+10h]
0x180009de9  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180009df0  mov     edx, 2Ah ; '*'
0x180009df5  call    WPP_SF_
0x180009dfa  mov     rax, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x180009e01  mov     byte ptr [rax+2], 1
0x180009e05  mov     ecx, 2
0x180009e0a  call    cs:__imp_LsapDbExpMakeCacheValid
0x180009e10  cmp     byte ptr cs:word_18004706B+1, 0
0x180009e17  jz      short loc_180009E2B
0x180009e19  mov     r8b, r12b
0x180009e1c  mov     edx, 2
0x180009e21  mov     ecx, 2000002h
0x180009e26  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x180009e2b  call    ?LsaDbLogInfoTrustedDomainList@@YAXXZ; LsaDbLogInfoTrustedDomainList(void)
0x180009e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e37  test    [rcx+1Ch], edi
0x180009e3a  jz      short loc_180009E54
0x180009e3c  mov     edx, 2Fh ; '/'
0x180009e41  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009e48  mov     rcx, [rcx+10h]
0x180009e4c  mov     r9d, ebx
0x180009e4f  call    WPP_SF_d
0x180009e54  lea     r11, [rsp+40h+var_s0]
0x180009e59  mov     eax, ebx
0x180009e5b  mov     rbx, [r11+40h]
0x180009e5f  mov     rsi, [r11+48h]
0x180009e63  mov     rsp, r11
0x180009e66  pop     r15
0x180009e68  pop     r14
0x180009e6a  pop     r12
0x180009e6c  pop     rdi
0x180009e6d  pop     rbp
0x180009e6e  retn
0x180009e6f  call    cs:__imp_SamIAmIGC
0x180009e75  test    al, al
0x180009e77  jz      short loc_180009E05
0x180009e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e80  test    [rcx+1Ch], edi
0x180009e83  jz      short loc_180009E9A
0x180009e85  mov     rcx, [rcx+10h]
0x180009e89  lea     r8, WPP_d732922acb273e81328a1f77e1e7700c_Traceguids
0x180009e90  mov     edx, 2Eh ; '.'
0x180009e95  call    WPP_SF_
0x180009e9a  call    ?LsaDbpRebuildFtCacheGC@@YAJXZ; LsaDbpRebuildFtCacheGC(void)
0x180009e9f  mov     ebx, eax
0x180009ea1  test    eax, eax
0x180009ea3  jns     loc_180009E05
0x180009ea9  mov     ecx, 2
0x180009eae  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x180009eb4  call    ?LsaDbpPurgeTrustedDomainCache@@YAXXZ; LsaDbpPurgeTrustedDomainCache(void)
0x180009eb9  jmp     loc_180009E10
```
