# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x180119b90`
- end: `0x180119cfa`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180119d00`

## callees

- `0x1800150c0`
- `0x1800aa16c`
- `0x1800eb920`
- `0x1800ef360`
- `0x180119b90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180119c9a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180119c9a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180119c3f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180119c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180119cbe`

## string_xrefs

- `0x180119c38`: `kernelbase.dll`
- `0x180119bc2`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x180119c02`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x180119c93`: `GetTempPath2W`
- `0x180119bd5`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x180119c15`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x180119be0`: `Not-null check failed: phDll`

## pseudocode

```c
signed int __fastcall Windows::COM::LoadSystemLibraryAndFunction(__int64 a1, __int64 a2, HMODULE *a3, FARPROC *a4)
{
  const char *v6; // rax
  signed int result; // eax
  HMODULE Library; // rax
  bool v9; // cc
  FARPROC ProcAddress; // rax
  const char *v11; // [rsp+20h] [rbp-30h] BYREF
  const char *v12; // [rsp+28h] [rbp-28h]
  __int64 v13; // [rsp+30h] [rbp-20h]
  const char *v14; // [rsp+38h] [rbp-18h]
  int v15; // [rsp+40h] [rbp-10h] BYREF

  v15 = 0;
  if ( !a3 )
  {
    v13 = 108;
    v11 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: phDll";
LABEL_3:
    v14 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v11);
  }
  if ( !a4 )
  {
    v13 = 109;
    v11 = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12 = "Windows::COM::LoadSystemLibraryAndFunction";
    v6 = "Not-null check failed: ppfn";
    goto LABEL_3;
  }
  *a4 = 0;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(a3, Library);
  if ( !*a3 )
  {
    if ( !GetLastError() )
    {
LABEL_8:
      result = 14077;
LABEL_10:
      v9 = result <= 0;
      goto LABEL_11;
    }
    result = GetLastError();
    if ( result )
      goto LABEL_10;
LABEL_19:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180119CF9LL);
  }
  ProcAddress = GetProcAddress(*a3, "GetTempPath2W");
  *a4 = ProcAddress;
  if ( ProcAddress )
    return 0;
  if ( !GetLastError() )
    goto LABEL_8;
  result = GetLastError();
  v9 = result <= 0;
  if ( !result )
    goto LABEL_19;
LABEL_11:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180119b90  mov     [rsp-8+arg_0], rbx
0x180119b95  mov     [rsp-8+arg_8], rdi
0x180119b9a  push    rbp
0x180119b9b  mov     rbp, rsp
0x180119b9e  sub     rsp, 50h
0x180119ba2  mov     rax, cs:__security_cookie
0x180119ba9  xor     rax, rsp
0x180119bac  mov     [rbp+var_8], rax
0x180119bb0  mov     [rbp+var_10], 0
0x180119bb7  mov     rbx, r9
0x180119bba  mov     rdi, r8
0x180119bbd  test    r8, r8
0x180119bc0  jnz     short loc_180119BFD
0x180119bc2  lea     rax, aOnecoreBaseWcp_25; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180119bc9  mov     [rbp+var_20], 6Ch ; 'l'
0x180119bd1  mov     [rbp+var_30], rax
0x180119bd5  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x180119bdc  mov     [rbp+var_28], rax
0x180119be0  lea     rax, aNotNullCheckFa_61; "Not-null check failed: phDll"
0x180119be7  lea     rdx, [rbp+var_30]
0x180119beb  mov     [rbp+var_18], rax
0x180119bef  lea     rcx, [rbp+var_10]
0x180119bf3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180119bf8  jmp     loc_180119CD2
0x180119bfd  test    rbx, rbx
0x180119c00  jnz     short loc_180119C29
0x180119c02  lea     rax, aOnecoreBaseWcp_25; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180119c09  mov     [rbp+var_20], 6Dh ; 'm'
0x180119c11  mov     [rbp+var_30], rax
0x180119c15  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x180119c1c  mov     [rbp+var_28], rax
0x180119c20  lea     rax, aNotNullCheckFa_27; "Not-null check failed: ppfn"
0x180119c27  jmp     short loc_180119BE7
0x180119c29  xor     edx, edx; hFile
0x180119c2b  mov     qword ptr [r9], 0
0x180119c32  mov     r8d, 800h; dwFlags
0x180119c38  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180119c3f  call    cs:__imp_LoadLibraryExW
0x180119c46  nop     dword ptr [rax+rax+00h]
0x180119c4b  mov     rdx, rax
0x180119c4e  mov     rcx, rdi
0x180119c51  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x180119c56  mov     rcx, [rdi]; hModule
0x180119c59  test    rcx, rcx
0x180119c5c  jnz     short loc_180119C93
0x180119c5e  call    cs:__imp_GetLastError
0x180119c65  nop     dword ptr [rax+rax+00h]
0x180119c6a  test    eax, eax
0x180119c6c  jnz     short loc_180119C75
0x180119c6e  mov     eax, 36FDh
0x180119c73  jmp     short loc_180119C85
0x180119c75  call    cs:__imp_GetLastError
0x180119c7c  nop     dword ptr [rax+rax+00h]
0x180119c81  test    eax, eax
0x180119c83  jz      short loc_180119CEF
0x180119c85  test    eax, eax
0x180119c87  jle     short loc_180119CD2
0x180119c89  movzx   eax, ax
0x180119c8c  or      eax, 80070000h
0x180119c91  jmp     short loc_180119CD2
0x180119c93  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x180119c9a  call    cs:__imp_GetProcAddress
0x180119ca1  nop     dword ptr [rax+rax+00h]
0x180119ca6  mov     [rbx], rax
0x180119ca9  test    rax, rax
0x180119cac  jnz     short loc_180119CD0
0x180119cae  call    cs:__imp_GetLastError
0x180119cb5  nop     dword ptr [rax+rax+00h]
0x180119cba  test    eax, eax
0x180119cbc  jz      short loc_180119C6E
0x180119cbe  call    cs:__imp_GetLastError
0x180119cc5  nop     dword ptr [rax+rax+00h]
0x180119cca  test    eax, eax
0x180119ccc  jz      short loc_180119CEF
0x180119cce  jmp     short loc_180119C87
0x180119cd0  xor     eax, eax
0x180119cd2  mov     rcx, [rbp+var_8]
0x180119cd6  xor     rcx, rsp; StackCookie
0x180119cd9  call    __security_check_cookie
0x180119cde  mov     rbx, [rsp+50h+arg_0]
0x180119ce3  mov     rdi, [rsp+50h+arg_8]
0x180119ce8  add     rsp, 50h
0x180119cec  pop     rbp
0x180119ced  retn
0x180119cef  mov     ecx, 0C00000E5h; int
0x180119cf4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
