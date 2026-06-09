# Microsoft::InformationProtection::CProtectedFile::QueryCLSIDFromRegistry(_GUID *)

- ea: `0x180053d94`
- end: `0x18005409d`
- name: `?QueryCLSIDFromRegistry@CProtectedFile@InformationProtection@Microsoft@@AEAA_NPEAU_GUID@@@Z`
- size: `777`
- prototype: `char __fastcall(void **this, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180053b68`

## callees

- `0x180001284`
- `0x18000343a`
- `0x18002913c`
- `0x18002950c`
- `0x18002aa30`
- `0x1800516b8`
- `0x180052a30`
- `0x180053598`
- `0x180053c68`
- `0x180053d94`
- `0x1800573dc`
- `0x1800574fc`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053e85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053e85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053ead`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180053ead`
- `ole32!CLSIDFromString` at `0x180053f39`
- `ole32!CLSIDFromString` at `0x180053f39`

## string_xrefs

- `0x180054074`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\protectedfile\cprotectedfile.cpp`
- `0x180054067`: `CLSIDFromString(wstrLocalValue.c_str(), pclsid)`
- `0x180053fe9`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.cpp`
- `0x18005403a`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.cpp`
- `0x18005401d`: `Failure opening registry key '%ws'.`
- `0x18005402d`: `RegOpenKeyEx(hRoot, pszSubkey, 0, fAccess, &m_hKey)`

## pseudocode

```c
char __fastcall Microsoft::InformationProtection::CProtectedFile::QueryCLSIDFromRegistry(void **this, struct _GUID *a2)
{
  const WCHAR *v4; // rbx
  int v5; // ecx
  __int64 v6; // rax
  const WCHAR *v7; // rcx
  LSTATUS v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  LPCOLESTR *v11; // r8
  const OLECHAR *v12; // rcx
  HRESULT v13; // eax
  int v15; // eax
  unsigned int v16; // [rsp+40h] [rbp-ED8h] BYREF
  HKEY hKey[2]; // [rsp+48h] [rbp-ED0h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+58h] [rbp-EC0h] BYREF
  unsigned __int64 v19; // [rsp+68h] [rbp-EB0h]
  unsigned __int64 v20; // [rsp+70h] [rbp-EA8h]
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-E98h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp-E80h]
  _BYTE pExceptionObject[1216]; // [rsp+B0h] [rbp-E68h] BYREF
  _BYTE v24[1216]; // [rsp+570h] [rbp-9A8h] BYREF
  _BYTE v25[1216]; // [rsp+A30h] [rbp-4E8h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v22 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  std::wstring::assign(lpSubKey, (void *)&Src);
  hKey[0] = 0;
  std::wstring::operator+=(lpSubKey, L"SOFTWARE\\Microsoft\\MSDRM\\Protectors\\");
  std::wstring::operator+=(lpSubKey, this[1]);
  try
  {
    if ( v22 < 8 )
    {
      v4 = (const WCHAR *)lpSubKey;
    }
    else
    {
      v4 = lpSubKey[0];
      if ( !lpSubKey[0] )
      {
        v5 = -2147024809;
LABEL_10:
        if ( v5 < 0 )
        {
          Microsoft::FoundationServices::Common::FsException::FsException(
            (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
            L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.cpp",
            0x5Du,
            L"StringCchLength(pszSubkey, STRSAFE_MAX_CCH, 0)",
            v5);
          throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
        }
        hKey[0] = 0;
        v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, hKey);
        if ( v8 )
        {
          v15 = HR_FROM_WIN32(v8);
          Microsoft::FoundationServices::Common::FsException::FsException(
            (Microsoft::FoundationServices::Common::FsException *)v24,
            L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.cpp",
            0x62u,
            L"RegOpenKeyEx(hRoot, pszSubkey, 0, fAccess, &m_hKey)",
            v15,
            L"Failure opening registry key '%ws'.",
            v4);
          throw (Microsoft::FoundationServices::Common::FsException *)v24;
        }
        goto LABEL_31;
      }
    }
    v6 = 0x7FFFFFFF;
    v7 = v4;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v5 = v6 == 0 ? 0x80070057 : 0;
    goto LABEL_10;
  }
  catch ( ... )
  {
    Microsoft::InformationProtection::IppUtil::HandlePublicAPIException();
  }
LABEL_31:
  v16 = 0;
  v20 = 7;
  v19 = 0;
  LOWORD(lpsz[0]) = 0;
  Microsoft::FoundationServices::Common::Registry::Read<unsigned short>(hKey, v9, 0, &v16);
  if ( v16 > v19 )
    std::wstring::append(lpsz, v16 - v19);
  else
    std::wstring::erase(lpsz, v16, -1);
  v11 = lpsz;
  if ( v20 >= 8 )
    v11 = (LPCOLESTR *)lpsz[0];
  Microsoft::FoundationServices::Common::Registry::Read<unsigned short>(hKey, v10, v11, &v16);
  v12 = (const OLECHAR *)lpsz;
  if ( v20 >= 8 )
    v12 = lpsz[0];
  v13 = CLSIDFromString(v12, a2);
  if ( v13 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)v25,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\protectedfile\\cprotectedfile.cpp",
      0x9Eu,
      L"CLSIDFromString(wstrLocalValue.c_str(), pclsid)",
      v13);
    throw (Microsoft::FoundationServices::Common::FsException *)v25;
  }
  if ( v20 >= 8 )
    operator delete((void *)lpsz[0]);
  v20 = 7;
  v19 = 0;
  LOWORD(lpsz[0]) = 0;
  Microsoft::FoundationServices::Common::Registry::~Registry((Microsoft::FoundationServices::Common::Registry *)hKey);
  if ( v22 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return 1;
}

```

## disassembly

```asm
0x180053d94  mov     r11, rsp
0x180053d97  push    rsi
0x180053d98  push    rdi
0x180053d99  push    r14
0x180053d9b  sub     rsp, 0F00h
0x180053da2  mov     [rsp+0F18h+var_EC8], 0FFFFFFFFFFFFFFFEh
0x180053dab  mov     [r11+18h], rbx
0x180053daf  mov     rax, cs:__security_cookie
0x180053db6  xor     rax, rsp
0x180053db9  mov     [rsp+0F18h+var_28], rax
0x180053dc1  mov     rdi, rdx
0x180053dc4  mov     rbx, rcx
0x180053dc7  mov     r14d, 7
0x180053dcd  mov     [r11-0E80h], r14
0x180053dd4  xor     esi, esi
0x180053dd6  mov     [r11-0E88h], rsi
0x180053ddd  mov     word ptr [rsp+0F18h+lpSubKey], si
0x180053de5  xor     r8d, r8d
0x180053de8  lea     rdx, Src; Src
0x180053def  lea     rcx, [r11-0E98h]; void *
0x180053df6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180053dfb  nop
0x180053dfc  mov     [rsp+0F18h+hKey], rsi
0x180053e01  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MSDRM\\Protectors"...
0x180053e08  lea     rcx, [rsp+0F18h+lpSubKey]; Src
0x180053e10  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180053e15  mov     rdx, [rbx+8]; void *
0x180053e19  lea     rcx, [rsp+0F18h+lpSubKey]; Src
0x180053e21  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180053e26  nop
0x180053e27  cmp     [rsp+0F18h+var_E80], 8
0x180053e30  jb      short loc_180053E46
0x180053e32  mov     rbx, [rsp+0F18h+lpSubKey]
0x180053e3a  test    rbx, rbx
0x180053e3d  jnz     short loc_180053E4E
0x180053e3f  mov     ecx, 80070057h
0x180053e44  jmp     short loc_180053E73
0x180053e46  lea     rbx, [rsp+0F18h+lpSubKey]
0x180053e4e  mov     eax, 7FFFFFFFh
0x180053e53  mov     rcx, rbx
0x180053e56  cmp     [rcx], si
0x180053e59  jz      short loc_180053E65
0x180053e5b  add     rcx, 2
0x180053e5f  sub     rax, 1
0x180053e63  jnz     short loc_180053E56
0x180053e65  neg     rax
0x180053e68  sbb     eax, eax
0x180053e6a  not     eax
0x180053e6c  mov     ecx, 80070057h
0x180053e71  and     ecx, eax
0x180053e73  test    ecx, ecx
0x180053e75  js      loc_180053FD8
0x180053e7b  mov     rcx, [rsp+0F18h+hKey]; hKey
0x180053e80  test    rcx, rcx
0x180053e83  jz      short loc_180053E8B
0x180053e85  call    cs:__imp_RegCloseKey
0x180053e8b  mov     [rsp+0F18h+hKey], rsi
0x180053e90  lea     rax, [rsp+0F18h+hKey]
0x180053e95  mov     [rsp+0F18h+phkResult], rax; phkResult
0x180053e9a  mov     r9d, 20019h; samDesired
0x180053ea0  xor     r8d, r8d; ulOptions
0x180053ea3  mov     rdx, rbx; lpSubKey
0x180053ea6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180053ead  call    cs:__imp_RegOpenKeyExW
0x180053eb3  test    eax, eax
0x180053eb5  jnz     loc_180054011
0x180053ebb  mov     [rsp+0F18h+var_ED8], esi
0x180053ebf  mov     [rsp+0F18h+var_EA8], r14
0x180053ec4  mov     [rsp+0F18h+var_EB0], rsi
0x180053ec9  mov     word ptr [rsp+0F18h+lpsz], si
0x180053ece  lea     r9, [rsp+0F18h+var_ED8]
0x180053ed3  xor     r8d, r8d
0x180053ed6  lea     rcx, [rsp+0F18h+hKey]
0x180053edb  call    ??$Read@G@Registry@Common@FoundationServices@Microsoft@@QEAAXPEBGPEAGPEAKK@Z; Microsoft::FoundationServices::Common::Registry::Read<ushort>(ushort const *,ushort *,ulong *,ulong)
0x180053ee0  mov     edx, [rsp+0F18h+var_ED8]
0x180053ee4  lea     rcx, [rsp+0F18h+lpsz]
0x180053ee9  cmp     rdx, [rsp+0F18h+var_EB0]
0x180053eee  ja      short loc_180053EFB
0x180053ef0  or      r8, 0FFFFFFFFFFFFFFFFh
0x180053ef4  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180053ef9  jmp     short loc_180053F05
0x180053efb  sub     rdx, [rsp+0F18h+var_EB0]
0x180053f00  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180053f05  lea     r8, [rsp+0F18h+lpsz]
0x180053f0a  cmp     [rsp+0F18h+var_EA8], 8
0x180053f10  cmovnb  r8, [rsp+0F18h+lpsz]
0x180053f16  lea     r9, [rsp+0F18h+var_ED8]
0x180053f1b  lea     rcx, [rsp+0F18h+hKey]
0x180053f20  call    ??$Read@G@Registry@Common@FoundationServices@Microsoft@@QEAAXPEBGPEAGPEAKK@Z; Microsoft::FoundationServices::Common::Registry::Read<ushort>(ushort const *,ushort *,ulong *,ulong)
0x180053f25  lea     rcx, [rsp+0F18h+lpsz]
0x180053f2a  cmp     [rsp+0F18h+var_EA8], 8
0x180053f30  cmovnb  rcx, [rsp+0F18h+lpsz]; lpsz
0x180053f36  mov     rdx, rdi; pclsid
0x180053f39  call    cs:__imp_CLSIDFromString
0x180053f3f  test    eax, eax
0x180053f41  js      loc_180054063
0x180053f47  cmp     [rsp+0F18h+var_EA8], 8
0x180053f4d  jb      short loc_180053F59
0x180053f4f  mov     rcx, [rsp+0F18h+lpsz]; Block
0x180053f54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053f59  mov     [rsp+0F18h+var_EA8], r14
0x180053f5e  mov     [rsp+0F18h+var_EB0], rsi
0x180053f63  mov     word ptr [rsp+0F18h+lpsz], si
0x180053f68  lea     rcx, [rsp+0F18h+hKey]; this
0x180053f6d  call    ??1Registry@Common@FoundationServices@Microsoft@@QEAA@XZ; Microsoft::FoundationServices::Common::Registry::~Registry(void)
0x180053f72  nop
0x180053f73  cmp     [rsp+0F18h+var_E80], 8
0x180053f7c  jb      short loc_180053F8B
0x180053f7e  mov     rcx, [rsp+0F18h+lpSubKey]; Block
0x180053f86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053f8b  mov     al, 1
0x180053f8d  mov     rcx, [rsp+0F18h+var_28]
0x180053f95  xor     rcx, rsp; StackCookie
0x180053f98  call    __security_check_cookie
0x180053f9d  mov     rbx, [rsp+0F18h+arg_10]
0x180053fa5  add     rsp, 0F00h
0x180053fac  pop     r14
0x180053fae  pop     rdi
0x180053faf  pop     rsi
0x180053fb0  retn
0x180053fb1  lea     rcx, [rsp+0F18h+hKey]; this
0x180053fb6  call    ??1Registry@Common@FoundationServices@Microsoft@@QEAA@XZ; Microsoft::FoundationServices::Common::Registry::~Registry(void)
0x180053fbb  nop
0x180053fbc  cmp     [rsp+0F18h+var_E80], 8
0x180053fc5  jb      short loc_180053FD4
0x180053fc7  mov     rcx, [rsp+0F18h+lpSubKey]; Block
0x180053fcf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053fd4  xor     al, al
0x180053fd6  jmp     short loc_180053F8D
0x180053fd8  mov     dword ptr [rsp+0F18h+phkResult], ecx; int
0x180053fdc  lea     r9, aStringcchlengt_2; "StringCchLength(pszSubkey, STRSAFE_MAX_"...
0x180053fe3  mov     r8d, 5Dh ; ']'; unsigned int
0x180053fe9  lea     rdx, aDsSecurityRmSr_10; "ds\\security\\rm\\src\\client\\promethi"...
0x180053ff0  lea     rcx, [rsp+0F18h+pExceptionObject]; this
0x180053ff8  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180053ffd  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180054004  lea     rcx, [rsp+0F18h+pExceptionObject]; pExceptionObject
0x18005400c  call    _CxxThrowException_0
0x180054011  mov     ecx, eax; unsigned int
0x180054013  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180054018  mov     [rsp+0F18h+var_EE8], rbx
0x18005401d  lea     rcx, aFailureOpening; "Failure opening registry key '%ws'."
0x180054024  mov     [rsp+0F18h+var_EF0], rcx; unsigned __int16 *
0x180054029  mov     dword ptr [rsp+0F18h+phkResult], eax; int
0x18005402d  lea     r9, aRegopenkeyexHr; "RegOpenKeyEx(hRoot, pszSubkey, 0, fAcce"...
0x180054034  mov     r8d, 62h ; 'b'; unsigned int
0x18005403a  lea     rdx, aDsSecurityRmSr_10; "ds\\security\\rm\\src\\client\\promethi"...
0x180054041  lea     rcx, [rsp+0F18h+var_9A8]; this
0x180054049  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J0ZZ; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18005404e  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180054055  lea     rcx, [rsp+0F18h+var_9A8]; pExceptionObject
0x18005405d  call    _CxxThrowException_0
0x180054063  mov     dword ptr [rsp+0F18h+phkResult], eax; int
0x180054067  lea     r9, aClsidfromstrin_0; "CLSIDFromString(wstrLocalValue.c_str(),"...
0x18005406e  mov     r8d, 9Eh; unsigned int
0x180054074  lea     rdx, aDsSecurityRmSr_0; "ds\\security\\rm\\src\\client\\promethi"...
0x18005407b  lea     rcx, [rsp+0F18h+var_4E8]; this
0x180054083  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180054088  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005408f  lea     rcx, [rsp+0F18h+var_4E8]; pExceptionObject
0x180054097  call    _CxxThrowException_0
```
