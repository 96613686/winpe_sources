# _lambda_5711edda10199220f041ed71b5ec8561_::operator()(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18006fbbc`
- end: `0x18006fc74`
- name: `??R_lambda_5711edda10199220f041ed71b5ec8561_@@QEBAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18006d400`

## callees

- `0x18006d694`
- `0x18006f800`
- `0x18006fbbc`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006fc1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006fc1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006fbe9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006fbe9`

## string_xrefs

- `0x18006fbe2`: `winbioext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 _lambda_5711edda10199220f041ed71b5ec8561_::operator()(HMODULE a1, __int64 a2, _BYTE *a3, ...)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  HMODULE v8; // [rsp+30h] [rbp+10h] BYREF
  __int64 v9; // [rsp+38h] [rbp+18h] BYREF
  __int64 v10; // [rsp+48h] [rbp+28h] BYREF
  va_list va; // [rsp+48h] [rbp+28h]
  va_list va1; // [rsp+50h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, _QWORD);
  v9 = a2;
  v8 = a1;
  Library = LoadLibraryExW(L"winbioext.dll", 0, 0x800u);
  v8 = Library;
  if ( !Library )
  {
    LODWORD(v9) = 0;
LABEL_3:
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v9);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "WinBioIsESSCapable");
  if ( !ProcAddress )
  {
    LODWORD(v9) = 1;
    goto LABEL_3;
  }
  LOBYTE(v10) = 0;
  if ( ((int (__fastcall *)(__int64 *))ProcAddress)((__int64 *)va) >= 0 )
  {
    *a3 = v10;
    v7 = 1;
  }
  else
  {
    LODWORD(v9) = 2;
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v9);
    v7 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
  return v7;
}

```

## disassembly

```asm
0x18006fbbc  mov     rax, rsp
0x18006fbbf  mov     [rax+18h], rbx
0x18006fbc3  mov     [rax+20h], r9
0x18006fbc7  mov     [rax+10h], rdx
0x18006fbcb  mov     [rax+8], rcx
0x18006fbcf  push    rbp
0x18006fbd0  mov     rbp, rsp
0x18006fbd3  sub     rsp, 20h
0x18006fbd7  mov     rbx, r8
0x18006fbda  xor     edx, edx; hFile
0x18006fbdc  mov     r8d, 800h; dwFlags
0x18006fbe2  lea     rcx, aWinbioextDll; "winbioext.dll"
0x18006fbe9  call    cs:__imp_LoadLibraryExW
0x18006fbef  mov     [rbp+arg_0], rax
0x18006fbf3  test    rax, rax
0x18006fbf6  jnz     short loc_18006FC12
0x18006fbf8  mov     dword ptr [rbp+arg_8], eax
0x18006fbfb  lea     rcx, [rbp+arg_8]
0x18006fbff  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x18006fc04  nop
0x18006fc05  lea     rcx, [rbp+arg_0]
0x18006fc09  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18006fc0e  xor     eax, eax
0x18006fc10  jmp     short loc_18006FC69
0x18006fc12  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x18006fc19  mov     rcx, rax; hModule
0x18006fc1c  call    cs:__imp_GetProcAddress
0x18006fc22  test    rax, rax
0x18006fc25  jnz     short loc_18006FC2F
0x18006fc27  lea     ebx, [rax+1]
0x18006fc2a  mov     dword ptr [rbp+arg_8], ebx
0x18006fc2d  jmp     short loc_18006FBFB
0x18006fc2f  mov     byte ptr [rbp+arg_18], 0
0x18006fc33  lea     rcx, [rbp+arg_18]
0x18006fc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc3c  test    eax, eax
0x18006fc3e  jns     short loc_18006FC54
0x18006fc40  mov     dword ptr [rbp+arg_8], 2
0x18006fc47  lea     rcx, [rbp+arg_8]
0x18006fc4b  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x18006fc50  xor     ebx, ebx
0x18006fc52  jmp     short loc_18006FC5E
0x18006fc54  mov     al, byte ptr [rbp+arg_18]
0x18006fc57  mov     [rbx], al
0x18006fc59  mov     ebx, 1
0x18006fc5e  lea     rcx, [rbp+arg_0]
0x18006fc62  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18006fc67  mov     eax, ebx
0x18006fc69  mov     rbx, [rsp+20h+arg_10]
0x18006fc6e  add     rsp, 20h
0x18006fc72  pop     rbp
0x18006fc73  retn
```
