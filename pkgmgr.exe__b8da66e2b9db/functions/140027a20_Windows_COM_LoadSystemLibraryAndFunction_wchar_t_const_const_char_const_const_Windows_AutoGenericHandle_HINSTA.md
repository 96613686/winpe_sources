# Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))

- ea: `0x140027a20`
- end: `0x140027b70`
- name: `?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z`
- size: `336`
- prototype: `signed int __fastcall(__int64, __int64, HMODULE *, FARPROC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140027b78`

## callees

- `0x140002360`
- `0x14000731c`
- `0x1400074c0`
- `0x140027a20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140027b1c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140027b1c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140027ad5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x140027ad5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140027b34`

## string_xrefs

- `0x140027ace`: `kernelbase.dll`
- `0x140027a52`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140027a98`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140027b12`: `GetTempPath2W`
- `0x140027a65`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x140027aab`: `Windows::COM::LoadSystemLibraryAndFunction`
- `0x140027a70`: `Not-null check failed: phDll`

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
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v15,
             &v11,
             2147500035LL);
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
  if ( *a3 )
    INTERNAL_ERROR_ACTION();
  *a3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTempPath2W");
    *a4 = ProcAddress;
    if ( ProcAddress )
      return 0;
    if ( GetLastError() )
    {
      result = GetLastError();
      v9 = result <= 0;
      if ( !result )
        INTERNAL_ERROR_ACTION();
      goto LABEL_10;
    }
  }
  else if ( GetLastError() )
  {
    result = GetLastError();
    v9 = result <= 0;
    if ( !result )
      INTERNAL_ERROR_ACTION();
    goto LABEL_10;
  }
  result = 14077;
  v9 = 0;
LABEL_10:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140027a20  mov     [rsp-8+arg_0], rbx
0x140027a25  mov     [rsp-8+arg_8], rdi
0x140027a2a  push    rbp
0x140027a2b  mov     rbp, rsp
0x140027a2e  sub     rsp, 50h
0x140027a32  mov     rax, cs:__security_cookie
0x140027a39  xor     rax, rsp
0x140027a3c  mov     [rbp+var_8], rax
0x140027a40  mov     [rbp+var_10], 0
0x140027a47  mov     rbx, r9
0x140027a4a  mov     rdi, r8
0x140027a4d  test    r8, r8
0x140027a50  jnz     short loc_140027A93
0x140027a52  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140027a59  mov     [rbp+var_20], 6Ch ; 'l'
0x140027a61  mov     [rbp+var_30], rax
0x140027a65  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x140027a6c  mov     [rbp+var_28], rax
0x140027a70  lea     rax, aNotNullCheckFa_1; "Not-null check failed: phDll"
0x140027a77  mov     r8d, 80004003h
0x140027a7d  mov     [rbp+var_18], rax
0x140027a81  lea     rdx, [rbp+var_30]
0x140027a85  lea     rcx, [rbp+var_10]
0x140027a89  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140027a8e  jmp     loc_140027B42
0x140027a93  test    rbx, rbx
0x140027a96  jnz     short loc_140027ABF
0x140027a98  lea     rax, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140027a9f  mov     [rbp+var_20], 6Dh ; 'm'
0x140027aa7  mov     [rbp+var_30], rax
0x140027aab  lea     rax, aWindowsComLoad; "Windows::COM::LoadSystemLibraryAndFunct"...
0x140027ab2  mov     [rbp+var_28], rax
0x140027ab6  lea     rax, aNotNullCheckFa_0; "Not-null check failed: ppfn"
0x140027abd  jmp     short loc_140027A77
0x140027abf  xor     edx, edx; hFile
0x140027ac1  mov     qword ptr [r9], 0
0x140027ac8  mov     r8d, 800h; dwFlags
0x140027ace  lea     rcx, LibFileName; "kernelbase.dll"
0x140027ad5  call    cs:__imp_LoadLibraryExW
0x140027adb  cmp     qword ptr [rdi], 0
0x140027adf  jnz     short loc_140027B5E
0x140027ae1  mov     [rdi], rax
0x140027ae4  test    rax, rax
0x140027ae7  jnz     short loc_140027B12
0x140027ae9  call    cs:__imp_GetLastError
0x140027aef  test    eax, eax
0x140027af1  jnz     short loc_140027B06
0x140027af3  mov     eax, 36FDh
0x140027af8  test    eax, eax
0x140027afa  jle     short loc_140027B42
0x140027afc  movzx   eax, ax
0x140027aff  or      eax, 80070000h
0x140027b04  jmp     short loc_140027B42
0x140027b06  call    cs:__imp_GetLastError
0x140027b0c  test    eax, eax
0x140027b0e  jz      short loc_140027B64
0x140027b10  jmp     short loc_140027AFA
0x140027b12  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x140027b19  mov     rcx, rax; hModule
0x140027b1c  call    cs:__imp_GetProcAddress
0x140027b22  mov     [rbx], rax
0x140027b25  test    rax, rax
0x140027b28  jnz     short loc_140027B40
0x140027b2a  call    cs:__imp_GetLastError
0x140027b30  test    eax, eax
0x140027b32  jz      short loc_140027AF3
0x140027b34  call    cs:__imp_GetLastError
0x140027b3a  test    eax, eax
0x140027b3c  jz      short loc_140027B6A
0x140027b3e  jmp     short loc_140027AFA
0x140027b40  xor     eax, eax
0x140027b42  mov     rcx, [rbp+var_8]
0x140027b46  xor     rcx, rsp; StackCookie
0x140027b49  call    __security_check_cookie
0x140027b4e  mov     rbx, [rsp+50h+arg_0]
0x140027b53  mov     rdi, [rsp+50h+arg_8]
0x140027b58  add     rsp, 50h
0x140027b5c  pop     rbp
0x140027b5d  retn
0x140027b5e  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140027b64  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140027b6a  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
