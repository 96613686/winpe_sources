# VsRegCopyTree(HKEY__ *,ushort const *,HKEY__ *,ulong,void *,IRegistryFilter *,ushort const *)

- ea: `0x14004ab74`
- end: `0x14004b03c`
- name: `?VsRegCopyTree@@YA_JPEAUHKEY__@@PEBG0KPEAXPEAUIRegistryFilter@@1@Z`
- size: `1224`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, HKEY, unsigned int, HANDLE hToken, struct IRegistryFilter *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14004ab74`
- `0x14004ba9c`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002190`
- `0x140002c10`
- `0x140002f00`
- `0x140007740`
- `0x14000fce0`
- `0x14000fea0`
- `0x14002fa90`
- `0x140033ab0`
- `0x1400464b0`
- `0x140046514`
- `0x14004ab74`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004ad9c`
- `ADVAPI32!RegCloseKey` at `0x14004afeb`
- `ADVAPI32!RegCloseKey` at `0x14004ad9c`
- `ADVAPI32!RegCloseKey` at `0x14004afeb`
- `ADVAPI32!RegCreateKeyExW` at `0x14004ace1`
- `ADVAPI32!RegCreateKeyExW` at `0x14004ace1`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ac09`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ac09`
- `ADVAPI32!RegSetValueExW` at `0x14004afab`
- `ADVAPI32!RegSetValueExW` at `0x14004afab`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004ae20`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14004ae20`
- `ADVAPI32!RegEnumKeyExW` at `0x14004ac69`
- `ADVAPI32!RegEnumKeyExW` at `0x14004ac69`
- `ADVAPI32!RegQueryValueExW` at `0x14004aee9`
- `ADVAPI32!RegQueryValueExW` at `0x14004aee9`
- `ADVAPI32!RegEnumValueW` at `0x14004ae93`
- `ADVAPI32!RegEnumValueW` at `0x14004ae93`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004abdb`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004abdb`
- `ADVAPI32!RevertToSelf` at `0x14004aff7`
- `ADVAPI32!RevertToSelf` at `0x14004aff7`

## string_xrefs

- `0x14004af27`: `PkgDef merge registry encountered data collision for key value '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall VsRegCopyTree(
        HKEY a1,
        const unsigned __int16 *a2,
        HKEY a3,
        DWORD a4,
        HANDLE hToken,
        struct IRegistryFilter *a6,
        const unsigned __int16 *a7)
{
  DWORD v7; // r14d
  bool v10; // si
  unsigned __int64 v11; // rbx
  DWORD v12; // r15d
  unsigned int v13; // edi
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v15; // r14
  __int64 v16; // r8
  __int64 v17; // r8
  bool v18; // zf
  BYTE *v19; // rax
  const struct std::nothrow_t *v20; // rdx
  BYTE *v21; // rbx
  DWORD v22; // r15d
  DWORD i; // r14d
  LSTATUS Value; // edi
  struct ATL::IAtlStringMgr *v25; // rax
  unsigned __int16 *v26; // rdi
  unsigned int v27; // edx
  unsigned __int16 *v29; // [rsp+60h] [rbp-A0h] BYREF
  bool v30; // [rsp+68h] [rbp-98h]
  HKEY v31; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v32; // [rsp+78h] [rbp-88h]
  DWORD dwOptions; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY v35; // [rsp+90h] [rbp-70h] BYREF
  DWORD cchName; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchClass; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD Type; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v39; // [rsp+A8h] [rbp-58h]
  DWORD dwDisposition[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Class[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v7 = a4;
  dwOptions = a4;
  v31 = a3;
  v32 = a2;
  v39 = hToken;
  hKey = 0;
  v10 = ImpersonateLoggedOnUser(hToken);
  v30 = v10;
  if ( a2 )
  {
    v11 = (unsigned int)RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    goto LABEL_6;
  }
  if ( !a1 )
  {
    v11 = 87;
LABEL_6:
    if ( (_DWORD)v11 )
      goto LABEL_49;
    goto LABEL_7;
  }
  hKey = a1;
LABEL_7:
  cchName = 260;
  cchClass = 260;
  v11 = 0;
  v12 = 0;
  do
  {
    v13 = RegEnumKeyExW(hKey, v12, SubKey, &cchName, 0, Class, &cchClass, 0);
    if ( v13 )
      break;
    if ( !a6
      || (*(unsigned __int8 (__fastcall **)(struct IRegistryFilter *, HKEY, const unsigned __int16 *, WCHAR *))(*(_QWORD *)a6 + 8LL))(
           a6,
           hKey,
           a7,
           SubKey) )
    {
      v13 = RegCreateKeyExW(v31, SubKey, 0, Class, v7, CLogger::ms_bLoggingOn ? 131103 : 131078, 0, &v35, dwDisposition);
      if ( v13 )
        break;
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v15 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
      v29 = v15;
      if ( a7 )
      {
        v16 = -1;
        do
          ++v16;
        while ( a7[v16] );
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, a7);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v29, 92);
        v17 = -1;
        do
          ++v17;
        while ( SubKey[v17] );
        ATL::CSimpleStringT<unsigned short,0>::Append(&v29, SubKey, v17);
        v11 = (unsigned __int64)v29;
        v15 = v29;
      }
      v13 = VsRegCopyTree(hKey, SubKey, v35, dwOptions, v39, a6, (const unsigned __int16 *)v11);
      RegCloseKey(v35);
      v11 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      }
      v7 = dwOptions;
    }
    ++v12;
    cchName = 260;
    cchClass = 260;
  }
  while ( !v13 );
  v18 = v13 == 259;
  if ( v13 == 259 )
  {
    v13 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &dwOptions, 0, 0);
    if ( !v13 )
    {
      v19 = (BYTE *)operator new[](dwOptions + 1);
      v21 = v19;
      v39 = v19;
      if ( v19 )
      {
        memset_0(v19, 0, dwOptions);
        v22 = dwOptions;
        for ( i = 0; ; ++i )
        {
          cchName = 260;
          v13 = RegEnumValueW(hKey, i, SubKey, &cchName, 0, &Type, v21, &dwOptions);
          if ( v13 )
            break;
          if ( !a6
            || (*(unsigned __int8 (__fastcall **)(struct IRegistryFilter *, const unsigned __int16 *, WCHAR *))(*(_QWORD *)a6 + 24LL))(
                 a6,
                 a7,
                 SubKey) )
          {
            if ( CLogger::ms_bLoggingOn )
            {
              Value = RegQueryValueExW(v31, SubKey, 0, 0, 0, 0);
              if ( Value != 2 )
              {
                v25 = ATL::CAtlStringMgr::GetInstance();
                if ( !v25 )
                  ATL::AtlThrowImpl(-2147467259);
                v29 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v25 + 24LL))(v25)
                                         + 24);
                if ( Value )
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &v29,
                    L"Error while merging value '%s'",
                    SubKey);
                  v27 = (unsigned __int16)Value | 0x80070000;
                  if ( Value <= 0 )
                    v27 = Value;
                  v26 = v29;
                  CLogger::LogError(v29, v27, 0);
                }
                else
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &v29,
                    L"PkgDef merge registry encountered data collision for key value '%s'",
                    SubKey);
                  v26 = v29;
                  CLogger::LogWarn(v29, 0, 0);
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 - 2, 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v26 - 3) + 8LL))(*((_QWORD *)v26 - 3));
                }
              }
            }
            v13 = RegSetValueExW(v31, SubKey, 0, Type, v21, dwOptions);
            if ( v13 )
              break;
          }
          dwOptions = v22;
        }
      }
      else
      {
        v13 = 14;
      }
      operator delete(v21, v20);
      v11 = 0;
    }
    v18 = v13 == 259;
  }
  if ( !v18 )
    v11 = v13;
  if ( v32 )
    RegCloseKey(hKey);
LABEL_49:
  if ( v10 )
    RevertToSelf();
  return v11;
}

```

## disassembly

```asm
0x14004ab74  push    rbp
0x14004ab76  push    rbx
0x14004ab77  push    rsi
0x14004ab78  push    rdi
0x14004ab79  push    r12
0x14004ab7b  push    r13
0x14004ab7d  push    r14
0x14004ab7f  push    r15
0x14004ab81  lea     rbp, [rsp-3F8h]
0x14004ab89  sub     rsp, 4F8h
0x14004ab90  mov     rax, cs:__security_cookie
0x14004ab97  xor     rax, rsp
0x14004ab9a  mov     [rbp+430h+var_50], rax
0x14004aba1  mov     r14d, r9d
0x14004aba4  mov     [rbp+430h+dwOptions], r9d
0x14004aba8  mov     [rsp+530h+var_4C0], r8
0x14004abad  mov     rdi, rdx
0x14004abb0  mov     [rsp+530h+var_4B8], rdx
0x14004abb5  mov     rbx, rcx
0x14004abb8  mov     rax, [rbp+430h+hToken]
0x14004abbf  mov     [rbp+430h+var_488], rax
0x14004abc3  mov     r12, [rbp+430h+arg_28]
0x14004abca  mov     r13, [rbp+430h+arg_30]
0x14004abd1  xor     r15d, r15d
0x14004abd4  mov     [rbp+430h+hKey], r15
0x14004abd8  mov     rcx, rax; hToken
0x14004abdb  call    cs:__imp_ImpersonateLoggedOnUser
0x14004abe1  test    eax, eax
0x14004abe3  setnz   sil
0x14004abe7  mov     [rsp+530h+var_4C8], sil
0x14004abec  test    rdi, rdi
0x14004abef  jz      short loc_14004AC13
0x14004abf1  lea     rax, [rbp+430h+hKey]
0x14004abf5  mov     [rsp+530h+phkResult], rax; phkResult
0x14004abfa  mov     r9d, 20019h; samDesired
0x14004ac00  xor     r8d, r8d; ulOptions
0x14004ac03  mov     rdx, rdi; lpSubKey
0x14004ac06  mov     rcx, rbx; hKey
0x14004ac09  call    cs:__imp_RegOpenKeyExW
0x14004ac0f  mov     ebx, eax
0x14004ac11  jmp     short loc_14004AC23
0x14004ac13  test    rbx, rbx
0x14004ac16  jz      short loc_14004AC1E
0x14004ac18  mov     [rbp+430h+hKey], rbx
0x14004ac1c  jmp     short loc_14004AC2B
0x14004ac1e  mov     ebx, 57h ; 'W'
0x14004ac23  test    ebx, ebx
0x14004ac25  jnz     loc_14004AFF2
0x14004ac2b  mov     eax, 104h
0x14004ac30  mov     [rbp+430h+cchName], eax
0x14004ac33  mov     [rbp+430h+cchClass], eax
0x14004ac36  xor     ebx, ebx
0x14004ac38  mov     r15d, ebx
0x14004ac3b  mov     [rsp+530h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x14004ac40  lea     rax, [rbp+430h+cchClass]
0x14004ac44  mov     [rsp+530h+lpcchClass], rax; lpcchClass
0x14004ac49  lea     rax, [rbp+430h+Class]
0x14004ac50  mov     [rsp+530h+lpClass], rax; lpClass
0x14004ac55  mov     [rsp+530h+phkResult], rbx; lpReserved
0x14004ac5a  lea     r9, [rbp+430h+cchName]; lpcchName
0x14004ac5e  lea     r8, [rbp+430h+SubKey]; lpName
0x14004ac62  mov     edx, r15d; dwIndex
0x14004ac65  mov     rcx, [rbp+430h+hKey]; hKey
0x14004ac69  call    cs:__imp_RegEnumKeyExW
0x14004ac6f  mov     edi, eax
0x14004ac71  test    eax, eax
0x14004ac73  jnz     loc_14004ADDC
0x14004ac79  test    r12, r12
0x14004ac7c  jz      short loc_14004AC9B
0x14004ac7e  mov     rax, [r12]
0x14004ac82  lea     r9, [rbp+430h+SubKey]
0x14004ac86  mov     r8, r13
0x14004ac89  mov     rdx, [rbp+430h+hKey]
0x14004ac8d  mov     rcx, r12
0x14004ac90  call    qword ptr [rax+8]
0x14004ac93  test    al, al
0x14004ac95  jz      loc_14004ADC6
0x14004ac9b  mov     al, cs:?ms_bLoggingOn@CLogger@@0_NA; bool CLogger::ms_bLoggingOn
0x14004aca1  neg     al
0x14004aca3  sbb     ecx, ecx
0x14004aca5  and     ecx, 19h
0x14004aca8  add     ecx, 20006h
0x14004acae  lea     rax, [rbp+430h+dwDisposition]
0x14004acb2  mov     [rsp+530h+lpdwDisposition], rax; lpdwDisposition
0x14004acb7  lea     rax, [rbp+430h+var_4A0]
0x14004acbb  mov     [rsp+530h+lpftLastWriteTime], rax; phkResult
0x14004acc0  mov     [rsp+530h+lpcchClass], rbx; lpSecurityAttributes
0x14004acc5  mov     dword ptr [rsp+530h+lpClass], ecx; samDesired
0x14004acc9  mov     dword ptr [rsp+530h+phkResult], r14d; dwOptions
0x14004acce  lea     r9, [rbp+430h+Class]; lpClass
0x14004acd5  xor     r8d, r8d; Reserved
0x14004acd8  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x14004acdc  mov     rcx, [rsp+530h+var_4C0]; hKey
0x14004ace1  call    cs:__imp_RegCreateKeyExW
0x14004ace7  mov     edi, eax
0x14004ace9  test    eax, eax
0x14004aceb  jnz     loc_14004ADDC
0x14004acf1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004acf6  mov     rcx, rax
0x14004acf9  xor     edi, edi
0x14004acfb  test    rax, rax
0x14004acfe  jz      loc_14004B031
0x14004ad04  mov     rax, [rax]
0x14004ad07  call    qword ptr [rax+18h]
0x14004ad0a  lea     r14, [rax+18h]
0x14004ad0e  mov     [rsp+530h+var_4D0], r14
0x14004ad13  test    r13, r13
0x14004ad16  jz      short loc_14004AD6D
0x14004ad18  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004ad1c  mov     r8, rbx
0x14004ad1f  inc     r8
0x14004ad22  cmp     [r13+r8*2+0], di
0x14004ad28  jnz     short loc_14004AD1F
0x14004ad2a  mov     rdx, r13
0x14004ad2d  lea     rcx, [rsp+530h+var_4D0]
0x14004ad32  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14004ad37  mov     edx, 5Ch ; '\'
0x14004ad3c  lea     rcx, [rsp+530h+var_4D0]
0x14004ad41  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x14004ad46  lea     rax, [rbp+430h+SubKey]
0x14004ad4a  mov     r8, rbx
0x14004ad4d  inc     r8
0x14004ad50  cmp     [rax+r8*2], di
0x14004ad55  jnz     short loc_14004AD4D
0x14004ad57  lea     rdx, [rbp+430h+SubKey]
0x14004ad5b  lea     rcx, [rsp+530h+var_4D0]
0x14004ad60  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14004ad65  mov     rbx, [rsp+530h+var_4D0]
0x14004ad6a  mov     r14, rbx
0x14004ad6d  mov     [rsp+530h+lpcchClass], rbx; unsigned __int16 *
0x14004ad72  mov     [rsp+530h+lpClass], r12; struct IRegistryFilter *
0x14004ad77  mov     rax, [rbp+430h+var_488]
0x14004ad7b  mov     [rsp+530h+phkResult], rax; hToken
0x14004ad80  mov     r9d, [rbp+430h+dwOptions]; unsigned int
0x14004ad84  mov     r8, [rbp+430h+var_4A0]; HKEY
0x14004ad88  lea     rdx, [rbp+430h+SubKey]; unsigned __int16 *
0x14004ad8c  mov     rcx, [rbp+430h+hKey]; HKEY
0x14004ad90  call    ?VsRegCopyTree@@YA_JPEAUHKEY__@@PEBG0KPEAXPEAUIRegistryFilter@@1@Z; VsRegCopyTree(HKEY__ *,ushort const *,HKEY__ *,ulong,void *,IRegistryFilter *,ushort const *)
0x14004ad95  mov     rdi, rax
0x14004ad98  mov     rcx, [rbp+430h+var_4A0]; hKey
0x14004ad9c  call    cs:__imp_RegCloseKey
0x14004ada2  nop
0x14004ada3  lea     rdx, [r14-18h]
0x14004ada7  or      ecx, 0FFFFFFFFh
0x14004adaa  lock xadd [rdx+10h], ecx
0x14004adaf  xor     ebx, ebx
0x14004adb1  sub     ecx, 1
0x14004adb4  jg      short loc_14004ADC2
0x14004adb6  lfence
0x14004adb9  mov     rcx, [rdx]
0x14004adbc  mov     rax, [rcx]
0x14004adbf  call    qword ptr [rax+8]
0x14004adc2  mov     r14d, [rbp+430h+dwOptions]
0x14004adc6  inc     r15d
0x14004adc9  mov     eax, 104h
0x14004adce  mov     [rbp+430h+cchName], eax
0x14004add1  mov     [rbp+430h+cchClass], eax
0x14004add4  test    edi, edi
0x14004add6  jz      loc_14004AC3B
0x14004addc  cmp     edi, 103h
0x14004ade2  jnz     loc_14004AFDA
0x14004ade8  mov     [rsp+530h+var_4D8], rbx; lpftLastWriteTime
0x14004aded  mov     [rsp+530h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x14004adf2  lea     rax, [rbp+430h+dwOptions]
0x14004adf6  mov     [rsp+530h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14004adfb  mov     [rsp+530h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x14004ae00  mov     [rsp+530h+lpftLastWriteTime], rbx; lpcValues
0x14004ae05  mov     [rsp+530h+lpcchClass], rbx; lpcbMaxClassLen
0x14004ae0a  mov     [rsp+530h+lpClass], rbx; lpcbMaxSubKeyLen
0x14004ae0f  mov     [rsp+530h+phkResult], rbx; lpcSubKeys
0x14004ae14  xor     r9d, r9d; lpReserved
0x14004ae17  xor     r8d, r8d; lpcchClass
0x14004ae1a  xor     edx, edx; lpClass
0x14004ae1c  mov     rcx, [rbp+430h+hKey]; hKey
0x14004ae20  call    cs:__imp_RegQueryInfoKeyW
0x14004ae26  mov     edi, eax
0x14004ae28  test    eax, eax
0x14004ae2a  jnz     loc_14004AFD4
0x14004ae30  mov     ecx, [rbp+430h+dwOptions]
0x14004ae33  inc     ecx; unsigned __int64
0x14004ae35  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14004ae3a  mov     rbx, rax
0x14004ae3d  mov     [rbp+430h+var_488], rax
0x14004ae41  xor     edi, edi
0x14004ae43  test    rax, rax
0x14004ae46  jz      loc_14004AFC5
0x14004ae4c  mov     r8d, [rbp+430h+dwOptions]; Size
0x14004ae50  xor     edx, edx; Val
0x14004ae52  mov     rcx, rax; void *
0x14004ae55  call    memset_0
0x14004ae5a  mov     r15d, [rbp+430h+dwOptions]
0x14004ae5e  mov     r14d, edi
0x14004ae61  mov     [rbp+430h+cchName], 104h
0x14004ae68  lea     rax, [rbp+430h+dwOptions]
0x14004ae6c  mov     [rsp+530h+lpftLastWriteTime], rax; lpcbData
0x14004ae71  mov     [rsp+530h+lpcchClass], rbx; lpData
0x14004ae76  lea     rax, [rbp+430h+Type]
0x14004ae7a  mov     [rsp+530h+lpClass], rax; lpType
0x14004ae7f  mov     [rsp+530h+phkResult], rdi; lpReserved
0x14004ae84  lea     r9, [rbp+430h+cchName]; lpcchValueName
0x14004ae88  lea     r8, [rbp+430h+SubKey]; lpValueName
0x14004ae8c  mov     edx, r14d; dwIndex
0x14004ae8f  mov     rcx, [rbp+430h+hKey]; hKey
0x14004ae93  call    cs:__imp_RegEnumValueW
0x14004ae99  mov     edi, eax
0x14004ae9b  test    eax, eax
0x14004ae9d  jnz     loc_14004AFCA
0x14004aea3  xor     edi, edi
0x14004aea5  test    r12, r12
0x14004aea8  jz      short loc_14004AEC3
0x14004aeaa  mov     rax, [r12]
0x14004aeae  lea     r8, [rbp+430h+SubKey]
0x14004aeb2  mov     rdx, r13
0x14004aeb5  mov     rcx, r12
0x14004aeb8  call    qword ptr [rax+18h]
0x14004aebb  test    al, al
0x14004aebd  jz      loc_14004AFB9
0x14004aec3  cmp     cs:?ms_bLoggingOn@CLogger@@0_NA, dil; bool CLogger::ms_bLoggingOn
0x14004aeca  jz      loc_14004AF8F
0x14004aed0  mov     [rsp+530h+lpClass], rdi; lpcbData
0x14004aed5  mov     [rsp+530h+phkResult], rdi; lpData
0x14004aeda  xor     r9d, r9d; lpType
0x14004aedd  xor     r8d, r8d; lpReserved
0x14004aee0  lea     rdx, [rbp+430h+SubKey]; lpValueName
0x14004aee4  mov     rcx, [rsp+530h+var_4C0]; hKey
0x14004aee9  call    cs:__imp_RegQueryValueExW
0x14004aeef  mov     edi, eax
0x14004aef1  cmp     eax, 2
0x14004aef4  jz      loc_14004AF8F
0x14004aefa  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004aeff  test    rax, rax
0x14004af02  jz      loc_14004B023
0x14004af08  mov     rdx, [rax]
0x14004af0b  mov     rcx, rax
0x14004af0e  call    qword ptr [rdx+18h]
0x14004af11  add     rax, 18h
0x14004af15  mov     [rsp+530h+var_4D0], rax
0x14004af1a  lea     r8, [rbp+430h+SubKey]
0x14004af1e  lea     rcx, [rsp+530h+var_4D0]
0x14004af23  test    edi, edi
0x14004af25  jnz     short loc_14004AF47
0x14004af27  lea     rdx, aPkgdefMergeReg; "PkgDef merge registry encountered data "...
0x14004af2e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14004af33  xor     r8d, r8d; unsigned __int16 *
0x14004af36  xor     edx, edx; int
0x14004af38  mov     rdi, [rsp+530h+var_4D0]
0x14004af3d  mov     rcx, rdi; unsigned __int16 *
0x14004af40  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14004af45  jmp     short loc_14004AF72
0x14004af47  lea     rdx, aErrorWhileMerg; "Error while merging value '%s'"
0x14004af4e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14004af53  movzx   edx, di
0x14004af56  or      edx, 80070000h
0x14004af5c  test    edi, edi
0x14004af5e  cmovle  edx, edi; int
0x14004af61  xor     r8d, r8d; unsigned __int16 *
0x14004af64  mov     rdi, [rsp+530h+var_4D0]
0x14004af69  mov     rcx, rdi; unsigned __int16 *
0x14004af6c  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14004af71  nop
0x14004af72  lea     rdx, [rdi-18h]
0x14004af76  or      eax, 0FFFFFFFFh
0x14004af79  lock xadd [rdx+10h], eax
0x14004af7e  sub     eax, 1
0x14004af81  jg      short loc_14004AF8F
0x14004af83  lfence
0x14004af86  mov     rcx, [rdx]
0x14004af89  mov     rax, [rcx]
0x14004af8c  call    qword ptr [rax+8]
0x14004af8f  mov     eax, [rbp+430h+dwOptions]
0x14004af92  mov     dword ptr [rsp+530h+lpClass], eax; cbData
0x14004af96  mov     [rsp+530h+phkResult], rbx; lpData
0x14004af9b  mov     r9d, [rbp+430h+Type]; dwType
0x14004af9f  xor     r8d, r8d; Reserved
0x14004afa2  lea     rdx, [rbp+430h+SubKey]; lpValueName
0x14004afa6  mov     rcx, [rsp+530h+var_4C0]; hKey
0x14004afab  call    cs:__imp_RegSetValueExW
0x14004afb1  mov     edi, eax
0x14004afb3  test    eax, eax
0x14004afb5  jnz     short loc_14004AFCA
0x14004afb7  xor     edi, edi
0x14004afb9  inc     r14d
0x14004afbc  mov     [rbp+430h+dwOptions], r15d
0x14004afc0  jmp     loc_14004AE61
0x14004afc5  mov     edi, 0Eh
0x14004afca  mov     rcx, rbx; void *
0x14004afcd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004afd2  xor     ebx, ebx
0x14004afd4  cmp     edi, 103h
0x14004afda  cmovnz  ebx, edi
0x14004afdd  xor     r15d, r15d
0x14004afe0  cmp     [rsp+530h+var_4B8], r15
0x14004afe5  jz      short loc_14004AFF2
0x14004afe7  mov     rcx, [rbp+430h+hKey]; hKey
0x14004afeb  call    cs:__imp_RegCloseKey
0x14004aff1  nop
0x14004aff2  test    sil, sil
0x14004aff5  jz      short loc_14004AFFD
0x14004aff7  call    cs:__imp_RevertToSelf
0x14004affd  mov     rax, rbx
  ... truncated ...
```
