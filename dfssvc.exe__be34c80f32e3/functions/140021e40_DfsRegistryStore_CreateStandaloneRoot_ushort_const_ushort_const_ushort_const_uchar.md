# DfsRegistryStore::CreateStandaloneRoot(ushort const *,ushort const *,ushort const *,uchar)

- ea: `0x140021e40`
- end: `0x140022592`
- name: `?CreateStandaloneRoot@DfsRegistryStore@@QEAAKPEBG00E@Z`
- size: `1874`
- prototype: `unsigned int __usercall@<eax>(DfsRegistryStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int8)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140010924`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b28`
- `0x140005b90`
- `0x140005c10`
- `0x140005f20`
- `0x14000971c`
- `0x14000abc4`
- `0x14000cbb0`
- `0x14000e228`
- `0x14000f784`
- `0x14000f808`
- `0x140021e40`
- `0x140024768`
- `0x140028098`
- `0x14002a780`
- `0x14002ccc4`
- `0x14002e1b8`
- `0x14002fbb0`
- `0x140036a00`
- `0x140038abc`
- `0x14003df3c`
- `0x14004ad44`
- `0x1400571ac`
- `0x140057cdc`
- `0x140057f64`
- `0x1400586a8`
- `0x140059044`
- `0x1400591e4`
- `0x140059e24`
- `0x140059e6c`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002248c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002248c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002212d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002246b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002212d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002246b`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::CreateStandaloneRoot(
        DfsRegistryStore *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int8 a5)
{
  DfsRegistryStore *v7; // r14
  char v8; // r13
  unsigned __int16 *v9; // r12
  HKEY v10; // rsi
  unsigned int inited; // ebx
  char IsScopedServerName; // r14
  const unsigned __int16 *v13; // rax
  unsigned __int64 v14; // r12
  DfsRootFolder *v15; // rax
  unsigned __int8 v16; // r8
  unsigned int v17; // eax
  DfsStore *v18; // rcx
  unsigned int *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int16 *v23; // rbx
  DfsStore *v24; // rcx
  DfsStore *v25; // rdi
  DfsRegistryStore *v26; // rcx
  DfsRegistryStore *v27; // rcx
  __int64 v28; // rdx
  unsigned __int8 v29; // r8
  DfsRootFolder *v30; // rax
  char v32; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v33; // [rsp+51h] [rbp-AFh] BYREF
  char v34; // [rsp+52h] [rbp-AEh]
  unsigned __int8 v35[5]; // [rsp+53h] [rbp-ADh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DfsRootFolder *v37; // [rsp+60h] [rbp-A0h]
  unsigned int v38; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  DfsStore *v40; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v41; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v42; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v43; // [rsp+90h] [rbp-70h]
  DfsGeneric *v44; // [rsp+98h] [rbp-68h] BYREF
  void *v45; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v46; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING v48; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v49; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING String2; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v51; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-10h]
  _BYTE v53[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v54[68]; // [rsp+140h] [rbp+40h] BYREF
  int v55; // [rsp+184h] [rbp+84h]

  v40 = this;
  v49 = a4;
  v43 = a3;
  v7 = this;
  v52 = 0;
  v51 = 0;
  memset_0(v53, 0, sizeof(v53));
  memset_0(v54, 0, 0x98u);
  v45 = 0;
  String2 = 0;
  v37 = 0;
  v8 = 0;
  v48 = 0;
  v44 = 0;
  v9 = 0;
  v46 = 0;
  v47 = 0;
  v34 = 0;
  v32 = 0;
  v35[0] = 0;
  v33 = 0;
  v42 = 0;
  Block = 0;
  v38 = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 17, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, a3);
  }
  if ( !(unsigned int)DfsRtlInitUnicodeStringEx(&v48, a3) && !DfsIsSpecialDomainShare(&v48) )
  {
    IsScopedServerName = DfsIsScopedServerName(a2);
    if ( IsScopedServerName
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)pWppControl + 2), 18, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, a2);
    }
    v13 = DfsNormaliseHostName(a2, v35);
    v41 = v13;
    if ( !v13 )
    {
      v10 = hKey;
      inited = 8;
      v9 = 0;
LABEL_33:
      v7 = v40;
      goto LABEL_34;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_SS(
        *((_QWORD *)pWppControl + 2),
        19,
        (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
        (_DWORD)a2,
        (__int64)v13);
    }
    v14 = (unsigned __int64)a2 & -(__int64)(IsScopedServerName != 0);
    inited = DfsRtlInitUnicodeStringEx(&String2, v14);
    if ( inited )
      goto LABEL_68;
    inited = DfsGetNamespaceRegistrySubkeyName(a2, v43, IsScopedServerName, (const unsigned __int16 **)&v42);
    if ( inited )
      goto LABEL_68;
    inited = DfsStore::LookupRoot(v40, &String2, &v48, IsScopedServerName, &v44, v43, 1u, &v33);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_qd(*((_QWORD *)pWppControl + 2), 20, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v37, inited);
    }
    if ( inited )
      goto LABEL_68;
    if ( !v33 )
    {
      v10 = hKey;
      inited = 80;
LABEL_32:
      v9 = (unsigned __int16 *)v41;
      goto LABEL_33;
    }
    v8 = 1;
    CRegistry::OpenKey((CRegistry *)&v46, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfs\\Roots\\Standalone", 0x20006u);
    inited = v47;
    if ( v47 )
      goto LABEL_68;
    v34 = 1;
    if ( a5 )
    {
      inited = DfsReadRegistrySecurityInfo(v46, &v45);
      if ( inited )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_55;
        v19 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x840) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_55;
        v20 = 21;
LABEL_54:
        WPP_SF_D(*((_QWORD *)v19 + 2), v20, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, inited);
LABEL_55:
        v10 = hKey;
LABEL_86:
        CRegistry::DeleteKey(&v46, v42);
LABEL_87:
        if ( v8 )
        {
          v7 = v40;
          DfsStore::DeleteRootFolder(v40, v44);
          v9 = (unsigned __int16 *)v41;
          goto LABEL_34;
        }
        goto LABEL_32;
      }
      inited = DfsDoesUserHaveDesiredAccessToRegistry(0x10000000, v45);
      SHashFree(v45, v21, v22);
      if ( inited )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_55;
        v19 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x840) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_55;
        v20 = 22;
        goto LABEL_54;
      }
    }
    DfsStore::StoreInitializeNameInformation(v18, (struct _DFS_NAME_INFORMATION_ *)v54, &v48, 0, v49);
    v23 = v43;
    v55 |= 0x80u;
    DfsStore::StoreInitializeReplicaInformation(
      v24,
      (struct _DFS_REPLICA_LIST_INFORMATION_ *)&v51,
      (struct _DFS_REPLICA_INFORMATION__ *)v53,
      L".",
      v43);
    inited = DfsCreateNamespaceStateInRegistry(v46, v42, a2, (const BYTE *)v23, (BYTE *)v23, IsScopedServerName, &hKey);
    if ( inited
      || (v25 = v40,
          v32 = 1,
          (inited = DfsStore::CreateNameInformationBlob(v40, (struct _DFS_NAME_INFORMATION_ *)v54, &Block, &v38)) != 0) )
    {
LABEL_68:
      v10 = hKey;
    }
    else
    {
      v10 = hKey;
      inited = DfsRegistryStore::SetMetadata(v26, hKey, 0, L"ID", Block, v38);
      if ( Block )
        operator delete(Block);
      if ( inited )
        goto LABEL_85;
      inited = (*(__int64 (__fastcall **)(DfsStore *, __int128 *, void **, unsigned int *))(*(_QWORD *)v25 + 144LL))(
                 v25,
                 &v51,
                 &Block,
                 &v38);
      if ( !inited )
      {
        inited = DfsRegistryStore::SetMetadata(v27, v10, 0, L"Svc", Block, v38);
        if ( Block )
          operator delete(Block);
        if ( inited )
          goto LABEL_85;
        inited = (*(__int64 (__fastcall **)(DfsStore *, unsigned __int64, unsigned __int16 *))(*(_QWORD *)v25 + 64LL))(
                   v25,
                   v14,
                   v43);
        if ( !inited )
        {
          v8 = 0;
          inited = DfsRootFolder::AcquireRootShareDirectory(v37);
          if ( !inited )
          {
            DfsRootFolder::MakeDfsShareOnline((unsigned __int64)v37, v28, v29);
            DfsRootFolder::SetRootFolderSynchronized(v37);
LABEL_70:
            v30 = v37;
            ++*((_DWORD *)v37 + 30);
            ReleaseSRWLockExclusive((PSRWLOCK)v30 + 14);
            v9 = (unsigned __int16 *)v41;
            goto LABEL_71;
          }
        }
      }
    }
    if ( !inited )
      goto LABEL_70;
LABEL_85:
    if ( !v34 )
      goto LABEL_87;
    goto LABEL_86;
  }
  v10 = hKey;
  inited = 87;
LABEL_34:
  if ( v37 )
  {
    *((_DWORD *)v37 + 68) |= 0x4000u;
    v15 = v37;
    ++*((_DWORD *)v37 + 30);
    ReleaseSRWLockExclusive((PSRWLOCK)v15 + 14);
    DfsStore::RemoveRootFolder(v7, v37, v16);
    v17 = DfsRootFolder::ReleaseRootShareDirectory(v37);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (((1 << (v17 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 23, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v17);
    }
  }
LABEL_71:
  if ( v32 )
    RegCloseKey(v10);
  if ( v37 )
    DfsGeneric::ReleaseReference(v37);
  if ( v44 )
    DfsGeneric::ReleaseReference(v44);
  if ( v35[0] )
    operator delete(v9);
  operator delete(v42);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (inited != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SD(
      *((_QWORD *)pWppControl + 2),
      24,
      (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
      (_DWORD)v43,
      inited);
  }
  CRegistry::~CRegistry((CRegistry *)&v46);
  return inited;
}

```

## disassembly

```asm
0x140021e40  mov     [rsp-8+arg_18], rbx
0x140021e45  push    rbp
0x140021e46  push    rsi
0x140021e47  push    rdi
0x140021e48  push    r12
0x140021e4a  push    r13
0x140021e4c  push    r14
0x140021e4e  push    r15
0x140021e50  lea     rbp, [rsp-0F0h]
0x140021e58  sub     rsp, 1F0h
0x140021e5f  mov     rax, cs:__security_cookie
0x140021e66  xor     rax, rsp
0x140021e69  mov     [rbp+120h+var_40], rax
0x140021e70  xor     eax, eax
0x140021e72  mov     [rsp+220h+var_1A8], rcx
0x140021e77  mov     rbx, r8
0x140021e7a  mov     [rbp+120h+var_158], r9
0x140021e7e  mov     rsi, rdx
0x140021e81  mov     [rbp+120h+var_190], rbx
0x140021e85  mov     r14, rcx
0x140021e88  mov     [rbp+120h+var_130], rax
0x140021e8c  lea     edi, [rax+40h]
0x140021e8f  xorps   xmm0, xmm0
0x140021e92  mov     r8d, edi; Size
0x140021e95  lea     rcx, [rbp+120h+var_120]; void *
0x140021e99  xor     edx, edx; Val
0x140021e9b  movups  [rbp+120h+var_140], xmm0
0x140021e9f  call    memset_0
0x140021ea4  xor     edx, edx; Val
0x140021ea6  lea     r8d, [rdi+58h]; Size
0x140021eaa  lea     rcx, [rbp+120h+var_E0]; void *
0x140021eae  call    memset_0
0x140021eb3  xor     eax, eax
0x140021eb5  xorps   xmm0, xmm0
0x140021eb8  xorps   xmm1, xmm1
0x140021ebb  mov     [rbp+120h+var_180], rax
0x140021ebf  movups  xmmword ptr [rbp+120h+String2.Length], xmm0
0x140021ec3  mov     [rsp+220h+var_1C0], rax
0x140021ec8  mov     r13b, al
0x140021ecb  movups  xmmword ptr [rbp+120h+var_168.Length], xmm1
0x140021ecf  mov     [rbp+120h+var_188], rax
0x140021ed3  mov     r12d, eax
0x140021ed6  mov     [rbp+120h+var_178], rax
0x140021eda  mov     [rbp+120h+var_170], eax
0x140021edd  mov     [rsp+220h+var_1CE], al
0x140021ee1  mov     [rsp+220h+var_1D0], al
0x140021ee5  mov     [rsp+220h+var_1CD], al
0x140021ee9  mov     [rsp+220h+var_1CF], al
0x140021eed  mov     [rbp+120h+var_198], rax
0x140021ef1  mov     [rsp+220h+Block], rax
0x140021ef6  mov     [rsp+220h+var_1B8], eax
0x140021efa  mov     [rsp+220h+hKey], rax
0x140021eff  lea     rcx, WPP_GLOBAL_Control
0x140021f06  cmp     cs:WPP_GLOBAL_Control, rcx
0x140021f0d  lea     r15d, [rdi-20h]
0x140021f11  jz      short loc_140021F41
0x140021f13  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140021f1a  test    rcx, rcx
0x140021f1d  jz      short loc_140021F41
0x140021f1f  test    [rcx+1Ch], r15b
0x140021f23  jz      short loc_140021F41
0x140021f25  cmp     byte ptr [rcx+19h], 3
0x140021f29  jb      short loc_140021F41
0x140021f2b  mov     rcx, [rcx+10h]
0x140021f2f  lea     edx, [rdi-2Fh]
0x140021f32  mov     r9, rbx
0x140021f35  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140021f3c  call    WPP_SF_S
0x140021f41  mov     rdx, rbx
0x140021f44  lea     rcx, [rbp+120h+var_168]
0x140021f48  call    DfsRtlInitUnicodeStringEx
0x140021f4d  test    eax, eax
0x140021f4f  jz      short loc_140021F60
0x140021f51  mov     rsi, [rsp+220h+hKey]
0x140021f56  mov     ebx, 57h ; 'W'
0x140021f5b  jmp     loc_14002210B
0x140021f60  lea     rcx, [rbp+120h+var_168]; struct _UNICODE_STRING *
0x140021f64  call    ?DfsIsSpecialDomainShare@@YAEPEAU_UNICODE_STRING@@@Z; DfsIsSpecialDomainShare(_UNICODE_STRING *)
0x140021f69  test    al, al
0x140021f6b  jnz     short loc_140021F51
0x140021f6d  mov     rcx, rsi; SourceString
0x140021f70  call    ?DfsIsScopedServerName@@YAEPEBG@Z; DfsIsScopedServerName(ushort const *)
0x140021f75  mov     r14b, al
0x140021f78  test    al, al
0x140021f7a  jz      short loc_140021FBE
0x140021f7c  lea     rbx, WPP_GLOBAL_Control
0x140021f83  cmp     cs:WPP_GLOBAL_Control, rbx
0x140021f8a  jz      short loc_140021FC5
0x140021f8c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140021f93  test    rcx, rcx
0x140021f96  jz      short loc_140021FC5
0x140021f98  test    [rcx+1Ch], r15b
0x140021f9c  jz      short loc_140021FC5
0x140021f9e  cmp     byte ptr [rcx+19h], 3
0x140021fa2  jb      short loc_140021FC5
0x140021fa4  mov     rcx, [rcx+10h]
0x140021fa8  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140021faf  mov     edx, 12h
0x140021fb4  mov     r9, rsi
0x140021fb7  call    WPP_SF_S
0x140021fbc  jmp     short loc_140021FC5
0x140021fbe  lea     rbx, WPP_GLOBAL_Control
0x140021fc5  lea     rdx, [rsp+220h+var_1CD]; unsigned __int8 *
0x140021fca  mov     rcx, rsi; unsigned __int16 *
0x140021fcd  call    ?DfsNormaliseHostName@@YAPEBGPEBGPEAE@Z; DfsNormaliseHostName(ushort const *,uchar *)
0x140021fd2  mov     [rbp+120h+var_1A0], rax
0x140021fd6  test    rax, rax
0x140021fd9  jnz     short loc_140021FEB
0x140021fdb  mov     rsi, [rsp+220h+hKey]
0x140021fe0  lea     ebx, [rax+8]
0x140021fe3  mov     r12, rax
0x140021fe6  jmp     loc_140022106
0x140021feb  cmp     cs:WPP_GLOBAL_Control, rbx
0x140021ff2  jz      short loc_140022029
0x140021ff4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140021ffb  test    rcx, rcx
0x140021ffe  jz      short loc_140022029
0x140022000  test    [rcx+1Ch], r15b
0x140022004  jz      short loc_140022029
0x140022006  cmp     byte ptr [rcx+19h], 3
0x14002200a  jb      short loc_140022029
0x14002200c  mov     rcx, [rcx+10h]
0x140022010  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140022017  mov     edx, 13h
0x14002201c  mov     [rsp+220h+var_200], rax
0x140022021  mov     r9, rsi
0x140022024  call    WPP_SF_SS
0x140022029  mov     al, r14b
0x14002202c  lea     rcx, [rbp+120h+String2]
0x140022030  neg     al
0x140022032  sbb     r12, r12
0x140022035  and     r12, rsi
0x140022038  mov     rdx, r12
0x14002203b  call    DfsRtlInitUnicodeStringEx
0x140022040  mov     ebx, eax
0x140022042  test    eax, eax
0x140022044  jnz     loc_140022452
0x14002204a  mov     rdx, [rbp+120h+var_190]; unsigned __int16 *
0x14002204e  lea     r9, [rbp+120h+var_198]; unsigned __int16 **
0x140022052  mov     r8b, r14b; unsigned __int8
0x140022055  mov     rcx, rsi; unsigned __int16 *
0x140022058  call    ?DfsGetNamespaceRegistrySubkeyName@@YAKPEBG0EPEAPEBG@Z; DfsGetNamespaceRegistrySubkeyName(ushort const *,ushort const *,uchar,ushort const * *)
0x14002205d  mov     ebx, eax
0x14002205f  test    eax, eax
0x140022061  jnz     loc_140022452
0x140022067  mov     rcx, [rsp+220h+var_1A8]; this
0x14002206c  lea     rax, [rsp+220h+var_1CF]
0x140022071  mov     [rsp+220h+var_1E8], rax; unsigned __int8 *
0x140022076  lea     r8, [rbp+120h+var_168]; struct _UNICODE_STRING *
0x14002207a  mov     rax, [rbp+120h+var_190]
0x14002207e  lea     rdx, [rbp+120h+String2]; String2
0x140022082  mov     byte ptr [rsp+220h+var_1F0], 1; unsigned __int8
0x140022087  mov     r9b, r14b; unsigned __int8
0x14002208a  mov     [rsp+220h+var_1F8], rax; unsigned __int16 *
0x14002208f  lea     rax, [rbp+120h+var_188]
0x140022093  mov     [rsp+220h+var_200], rax; struct DfsRootFolder **
0x140022098  call    ?LookupRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@PEBGEPEAE@Z; DfsStore::LookupRoot(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *,ushort const *,uchar,uchar *)
0x14002209d  mov     ebx, eax
0x14002209f  lea     rax, WPP_GLOBAL_Control
0x1400220a6  cmp     cs:WPP_GLOBAL_Control, rax
0x1400220ad  jz      short loc_1400220E5
0x1400220af  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400220b6  test    rcx, rcx
0x1400220b9  jz      short loc_1400220E5
0x1400220bb  test    [rcx+1Ch], r15b
0x1400220bf  jz      short loc_1400220E5
0x1400220c1  cmp     byte ptr [rcx+19h], 3
0x1400220c5  jb      short loc_1400220E5
0x1400220c7  mov     r9, [rsp+220h+var_1C0]
0x1400220cc  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x1400220d3  mov     rcx, [rcx+10h]
0x1400220d7  mov     edx, 14h
0x1400220dc  mov     dword ptr [rsp+220h+var_200], ebx
0x1400220e0  call    WPP_SF_qd
0x1400220e5  test    ebx, ebx
0x1400220e7  jnz     loc_140022452
0x1400220ed  cmp     [rsp+220h+var_1CF], r13b
0x1400220f2  jnz     loc_1400221B8
0x1400220f8  mov     rsi, [rsp+220h+hKey]
0x1400220fd  mov     ebx, 50h ; 'P'
0x140022102  mov     r12, [rbp+120h+var_1A0]
0x140022106  mov     r14, [rsp+220h+var_1A8]
0x14002210b  mov     rcx, [rsp+220h+var_1C0]
0x140022110  test    rcx, rcx
0x140022113  jz      loc_14002247B
0x140022119  bts     dword ptr [rcx+110h], 0Eh
0x140022121  mov     rax, [rsp+220h+var_1C0]
0x140022126  inc     dword ptr [rax+78h]
0x140022129  lea     rcx, [rax+70h]; SRWLock
0x14002212d  call    cs:__imp_ReleaseSRWLockExclusive
0x140022134  nop     dword ptr [rax+rax+00h]
0x140022139  mov     rdx, [rsp+220h+var_1C0]; struct DfsRootFolder *
0x14002213e  mov     rcx, r14; this
0x140022141  call    ?RemoveRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@E@Z; DfsStore::RemoveRootFolder(DfsRootFolder *,uchar)
0x140022146  mov     rcx, [rsp+220h+var_1C0]; this
0x14002214b  call    ?ReleaseRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::ReleaseRootShareDirectory(void)
0x140022150  mov     r9d, eax
0x140022153  lea     rdi, WPP_GLOBAL_Control
0x14002215a  cmp     cs:WPP_GLOBAL_Control, rdi
0x140022161  jz      loc_140022482
0x140022167  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002216e  test    r10, r10
0x140022171  jz      loc_140022482
0x140022177  mov     ecx, eax
0x140022179  mov     eax, r15d
0x14002217c  neg     ecx
0x14002217e  sbb     edx, edx
0x140022180  and     edx, 0FFFFFFECh
0x140022183  add     edx, 1Fh
0x140022186  bts     eax, edx
0x140022189  test    [r10+1Ch], eax
0x14002218d  jz      loc_140022482
0x140022193  cmp     byte ptr [r10+19h], 3
0x140022198  jb      loc_140022482
0x14002219e  mov     rcx, [r10+10h]
0x1400221a2  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x1400221a9  mov     edx, 17h
0x1400221ae  call    WPP_SF_D
0x1400221b3  jmp     loc_140022482
0x1400221b8  mov     r9d, 20006h; unsigned int
0x1400221be  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfs\\Roots\\Standa"...
0x1400221c5  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400221cc  lea     rcx, [rbp+120h+var_178]; this
0x1400221d0  mov     r13b, 1
0x1400221d3  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x1400221d8  mov     ebx, [rbp+120h+var_170]
0x1400221db  test    ebx, ebx
0x1400221dd  jnz     loc_140022452
0x1400221e3  mov     [rsp+220h+var_1CE], r13b
0x1400221e8  cmp     [rbp+120h+arg_20], bl
0x1400221ee  jz      loc_1400222A7
0x1400221f4  mov     rcx, [rbp+120h+var_178]; hKey
0x1400221f8  lea     rdx, [rbp+120h+var_180]
0x1400221fc  call    DfsReadRegistrySecurityInfo
0x140022201  mov     ebx, eax
0x140022203  test    eax, eax
0x140022205  jz      short loc_14002223D
0x140022207  lea     rax, WPP_GLOBAL_Control
0x14002220e  cmp     cs:WPP_GLOBAL_Control, rax
0x140022215  jz      loc_14002229D
0x14002221b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140022222  test    rcx, rcx
0x140022225  jz      short loc_14002229D
0x140022227  bts     edi, 0Bh
0x14002222b  test    [rcx+1Ch], edi
0x14002222e  jz      short loc_14002229D
0x140022230  cmp     [rcx+19h], r13b
0x140022234  jb      short loc_14002229D
0x140022236  mov     edx, 15h
0x14002223b  jmp     short loc_14002228A
0x14002223d  mov     rdx, [rbp+120h+var_180]
0x140022241  mov     ecx, 10000000h
0x140022246  call    DfsDoesUserHaveDesiredAccessToRegistry
0x14002224b  mov     rcx, [rbp+120h+var_180]
0x14002224f  mov     ebx, eax
0x140022251  call    SHashFree
0x140022256  test    ebx, ebx
0x140022258  jz      short loc_1400222A7
0x14002225a  lea     rax, WPP_GLOBAL_Control
0x140022261  cmp     cs:WPP_GLOBAL_Control, rax
0x140022268  jz      short loc_14002229D
0x14002226a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140022271  test    rcx, rcx
0x140022274  jz      short loc_14002229D
0x140022276  bts     edi, 0Bh
0x14002227a  test    [rcx+1Ch], edi
0x14002227d  jz      short loc_14002229D
0x14002227f  cmp     [rcx+19h], r13b
0x140022283  jb      short loc_14002229D
0x140022285  mov     edx, 16h
0x14002228a  mov     rcx, [rcx+10h]
0x14002228e  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140022295  mov     r9d, ebx
0x140022298  call    WPP_SF_D
0x14002229d  mov     rsi, [rsp+220h+hKey]
0x1400222a2  jmp     loc_140022562
0x1400222a7  mov     rax, [rbp+120h+var_158]
0x1400222ab  lea     r8, [rbp+120h+var_168]; struct _UNICODE_STRING *
0x1400222af  xor     r9d, r9d; struct _GUID *
0x1400222b2  mov     [rsp+220h+var_200], rax; unsigned __int16 *
0x1400222b7  lea     rdx, [rbp+120h+var_E0]; struct _DFS_NAME_INFORMATION_ *
0x1400222bb  call    ?StoreInitializeNameInformation@DfsStore@@QEAAKPEAU_DFS_NAME_INFORMATION_@@PEAU_UNICODE_STRING@@PEAU_GUID@@PEBG@Z; DfsStore::StoreInitializeNameInformation(_DFS_NAME_INFORMATION_ *,_UNICODE_STRING *,_GUID *,ushort const *)
0x1400222c0  mov     rbx, [rbp+120h+var_190]
0x1400222c4  lea     r9, asc_1400640F8; "."
0x1400222cb  bts     [rbp+120h+var_9C], 7
0x1400222d3  lea     r8, [rbp+120h+var_120]; struct _DFS_REPLICA_INFORMATION__ *
0x1400222d7  lea     rdx, [rbp+120h+var_140]; struct _DFS_REPLICA_LIST_INFORMATION_ *
0x1400222db  mov     [rsp+220h+var_200], rbx; unsigned __int16 *
0x1400222e0  call    ?StoreInitializeReplicaInformation@DfsStore@@QEAAKPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEAU_DFS_REPLICA_INFORMATION__@@PEBG2@Z; DfsStore::StoreInitializeReplicaInformation(_DFS_REPLICA_LIST_INFORMATION_ *,_DFS_REPLICA_INFORMATION__ *,ushort const *,ushort const *)
0x1400222e5  mov     rdx, [rbp+120h+var_198]; unsigned __int16 *
0x1400222e9  lea     rax, [rsp+220h+hKey]
0x1400222ee  mov     rcx, [rbp+120h+var_178]; HKEY
0x1400222f2  mov     r9, rbx; unsigned __int16 *
0x1400222f5  mov     [rsp+220h+var_1F0], rax; HKEY *
0x1400222fa  mov     r8, rsi; unsigned __int16 *
0x1400222fd  mov     byte ptr [rsp+220h+var_1F8], r14b; unsigned __int8
0x140022302  mov     [rsp+220h+var_200], rbx; unsigned __int16 *
0x140022307  call    ?DfsCreateNamespaceStateInRegistry@@YAKPEAUHKEY__@@PEBG111EPEAPEAU1@@Z; DfsCreateNamespaceStateInRegistry(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,HKEY__ * *)
0x14002230c  mov     ebx, eax
0x14002230e  test    eax, eax
  ... truncated ...
```
