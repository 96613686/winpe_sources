# Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory>(HKEY__ *,ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14004e9b4`
- end: `0x14004ee18`
- name: `??$ReadEntries@VCDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@BindingRedirects@PkgDef@VisualStudio@Microsoft@@YAJPEAUHKEY__@@AEAV?$CAtlList@VCDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@6@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004df90`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002154`
- `0x140002c10`
- `0x140002dd0`
- `0x140002e30`
- `0x140003070`
- `0x14001e390`
- `0x140030204`
- `0x140033ab0`
- `0x1400452d8`
- `0x140046514`
- `0x14004d224`
- `0x14004e9b4`
- `0x140050490`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004ed72`
- `ADVAPI32!RegCloseKey` at `0x14004ed8a`
- `ADVAPI32!RegCloseKey` at `0x14004edbe`
- `ADVAPI32!RegCloseKey` at `0x14004ed72`
- `ADVAPI32!RegCloseKey` at `0x14004ed8a`
- `ADVAPI32!RegCloseKey` at `0x14004edbe`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ea2c`
- `ADVAPI32!RegOpenKeyExW` at `0x14004eb30`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ea2c`
- `ADVAPI32!RegOpenKeyExW` at `0x14004eb30`
- `ADVAPI32!RegEnumKeyExW` at `0x14004ead6`
- `ADVAPI32!RegEnumKeyExW` at `0x14004ead6`
- `ole32!CLSIDFromString` at `0x14004eaeb`
- `ole32!CLSIDFromString` at `0x14004eaeb`

## string_xrefs

- `0x14004ed23`: `Binding Redirect / CodeBase entry from configuration hive is malformed, ignoring.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory>(
        HKEY hKey,
        __int64 a2,
        LPCWSTR *a3)
{
  LPCWSTR *v3; // r13
  int Values; // r14d
  HKEY v7; // r12
  HKEY v8; // r15
  DWORD v9; // ebx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v11; // rax
  WCHAR *v12; // rdi
  HKEY v13; // rbx
  LSTATUS v14; // eax
  struct ATL::IAtlStringMgr *v15; // rax
  struct ATL::IAtlStringMgr *v16; // rax
  struct ATL::IAtlStringMgr *v17; // rax
  struct ATL::IAtlStringMgr *v18; // rax
  __int64 v19; // r13
  unsigned __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // r8
  _QWORD *i; // rcx
  __int64 *v24; // r15
  __int64 v25; // rbx
  __int64 **v26; // rax
  HKEY v27; // rbx
  int v29; // [rsp+40h] [rbp-99h]
  HKEY phkResult; // [rsp+48h] [rbp-91h] BYREF
  WCHAR *v31; // [rsp+50h] [rbp-89h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-81h] BYREF
  HKEY v33[2]; // [rsp+60h] [rbp-79h] BYREF
  __int64 v34; // [rsp+70h] [rbp-69h]
  LPCWSTR *v35; // [rsp+78h] [rbp-61h]
  __int128 v36; // [rsp+80h] [rbp-59h]
  __int64 v37; // [rsp+90h] [rbp-49h]
  DWORD cchName; // [rsp+98h] [rbp-41h] BYREF
  void **v39; // [rsp+A0h] [rbp-39h] BYREF
  CLSID v40; // [rsp+A8h] [rbp-31h]
  __int64 v41; // [rsp+B8h] [rbp-21h]
  __int64 v42; // [rsp+C0h] [rbp-19h]
  __int64 v43; // [rsp+C8h] [rbp-11h]
  __int64 v44; // [rsp+D0h] [rbp-9h]
  signed __int32 v45; // [rsp+DCh] [rbp+3h]
  struct _FILETIME ftLastWriteTime; // [rsp+E0h] [rbp+7h] BYREF
  CLSID pclsid; // [rsp+E8h] [rbp+Fh] BYREF

  v3 = a3;
  v35 = a3;
  Values = 0;
  ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory>>::RemoveAll(a2);
  v36 = 0;
  v37 = 0;
  v7 = 0;
  DWORD2(v36) = 0;
  hKeya = 0;
  if ( RegOpenKeyExW(hKey, *v3, 0, 0x20019u, &hKeya) )
  {
    Values = 1;
  }
  else
  {
    v8 = hKeya;
    v7 = hKeya;
    *(_QWORD *)&v36 = hKeya;
    DWORD2(v36) = 0;
    v9 = 0;
    v29 = 0;
    cchName = 50;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v11 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
    v12 = (WCHAR *)(v11 + 24);
    v31 = (WCHAR *)(v11 + 24);
    if ( ((1 - *(_DWORD *)(v11 + 16)) | (*(_DWORD *)(v11 + 12) - 50)) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v31, 50);
      v12 = v31;
    }
    while ( 1 )
    {
      if ( *((int *)v12 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v31, *((unsigned int *)v12 - 4));
        v12 = v31;
      }
      if ( RegEnumKeyExW(v8, v9, v12, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      Values = CLSIDFromString(v12, &pclsid);
      if ( Values < 0 )
        break;
      v13 = 0;
      v33[0] = 0;
      v33[1] = 0;
      v34 = 0;
      phkResult = 0;
      v14 = RegOpenKeyExW(v8, v12, 0, 0x20019u, &phkResult);
      if ( !v14 )
      {
        v13 = phkResult;
        v33[0] = phkResult;
        LODWORD(v33[1]) = 0;
      }
      Values = (unsigned __int16)(v14 != 0 ? v14 : 0) | 0x80070000;
      if ( (v14 != 0 ? v14 : 0) <= 0 )
        Values = v14 != 0 ? v14 : 0;
      if ( Values < 0 )
      {
        if ( v13 )
          RegCloseKey(v13);
        break;
      }
      memset_0(&v39, 0, 0x40u);
      v39 = &Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory::`vftable';
      v15 = ATL::CAtlStringMgr::GetInstance();
      if ( !v15
        || (v41 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v15 + 24LL))(v15) + 24,
            (v16 = ATL::CAtlStringMgr::GetInstance()) == 0)
        || (v42 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v16 + 24LL))(v16) + 24,
            (v17 = ATL::CAtlStringMgr::GetInstance()) == 0)
        || (v43 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v17 + 24LL))(v17) + 24,
            (v18 = ATL::CAtlStringMgr::GetInstance()) == 0) )
      {
        ATL::AtlThrowImpl(-2147467259);
      }
      v44 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v18 + 24LL))(v18) + 24;
      v45 = _InterlockedIncrement((volatile signed __int32 *)&Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory::s_IdCounter);
      v40 = pclsid;
      Values = Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory::ReadValues(
                 (Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory *)&v39,
                 (struct ATL::CRegKey *)v33);
      if ( Values < 0 )
      {
        _mm_lfence();
        phkResult = (HKEY)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v3 - 12) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &phkResult,
          L"\\%s",
          v12);
        v27 = phkResult;
        CLogger::LogError(
          L"Binding Redirect / CodeBase entry from configuration hive is malformed, ignoring.",
          Values,
          (const unsigned __int16 *)phkResult);
        Values = 0;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
        }
      }
      else
      {
        v19 = *(_QWORD *)(a2 + 8);
        if ( !*(_QWORD *)(a2 + 32) )
        {
          v20 = *(unsigned int *)(a2 + 40);
          if ( *(_DWORD *)(a2 + 40) )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / v20 < 0x50 )
              goto LABEL_45;
            v20 *= 80LL;
          }
          v21 = malloc_0(v20 + 8);
          if ( !v21 )
LABEL_45:
            ATL::AtlThrowImpl(-2147024882);
          *v21 = *(_QWORD *)(a2 + 24);
          *(_QWORD *)(a2 + 24) = v21;
          v22 = (unsigned int)(*(_DWORD *)(a2 + 40) - 1);
          for ( i = &v21[10 * v22 + 1]; (int)v22 >= 0; LODWORD(v22) = v22 - 1 )
          {
            *i = *(_QWORD *)(a2 + 32);
            *(_QWORD *)(a2 + 32) = i;
            i -= 10;
          }
        }
        v24 = *(__int64 **)(a2 + 32);
        v25 = *v24;
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory::CDbProviderFactory(
          (Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory *)(v24 + 2),
          (const struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory *)&v39);
        *(_QWORD *)(a2 + 32) = v25;
        v24[1] = v19;
        *v24 = 0;
        ++*(_QWORD *)(a2 + 16);
        v26 = *(__int64 ***)(a2 + 8);
        if ( v26 )
          *v26 = v24;
        else
          *(_QWORD *)a2 = v24;
        *(_QWORD *)(a2 + 8) = v24;
        v3 = v35;
      }
      v9 = ++v29;
      cchName = 50;
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory::~CDbProviderFactory((Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory *)&v39);
      if ( v33[0] )
        RegCloseKey(v33[0]);
      v8 = hKeya;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    }
  }
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)Values;
}

```

## disassembly

```asm
0x14004e9b4  mov     [rsp-8+arg_18], rbx
0x14004e9b9  push    rbp
0x14004e9ba  push    rsi
0x14004e9bb  push    rdi
0x14004e9bc  push    r12
0x14004e9be  push    r13
0x14004e9c0  push    r14
0x14004e9c2  push    r15
0x14004e9c4  lea     rbp, [rsp-27h]
0x14004e9c9  sub     rsp, 100h
0x14004e9d0  mov     rax, cs:__security_cookie
0x14004e9d7  xor     rax, rsp
0x14004e9da  mov     [rbp+57h+var_38], rax
0x14004e9de  mov     r13, r8
0x14004e9e1  mov     [rbp+57h+var_B8], r8
0x14004e9e5  mov     rsi, rdx
0x14004e9e8  mov     rbx, rcx
0x14004e9eb  xor     r14d, r14d
0x14004e9ee  mov     rcx, rdx
0x14004e9f1  call    ?RemoveAll@?$CAtlList@VCDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@QEAAXXZ
0x14004e9f6  xorps   xmm0, xmm0
0x14004e9f9  xor     eax, eax
0x14004e9fb  movups  [rbp+57h+var_B0], xmm0
0x14004e9ff  mov     [rbp+57h+var_A0], rax
0x14004ea03  xor     r12d, r12d
0x14004ea06  and     dword ptr [rbp+57h+var_B0+8], eax
0x14004ea09  and     [rbp+57h+var_A0], rax
0x14004ea0d  and     [rsp+130h+hKey], r12
0x14004ea12  lea     rax, [rsp+130h+hKey]
0x14004ea17  mov     [rsp+130h+phkResult], rax; phkResult
0x14004ea1c  mov     r9d, 20019h; samDesired
0x14004ea22  xor     r8d, r8d; ulOptions
0x14004ea25  mov     rdx, [r13+0]; lpSubKey
0x14004ea29  mov     rcx, rbx; hKey
0x14004ea2c  call    cs:__imp_RegOpenKeyExW
0x14004ea32  test    eax, eax
0x14004ea34  jnz     loc_14004EDB0
0x14004ea3a  mov     r15, [rsp+130h+hKey]
0x14004ea3f  mov     r12, r15
0x14004ea42  mov     qword ptr [rbp+57h+var_B0], r15
0x14004ea46  and     dword ptr [rbp+57h+var_B0+8], eax
0x14004ea49  xor     ebx, ebx
0x14004ea4b  mov     [rsp+130h+var_F0], ebx
0x14004ea4f  mov     [rbp+57h+cchName], 32h ; '2'
0x14004ea56  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004ea5b  mov     rcx, rax
0x14004ea5e  test    rax, rax
0x14004ea61  jz      loc_14004EDFC
0x14004ea67  mov     rax, [rax]
0x14004ea6a  call    qword ptr [rax+18h]
0x14004ea6d  lea     rdi, [rax+18h]
0x14004ea71  mov     [rsp+130h+var_E0], rdi
0x14004ea76  lea     ecx, [rbx+1]
0x14004ea79  sub     ecx, [rdi-8]
0x14004ea7c  mov     eax, [rdi-0Ch]
0x14004ea7f  sub     eax, 32h ; '2'
0x14004ea82  or      eax, ecx
0x14004ea84  jge     short loc_14004EA98
0x14004ea86  lea     edx, [rbx+32h]
0x14004ea89  lea     rcx, [rsp+130h+var_E0]
0x14004ea8e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z
0x14004ea93  mov     rdi, [rsp+130h+var_E0]
0x14004ea98  cmp     dword ptr [rdi-8], 1
0x14004ea9c  jle     short loc_14004EAB0
0x14004ea9e  mov     edx, [rdi-10h]
0x14004eaa1  lea     rcx, [rsp+130h+var_E0]
0x14004eaa6  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z
0x14004eaab  mov     rdi, [rsp+130h+var_E0]
0x14004eab0  lea     rax, [rbp+57h+ftLastWriteTime]
0x14004eab4  mov     [rsp+130h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14004eab9  xor     eax, eax
0x14004eabb  mov     [rsp+130h+lpcchClass], rax; lpcchClass
0x14004eac0  mov     [rsp+130h+lpClass], rax; lpClass
0x14004eac5  mov     [rsp+130h+phkResult], rax; lpReserved
0x14004eaca  lea     r9, [rbp+57h+cchName]; lpcchName
0x14004eace  mov     r8, rdi; lpName
0x14004ead1  mov     edx, ebx; dwIndex
0x14004ead3  mov     rcx, r15; hKey
0x14004ead6  call    cs:__imp_RegEnumKeyExW
0x14004eadc  test    eax, eax
0x14004eade  jnz     loc_14004ED91
0x14004eae4  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14004eae8  mov     rcx, rdi; lpsz
0x14004eaeb  call    cs:__imp_CLSIDFromString
0x14004eaf1  mov     r14d, eax
0x14004eaf4  xor     ecx, ecx
0x14004eaf6  test    eax, eax
0x14004eaf8  js      loc_14004ED91
0x14004eafe  xorps   xmm0, xmm0
0x14004eb01  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x14004eb05  mov     ebx, ecx
0x14004eb07  mov     [rbp+57h+var_D0], rcx
0x14004eb0b  mov     dword ptr [rbp+57h+var_D0+8], ecx
0x14004eb0e  mov     [rbp+57h+var_C0], rcx
0x14004eb12  mov     [rsp+130h+var_E8], rcx
0x14004eb17  lea     rax, [rsp+130h+var_E8]
0x14004eb1c  mov     [rsp+130h+phkResult], rax; phkResult
0x14004eb21  mov     r9d, 20019h; samDesired
0x14004eb27  xor     r8d, r8d; ulOptions
0x14004eb2a  mov     rdx, rdi; lpSubKey
0x14004eb2d  mov     rcx, r15; hKey
0x14004eb30  call    cs:__imp_RegOpenKeyExW
0x14004eb36  test    eax, eax
0x14004eb38  jnz     short loc_14004EB46
0x14004eb3a  mov     rbx, [rsp+130h+var_E8]
0x14004eb3f  mov     [rbp+57h+var_D0], rbx
0x14004eb43  and     dword ptr [rbp+57h+var_D0+8], eax
0x14004eb46  mov     ecx, eax
0x14004eb48  neg     ecx
0x14004eb4a  sbb     edx, edx
0x14004eb4c  and     edx, eax
0x14004eb4e  movzx   r14d, dx
0x14004eb52  or      r14d, 80070000h
0x14004eb59  test    edx, edx
0x14004eb5b  cmovle  r14d, edx
0x14004eb5f  test    r14d, r14d
0x14004eb62  js      loc_14004ED82
0x14004eb68  xor     edx, edx; Val
0x14004eb6a  lea     r8d, [rdx+40h]; Size
0x14004eb6e  lea     rcx, [rbp+57h+var_90]; void *
0x14004eb72  call    memset_0
0x14004eb77  lea     rax, ??_7CDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@6B@
0x14004eb7e  mov     [rbp+57h+var_90], rax
0x14004eb82  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004eb87  mov     rcx, rax
0x14004eb8a  test    rax, rax
0x14004eb8d  jz      loc_14004EDEE
0x14004eb93  mov     rax, [rax]
0x14004eb96  call    qword ptr [rax+18h]
0x14004eb99  add     rax, 18h
0x14004eb9d  mov     [rbp+57h+var_78], rax
0x14004eba1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004eba6  mov     rcx, rax
0x14004eba9  test    rax, rax
0x14004ebac  jz      loc_14004EDEE
0x14004ebb2  mov     rax, [rax]
0x14004ebb5  call    qword ptr [rax+18h]
0x14004ebb8  add     rax, 18h
0x14004ebbc  mov     [rbp+57h+var_70], rax
0x14004ebc0  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004ebc5  mov     rcx, rax
0x14004ebc8  test    rax, rax
0x14004ebcb  jz      loc_14004EDEE
0x14004ebd1  mov     rax, [rax]
0x14004ebd4  call    qword ptr [rax+18h]
0x14004ebd7  add     rax, 18h
0x14004ebdb  mov     [rbp+57h+var_68], rax
0x14004ebdf  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004ebe4  mov     rcx, rax
0x14004ebe7  test    rax, rax
0x14004ebea  jz      loc_14004EDEE
0x14004ebf0  mov     rax, [rax]
0x14004ebf3  call    qword ptr [rax+18h]
0x14004ebf6  add     rax, 18h
0x14004ebfa  mov     [rbp+57h+var_60], rax
0x14004ebfe  mov     eax, 1
0x14004ec03  lock xadd cs:?s_IdCounter@CDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@0KC, eax
0x14004ec0b  inc     eax
0x14004ec0d  mov     [rbp+57h+var_54], eax
0x14004ec10  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x14004ec14  movdqu  [rbp+57h+var_88], xmm0
0x14004ec19  lea     rdx, [rbp+57h+var_D0]; struct ATL::CRegKey *
0x14004ec1d  lea     rcx, [rbp+57h+var_90]; this
0x14004ec21  call    ?ReadValues@CDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAAJAEAVCRegKey@ATL@@@Z
0x14004ec26  mov     r14d, eax
0x14004ec29  test    eax, eax
0x14004ec2b  js      loc_14004ECEB
0x14004ec31  mov     r13, [rsi+8]
0x14004ec35  cmp     qword ptr [rsi+20h], 0
0x14004ec3a  jnz     short loc_14004ECAC
0x14004ec3c  mov     ecx, [rsi+28h]
0x14004ec3f  test    rcx, rcx
0x14004ec42  jz      short loc_14004EC5F
0x14004ec44  xor     edx, edx
0x14004ec46  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004ec4a  div     rcx
0x14004ec4d  cmp     rax, 50h ; 'P'
0x14004ec51  jb      loc_14004EE0D
0x14004ec57  lea     rcx, [rcx+rcx*4]
0x14004ec5b  shl     rcx, 4
0x14004ec5f  add     rcx, 8; Size
0x14004ec63  call    malloc_0
0x14004ec68  test    rax, rax
0x14004ec6b  jz      loc_14004EE0D
0x14004ec71  mov     rcx, [rsi+18h]
0x14004ec75  mov     [rax], rcx
0x14004ec78  mov     [rsi+18h], rax
0x14004ec7c  mov     r8d, [rsi+28h]
0x14004ec80  dec     r8d
0x14004ec83  lea     rcx, [r8+r8*4]
0x14004ec87  shl     rcx, 4
0x14004ec8b  add     rcx, 8
0x14004ec8f  add     rcx, rax
0x14004ec92  test    r8d, r8d
0x14004ec95  js      short loc_14004ECAC
0x14004ec97  mov     rax, [rsi+20h]
0x14004ec9b  mov     [rcx], rax
0x14004ec9e  mov     [rsi+20h], rcx
0x14004eca2  sub     rcx, 50h ; 'P'
0x14004eca6  sub     r8d, 1
0x14004ecaa  jns     short loc_14004EC97
0x14004ecac  mov     r15, [rsi+20h]
0x14004ecb0  mov     rbx, [r15]
0x14004ecb3  lea     rcx, [r15+10h]; this
0x14004ecb7  lea     rdx, [rbp+57h+var_90]; struct Microsoft::VisualStudio::PkgDef::BindingRedirects::CDbProviderFactory *
0x14004ecbb  call    ??0CDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@AEBV01234@@Z
0x14004ecc0  mov     [rsi+20h], rbx
0x14004ecc4  mov     [r15+8], r13
0x14004ecc8  and     qword ptr [r15], 0
0x14004eccc  inc     qword ptr [rsi+10h]
0x14004ecd0  mov     rax, [rsi+8]
0x14004ecd4  test    rax, rax
0x14004ecd7  jz      short loc_14004ECDE
0x14004ecd9  mov     [rax], r15
0x14004ecdc  jmp     short loc_14004ECE1
0x14004ecde  mov     [rsi], r15
0x14004ece1  mov     [rsi+8], r15
0x14004ece5  mov     r13, [rbp+57h+var_B8]
0x14004ece9  jmp     short loc_14004ED4F
0x14004eceb  lfence
0x14004ecee  mov     rcx, [r13+0]
0x14004ecf2  sub     rcx, 18h
0x14004ecf6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z
0x14004ecfb  add     rax, 18h
0x14004ecff  mov     [rsp+130h+var_E8], rax
0x14004ed04  mov     r8, rdi
0x14004ed07  lea     rdx, aS_4
0x14004ed0e  lea     rcx, [rsp+130h+var_E8]
0x14004ed13  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ
0x14004ed18  mov     rbx, [rsp+130h+var_E8]
0x14004ed1d  mov     r8, rbx; unsigned __int16 *
0x14004ed20  mov     edx, r14d; int
0x14004ed23  lea     rcx, aBindingRedirec_0
0x14004ed2a  call    ?LogError@CLogger@@SAXPEBGJ0@Z
0x14004ed2f  xor     r14d, r14d
0x14004ed32  lea     rdx, [rbx-18h]
0x14004ed36  or      eax, 0FFFFFFFFh
0x14004ed39  lock xadd [rdx+10h], eax
0x14004ed3e  sub     eax, 1
0x14004ed41  jg      short loc_14004ED4F
0x14004ed43  lfence
0x14004ed46  mov     rcx, [rdx]
0x14004ed49  mov     rax, [rcx]
0x14004ed4c  call    qword ptr [rax+8]
0x14004ed4f  mov     ebx, [rsp+130h+var_F0]
0x14004ed53  inc     ebx
0x14004ed55  mov     [rsp+130h+var_F0], ebx
0x14004ed59  mov     [rbp+57h+cchName], 32h ; '2'
0x14004ed60  lea     rcx, [rbp+57h+var_90]; this
0x14004ed64  call    ??1CDbProviderFactory@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAA@XZ
0x14004ed69  mov     rcx, [rbp+57h+var_D0]; hKey
0x14004ed6d  test    rcx, rcx
0x14004ed70  jz      short loc_14004ED78
0x14004ed72  call    cs:__imp_RegCloseKey
0x14004ed78  mov     r15, [rsp+130h+hKey]
0x14004ed7d  jmp     loc_14004EA98
0x14004ed82  test    rbx, rbx
0x14004ed85  jz      short loc_14004ED91
0x14004ed87  mov     rcx, rbx; hKey
0x14004ed8a  call    cs:__imp_RegCloseKey
0x14004ed90  nop
0x14004ed91  lea     rdx, [rdi-18h]
0x14004ed95  or      eax, 0FFFFFFFFh
0x14004ed98  lock xadd [rdx+10h], eax
0x14004ed9d  sub     eax, 1
0x14004eda0  jg      short loc_14004EDB6
0x14004eda2  lfence
0x14004eda5  mov     rcx, [rdx]
0x14004eda8  mov     rax, [rcx]
0x14004edab  call    qword ptr [rax+8]
0x14004edae  jmp     short loc_14004EDB6
0x14004edb0  mov     r14d, 1
0x14004edb6  test    r12, r12
0x14004edb9  jz      short loc_14004EDC4
0x14004edbb  mov     rcx, r12; hKey
0x14004edbe  call    cs:__imp_RegCloseKey
0x14004edc4  mov     eax, r14d
0x14004edc7  mov     rcx, [rbp+57h+var_38]
0x14004edcb  xor     rcx, rsp; StackCookie
0x14004edce  call    __security_check_cookie
0x14004edd3  mov     rbx, [rsp+130h+arg_18]
0x14004eddb  add     rsp, 100h
0x14004ede2  pop     r15
0x14004ede4  pop     r14
0x14004ede6  pop     r13
0x14004ede8  pop     r12
0x14004edea  pop     rdi
0x14004edeb  pop     rsi
0x14004edec  pop     rbp
0x14004eded  retn
0x14004edee  mov     ecx, 80004005h; int
0x14004edf3  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x14004edf9  jmp     short $+2
0x14004edfb  nop
0x14004edfc  mov     ecx, 80004005h; int
0x14004ee01  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x14004ee07  jmp     short loc_14004EE0C
0x14004ee0c  nop
0x14004ee0d  mov     ecx, 8007000Eh; int
0x14004ee12  call    ?AtlThrowImpl@ATL@@YAXJ@Z
  ... truncated ...
```
