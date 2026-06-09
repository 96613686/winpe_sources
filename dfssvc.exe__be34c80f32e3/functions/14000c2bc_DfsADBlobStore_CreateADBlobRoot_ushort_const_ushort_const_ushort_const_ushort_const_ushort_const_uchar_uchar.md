# DfsADBlobStore::CreateADBlobRoot(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,uchar)

- ea: `0x14000c2bc`
- end: `0x14000c8ed`
- name: `?CreateADBlobRoot@DfsADBlobStore@@QEAAKPEBG0000EE@Z`
- size: `1585`
- prototype: `unsigned int __fastcall(DfsADBlobStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, PCWSTR SourceString, const unsigned __int16 *, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140010614`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b90`
- `0x140005c10`
- `0x140005dc8`
- `0x140005f20`
- `0x14000971c`
- `0x14000abc4`
- `0x14000bfa0`
- `0x14000c2bc`
- `0x14000cbb0`
- `0x14000e228`
- `0x14000e278`
- `0x140028098`
- `0x14002ccc4`
- `0x14002e1b8`
- `0x14002fbb0`
- `0x140038abc`
- `0x14003df3c`
- `0x14003e714`
- `0x14003ea74`
- `0x14004a414`
- `0x14004ad44`
- `0x140057f64`
- `0x1400586a8`
- `0x140059044`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000c6cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000c6cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c6ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c7aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c6ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c7aa`

## pseudocode

```c
__int64 __fastcall DfsADBlobStore::CreateADBlobRoot(
        DfsADBlobStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        WCHAR *SourceString,
        unsigned __int16 *a6,
        unsigned __int8 a7,
        unsigned __int8 a8)
{
  const unsigned __int16 *v9; // r15
  DfsADBlobStore *v11; // r13
  __int64 v12; // rdx
  unsigned int inited; // ebx
  const unsigned __int16 *AdDomainName; // rax
  unsigned int v15; // eax
  _UNKNOWN **v16; // rdx
  unsigned int *v17; // rcx
  DfsGeneric *v18; // rbx
  __int64 (__fastcall *v19)(DfsADBlobStore *, const unsigned __int16 *, WCHAR *, const unsigned __int16 *, int, LPCWSTR, DfsGeneric *, DfsRootFolder **); // r13
  const unsigned __int16 *v20; // rax
  unsigned int v21; // eax
  DfsRootFolder *v22; // rax
  DfsRootFolder *v23; // rax
  unsigned __int8 v24; // r8
  __int64 v25; // r9
  int v27; // [rsp+28h] [rbp-89h]
  unsigned __int8 v28; // [rsp+58h] [rbp-59h] BYREF
  char v29; // [rsp+59h] [rbp-58h]
  DfsRootFolder *v30; // [rsp+60h] [rbp-51h] BYREF
  DfsGeneric *v31; // [rsp+68h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+80h] [rbp-31h]
  struct _UNICODE_STRING v35; // [rsp+88h] [rbp-29h] BYREF
  struct _UNICODE_STRING v36; // [rsp+98h] [rbp-19h] BYREF
  UNICODE_STRING String2; // [rsp+A8h] [rbp-9h] BYREF

  v30 = 0;
  v35 = 0;
  v31 = 0;
  v36 = 0;
  hKey = 0;
  v9 = a3;
  String2 = 0;
  v34 = 0;
  v29 = 0;
  v11 = this;
  v28 = 0;
  lpSubKey = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SS(
      *((_QWORD *)pWppControl + 2),
      15,
      (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
      (_DWORD)SourceString,
      (__int64)a2);
  }
  inited = DfsRtlInitUnicodeStringEx(&v35, SourceString);
  if ( inited || (inited = DfsRtlInitUnicodeStringEx(&v36, a4)) != 0 )
  {
LABEL_59:
    if ( v30 )
    {
      v28 = 0;
      DfsUpdateRootRemoteServerName(SourceString, v9, a2, a4, 0);
      DfsADBlobStore::RemoveRootTargetFromMetadata(v11, v30, a2, a4, &v28);
      if ( v28 )
        DfsDeleteNamespaceEntry(SourceString, v9, 0);
      *((_DWORD *)v30 + 68) |= 0x4000u;
      v23 = v30;
      ++*((_DWORD *)v30 + 30);
      ReleaseSRWLockExclusive((PSRWLOCK)v23 + 14);
      DfsStore::RemoveRootFolder(v11, v30, v24);
      v25 = DfsRootFolder::ReleaseRootShareDirectory(v30);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( pWppControl )
        {
          v12 = (_DWORD)v25 != 0 ? 11 : 31;
          if ( (((1 << ((_DWORD)v25 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
            && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 20, WPP_85082c1995493ee34407538da2d11b51_Traceguids, v25);
          }
        }
      }
    }
    if ( !v29 )
      goto LABEL_69;
    goto LABEL_68;
  }
  if ( a8 )
    AdDomainName = a2;
  else
    AdDomainName = DfsGetAdDomainName();
  inited = DfsRtlInitUnicodeStringEx(&String2, AdDomainName);
  if ( inited )
    goto LABEL_58;
  if ( DfsIsSpecialDomainShare(&v35) || DfsIsSpecialDomainShare(&v36) )
  {
    inited = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_SD(
        *((_QWORD *)pWppControl + 2),
        16,
        (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
        (_DWORD)SourceString,
        87);
    }
    goto LABEL_58;
  }
  inited = DfsGetNamespaceRegistrySubkeyName(a2, SourceString, a8, &lpSubKey);
  if ( inited )
  {
LABEL_58:
    v9 = a3;
    goto LABEL_59;
  }
  v15 = DfsStore::LookupRoot(v11, &String2, &v35, a8, &v31, a4, 1u, &v28);
  inited = v15;
  v16 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v17 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 17, WPP_85082c1995493ee34407538da2d11b51_Traceguids, v31, v15);
    v16 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v17 = pWppControl;
  }
  if ( !inited )
  {
    if ( !v28 )
    {
      if ( *((_DWORD *)v31 + 78) == 512 )
      {
        inited = 183;
        if ( v16 != &WPP_GLOBAL_Control && v17 && (v17[7] & 0x820) != 0 && *((_BYTE *)v17 + 25) >= 3u )
          WPP_SF_SD(
            *((_QWORD *)v17 + 2),
            19,
            (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
            (_DWORD)SourceString,
            183);
      }
      else
      {
        if ( v16 != &WPP_GLOBAL_Control && v17 && (v17[7] & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 2u )
          WPP_SF_SS(
            *((_QWORD *)v17 + 2),
            18,
            (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
            (_DWORD)a2,
            (__int64)a4);
        inited = 87;
      }
      DfsGeneric::ReleaseReference(v31);
      goto LABEL_80;
    }
    v28 = 1;
    CRegistry::OpenKey((CRegistry *)&hKey, HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfs\\Roots\\Domain", 0x20006u);
    inited = v34;
    if ( v34 )
      goto LABEL_52;
    inited = DfsCreateNamespaceStateInRegistry(hKey, lpSubKey, a2, (const BYTE *)a4, (BYTE *)SourceString, a8, 0);
    if ( inited )
      goto LABEL_52;
    v18 = v31;
    v19 = *(__int64 (__fastcall **)(DfsADBlobStore *, const unsigned __int16 *, WCHAR *, const unsigned __int16 *, int, LPCWSTR, DfsGeneric *, DfsRootFolder **))(*(_QWORD *)v11 + 64LL);
    v20 = a8 ? a2 : DfsGetAdDomainName();
    LOBYTE(v27) = a8;
    inited = v19(this, v20, SourceString, a4, v27, lpSubKey, v18, &v30);
    if ( inited
      || (v28 = 0,
          (inited = (*(__int64 (__fastcall **)(DfsRootFolder *, const unsigned __int16 *))(*(_QWORD *)v30 + 104LL))(
                      v30,
                      a3)) != 0)
      || (v29 = 1, a8)
      && (inited = (*(__int64 (__fastcall **)(DfsRootFolder *, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)v30 + 168LL))(
                     v30,
                     a3,
                     a2)) != 0 )
    {
      v11 = this;
    }
    else
    {
      v11 = this;
      v21 = DfsADBlobStore::AddRootTargetToMetadata(this, v30, a7, a2, a4, SourceString, a6);
      inited = v21;
      if ( v21 == 80 || v21 == 183 || !v21 )
      {
        inited = DfsUpdateRootRemoteServerName(SourceString, a3, a2, a4, 1u);
        if ( !inited )
        {
          inited = DfsRootFolder::AcquireRootShareDirectory(v30);
          if ( !inited )
          {
            DfsRootFolder::MakeDfsShareOnline(v30);
            DfsRootFolder::SetRootFolderSynchronized(v30);
            v22 = v30;
            ++*((_DWORD *)v30 + 30);
            ReleaseSRWLockExclusive((PSRWLOCK)v22 + 14);
LABEL_68:
            LOBYTE(v12) = 1;
            (*(void (__fastcall **)(DfsRootFolder *, __int64, _QWORD))(*(_QWORD *)v30 + 128LL))(v30, v12, inited);
LABEL_69:
            if ( v31 )
              DfsGeneric::ReleaseReference(v31);
            if ( v30 )
              DfsGeneric::ReleaseReference(v30);
            if ( inited == 183 )
              inited = 50;
            operator delete((void *)lpSubKey);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (((1 << (inited != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
              && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              WPP_SF_SSd(
                *((_QWORD *)pWppControl + 2),
                21,
                (unsigned int)WPP_85082c1995493ee34407538da2d11b51_Traceguids,
                (_DWORD)a2,
                (__int64)SourceString,
                inited);
            }
            goto LABEL_80;
          }
        }
      }
    }
    RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
    if ( v28 )
LABEL_52:
      DfsStore::DeleteRootFolder(v11, v31);
    goto LABEL_58;
  }
LABEL_80:
  CRegistry::~CRegistry((CRegistry *)&hKey);
  return inited;
}

```

## disassembly

```asm
0x14000c2bc  mov     rax, rsp
0x14000c2bf  mov     [rax+10h], rbx
0x14000c2c3  mov     [rax+18h], r8
0x14000c2c7  mov     [rax+8], rcx
0x14000c2cb  push    rbp
0x14000c2cc  push    rsi
0x14000c2cd  push    rdi
0x14000c2ce  push    r12
0x14000c2d0  push    r13
0x14000c2d2  push    r14
0x14000c2d4  push    r15
0x14000c2d6  lea     rbp, [rax-3Fh]
0x14000c2da  sub     rsp, 0B0h
0x14000c2e1  xor     eax, eax
0x14000c2e3  xorps   xmm0, xmm0
0x14000c2e6  xorps   xmm1, xmm1
0x14000c2e9  mov     [rbp+37h+var_88], rax
0x14000c2ed  movups  xmmword ptr [rbp+37h+var_60.Length], xmm0
0x14000c2f1  mov     [rbp+37h+var_80], rax
0x14000c2f5  mov     r12, r9
0x14000c2f8  movups  xmmword ptr [rbp+37h+var_50.Length], xmm1
0x14000c2fc  mov     [rbp+37h+hKey], rax
0x14000c300  mov     r15, r8
0x14000c303  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x14000c307  mov     [rbp+37h+var_68], eax
0x14000c30a  mov     r14, rdx
0x14000c30d  mov     [rbp+37h+var_8F], al
0x14000c310  mov     r13, rcx
0x14000c313  mov     [rbp+37h+var_90], al
0x14000c316  mov     [rbp+37h+lpSubKey], rax
0x14000c31a  mov     rsi, [rbp+37h+SourceString]
0x14000c31e  lea     rcx, WPP_GLOBAL_Control
0x14000c325  cmp     cs:WPP_GLOBAL_Control, rcx
0x14000c32c  lea     edi, [rax+20h]
0x14000c32f  jz      short loc_14000C364
0x14000c331  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000c338  test    rcx, rcx
0x14000c33b  jz      short loc_14000C364
0x14000c33d  test    [rcx+1Ch], dil
0x14000c341  jz      short loc_14000C364
0x14000c343  cmp     byte ptr [rcx+19h], 3
0x14000c347  jb      short loc_14000C364
0x14000c349  mov     rcx, [rcx+10h]
0x14000c34d  lea     edx, [rax+0Fh]
0x14000c350  mov     r9, rsi
0x14000c353  mov     [rsp+0E0h+var_C0], r14
0x14000c358  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000c35f  call    WPP_SF_SS
0x14000c364  mov     rdx, rsi
0x14000c367  lea     rcx, [rbp+37h+var_60]
0x14000c36b  call    DfsRtlInitUnicodeStringEx
0x14000c370  mov     ebx, eax
0x14000c372  test    eax, eax
0x14000c374  jnz     loc_14000C73F
0x14000c37a  mov     rdx, r12
0x14000c37d  lea     rcx, [rbp+37h+var_50]
0x14000c381  call    DfsRtlInitUnicodeStringEx
0x14000c386  mov     ebx, eax
0x14000c388  test    eax, eax
0x14000c38a  jnz     loc_14000C73F
0x14000c390  mov     r15b, [rbp+37h+arg_38]
0x14000c394  test    r15b, r15b
0x14000c397  jz      short loc_14000C39E
0x14000c399  mov     rax, r14
0x14000c39c  jmp     short loc_14000C3A3
0x14000c39e  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x14000c3a3  mov     rdx, rax
0x14000c3a6  lea     rcx, [rbp+37h+String2]
0x14000c3aa  call    DfsRtlInitUnicodeStringEx
0x14000c3af  mov     ebx, eax
0x14000c3b1  test    eax, eax
0x14000c3b3  jnz     loc_14000C73B
0x14000c3b9  lea     rcx, [rbp+37h+var_60]; struct _UNICODE_STRING *
0x14000c3bd  call    ?DfsIsSpecialDomainShare@@YAEPEAU_UNICODE_STRING@@@Z; DfsIsSpecialDomainShare(_UNICODE_STRING *)
0x14000c3c2  test    al, al
0x14000c3c4  jnz     loc_14000C6EF
0x14000c3ca  lea     rcx, [rbp+37h+var_50]; struct _UNICODE_STRING *
0x14000c3ce  call    ?DfsIsSpecialDomainShare@@YAEPEAU_UNICODE_STRING@@@Z; DfsIsSpecialDomainShare(_UNICODE_STRING *)
0x14000c3d3  test    al, al
0x14000c3d5  jnz     loc_14000C6EF
0x14000c3db  lea     r9, [rbp+37h+lpSubKey]; unsigned __int16 **
0x14000c3df  mov     r8b, r15b; unsigned __int8
0x14000c3e2  mov     rdx, rsi; unsigned __int16 *
0x14000c3e5  mov     rcx, r14; unsigned __int16 *
0x14000c3e8  call    ?DfsGetNamespaceRegistrySubkeyName@@YAKPEBG0EPEAPEBG@Z; DfsGetNamespaceRegistrySubkeyName(ushort const *,ushort const *,uchar,ushort const * *)
0x14000c3ed  mov     ebx, eax
0x14000c3ef  test    eax, eax
0x14000c3f1  jnz     loc_14000C73B
0x14000c3f7  lea     rax, [rbp+37h+var_90]
0x14000c3fb  mov     r9b, r15b; unsigned __int8
0x14000c3fe  mov     [rsp+38h], rax; unsigned __int8 *
0x14000c403  lea     r8, [rbp+37h+var_60]; struct _UNICODE_STRING *
0x14000c407  mov     byte ptr [rsp+0E0h+var_B0], 1; HKEY *
0x14000c40c  lea     rax, [rbp+37h+var_80]
0x14000c410  mov     [rsp+0E0h+var_B8], r12; unsigned __int16 *
0x14000c415  lea     rdx, [rbp+37h+String2]; String2
0x14000c419  mov     rcx, r13; this
0x14000c41c  mov     [rsp+0E0h+var_C0], rax; struct DfsRootFolder **
0x14000c421  call    ?LookupRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@PEBGEPEAE@Z; DfsStore::LookupRoot(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *,ushort const *,uchar,uchar *)
0x14000c426  mov     ebx, eax
0x14000c428  mov     rdx, cs:WPP_GLOBAL_Control
0x14000c42f  lea     r8, WPP_GLOBAL_Control
0x14000c436  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000c43d  cmp     rdx, r8
0x14000c440  jz      short loc_14000C485
0x14000c442  test    rcx, rcx
0x14000c445  jz      short loc_14000C485
0x14000c447  test    [rcx+1Ch], dil
0x14000c44b  jz      short loc_14000C485
0x14000c44d  cmp     byte ptr [rcx+19h], 3
0x14000c451  jb      short loc_14000C485
0x14000c453  mov     r9, [rbp+37h+var_80]
0x14000c457  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000c45e  mov     rcx, [rcx+10h]
0x14000c462  mov     edx, 11h
0x14000c467  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14000c46b  call    WPP_SF_qd
0x14000c470  mov     rdx, cs:WPP_GLOBAL_Control
0x14000c477  lea     r8, WPP_GLOBAL_Control
0x14000c47e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000c485  test    ebx, ebx
0x14000c487  jnz     loc_14000C8C6
0x14000c48d  cmp     [rbp+37h+var_90], bl
0x14000c490  jnz     loc_14000C528
0x14000c496  mov     rax, [rbp+37h+var_80]
0x14000c49a  cmp     dword ptr [rax+138h], 200h
0x14000c4a4  jz      short loc_14000C4DE
0x14000c4a6  cmp     rdx, r8
0x14000c4a9  jz      short loc_14000C4D7
0x14000c4ab  test    rcx, rcx
0x14000c4ae  jz      short loc_14000C4D7
0x14000c4b0  test    byte ptr [rcx+1Ch], 40h
0x14000c4b4  jz      short loc_14000C4D7
0x14000c4b6  cmp     byte ptr [rcx+19h], 2
0x14000c4ba  jb      short loc_14000C4D7
0x14000c4bc  mov     rcx, [rcx+10h]
0x14000c4c0  lea     edx, [rbx+12h]
0x14000c4c3  mov     r9, r14
0x14000c4c6  mov     [rsp+0E0h+var_C0], r12
0x14000c4cb  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000c4d2  call    WPP_SF_SS
0x14000c4d7  mov     ebx, 57h ; 'W'
0x14000c4dc  jmp     short loc_14000C51A
0x14000c4de  mov     eax, 0B7h
0x14000c4e3  mov     ebx, eax
0x14000c4e5  cmp     rdx, r8
0x14000c4e8  jz      short loc_14000C51A
0x14000c4ea  test    rcx, rcx
0x14000c4ed  jz      short loc_14000C51A
0x14000c4ef  bts     edi, 0Bh
0x14000c4f3  test    [rcx+1Ch], edi
0x14000c4f6  jz      short loc_14000C51A
0x14000c4f8  cmp     byte ptr [rcx+19h], 3
0x14000c4fc  jb      short loc_14000C51A
0x14000c4fe  mov     rcx, [rcx+10h]
0x14000c502  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
0x14000c509  mov     edx, 13h
0x14000c50e  mov     dword ptr [rsp+0E0h+var_C0], eax
0x14000c512  mov     r9, rsi
0x14000c515  call    WPP_SF_SD
0x14000c51a  mov     rcx, [rbp+37h+var_80]; this
0x14000c51e  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14000c523  jmp     loc_14000C8C6
0x14000c528  mov     r9d, 20006h; unsigned int
0x14000c52e  mov     [rbp+37h+var_90], 1
0x14000c532  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Dfs\\Roots\\Domain"
0x14000c539  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14000c540  lea     rcx, [rbp+37h+hKey]; this
0x14000c544  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x14000c549  mov     ebx, [rbp+37h+var_68]
0x14000c54c  test    ebx, ebx
0x14000c54e  jnz     loc_14000C6E1
0x14000c554  and     [rsp+0E0h+var_B0], 0
0x14000c55a  mov     r9, r12; unsigned __int16 *
0x14000c55d  mov     rdx, [rbp+37h+lpSubKey]; unsigned __int16 *
0x14000c561  mov     r8, r14; unsigned __int16 *
0x14000c564  mov     rcx, [rbp+37h+hKey]; HKEY
0x14000c568  mov     byte ptr [rsp+0E0h+var_B8], r15b; unsigned __int8
0x14000c56d  mov     [rsp+0E0h+var_C0], rsi; unsigned __int16 *
0x14000c572  call    ?DfsCreateNamespaceStateInRegistry@@YAKPEAUHKEY__@@PEBG111EPEAPEAU1@@Z; DfsCreateNamespaceStateInRegistry(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,HKEY__ * *)
0x14000c577  mov     ebx, eax
0x14000c579  test    eax, eax
0x14000c57b  jnz     loc_14000C6E1
0x14000c581  mov     rax, [r13+0]
0x14000c585  mov     rbx, [rbp+37h+var_80]
0x14000c589  mov     r13, [rax+40h]
0x14000c58d  test    r15b, r15b
0x14000c590  jz      short loc_14000C597
0x14000c592  mov     rax, r14
0x14000c595  jmp     short loc_14000C59C
0x14000c597  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x14000c59c  lea     rcx, [rbp+37h+var_88]
0x14000c5a0  mov     rdx, rax
0x14000c5a3  mov     [rsp+38h], rcx
0x14000c5a8  mov     r9, r12
0x14000c5ab  mov     rcx, [rbp+37h+lpSubKey]
0x14000c5af  mov     r8, rsi
0x14000c5b2  mov     [rsp+0E0h+var_B0], rbx
0x14000c5b7  mov     rax, r13
0x14000c5ba  mov     [rsp+0E0h+var_B8], rcx
0x14000c5bf  mov     rcx, [rbp+37h+arg_0]
0x14000c5c3  mov     byte ptr [rsp+0E0h+var_C0], r15b
0x14000c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5cd  mov     ebx, eax
0x14000c5cf  test    eax, eax
0x14000c5d1  jnz     loc_14000C6BD
0x14000c5d7  mov     rcx, [rbp+37h+var_88]
0x14000c5db  mov     rdx, [rbp+37h+arg_10]
0x14000c5df  mov     [rbp+37h+var_90], al
0x14000c5e2  mov     rax, [rcx]
0x14000c5e5  mov     rax, [rax+68h]
0x14000c5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c5ee  mov     ebx, eax
0x14000c5f0  test    eax, eax
0x14000c5f2  jnz     loc_14000C6BD
0x14000c5f8  test    r15b, r15b
0x14000c5fb  mov     [rbp+37h+var_8F], 1
0x14000c5ff  mov     r15, [rbp+37h+arg_10]
0x14000c603  jz      short loc_14000C628
0x14000c605  mov     rcx, [rbp+37h+var_88]
0x14000c609  mov     r8, r14
0x14000c60c  mov     rdx, r15
0x14000c60f  mov     rax, [rcx]
0x14000c612  mov     rax, [rax+0A8h]
0x14000c619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c61e  mov     ebx, eax
0x14000c620  test    eax, eax
0x14000c622  jnz     loc_14000C6BD
0x14000c628  mov     rax, [rbp+37h+arg_28]
0x14000c62c  mov     r9, r14; unsigned __int16 *
0x14000c62f  mov     r13, [rbp+37h+arg_0]
0x14000c633  mov     r8b, [rbp+37h+arg_30]; unsigned __int8
0x14000c637  mov     rcx, r13; this
0x14000c63a  mov     rdx, [rbp+37h+var_88]; struct DfsRootFolder *
0x14000c63e  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 *
0x14000c643  mov     [rsp+0E0h+var_B8], rsi; unsigned __int16 *
0x14000c648  mov     [rsp+0E0h+var_C0], r12; unsigned __int16 *
0x14000c64d  call    ?AddRootTargetToMetadata@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@EPEBG111@Z; DfsADBlobStore::AddRootTargetToMetadata(DfsRootFolder *,uchar,ushort const *,ushort const *,ushort const *,ushort const *)
0x14000c652  mov     ebx, eax
0x14000c654  cmp     eax, 50h ; 'P'
0x14000c657  jz      short loc_14000C664
0x14000c659  cmp     eax, 0B7h
0x14000c65e  jz      short loc_14000C664
0x14000c660  test    eax, eax
0x14000c662  jnz     short loc_14000C6C1
0x14000c664  mov     r9, r12; unsigned __int16 *
0x14000c667  mov     byte ptr [rsp+0E0h+var_C0], 1; unsigned __int8
0x14000c66c  mov     r8, r14; unsigned __int16 *
0x14000c66f  mov     rdx, r15; unsigned __int16 *
0x14000c672  mov     rcx, rsi; SourceString
0x14000c675  call    ?DfsUpdateRootRemoteServerName@@YAKPEBG000E@Z; DfsUpdateRootRemoteServerName(ushort const *,ushort const *,ushort const *,ushort const *,uchar)
0x14000c67a  mov     ebx, eax
0x14000c67c  test    eax, eax
0x14000c67e  jnz     short loc_14000C6C1
0x14000c680  mov     rcx, [rbp+37h+var_88]; this
0x14000c684  call    ?AcquireRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::AcquireRootShareDirectory(void)
0x14000c689  mov     ebx, eax
0x14000c68b  test    eax, eax
0x14000c68d  jnz     short loc_14000C6C1
0x14000c68f  mov     rcx, [rbp+37h+var_88]; this
0x14000c693  call    ?MakeDfsShareOnline@DfsRootFolder@@QEAAKXZ; DfsRootFolder::MakeDfsShareOnline(void)
0x14000c698  mov     rcx, [rbp+37h+var_88]; this
0x14000c69c  call    ?SetRootFolderSynchronized@DfsRootFolder@@QEAAXXZ; DfsRootFolder::SetRootFolderSynchronized(void)
0x14000c6a1  mov     rax, [rbp+37h+var_88]
0x14000c6a5  inc     dword ptr [rax+78h]
0x14000c6a8  lea     rcx, [rax+70h]; SRWLock
0x14000c6ac  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c6b3  nop     dword ptr [rax+rax+00h]
0x14000c6b8  jmp     loc_14000C824
0x14000c6bd  mov     r13, [rbp+37h+arg_0]
0x14000c6c1  mov     rdx, [rbp+37h+lpSubKey]; lpSubKey
0x14000c6c5  xor     r9d, r9d; Reserved
0x14000c6c8  mov     rcx, [rbp+37h+hKey]; hKey
0x14000c6cc  xor     r8d, r8d; samDesired
0x14000c6cf  call    cs:__imp_RegDeleteKeyExW
0x14000c6d6  nop     dword ptr [rax+rax+00h]
0x14000c6db  cmp     [rbp+37h+var_90], 0
0x14000c6df  jz      short loc_14000C73B
0x14000c6e1  mov     rdx, [rbp+37h+var_80]; struct DfsRootFolder *
0x14000c6e5  mov     rcx, r13; this
0x14000c6e8  call    ?DeleteRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@@Z; DfsStore::DeleteRootFolder(DfsRootFolder *)
0x14000c6ed  jmp     short loc_14000C73B
0x14000c6ef  mov     ebx, 57h ; 'W'
0x14000c6f4  lea     rax, WPP_GLOBAL_Control
0x14000c6fb  cmp     cs:WPP_GLOBAL_Control, rax
0x14000c702  jz      short loc_14000C73B
0x14000c704  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14000c70b  test    rcx, rcx
0x14000c70e  jz      short loc_14000C73B
0x14000c710  mov     eax, edi
0x14000c712  bts     eax, 0Bh
0x14000c716  test    [rcx+1Ch], eax
0x14000c719  jz      short loc_14000C73B
0x14000c71b  cmp     byte ptr [rcx+19h], 3
0x14000c71f  jb      short loc_14000C73B
0x14000c721  mov     rcx, [rcx+10h]
0x14000c725  lea     edx, [rbx-47h]
0x14000c728  mov     r9, rsi
0x14000c72b  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x14000c72f  lea     r8, WPP_85082c1995493ee34407538da2d11b51_Traceguids
  ... truncated ...
```
