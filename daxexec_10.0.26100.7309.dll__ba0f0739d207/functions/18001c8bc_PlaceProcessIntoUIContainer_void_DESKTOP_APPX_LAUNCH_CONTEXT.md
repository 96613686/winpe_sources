# PlaceProcessIntoUIContainer(void *,DESKTOP_APPX_LAUNCH_CONTEXT *)

- ea: `0x18001c8bc`
- end: `0x18001cb48`
- name: `?PlaceProcessIntoUIContainer@@YAXPEAXPEAUDESKTOP_APPX_LAUNCH_CONTEXT@@@Z`
- size: `652`
- prototype: `void __fastcall(HANDLE hProcess, struct DESKTOP_APPX_LAUNCH_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022b30`

## callees

- `0x1800053a0`
- `0x180011820`
- `0x18001482c`
- `0x180015400`
- `0x18001c8bc`
- `0x18002031c`
- `0x180020338`
- `0x180020514`
- `0x1800218c8`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c92a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c92a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ca9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ca9d`
- `ntdll!NtQueryInformationProcess` at `0x18001c97a`
- `ntdll!NtQueryInformationProcess` at `0x18001c97a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001c909`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001c909`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001ca2f`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x18001ca2f`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001ca5f`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x18001ca5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c9e5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c9e5`

## string_xrefs

- `0x18001cad3`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001cae8`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001cafa`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001cb0f`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001cb21`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001cb36`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001c902`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PlaceProcessIntoUIContainer(HANDLE hProcess, struct DESKTOP_APPX_LAUNCH_CONTEXT *a2)
{
  HMODULE LibraryW; // rax
  const char *v5; // r9
  const char *v6; // r9
  NTSTATUS v7; // eax
  __int64 v8; // rax
  __int64 v9; // r8
  const char *v10; // r9
  const WCHAR *v11; // rdx
  HANDLE v12; // rbx
  const char *v13; // r9
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-49h]
  HLOCAL hMem; // [rsp+30h] [rbp-39h] BYREF
  __int64 ProcessInformation; // [rsp+38h] [rbp-31h] BYREF
  _SECURITY_ATTRIBUTES JobAttributes; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v19; // [rsp+58h] [rbp-11h]
  HLOCAL *p_hMem; // [rsp+60h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-1h] BYREF
  char v22; // [rsp+70h] [rbp+7h]
  LPCWSTR lpName[4]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CentennialInUIJob>::GetImpl'::`2'::impl) )
  {
    if ( !qword_180108180 )
    {
      LibraryW = LoadLibraryW(L"user32.dll");
      if ( !LibraryW )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v5);
      qword_180108180 = (__int64)GetProcAddress(LibraryW, (LPCSTR)0xAFE);
      if ( !qword_180108180 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x1FB,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v6);
    }
    if ( !*((_BYTE *)a2 + 65) && *((_BYTE *)a2 + 64) )
    {
      ProcessInformation = 0;
      v7 = NtQueryInformationProcess(hProcess, ProcessLUIDDeviceMapsEnabled|0x40, &ProcessInformation, 8u, 0);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0x209,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          (const char *)(unsigned int)v7,
          v15);
      v8 = std::to_wstring(&p_hMem);
      wil::str_concat<std::wstring,unsigned short const * &,unsigned short const (&)[2],std::wstring>(
        lpName,
        a2,
        v9,
        v8);
      std::wstring::~wstring(&p_hMem);
      hMem = 0;
      p_hMem = &hMem;
      SecurityDescriptor = 0;
      v22 = 1;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:(A;;GA;;;SY)(A;;0x0004;;;ME)S:(ML;;NW;;;ME)",
              1u,
              &SecurityDescriptor,
              0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x21E,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v10);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hMem);
      *(&JobAttributes.nLength + 1) = 0;
      *(&JobAttributes.bInheritHandle + 1) = 0;
      JobAttributes.nLength = 24;
      JobAttributes.lpSecurityDescriptor = hMem;
      JobAttributes.bInheritHandle = 0;
      v11 = (const WCHAR *)lpName;
      if ( lpName[3] > (LPCWSTR)7 )
        v11 = lpName[0];
      v12 = CreateJobObjectW(&JobAttributes, v11);
      v19 = v12;
      if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x23A,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v13);
      if ( !AssignProcessToJobObject(v12, hProcess) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x240,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          v14);
      ((void (__fastcall *)(HANDLE, __int64))qword_180108180)(v12, 766);
      CloseHandle(v12);
      if ( hMem )
        LocalFree(hMem);
      std::wstring::~wstring(lpName);
    }
  }
}

```

## disassembly

```asm
0x18001c8bc  mov     [rsp-8+arg_10], rbx
0x18001c8c1  push    rbp
0x18001c8c2  push    rsi
0x18001c8c3  push    rdi
0x18001c8c4  lea     rbp, [rsp-47h]
0x18001c8c9  sub     rsp, 0B0h
0x18001c8d0  mov     rax, cs:__security_cookie
0x18001c8d7  xor     rax, rsp
0x18001c8da  mov     [rbp+57h+var_20], rax
0x18001c8de  mov     rbx, rdx
0x18001c8e1  mov     rdi, rcx
0x18001c8e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialInUIJob@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialInUIJob@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob> `wil::Feature<__WilFeatureTraits_Feature_CentennialInUIJob>::GetImpl(void)'::`2'::impl
0x18001c8eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialInUIJob@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob>::__private_IsEnabled(void)
0x18001c8f0  test    al, al
0x18001c8f2  jz      loc_18001CAB3
0x18001c8f8  cmp     cs:qword_180108180, 0
0x18001c900  jnz     short loc_18001C94A
0x18001c902  lea     rcx, LibFileName; "user32.dll"
0x18001c909  call    cs:__imp_LoadLibraryW
0x18001c910  nop     dword ptr [rax+rax+00h]
0x18001c915  mov     rcx, [rbp+5Fh]; this
0x18001c919  test    rax, rax
0x18001c91c  jz      loc_18001CAE8
0x18001c922  mov     edx, 0AFEh; lpProcName
0x18001c927  mov     rcx, rax; hModule
0x18001c92a  call    cs:__imp_GetProcAddress
0x18001c931  nop     dword ptr [rax+rax+00h]
0x18001c936  mov     cs:qword_180108180, rax
0x18001c93d  mov     rcx, [rbp+5Fh]; this
0x18001c941  test    rax, rax
0x18001c944  jz      loc_18001CAFA
0x18001c94a  cmp     byte ptr [rbx+41h], 0
0x18001c94e  jnz     loc_18001CAB3
0x18001c954  cmp     byte ptr [rbx+40h], 0
0x18001c958  jz      loc_18001CAB3
0x18001c95e  and     [rbp+57h+ProcessInformation], 0
0x18001c963  and     qword ptr [rsp+0C0h+var_A0], 0
0x18001c969  mov     r9d, 8; ProcessInformationLength
0x18001c96f  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18001c973  lea     edx, [r9+54h]; ProcessInformationClass
0x18001c977  mov     rcx, rdi; ProcessHandle
0x18001c97a  call    cs:__imp_NtQueryInformationProcess
0x18001c981  nop     dword ptr [rax+rax+00h]
0x18001c986  mov     rcx, [rbp+5Fh]; this
0x18001c98a  test    eax, eax
0x18001c98c  js      loc_18001CB0C
0x18001c992  mov     rdx, [rbp+57h+ProcessInformation]
0x18001c996  lea     rcx, [rbp+57h+var_60]; void *
0x18001c99a  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x18001c99f  nop
0x18001c9a0  mov     r9, rax
0x18001c9a3  mov     rdx, rbx
0x18001c9a6  lea     rcx, [rbp+57h+lpName]
0x18001c9aa  call    ??$str_concat@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEBGAEAY01$$CBGV12@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEBGAEAY01$$CBG$$QEAV12@@Z; wil::str_concat<std::wstring,ushort const * &,ushort const (&)[2],std::wstring>(ushort const * &,ushort const (&)[2],std::wstring &&)
0x18001c9af  nop
0x18001c9b0  lea     rcx, [rbp+57h+var_60]; void *
0x18001c9b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c9b9  and     [rbp+57h+hMem], 0
0x18001c9be  lea     rax, [rbp+57h+hMem]
0x18001c9c2  mov     [rbp+57h+var_60], rax
0x18001c9c6  and     [rbp+57h+SecurityDescriptor], 0
0x18001c9cb  mov     [rbp+57h+var_50], 1
0x18001c9cf  mov     rbx, [rbp+5Fh]
0x18001c9d3  xor     r9d, r9d; SecurityDescriptorSize
0x18001c9d6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001c9da  lea     edx, [r9+1]; StringSDRevision
0x18001c9de  lea     rcx, aDAGaSyA0x0004M; "D:(A;;GA;;;SY)(A;;0x0004;;;ME)S:(ML;;NW"...
0x18001c9e5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c9ec  nop     dword ptr [rax+rax+00h]
0x18001c9f1  test    eax, eax
0x18001c9f3  jz      loc_18001CB21
0x18001c9f9  lea     rcx, [rbp+57h+var_60]
0x18001c9fd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001ca02  and     dword ptr [rbp+57h+JobAttributes+4], 0
0x18001ca06  and     dword ptr [rbp+57h+JobAttributes+14h], 0
0x18001ca0a  mov     [rbp+57h+JobAttributes.nLength], 18h
0x18001ca11  mov     rax, [rbp+57h+hMem]
0x18001ca15  mov     [rbp+57h+JobAttributes.lpSecurityDescriptor], rax
0x18001ca19  and     [rbp+57h+JobAttributes.bInheritHandle], 0
0x18001ca1d  lea     rdx, [rbp+57h+lpName]
0x18001ca21  cmp     [rbp+57h+var_28], 7
0x18001ca26  cmova   rdx, [rbp+57h+lpName]; lpName
0x18001ca2b  lea     rcx, [rbp+57h+JobAttributes]; lpJobAttributes
0x18001ca2f  call    cs:__imp_CreateJobObjectW
0x18001ca36  nop     dword ptr [rax+rax+00h]
0x18001ca3b  mov     rbx, rax
0x18001ca3e  mov     [rbp+57h+var_68], rax
0x18001ca42  mov     rcx, [rbp+5Fh]; this
0x18001ca46  inc     rax
0x18001ca49  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ca4f  jz      loc_18001CB36
0x18001ca55  mov     rsi, [rbp+5Fh]
0x18001ca59  mov     rdx, rdi; hProcess
0x18001ca5c  mov     rcx, rbx; hJob
0x18001ca5f  call    cs:__imp_AssignProcessToJobObject
0x18001ca66  nop     dword ptr [rax+rax+00h]
0x18001ca6b  test    eax, eax
0x18001ca6d  jz      short loc_18001CAD3
0x18001ca6f  mov     edx, 2FEh
0x18001ca74  mov     rcx, rbx
0x18001ca77  mov     rax, cs:qword_180108180
0x18001ca7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca83  nop
0x18001ca84  mov     rcx, rbx; hObject
0x18001ca87  call    cs:__imp_CloseHandle
0x18001ca8e  nop     dword ptr [rax+rax+00h]
0x18001ca93  nop
0x18001ca94  mov     rcx, [rbp+57h+hMem]; hMem
0x18001ca98  test    rcx, rcx
0x18001ca9b  jz      short loc_18001CAAA
0x18001ca9d  call    cs:__imp_LocalFree
0x18001caa4  nop     dword ptr [rax+rax+00h]
0x18001caa9  nop
0x18001caaa  lea     rcx, [rbp+57h+lpName]; void *
0x18001caae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cab3  mov     rcx, [rbp+57h+var_20]
0x18001cab7  xor     rcx, rsp; StackCookie
0x18001caba  call    __security_check_cookie
0x18001cabf  mov     rbx, [rsp+0C0h+arg_10]
0x18001cac7  add     rsp, 0B0h
0x18001cace  pop     rdi
0x18001cacf  pop     rsi
0x18001cad0  pop     rbp
0x18001cad1  retn
0x18001cad3  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001cada  mov     edx, 240h; void *
0x18001cadf  mov     rcx, rsi; this
0x18001cae2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001cae8  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001caef  mov     edx, 1F8h; void *
0x18001caf4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001cafa  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001cb01  mov     edx, 1FBh; void *
0x18001cb06  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001cb0c  mov     r9d, eax; char *
0x18001cb0f  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001cb16  mov     edx, 209h; void *
0x18001cb1b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18001cb21  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001cb28  mov     edx, 21Eh; void *
0x18001cb2d  mov     rcx, rbx; this
0x18001cb30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001cb36  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001cb3d  mov     edx, 23Ah; void *
0x18001cb42  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
