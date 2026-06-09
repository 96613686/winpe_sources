# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c7c0`
- end: `0x18000ca5e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `670`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009e30`

## callees

- `0x180008f80`
- `0x18000b590`
- `0x18000be40`
- `0x18000be70`
- `0x18000c568`
- `0x18000c7c0`
- `0x18000cbac`
- `0x18032f050`
- `0x18032f0b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c9c2`
- `KERNEL32!CloseHandle` at `0x18000c9d6`
- `KERNEL32!CloseHandle` at `0x18000ca04`
- `KERNEL32!CloseHandle` at `0x18000c9c2`
- `KERNEL32!CloseHandle` at `0x18000c9d6`
- `KERNEL32!CloseHandle` at `0x18000ca04`
- `KERNEL32!GetLastError` at `0x18000c886`
- `KERNEL32!GetLastError` at `0x18000c886`
- `KERNEL32!OpenSemaphoreW` at `0x18000c878`
- `KERNEL32!OpenSemaphoreW` at `0x18000c94f`
- `KERNEL32!OpenSemaphoreW` at `0x18000c878`
- `KERNEL32!OpenSemaphoreW` at `0x18000c94f`

## string_xrefs

- `0x18000ca1a`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`
- `0x18000ca33`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`
- `0x18000ca4c`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        char a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v7; // rdx
  signed __int64 v8; // r9
  WCHAR *v9; // rcx
  WCHAR v10; // ax
  WCHAR *v11; // rax
  HANDLE v12; // rax
  void *v13; // r14
  const char *v14; // r9
  unsigned int LastError; // edi
  int v16; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v19; // rbx
  const char *v20; // r9
  int v21; // eax
  const char *v22; // r9
  const char *v23; // r9
  __int64 v24; // rax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v28; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  v7 = 260;
  v8 = (char *)a1 - (char *)Name;
  v9 = Name;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v10 = *(WCHAR *)((char *)v9 + v8);
    if ( !v10 )
      break;
    *v9++ = v10;
    --v7;
  }
  while ( v7 );
  v11 = v9 - 1;
  if ( v7 )
    v11 = v9;
  *v11 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v13 = v12;
  if ( !v12 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v14);
LABEL_15:
    if ( !v13 )
      return LastError;
    goto LABEL_31;
  }
  v16 = 0;
  v26 = 0;
  v27 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    goto LABEL_15;
  }
  if ( !a2 )
    goto LABEL_28;
  StringCchCatW(Name, 0x104u, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v28 = v19;
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           &v28,
                           0) )
  {
    v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v27);
    LastError = v21;
    if ( v21 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v21,
        v26);
      goto LABEL_22;
    }
    if ( v19 && !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D2,
        (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
        v23);
    v16 = v27;
LABEL_28:
    v24 = v26;
    if ( a4 )
      *a4 = 1;
    LastError = 0;
    *a3 = ((__int64)v16 << 31) | v24;
    goto LABEL_31;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v20);
LABEL_22:
  if ( v19 && !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D2,
      (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
      v22);
LABEL_31:
  if ( !CloseHandle(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x9D2,
      (unsigned int)"C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\wil\\resource.h",
      v25);
  return LastError;
}

```

## disassembly

```asm
0x18000c7c0  mov     [rsp-8+arg_0], rbx
0x18000c7c5  push    rbp
0x18000c7c6  push    rsi
0x18000c7c7  push    rdi
0x18000c7c8  push    r12
0x18000c7ca  push    r13
0x18000c7cc  push    r14
0x18000c7ce  push    r15
0x18000c7d0  lea     rbp, [rsp-150h]
0x18000c7d8  mov     eax, 250h
0x18000c7dd  call    _alloca_probe
0x18000c7e2  sub     rsp, rax
0x18000c7e5  mov     rax, cs:__security_cookie
0x18000c7ec  xor     rax, rsp
0x18000c7ef  mov     [rbp+180h+var_40], rax
0x18000c7f6  mov     rsi, r9
0x18000c7f9  xor     r13d, r13d
0x18000c7fc  mov     r15, r8
0x18000c7ff  mov     r12b, dl
0x18000c802  mov     r9, rcx
0x18000c805  test    rsi, rsi
0x18000c808  jz      short loc_18000C80D
0x18000c80a  mov     [rsi], r13b
0x18000c80d  mov     r10d, 104h
0x18000c813  mov     [r8], r13
0x18000c816  lea     rax, [rsp+280h+Name]
0x18000c81b  mov     edx, r10d
0x18000c81e  sub     r9, rax
0x18000c821  lea     rcx, [rsp+280h+Name]
0x18000c826  lea     rax, [rdx+7FFFFEFAh]
0x18000c82d  test    rax, rax
0x18000c830  jz      short loc_18000C849
0x18000c832  movzx   eax, word ptr [rcx+r9]
0x18000c837  test    ax, ax
0x18000c83a  jz      short loc_18000C849
0x18000c83c  mov     [rcx], ax
0x18000c83f  add     rcx, 2
0x18000c843  sub     rdx, 1
0x18000c847  jnz     short loc_18000C826
0x18000c849  test    rdx, rdx
0x18000c84c  lea     rax, [rcx-2]
0x18000c850  lea     r8, aP0; "_p0"
0x18000c857  mov     rdx, r10; unsigned __int64
0x18000c85a  cmovnz  rax, rcx
0x18000c85e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c863  mov     [rax], r13w
0x18000c867  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c86c  lea     r8, [rsp+280h+Name]; lpName
0x18000c871  xor     edx, edx; bInheritHandle
0x18000c873  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c878  call    cs:__imp_OpenSemaphoreW
0x18000c87e  mov     r14, rax
0x18000c881  test    rax, rax
0x18000c884  jnz     short loc_18000C8B2
0x18000c886  call    cs:__imp_GetLastError
0x18000c88c  cmp     eax, 2
0x18000c88f  jnz     short loc_18000C896
0x18000c891  mov     edi, r13d
0x18000c894  jmp     short loc_18000C8EF
0x18000c896  mov     rcx, [rbp+188h]; this
0x18000c89d  lea     r8, aWil; "wil"
0x18000c8a4  mov     edx, 0CDh; void *
0x18000c8a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c8ae  mov     edi, eax
0x18000c8b0  jmp     short loc_18000C8EF
0x18000c8b2  mov     ebx, r13d
0x18000c8b5  mov     [rsp+280h+var_260], r13d; int
0x18000c8ba  lea     rdx, [rsp+280h+var_260]; int *
0x18000c8bf  mov     [rsp+280h+var_25C], ebx
0x18000c8c3  mov     rcx, r14; void *
0x18000c8c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c8cb  mov     edi, eax
0x18000c8cd  test    eax, eax
0x18000c8cf  jns     short loc_18000C924
0x18000c8d1  lfence
0x18000c8d4  mov     rcx, [rbp+188h]; this
0x18000c8db  lea     r8, aWil; "wil"
0x18000c8e2  mov     r9d, eax; char *
0x18000c8e5  mov     edx, 0D3h; void *
0x18000c8ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8ef  test    r14, r14
0x18000c8f2  jnz     loc_18000CA01
0x18000c8f8  mov     eax, edi
0x18000c8fa  mov     rcx, [rbp+180h+var_40]
0x18000c901  xor     rcx, rsp; StackCookie
0x18000c904  call    __security_check_cookie
0x18000c909  mov     rbx, [rsp+280h+arg_0]
0x18000c911  add     rsp, 250h
0x18000c918  pop     r15
0x18000c91a  pop     r14
0x18000c91c  pop     r13
0x18000c91e  pop     r12
0x18000c920  pop     rdi
0x18000c921  pop     rsi
0x18000c922  pop     rbp
0x18000c923  retn
0x18000c924  test    r12b, r12b
0x18000c927  jz      loc_18000C9E4
0x18000c92d  lea     r8, asc_1803D4BD0; "h"
0x18000c934  mov     edx, 104h; unsigned __int64
0x18000c939  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c93e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c943  lea     r8, [rsp+280h+Name]; lpName
0x18000c948  xor     edx, edx; bInheritHandle
0x18000c94a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c94f  call    cs:__imp_OpenSemaphoreW
0x18000c955  xor     edx, edx
0x18000c957  lea     rcx, [rsp+280h+var_258]
0x18000c95c  mov     rbx, rax
0x18000c95f  mov     [rsp+280h+var_258], rax
0x18000c964  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18000c969  test    al, al
0x18000c96b  jz      short loc_18000C989
0x18000c96d  mov     rcx, [rbp+188h]; this
0x18000c974  lea     r8, aWil; "wil"
0x18000c97b  mov     edx, 0D9h; void *
0x18000c980  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c985  mov     edi, eax
0x18000c987  jmp     short loc_18000C9BA
0x18000c989  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c98e  mov     rcx, rbx; void *
0x18000c991  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c996  mov     edi, eax
0x18000c998  test    eax, eax
0x18000c99a  jns     short loc_18000C9CE
0x18000c99c  lfence
0x18000c99f  mov     rcx, [rbp+188h]; this
0x18000c9a6  lea     r8, aWil; "wil"
0x18000c9ad  mov     r9d, eax; char *
0x18000c9b0  mov     edx, 0DBh; void *
0x18000c9b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c9ba  test    rbx, rbx
0x18000c9bd  jz      short loc_18000CA01
0x18000c9bf  mov     rcx, rbx; hObject
0x18000c9c2  call    cs:__imp_CloseHandle
0x18000c9c8  test    eax, eax
0x18000c9ca  jz      short loc_18000CA2C
0x18000c9cc  jmp     short loc_18000CA01
0x18000c9ce  test    rbx, rbx
0x18000c9d1  jz      short loc_18000C9E0
0x18000c9d3  mov     rcx, rbx; hObject
0x18000c9d6  call    cs:__imp_CloseHandle
0x18000c9dc  test    eax, eax
0x18000c9de  jz      short loc_18000CA13
0x18000c9e0  mov     ebx, [rsp+280h+var_25C]
0x18000c9e4  movsxd  rax, [rsp+280h+var_260]
0x18000c9e9  movsxd  rcx, ebx
0x18000c9ec  shl     rcx, 1Fh
0x18000c9f0  test    rsi, rsi
0x18000c9f3  jz      short loc_18000C9F8
0x18000c9f5  mov     byte ptr [rsi], 1
0x18000c9f8  or      rax, rcx
0x18000c9fb  mov     edi, r13d
0x18000c9fe  mov     [r15], rax
0x18000ca01  mov     rcx, r14; hObject
0x18000ca04  call    cs:__imp_CloseHandle
0x18000ca0a  test    eax, eax
0x18000ca0c  jz      short loc_18000CA45
0x18000ca0e  jmp     loc_18000C8F8
0x18000ca13  mov     rcx, [rbp+188h]; this
0x18000ca1a  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000ca21  mov     edx, 9D2h; void *
0x18000ca26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca2c  mov     rcx, [rbp+188h]; this
0x18000ca33  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000ca3a  mov     edx, 9D2h; void *
0x18000ca3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ca45  mov     rcx, [rbp+188h]; this
0x18000ca4c  lea     r8, aCW1SExternalsV_9; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x18000ca53  mov     edx, 9D2h; void *
0x18000ca58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
