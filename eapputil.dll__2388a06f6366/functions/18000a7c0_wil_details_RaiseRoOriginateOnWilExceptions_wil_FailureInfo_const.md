# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x18000a7c0`
- end: `0x18000a8f9`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a7c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000a89e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000a89e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a8d5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a8d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8b3`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000a881`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000a881`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000a7e7`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000a7e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a84f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a85e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a86d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a84f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a85e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a86d`

## string_xrefs

- `0x18000a895`: `api-ms-win-core-winrt-error-l1-1-1.dll`

## pseudocode

```c
void __fastcall wil::details::RaiseRoOriginateOnWilExceptions(wil::details *this, const struct wil::FailureInfo *a2)
{
  bool v3; // di
  __int64 v4; // rcx
  FARPROC ProcAddress; // rax
  BSTR v6[2]; // [rsp+30h] [rbp-10h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp+20h] BYREF
  __int64 v8; // [rsp+68h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF
  BSTR v10; // [rsp+78h] [rbp+38h] BYREF

  v3 = 1;
  if ( *(_DWORD *)this <= 1u )
  {
    v8 = 0;
    if ( (unsigned int)GetRestrictedErrorInfo(&v8, a2) )
      goto LABEL_14;
    v6[0] = 0;
    LODWORD(phModule) = *((_DWORD *)this + 2);
    v10 = 0;
    bstrString = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *, HMODULE *, BSTR *, BSTR *))(*(_QWORD *)v8 + 24LL))(
           v8,
           v6,
           &phModule,
           &v10,
           &bstrString) >= 0 )
      v3 = *((_DWORD *)this + 2) != (_DWORD)phModule;
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v10 )
      SysFreeString(v10);
    if ( v6[0] )
      SysFreeString(v6[0]);
    if ( v3 )
    {
LABEL_14:
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
      if ( phModule )
        FreeLibrary(phModule);
    }
    else
    {
      v4 = v8;
      if ( !v8 )
        goto LABEL_20;
      SetRestrictedErrorInfo();
    }
    v4 = v8;
LABEL_20:
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x18000a7c0  push    rbp
0x18000a7c2  push    rbx
0x18000a7c3  push    rdi
0x18000a7c4  mov     rbp, rsp
0x18000a7c7  sub     rsp, 40h
0x18000a7cb  mov     rbx, rcx
0x18000a7ce  mov     edi, 1
0x18000a7d3  cmp     [rcx], edi
0x18000a7d5  ja      loc_18000A8F1
0x18000a7db  mov     [rbp+arg_8], 0
0x18000a7e3  lea     rcx, [rbp+arg_8]
0x18000a7e7  call    cs:__imp_GetRestrictedErrorInfo
0x18000a7ed  test    eax, eax
0x18000a7ef  jnz     loc_18000A889
0x18000a7f5  mov     [rbp+var_10], 0
0x18000a7fd  mov     eax, [rbx+8]
0x18000a800  mov     dword ptr [rbp+phModule], eax
0x18000a803  mov     [rbp+arg_18], 0
0x18000a80b  mov     [rbp+bstrString], 0
0x18000a813  mov     rcx, [rbp+arg_8]
0x18000a817  mov     rax, [rcx]
0x18000a81a  lea     rdx, [rbp+bstrString]
0x18000a81e  mov     [rsp+40h+var_20], rdx
0x18000a823  lea     r9, [rbp+arg_18]
0x18000a827  lea     r8, [rbp+phModule]
0x18000a82b  lea     rdx, [rbp+var_10]
0x18000a82f  mov     rax, [rax+18h]
0x18000a833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a838  test    eax, eax
0x18000a83a  js      short loc_18000A846
0x18000a83c  mov     eax, dword ptr [rbp+phModule]
0x18000a83f  cmp     [rbx+8], eax
0x18000a842  setnz   dil
0x18000a846  mov     rcx, [rbp+bstrString]; bstrString
0x18000a84a  test    rcx, rcx
0x18000a84d  jz      short loc_18000A855
0x18000a84f  call    cs:__imp_SysFreeString
0x18000a855  mov     rcx, [rbp+arg_18]; bstrString
0x18000a859  test    rcx, rcx
0x18000a85c  jz      short loc_18000A864
0x18000a85e  call    cs:__imp_SysFreeString
0x18000a864  mov     rcx, [rbp+var_10]; bstrString
0x18000a868  test    rcx, rcx
0x18000a86b  jz      short loc_18000A873
0x18000a86d  call    cs:__imp_SysFreeString
0x18000a873  test    dil, dil
0x18000a876  jnz     short loc_18000A889
0x18000a878  mov     rcx, [rbp+arg_8]
0x18000a87c  test    rcx, rcx
0x18000a87f  jz      short loc_18000A8DF
0x18000a881  call    cs:__imp_SetRestrictedErrorInfo
0x18000a887  jmp     short loc_18000A8DB
0x18000a889  mov     [rbp+phModule], 0
0x18000a891  lea     r8, [rbp+phModule]; phModule
0x18000a895  lea     rdx, aApiMsWinCoreWi_4; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x18000a89c  xor     ecx, ecx; dwFlags
0x18000a89e  call    cs:__imp_GetModuleHandleExW
0x18000a8a4  test    eax, eax
0x18000a8a6  jz      short loc_18000A8CC
0x18000a8a8  lea     rdx, aRooriginateerr; "RoOriginateErrorW"
0x18000a8af  mov     rcx, [rbp+phModule]; hModule
0x18000a8b3  call    cs:__imp_GetProcAddress
0x18000a8b9  test    rax, rax
0x18000a8bc  jz      short loc_18000A8CC
0x18000a8be  mov     r8, [rbx+18h]
0x18000a8c2  xor     edx, edx
0x18000a8c4  mov     ecx, [rbx+8]
0x18000a8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8cc  mov     rcx, [rbp+phModule]; hLibModule
0x18000a8d0  test    rcx, rcx
0x18000a8d3  jz      short loc_18000A8DB
0x18000a8d5  call    cs:__imp_FreeLibrary
0x18000a8db  mov     rcx, [rbp+arg_8]
0x18000a8df  test    rcx, rcx
0x18000a8e2  jz      short loc_18000A8F1
0x18000a8e4  mov     rax, [rcx]
0x18000a8e7  mov     rax, [rax+10h]
0x18000a8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8f0  nop
0x18000a8f1  add     rsp, 40h
0x18000a8f5  pop     rdi
0x18000a8f6  pop     rbx
0x18000a8f7  pop     rbp
0x18000a8f8  retn
```
