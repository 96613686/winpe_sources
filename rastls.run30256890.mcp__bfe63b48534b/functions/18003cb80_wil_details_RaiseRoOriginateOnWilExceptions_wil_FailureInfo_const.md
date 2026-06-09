# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x18003cb80`
- end: `0x18003ccae`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `302`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180021e74`
- `0x18003ae18`
- `0x18003ae3c`
- `0x18003cb80`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cc73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cc73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003cc58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003cc58`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18003cc35`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18003cc35`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18003cba7`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18003cba7`

## string_xrefs

- `0x18003cc4f`: `api-ms-win-core-winrt-error-l1-1-1.dll`

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
0x18003cb80  push    rbp
0x18003cb82  push    rbx
0x18003cb83  push    rdi
0x18003cb84  mov     rbp, rsp
0x18003cb87  sub     rsp, 40h
0x18003cb8b  mov     rbx, rcx
0x18003cb8e  mov     edi, 1
0x18003cb93  cmp     [rcx], edi
0x18003cb95  ja      loc_18003CCA5
0x18003cb9b  mov     [rbp+arg_8], 0
0x18003cba3  lea     rcx, [rbp+arg_8]
0x18003cba7  call    cs:__imp_GetRestrictedErrorInfo
0x18003cbae  nop     dword ptr [rax+rax+00h]
0x18003cbb3  test    eax, eax
0x18003cbb5  jnz     loc_18003CC43
0x18003cbbb  mov     [rbp+var_10], 0
0x18003cbc3  mov     eax, [rbx+8]
0x18003cbc6  mov     dword ptr [rbp+phModule], eax
0x18003cbc9  mov     [rbp+arg_18], 0
0x18003cbd1  mov     [rbp+arg_10], 0
0x18003cbd9  mov     rcx, [rbp+arg_8]
0x18003cbdd  mov     rax, [rcx]
0x18003cbe0  lea     rdx, [rbp+arg_10]
0x18003cbe4  mov     [rsp+40h+var_20], rdx
0x18003cbe9  lea     r9, [rbp+arg_18]
0x18003cbed  lea     r8, [rbp+phModule]
0x18003cbf1  lea     rdx, [rbp+var_10]
0x18003cbf5  mov     rax, [rax+18h]
0x18003cbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbfe  test    eax, eax
0x18003cc00  js      short loc_18003CC0C
0x18003cc02  mov     eax, dword ptr [rbp+phModule]
0x18003cc05  cmp     [rbx+8], eax
0x18003cc08  setnz   dil
0x18003cc0c  lea     rcx, [rbp+arg_10]
0x18003cc10  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cc15  lea     rcx, [rbp+arg_18]
0x18003cc19  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cc1e  lea     rcx, [rbp+var_10]
0x18003cc22  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cc27  test    dil, dil
0x18003cc2a  jnz     short loc_18003CC43
0x18003cc2c  mov     rcx, [rbp+arg_8]
0x18003cc30  test    rcx, rcx
0x18003cc33  jz      short loc_18003CC9B
0x18003cc35  call    cs:__imp_SetRestrictedErrorInfo
0x18003cc3c  nop     dword ptr [rax+rax+00h]
0x18003cc41  jmp     short loc_18003CC9B
0x18003cc43  mov     [rbp+phModule], 0
0x18003cc4b  lea     r8, [rbp+phModule]; phModule
0x18003cc4f  lea     rdx, aApiMsWinCoreWi_4; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x18003cc56  xor     ecx, ecx; dwFlags
0x18003cc58  call    cs:__imp_GetModuleHandleExW
0x18003cc5f  nop     dword ptr [rax+rax+00h]
0x18003cc64  test    eax, eax
0x18003cc66  jz      short loc_18003CC92
0x18003cc68  lea     rdx, aRooriginateerr; "RoOriginateErrorW"
0x18003cc6f  mov     rcx, [rbp+phModule]; hModule
0x18003cc73  call    cs:__imp_GetProcAddress
0x18003cc7a  nop     dword ptr [rax+rax+00h]
0x18003cc7f  test    rax, rax
0x18003cc82  jz      short loc_18003CC92
0x18003cc84  mov     r8, [rbx+18h]
0x18003cc88  xor     edx, edx
0x18003cc8a  mov     ecx, [rbx+8]
0x18003cc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc92  lea     rcx, [rbp+phModule]
0x18003cc96  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003cc9b  lea     rcx, [rbp+arg_8]
0x18003cc9f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18003cca4  nop
0x18003cca5  add     rsp, 40h
0x18003cca9  pop     rdi
0x18003ccaa  pop     rbx
0x18003ccab  pop     rbp
0x18003ccac  retn
```
