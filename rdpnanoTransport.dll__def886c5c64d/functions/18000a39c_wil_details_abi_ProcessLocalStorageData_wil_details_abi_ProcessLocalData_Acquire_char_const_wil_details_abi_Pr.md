# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a39c`
- end: `0x18000a574`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000b4f0`

## callees

- `0x18000a39c`
- `0x18000ab24`
- `0x18000b15c`
- `0x18000b930`
- `0x18000be70`
- `0x18000c624`
- `0x18000c74c`
- `0x18000cbac`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000a43b`
- `KERNEL32!CloseHandle` at `0x18000a43b`
- `KERNEL32!ReleaseMutex` at `0x18000a4e0`
- `KERNEL32!ReleaseMutex` at `0x18000a4e0`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a47b`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a47b`
- `KERNEL32!CreateMutexExW` at `0x18000a419`
- `KERNEL32!CreateMutexExW` at `0x18000a419`
- `KERNEL32!GetCurrentProcessId` at `0x18000a3dd`
- `KERNEL32!GetCurrentProcessId` at `0x18000a3dd`

## string_xrefs

- `0x18000a530`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`
- `0x18000a549`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`
- `0x18000a562`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  int LastErrorFailHr; // edi
  const char *v8; // r9
  DWORD v10; // eax
  const char *v11; // r9
  void *v12; // rsi
  __int64 v13; // rdx
  _DWORD *v14; // rcx
  const char *v15; // r9
  int v16; // eax
  HANDLE v17; // [rsp+30h] [rbp-D0h] BYREF
  void *v18; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v17 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
    goto LABEL_3;
  }
  v10 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v10 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v10 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xC2E,
        (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
        v11);
    v12 = v6;
  }
  v18 = 0;
  LastErrorFailHr = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v18);
  if ( LastErrorFailHr < 0 )
  {
    v13 = 299;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"wil",
      (const char *)(unsigned int)LastErrorFailHr,
      120);
    goto LABEL_15;
  }
  v14 = v18;
  if ( v18 )
  {
    *a2 = v18;
    ++*v14;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
            Name,
            &v17,
            a2);
    v6 = v17;
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      v13 = 308;
      goto LABEL_20;
    }
  }
  LastErrorFailHr = 0;
LABEL_15:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9DC,
      (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
      v15);
LABEL_3:
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D2,
      (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
      v8);
  return (unsigned int)LastErrorFailHr;
}

```

## disassembly

```asm
0x18000a39c  mov     [rsp-8+arg_10], rbx
0x18000a3a1  mov     [rsp-8+arg_18], rsi
0x18000a3a6  push    rbp
0x18000a3a7  push    rdi
0x18000a3a8  push    r14
0x18000a3aa  lea     rbp, [rsp-160h]
0x18000a3b2  mov     eax, 260h
0x18000a3b7  call    _alloca_probe
0x18000a3bc  sub     rsp, rax
0x18000a3bf  mov     rax, cs:__security_cookie
0x18000a3c6  xor     rax, rsp
0x18000a3c9  mov     [rbp+170h+var_20], rax
0x18000a3d0  mov     r14, rdx
0x18000a3d3  mov     qword ptr [rdx], 0
0x18000a3da  mov     rbx, rcx
0x18000a3dd  call    cs:__imp_GetCurrentProcessId
0x18000a3e3  mov     [rsp+270h+var_248], rbx
0x18000a3e8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a3ef  mov     r9d, eax
0x18000a3f2  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000a3fa  mov     edx, 104h; unsigned __int64
0x18000a3ff  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a404  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000a409  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a40f  lea     rdx, [rsp+270h+Name]; lpName
0x18000a414  xor     r8d, r8d; dwFlags
0x18000a417  xor     ecx, ecx; lpMutexAttributes
0x18000a419  call    cs:__imp_CreateMutexExW
0x18000a41f  mov     [rsp+270h+var_240], rax
0x18000a424  mov     rbx, rax
0x18000a427  test    rax, rax
0x18000a42a  jnz     short loc_18000A472
0x18000a42c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a431  mov     edi, eax
0x18000a433  test    rbx, rbx
0x18000a436  jz      short loc_18000A449
0x18000a438  mov     rcx, rbx; hObject
0x18000a43b  call    cs:__imp_CloseHandle
0x18000a441  test    eax, eax
0x18000a443  jz      loc_18000A55B
0x18000a449  mov     eax, edi
0x18000a44b  mov     rcx, [rbp+170h+var_20]
0x18000a452  xor     rcx, rsp; StackCookie
0x18000a455  call    __security_check_cookie
0x18000a45a  lea     r11, [rsp+270h+var_10]
0x18000a462  mov     rbx, [r11+30h]
0x18000a466  mov     rsi, [r11+38h]
0x18000a46a  mov     rsp, r11
0x18000a46d  pop     r14
0x18000a46f  pop     rdi
0x18000a470  pop     rbp
0x18000a471  retn
0x18000a472  xor     r8d, r8d; bAlertable
0x18000a475  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a478  mov     rcx, rbx; hHandle
0x18000a47b  call    cs:__imp_WaitForSingleObjectEx
0x18000a481  cmp     eax, 102h
0x18000a486  jz      short loc_18000A498
0x18000a488  test    eax, 0FFFFFF7Fh
0x18000a48d  jnz     loc_18000A529
0x18000a493  mov     rsi, rbx
0x18000a496  jmp     short loc_18000A49A
0x18000a498  xor     esi, esi
0x18000a49a  lea     rdx, [rsp+270h+var_238]; void **
0x18000a49f  mov     [rsp+270h+var_238], 0
0x18000a4a8  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a4ad  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000a4b2  mov     edi, eax
0x18000a4b4  test    eax, eax
0x18000a4b6  jns     short loc_18000A4BF
0x18000a4b8  mov     edx, 12Bh
0x18000a4bd  jmp     short loc_18000A511
0x18000a4bf  mov     rcx, [rsp+270h+var_238]
0x18000a4c4  test    rcx, rcx
0x18000a4c7  jz      short loc_18000A4EF
0x18000a4c9  mov     [r14], rcx
0x18000a4cc  mov     eax, [rcx]
0x18000a4ce  inc     eax
0x18000a4d0  mov     [rcx], eax
0x18000a4d2  xor     edi, edi
0x18000a4d4  test    rsi, rsi
0x18000a4d7  jz      loc_18000A433
0x18000a4dd  mov     rcx, rsi; hMutex
0x18000a4e0  call    cs:__imp_ReleaseMutex
0x18000a4e6  test    eax, eax
0x18000a4e8  jz      short loc_18000A542
0x18000a4ea  jmp     loc_18000A433
0x18000a4ef  mov     r8, r14
0x18000a4f2  lea     rdx, [rsp+270h+var_240]
0x18000a4f7  lea     rcx, [rsp+270h+Name]
0x18000a4fc  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000a501  mov     rbx, [rsp+270h+var_240]
0x18000a506  mov     edi, eax
0x18000a508  test    eax, eax
0x18000a50a  jns     short loc_18000A4D2
0x18000a50c  mov     edx, 134h; void *
0x18000a511  mov     rcx, [rbp+178h]; this
0x18000a518  lea     r8, aWil; "wil"
0x18000a51f  mov     r9d, edi; char *
0x18000a522  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a527  jmp     short loc_18000A4D4
0x18000a529  mov     rcx, [rbp+178h]; this
0x18000a530  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000a537  mov     edx, 0C2Eh; void *
0x18000a53c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a542  mov     rcx, [rbp+178h]; this
0x18000a549  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000a550  mov     edx, 9DCh; void *
0x18000a555  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a55b  mov     rcx, [rbp+178h]; this
0x18000a562  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000a569  mov     edx, 9D2h; void *
0x18000a56e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
