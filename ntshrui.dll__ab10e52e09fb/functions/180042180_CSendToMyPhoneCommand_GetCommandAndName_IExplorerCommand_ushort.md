# CSendToMyPhoneCommand::GetCommandAndName(IExplorerCommand * *,ushort * *)

- ea: `0x180042180`
- end: `0x180042340`
- name: `?GetCommandAndName@CSendToMyPhoneCommand@@MEAAJPEAPEAUIExplorerCommand@@PEAPEAG@Z`
- size: `448`
- prototype: `__int64 __fastcall(CSendToMyPhoneCommand *__hidden this, struct IExplorerCommand **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008900`
- `0x180015994`
- `0x180015ab0`
- `0x180015ad0`
- `0x1800214cc`
- `0x180021dd4`
- `0x180042180`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042293`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800421ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800421ca`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180042261`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180042261`

## string_xrefs

- `0x1800421bc`: `Software\Microsoft\Windows\CurrentVersion\Explorer\CommandStore`
- `0x1800421db`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004221d`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x180042272`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x1800422e6`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSendToMyPhoneCommand::GetCommandAndName(
        CSendToMyPhoneCommand *this,
        struct IExplorerCommand **a2,
        unsigned __int16 **a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rbx
  HRESULT v8; // edi
  __int64 v9; // rdx
  int v10; // eax
  struct IExplorerCommand *v11; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  LPVOID pv[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *ppv; // [rsp+78h] [rbp+38h] BYREF
  struct IExplorerCommand *v18; // [rsp+80h] [rbp+40h] BYREF
  HKEY v19; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  v19 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CommandStore",
         0,
         9u,
         &v19);
  if ( !v5 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      L"Windows.SendToMyPhone",
      -1);
    v7 = (unsigned __int16 *)pv[0];
    if ( !pv[0] )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC92,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      goto LABEL_14;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    v8 = SHCoCreateInstance(0, &CLSID_RegDataDrivenCommand, 0, &GUID_697d9b7b_a001_4cdd_8be8_eb7874b5b956, &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, HKEY, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v19, v7);
      if ( v8 >= 0 )
      {
        v18 = 0;
        v10 = Microsoft::WRL::ComPtr<IRegDataDrivenCommand>::As<IExplorerCommand>(&ppv, &v18);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v11 = v18;
          v18 = 0;
          *a2 = v11;
          *a3 = v7;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
          v6 = 0;
          goto LABEL_14;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC98,
          (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
          (const char *)(unsigned int)v10,
          phkResulta);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
        goto LABEL_8;
      }
      v9 = 3222;
    }
    else
    {
      v9 = 3221;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v8,
      phkResulta);
LABEL_8:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
    CoTaskMemFree(v7);
    v6 = v8;
    goto LABEL_14;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xC8F,
         (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
         (const char *)v5,
         phkResult);
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  return v6;
}

```

## disassembly

```asm
0x180042180  push    rbp
0x180042182  push    rbx
0x180042183  push    rsi
0x180042184  push    rdi
0x180042185  push    r14
0x180042187  mov     rbp, rsp
0x18004218a  sub     rsp, 40h
0x18004218e  mov     rsi, r8
0x180042191  mov     r14, rdx
0x180042194  mov     qword ptr [rdx], 0
0x18004219b  mov     qword ptr [r8], 0
0x1800421a2  mov     [rbp+arg_18], 0
0x1800421aa  lea     rax, [rbp+arg_18]
0x1800421ae  mov     qword ptr [rsp+40h+phkResult], rax; int
0x1800421b3  mov     r9d, 9; samDesired
0x1800421b9  xor     r8d, r8d; ulOptions
0x1800421bc  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800421c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800421ca  call    cs:__imp_RegOpenKeyExW
0x1800421d0  test    eax, eax
0x1800421d2  jz      short loc_1800421F3
0x1800421d4  mov     rcx, [rbp+28h]; this
0x1800421d8  mov     r9d, eax; char *
0x1800421db  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800421e2  mov     edx, 0C8Fh; void *
0x1800421e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800421ec  mov     ebx, eax
0x1800421ee  jmp     loc_18004232A
0x1800421f3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800421f7  lea     rdx, aWindowsSendtom; "Windows.SendToMyPhone"
0x1800421fe  lea     rcx, [rbp+pv]
0x180042202  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180042207  nop
0x180042208  mov     rbx, [rbp+pv]
0x18004220c  test    rbx, rbx
0x18004220f  jnz     short loc_180042234
0x180042211  mov     rcx, [rbp+28h]; this
0x180042215  mov     ebx, 8007000Eh
0x18004221a  mov     r9d, ebx; char *
0x18004221d  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180042224  mov     edx, 0C92h; void *
0x180042229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004222e  nop
0x18004222f  jmp     loc_18004232A
0x180042234  mov     [rbp+ppv], 0
0x18004223c  lea     rcx, [rbp+ppv]
0x180042240  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180042245  lea     rax, [rbp+ppv]
0x180042249  mov     qword ptr [rsp+40h+phkResult], rax; int
0x18004224e  lea     r9, _GUID_697d9b7b_a001_4cdd_8be8_eb7874b5b956; riid
0x180042255  xor     r8d, r8d; pUnkOuter
0x180042258  lea     rdx, CLSID_RegDataDrivenCommand; pclsid
0x18004225f  xor     ecx, ecx; pszCLSID
0x180042261  call    cs:__imp_SHCoCreateInstance
0x180042267  mov     edi, eax
0x180042269  test    eax, eax
0x18004226b  jns     short loc_1800422A0
0x18004226d  mov     edx, 0C95h; void *
0x180042272  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x180042279  mov     r9d, edi; char *
0x18004227c  mov     rcx, [rbp+28h]; this
0x180042280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042285  nop
0x180042286  lea     rcx, [rbp+ppv]
0x18004228a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004228f  nop
0x180042290  mov     rcx, rbx; pv
0x180042293  call    cs:__imp_CoTaskMemFree
0x180042299  mov     ebx, edi
0x18004229b  jmp     loc_18004232A
0x1800422a0  mov     rcx, [rbp+ppv]
0x1800422a4  mov     rax, [rcx]
0x1800422a7  mov     r8, rbx
0x1800422aa  mov     rdx, [rbp+arg_18]
0x1800422ae  mov     rax, [rax+18h]
0x1800422b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422b7  mov     edi, eax
0x1800422b9  test    eax, eax
0x1800422bb  jns     short loc_1800422C4
0x1800422bd  mov     edx, 0C96h
0x1800422c2  jmp     short loc_180042272
0x1800422c4  mov     [rbp+arg_10], 0
0x1800422cc  lea     rdx, [rbp+arg_10]
0x1800422d0  lea     rcx, [rbp+ppv]
0x1800422d4  call    ??$As@UIExplorerCommand@@@?$ComPtr@UIRegDataDrivenCommand@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExplorerCommand@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IRegDataDrivenCommand>::As<IExplorerCommand>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IExplorerCommand>>)
0x1800422d9  mov     edi, eax
0x1800422db  test    eax, eax
0x1800422dd  jns     short loc_180042302
0x1800422df  mov     rcx, [rbp+28h]; this
0x1800422e3  mov     r9d, eax; char *
0x1800422e6  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x1800422ed  mov     edx, 0C98h; void *
0x1800422f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800422f7  lea     rcx, [rbp+arg_10]
0x1800422fb  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180042300  jmp     short loc_180042286
0x180042302  mov     rax, [rbp+arg_10]
0x180042306  mov     [rbp+arg_10], 0
0x18004230e  mov     [r14], rax
0x180042311  mov     [rsi], rbx
0x180042314  lea     rcx, [rbp+arg_10]
0x180042318  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004231d  nop
0x18004231e  lea     rcx, [rbp+ppv]
0x180042322  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180042327  nop
0x180042328  xor     ebx, ebx
0x18004232a  lea     rcx, [rbp+arg_18]
0x18004232e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042333  mov     eax, ebx
0x180042335  add     rsp, 40h
0x180042339  pop     r14
0x18004233b  pop     rdi
0x18004233c  pop     rsi
0x18004233d  pop     rbx
0x18004233e  pop     rbp
0x18004233f  retn
```
