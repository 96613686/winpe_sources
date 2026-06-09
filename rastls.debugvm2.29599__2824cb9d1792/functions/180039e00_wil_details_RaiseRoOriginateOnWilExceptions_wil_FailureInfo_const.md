# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x180039e00`
- end: `0x180039f15`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `277`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800200b4`
- `0x180038250`
- `0x180038270`
- `0x180039e00`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180039ecc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180039ecc`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x180039eaf`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x180039eaf`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x180039e27`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x180039e27`

## string_xrefs

- `0x180039ec3`: `api-ms-win-core-winrt-error-l1-1-1.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::RaiseRoOriginateOnWilExceptions(wil::details *this, const struct wil::FailureInfo *a2)
{
  bool v3; // di
  FARPROC ProcAddress; // rax
  _QWORD v5[2]; // [rsp+30h] [rbp-10h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp+20h] BYREF
  __int64 v7; // [rsp+68h] [rbp+28h] BYREF
  __int64 v8; // [rsp+70h] [rbp+30h] BYREF
  __int64 v9; // [rsp+78h] [rbp+38h] BYREF

  v3 = 1;
  if ( *(_DWORD *)this <= 1u )
  {
    v7 = 0;
    if ( (unsigned int)GetRestrictedErrorInfo(&v7, a2) )
      goto LABEL_8;
    v5[0] = 0;
    LODWORD(phModule) = *((_DWORD *)this + 2);
    v9 = 0;
    v8 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD *, HMODULE *, __int64 *, __int64 *))(*(_QWORD *)v7 + 24LL))(
           v7,
           v5,
           &phModule,
           &v9,
           &v8) >= 0 )
      v3 = *((_DWORD *)this + 2) != (_DWORD)phModule;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v5);
    if ( v3 )
    {
LABEL_8:
      phModule = 0;
      if ( GetModuleHandleExW(0, L"api-ms-win-core-winrt-error-l1-1-1.dll", &phModule) )
      {
        ProcAddress = GetProcAddress(phModule, "RoOriginateErrorW");
        if ( ProcAddress )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(
            *((unsigned int *)this + 2),
            0,
            *((_QWORD *)this + 3));
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
    }
    else if ( v7 )
    {
      SetRestrictedErrorInfo();
    }
    ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v7);
  }
}

```

## disassembly

```asm
0x180039e00  push    rbp
0x180039e02  push    rbx
0x180039e03  push    rdi
0x180039e04  mov     rbp, rsp
0x180039e07  sub     rsp, 40h
0x180039e0b  mov     rbx, rcx
0x180039e0e  mov     edi, 1
0x180039e13  cmp     [rcx], edi
0x180039e15  ja      loc_180039F0D
0x180039e1b  mov     [rbp+arg_8], 0
0x180039e23  lea     rcx, [rbp+arg_8]
0x180039e27  call    cs:__imp_GetRestrictedErrorInfo
0x180039e2d  test    eax, eax
0x180039e2f  jnz     loc_180039EB7
0x180039e35  mov     [rbp+var_10], 0
0x180039e3d  mov     eax, [rbx+8]
0x180039e40  mov     dword ptr [rbp+phModule], eax
0x180039e43  mov     [rbp+arg_18], 0
0x180039e4b  mov     [rbp+arg_10], 0
0x180039e53  mov     rcx, [rbp+arg_8]
0x180039e57  mov     rax, [rcx]
0x180039e5a  lea     rdx, [rbp+arg_10]
0x180039e5e  mov     [rsp+40h+var_20], rdx
0x180039e63  lea     r9, [rbp+arg_18]
0x180039e67  lea     r8, [rbp+phModule]
0x180039e6b  lea     rdx, [rbp+var_10]
0x180039e6f  mov     rax, [rax+18h]
0x180039e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e78  test    eax, eax
0x180039e7a  js      short loc_180039E86
0x180039e7c  mov     eax, dword ptr [rbp+phModule]
0x180039e7f  cmp     [rbx+8], eax
0x180039e82  setnz   dil
0x180039e86  lea     rcx, [rbp+arg_10]
0x180039e8a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039e8f  lea     rcx, [rbp+arg_18]
0x180039e93  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039e98  lea     rcx, [rbp+var_10]
0x180039e9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039ea1  test    dil, dil
0x180039ea4  jnz     short loc_180039EB7
0x180039ea6  mov     rcx, [rbp+arg_8]
0x180039eaa  test    rcx, rcx
0x180039ead  jz      short loc_180039F03
0x180039eaf  call    cs:__imp_SetRestrictedErrorInfo
0x180039eb5  jmp     short loc_180039F03
0x180039eb7  mov     [rbp+phModule], 0
0x180039ebf  lea     r8, [rbp+phModule]; phModule
0x180039ec3  lea     rdx, aApiMsWinCoreWi_4; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x180039eca  xor     ecx, ecx; dwFlags
0x180039ecc  call    cs:__imp_GetModuleHandleExW
0x180039ed2  test    eax, eax
0x180039ed4  jz      short loc_180039EFA
0x180039ed6  lea     rdx, aRooriginateerr; "RoOriginateErrorW"
0x180039edd  mov     rcx, [rbp+phModule]; hModule
0x180039ee1  call    cs:__imp_GetProcAddress
0x180039ee7  test    rax, rax
0x180039eea  jz      short loc_180039EFA
0x180039eec  mov     r8, [rbx+18h]
0x180039ef0  xor     edx, edx
0x180039ef2  mov     ecx, [rbx+8]
0x180039ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039efa  lea     rcx, [rbp+phModule]
0x180039efe  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180039f03  lea     rcx, [rbp+arg_8]
0x180039f07  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180039f0c  nop
0x180039f0d  add     rsp, 40h
0x180039f11  pop     rdi
0x180039f12  pop     rbx
0x180039f13  pop     rbp
0x180039f14  retn
```
