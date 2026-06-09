# OleStdGetAuxUserType(_GUID const &,ushort,ushort *,uint,HKEY__ *)

- ea: `0x18004f860`
- end: `0x18004fb06`
- name: `?OleStdGetAuxUserType@@YAJAEBU_GUID@@GPEAGIPEAUHKEY__@@@Z`
- size: `678`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned __int16 auxUserType, wchar_t *clsid, unsigned int whichAuxUserType, HKEY__ *auxUserType)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180099cf0`
- `0x180099e50`

## callees

- `0x18001775c`
- `0x1800185ec`
- `0x18001a3c8`
- `0x18001b0e4`
- `0x1800242c4`
- `0x180034bfc`
- `0x180036488`
- `0x18004bafc`
- `0x18004f860`
- `0x18004fdfc`
- `0x18004fe20`
- `0x180052390`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f9e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fa44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f9e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fa44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fad0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fa13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004fa13`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18004fa81`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18004fa81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f92c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f92c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f8e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f8e0`

## string_xrefs

- `0x18004f90a`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004f9c3`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004fa24`: `com\ole32\ole232\stdimpl\icon.cpp`
- `0x18004f9a1`: `CLSID\%ls\AuxUserType\%d`

## pseudocode

```c
__int64 __fastcall OleStdGetAuxUserType(
        const _GUID *clsid,
        unsigned __int16 auxUserType,
        wchar_t *a3,
        unsigned int whichAuxUserType)
{
  int v6; // eax
  HSTRING__ *m_ptr; // rcx
  unsigned int v8; // ebx
  const wchar_t *StringRawBuffer; // rax
  HRESULT v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // edx
  const char *v13; // r8
  HKEY__ *v14; // rsi
  HRESULT v15; // eax
  LSTATUS v16; // eax
  int v17; // eax
  int buffer; // [rsp+20h] [rbp-E0h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > openedKey; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > typeKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int valueSize; // [rsp+50h] [rbp-B0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > displayNameStringOrResourceReference; // [rsp+58h] [rbp-A8h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+60h] [rbp-A0h] BYREF
  GuidString clsidString; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szKey[256]; // [rsp+C0h] [rbp-40h] BYREF
  void *retaddr; // [rsp+2E8h] [rbp+1E8h]

  *a3 = 0;
  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    displayNameStringOrResourceReference.m_ptr = 0;
    v6 = ((__int64 (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))oleClassInfo.m_ptr->lpVtbl[2].QueryInterface)(
           oleClassInfo.m_ptr,
           &displayNameStringOrResourceReference);
    m_ptr = displayNameStringOrResourceReference.m_ptr;
    v8 = v6;
    if ( v6 < 0 )
      goto LABEL_5;
    StringRawBuffer = WindowsGetStringRawBuffer(displayNameStringOrResourceReference.m_ptr, 0);
    v10 = ResolveStringOrResourceReference(0, 0, StringRawBuffer, 0x2Au, a3);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x6EBu, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v10);
      m_ptr = displayNameStringOrResourceReference.m_ptr;
LABEL_5:
      if ( m_ptr )
        WindowsDeleteString(m_ptr);
      goto LABEL_28;
    }
    if ( displayNameStringOrResourceReference.m_ptr )
      WindowsDeleteString(displayNameStringOrResourceReference.m_ptr);
LABEL_27:
    v8 = 0;
    goto LABEL_28;
  }
  openedKey.m_ptr = 0;
  v11 = OpenClassesRootKeyExW(0, 0x2000000u, &openedKey.m_ptr);
  if ( v11 )
  {
    wil::details::in1diag3::Log_Win32(retaddr, v12, v13, v11);
LABEL_25:
    if ( openedKey.m_ptr )
      RegCloseKey(openedKey.m_ptr);
    goto LABEL_27;
  }
  v14 = openedKey.m_ptr;
  GuidString::GuidString(&clsidString, clsid);
  buffer = 2;
  v15 = StringCchPrintfW(szKey, 0x100u, L"CLSID\\%ls\\AuxUserType\\%d", &clsidString, buffer);
  v8 = v15;
  if ( v15 >= 0 )
  {
    typeKey.m_ptr = 0;
    v16 = RegOpenKeyExW(v14, szKey, 0, 0x20019u, &typeKey.m_ptr);
    if ( v16 )
    {
      v8 = wil::details::in1diag3::Return_Win32(retaddr, 0x705u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v16);
    }
    else
    {
      valueSize = 84;
      if ( !RegLoadMUIStringW(typeKey.m_ptr, L"LocalizedString", a3, 0x54u, 0, 1u, 0)
        || (valueSize = 84, v17 = wRegQueryValue(v14, szKey, a3, &valueSize), (v8 = v17) == 0) )
      {
        if ( typeKey.m_ptr )
          RegCloseKey(typeKey.m_ptr);
        goto LABEL_25;
      }
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
    }
    if ( typeKey.m_ptr )
      RegCloseKey(typeKey.m_ptr);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x701u, "com\\ole32\\ole232\\stdimpl\\icon.cpp", v15);
  }
  if ( openedKey.m_ptr )
    RegCloseKey(openedKey.m_ptr);
LABEL_28:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return v8;
}

```

## disassembly

```asm
0x18004f860  mov     [rsp-8+arg_8], rbx
0x18004f865  push    rbp
0x18004f866  push    rsi
0x18004f867  push    rdi
0x18004f868  lea     rbp, [rsp-1D0h]
0x18004f870  sub     rsp, 2D0h
0x18004f877  mov     rax, cs:__security_cookie
0x18004f87e  xor     rax, rsp
0x18004f881  mov     [rbp+1E0h+var_20], rax
0x18004f888  xor     eax, eax
0x18004f88a  lea     r9, [rsp+2E0h+oleClassInfo]; ppv
0x18004f88f  mov     [auxUserType], ax
0x18004f893  mov     rdi, auxUserType
0x18004f896  lea     auxUserType, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18004f89d  mov     [rsp+2E0h+oleClassInfo.m_ptr], rax
0x18004f8a2  xor     edx, edx; pComCatalog
0x18004f8a4  mov     rbx, clsid
0x18004f8a7  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18004f8ac  test    eax, eax
0x18004f8ae  js      loc_18004F950
0x18004f8b4  mov     clsid, [rsp+2E0h+oleClassInfo.m_ptr]
0x18004f8b9  lea     rdx, [rsp+2E0h+displayNameStringOrResourceReference]
0x18004f8be  mov     [rsp+2E0h+displayNameStringOrResourceReference.m_ptr], 0
0x18004f8c7  mov     rax, [clsid]
0x18004f8ca  mov     rax, [rax+30h]
0x18004f8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8d3  mov     clsid, [rsp+2E0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004f8d8  mov     ebx, eax
0x18004f8da  test    eax, eax
0x18004f8dc  js      short loc_18004F923
0x18004f8de  xor     edx, edx; length
0x18004f8e0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004f8e6  mov     r9d, 2Ah ; '*'; bufferSize
0x18004f8ec  mov     [rsp+2E0h+buffer], rdi; buffer
0x18004f8f1  mov     auxUserType, rax; stringOrResourceReference
0x18004f8f4  xor     edx, edx; resourceContext
0x18004f8f6  xor     ecx, ecx; providedResourceManager
0x18004f8f8  call    ?ResolveStringOrResourceReference@@YAJPEAUIMrtResourceManager@@PEAUIResourceContext@@PEBG_KPEAG@Z; ResolveStringOrResourceReference(IMrtResourceManager *,IResourceContext *,ushort const *,unsigned __int64,ushort *)
0x18004f8fd  mov     ebx, eax
0x18004f8ff  test    eax, eax
0x18004f901  jns     short loc_18004F937
0x18004f903  mov     clsid, [rbp+1E8h]; callerReturnAddress
0x18004f90a  lea     auxUserType, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004f911  mov     r9d, eax; hr
0x18004f914  mov     edx, 6EBh; lineNumber
0x18004f919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f91e  mov     clsid, [rsp+2E0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004f923  test    clsid, clsid
0x18004f926  jz      loc_18004FAD8
0x18004f92c  call    cs:__imp_WindowsDeleteString
0x18004f932  jmp     loc_18004FAD8
0x18004f937  mov     clsid, [rsp+2E0h+displayNameStringOrResourceReference.m_ptr]; string
0x18004f93c  test    clsid, clsid
0x18004f93f  jz      loc_18004FAD6
0x18004f945  call    cs:__imp_WindowsDeleteString
0x18004f94b  jmp     loc_18004FAD6
0x18004f950  lea     auxUserType, [rsp+2E0h+openedKey]; phkResult
0x18004f955  mov     [rsp+2E0h+openedKey.m_ptr], 0
0x18004f95e  mov     edx, 2000000h; samDesired
0x18004f963  xor     ecx, ecx; pszSubKey
0x18004f965  call    OpenClassesRootKeyExW
0x18004f96a  test    eax, eax
0x18004f96c  jz      short loc_18004F982
0x18004f96e  mov     clsid, [rbp+1E8h]; callerReturnAddress
0x18004f975  mov     r9d, eax; lineNumber
0x18004f978  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18004f97d  jmp     loc_18004FAC6
0x18004f982  mov     rsi, [rsp+2E0h+openedKey.m_ptr]
0x18004f987  lea     clsid, [rsp+2E0h+clsidString]; this
0x18004f98c  mov     rdx, rbx; guid
0x18004f98f  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18004f994  lea     r9, [rsp+2E0h+clsidString]
0x18004f999  mov     dword ptr [rsp+2E0h+buffer], 2
0x18004f9a1  lea     auxUserType, aClsidLsAuxuser; "CLSID\\%ls\\AuxUserType\\%d"
0x18004f9a8  mov     edx, 100h; cchDest
0x18004f9ad  lea     clsid, [rbp+1E0h+szKey]; pszDest
0x18004f9b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f9b6  mov     ebx, eax
0x18004f9b8  test    eax, eax
0x18004f9ba  jns     short loc_18004F9F0
0x18004f9bc  mov     clsid, [rbp+1E8h]; callerReturnAddress
0x18004f9c3  lea     auxUserType, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004f9ca  mov     r9d, eax; hr
0x18004f9cd  mov     edx, 701h; lineNumber
0x18004f9d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f9d7  mov     clsid, [rsp+2E0h+openedKey.m_ptr]; hKey
0x18004f9dc  test    clsid, clsid
0x18004f9df  jz      loc_18004FAD8
0x18004f9e5  call    cs:__imp_RegCloseKey
0x18004f9eb  jmp     loc_18004FAD8
0x18004f9f0  lea     rax, [rsp+2E0h+typeKey]
0x18004f9f5  mov     [rsp+2E0h+typeKey.m_ptr], 0
0x18004f9fe  mov     r9d, 20019h; samDesired
0x18004fa04  mov     [rsp+2E0h+buffer], rax; phkResult
0x18004fa09  xor     r8d, r8d; ulOptions
0x18004fa0c  lea     rdx, [rbp+1E0h+szKey]; lpSubKey
0x18004fa10  mov     clsid, rsi; hKey
0x18004fa13  call    cs:__imp_RegOpenKeyExW
0x18004fa19  test    eax, eax
0x18004fa1b  jz      short loc_18004FA4C
0x18004fa1d  mov     clsid, [rbp+1E8h]; callerReturnAddress
0x18004fa24  lea     auxUserType, aComOle32Ole232_6; "com\\ole32\\ole232\\stdimpl\\icon.cpp"
0x18004fa2b  mov     r9d, eax; err
0x18004fa2e  mov     edx, 705h; lineNumber
0x18004fa33  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004fa38  mov     ebx, eax
0x18004fa3a  mov     clsid, [rsp+2E0h+typeKey.m_ptr]; hKey
0x18004fa3f  test    clsid, clsid
0x18004fa42  jz      short loc_18004F9D7
0x18004fa44  call    cs:__imp_RegCloseKey
0x18004fa4a  jmp     short loc_18004F9D7
0x18004fa4c  mov     clsid, [rsp+2E0h+typeKey.m_ptr]; hKey
0x18004fa51  lea     rdx, aLocalizedstrin; "LocalizedString"
0x18004fa58  mov     ebx, 54h ; 'T'
0x18004fa5d  mov     [rsp+2E0h+pszDirectory], 0; pszDirectory
0x18004fa66  mov     r9d, ebx; cbOutBuf
0x18004fa69  mov     [rsp+2E0h+Flags], 1; Flags
0x18004fa71  mov     auxUserType, rdi; pszOutBuf
0x18004fa74  mov     [rsp+2E0h+valueSize], ebx
0x18004fa78  mov     [rsp+2E0h+buffer], 0; pcbData
0x18004fa81  call    cs:__imp_RegLoadMUIStringW
0x18004fa87  test    eax, eax
0x18004fa89  jz      short loc_18004FAB6
0x18004fa8b  lea     r9, [rsp+2E0h+valueSize]; lpdwSize
0x18004fa90  mov     [rsp+2E0h+valueSize], ebx
0x18004fa94  mov     auxUserType, rdi; lpValue
0x18004fa97  lea     rdx, [rbp+1E0h+szKey]; lpSubKey
0x18004fa9b  mov     clsid, rsi; hKey
0x18004fa9e  call    wRegQueryValue
0x18004faa3  mov     ebx, eax
0x18004faa5  test    eax, eax
0x18004faa7  jz      short loc_18004FAB6
0x18004faa9  jle     short loc_18004FA3A
0x18004faab  movzx   ebx, ax
0x18004faae  or      ebx, 80070000h
0x18004fab4  jmp     short loc_18004FA3A
0x18004fab6  mov     clsid, [rsp+2E0h+typeKey.m_ptr]; hKey
0x18004fabb  test    clsid, clsid
0x18004fabe  jz      short loc_18004FAC6
0x18004fac0  call    cs:__imp_RegCloseKey
0x18004fac6  mov     clsid, [rsp+2E0h+openedKey.m_ptr]; hKey
0x18004facb  test    clsid, clsid
0x18004face  jz      short loc_18004FAD6
0x18004fad0  call    cs:__imp_RegCloseKey
0x18004fad6  xor     ebx, ebx
0x18004fad8  lea     clsid, [rsp+2E0h+oleClassInfo]; this
0x18004fadd  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18004fae2  mov     eax, ebx
0x18004fae4  mov     clsid, [rbp+1E0h+var_20]
0x18004faeb  xor     clsid, rsp; StackCookie
0x18004faee  call    __security_check_cookie
0x18004faf3  mov     rbx, [rsp+2E0h+arg_8]
0x18004fafb  add     rsp, 2D0h
0x18004fb02  pop     rdi
0x18004fb03  pop     rsi
0x18004fb04  pop     rbp
0x18004fb05  retn
```
