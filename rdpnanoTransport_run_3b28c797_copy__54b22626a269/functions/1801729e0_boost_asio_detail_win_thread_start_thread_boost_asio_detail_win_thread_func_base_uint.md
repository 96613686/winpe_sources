# boost::asio::detail::win_thread::start_thread(boost::asio::detail::win_thread::func_base *,uint)

- ea: `0x1801729e0`
- end: `0x180172c46`
- name: `?start_thread@win_thread@detail@asio@boost@@AEAAPEAVfunc_base@1234@PEAV51234@I@Z`
- size: `614`
- prototype: `struct boost::asio::detail::win_thread::func_base *__fastcall(boost::asio::detail::win_thread *__hidden this, struct boost::asio::detail::win_thread::func_base *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18015dc04`
- `0x180164258`
- `0x1801645a0`
- `0x18016d500`

## callees

- `0x180163f50`
- `0x18016dbe4`
- `0x1801729e0`
- `0x18032f050`
- `0x18032f0b0`
- `0x180344b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180172abd`
- `KERNEL32!CloseHandle` at `0x180172b5d`
- `KERNEL32!CloseHandle` at `0x180172b67`
- `KERNEL32!CloseHandle` at `0x180172bd5`
- `KERNEL32!CloseHandle` at `0x180172abd`
- `KERNEL32!CloseHandle` at `0x180172b5d`
- `KERNEL32!CloseHandle` at `0x180172b67`
- `KERNEL32!CloseHandle` at `0x180172bd5`
- `KERNEL32!GetLastError` at `0x180172a34`
- `KERNEL32!GetLastError` at `0x180172ab1`
- `KERNEL32!GetLastError` at `0x180172b51`
- `KERNEL32!GetLastError` at `0x180172a34`
- `KERNEL32!GetLastError` at `0x180172ab1`
- `KERNEL32!GetLastError` at `0x180172b51`
- `KERNEL32!WaitForSingleObject` at `0x180172bcb`
- `KERNEL32!WaitForSingleObject` at `0x180172bcb`
- `KERNEL32!CreateEventW` at `0x180172a1e`
- `KERNEL32!CreateEventW` at `0x180172aa2`
- `KERNEL32!CreateEventW` at `0x180172a1e`
- `KERNEL32!CreateEventW` at `0x180172aa2`

## string_xrefs

- `0x180172a62`: `class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class boost::asio::detail::win_thread::func_base *,unsigned int)`
- `0x180172ae9`: `class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class boost::asio::detail::win_thread::func_base *,unsigned int)`
- `0x180172b93`: `class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class boost::asio::detail::win_thread::func_base *,unsigned int)`
- `0x180172a28`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/asio/detail/impl/win_thread.ipp`
- `0x180172c20`: `thread.entry_event`
- `0x180172c35`: `thread.exit_event`
- `0x180172c0b`: `thread`

## pseudocode

```c
struct boost::asio::detail::win_thread::func_base *__fastcall boost::asio::detail::win_thread::start_thread(
        boost::asio::detail::win_thread *this,
        struct boost::asio::detail::win_thread::func_base *a2,
        unsigned int a3)
{
  HANDLE EventW; // rax
  DWORD LastError; // ebx
  const struct boost::source_location *v7; // r9
  HANDLE v8; // rax
  DWORD v9; // ebx
  const struct boost::source_location *v10; // r9
  uintptr_t v11; // rax
  DWORD v12; // ebx
  const struct boost::source_location *v13; // r9
  void *v14; // rcx
  char v16[8]; // [rsp+30h] [rbp-40h] BYREF
  const char *v17; // [rsp+38h] [rbp-38h]
  __int64 v18; // [rsp+40h] [rbp-30h]
  char v19[8]; // [rsp+48h] [rbp-28h] BYREF
  const char *v20; // [rsp+50h] [rbp-20h]
  __int64 v21; // [rsp+58h] [rbp-18h]
  unsigned int ThrdAddr; // [rsp+60h] [rbp-10h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)a2 + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct boost::asio::detail::win_thread::func_base *))(*(_QWORD *)a2 + 16LL))(a2);
    boost::system::error_code::error_code(
      (boost::system::error_code *)v19,
      LastError,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    v17 = "class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class "
          "boost::asio::detail::win_thread::func_base *,unsigned int)";
    *(_QWORD *)v16 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_thread.ipp";
    v18 = 0x1A00000050LL;
    if ( (v21 & 1) != 0 && (v21 != 1 || *(_DWORD *)v19) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v19,
        (const struct boost::system::error_code *)"thread.entry_event",
        v16,
        v7);
  }
  v8 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)a2 + 3) = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    CloseHandle(*((HANDLE *)a2 + 2));
    (*(void (__fastcall **)(struct boost::asio::detail::win_thread::func_base *))(*(_QWORD *)a2 + 16LL))(a2);
    boost::system::error_code::error_code(
      (boost::system::error_code *)v16,
      v9,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    v20 = "class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class "
          "boost::asio::detail::win_thread::func_base *,unsigned int)";
    *(_QWORD *)v19 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_thread.ipp";
    v21 = 0x1A0000005BLL;
    if ( (v18 & 1) != 0 && (v18 != 1 || *(_DWORD *)v16) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v16,
        (const struct boost::system::error_code *)"thread.exit_event",
        v19,
        v10);
  }
  ThrdAddr = 0;
  v11 = beginthreadex(0, a3, boost::asio::detail::win_thread_function, a2, 0, &ThrdAddr);
  *((_QWORD *)a2 + 1) = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    CloseHandle(*((HANDLE *)a2 + 2));
    CloseHandle(*((HANDLE *)a2 + 3));
    (*(void (__fastcall **)(struct boost::asio::detail::win_thread::func_base *))(*(_QWORD *)a2 + 16LL))(a2);
    boost::system::error_code::error_code(
      (boost::system::error_code *)v16,
      v12,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    v20 = "class boost::asio::detail::win_thread::func_base *__cdecl boost::asio::detail::win_thread::start_thread(class "
          "boost::asio::detail::win_thread::func_base *,unsigned int)";
    *(_QWORD *)v19 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_thread.ipp";
    v21 = 0x1A00000069LL;
    if ( (v18 & 1) != 0 && (v18 != 1 || *(_DWORD *)v16) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v16,
        (const struct boost::system::error_code *)"thread",
        v19,
        v13);
  }
  v14 = (void *)*((_QWORD *)a2 + 2);
  if ( v14 )
  {
    WaitForSingleObject(v14, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)a2 + 2));
    *((_QWORD *)a2 + 2) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1801729e0  mov     [rsp-18h+arg_0], rbx
0x1801729e5  mov     [rsp-18h+arg_18], rsi
0x1801729ea  push    rbp
0x1801729eb  push    rdi
0x1801729ec  push    r13
0x1801729ee  mov     rbp, rsp
0x1801729f1  mov     eax, 70h
0x1801729f6  call    _alloca_probe
0x1801729fb  sub     rsp, rax
0x1801729fe  mov     rax, cs:__security_cookie
0x180172a05  xor     rax, rsp
0x180172a08  mov     [rbp+var_8], rax
0x180172a0c  xor     r9d, r9d; lpName
0x180172a0f  mov     esi, r8d
0x180172a12  mov     rdi, rdx
0x180172a15  xor     r8d, r8d; bInitialState
0x180172a18  xor     ecx, ecx; lpEventAttributes
0x180172a1a  lea     edx, [r9+1]; bManualReset
0x180172a1e  call    cs:__imp_CreateEventW
0x180172a24  mov     [rdi+10h], rax
0x180172a28  lea     r13, aCW1SExternalsV_14; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x180172a2f  test    rax, rax
0x180172a32  jnz     short loc_180172A96
0x180172a34  call    cs:__imp_GetLastError
0x180172a3a  mov     ebx, eax
0x180172a3c  mov     rcx, rdi
0x180172a3f  mov     rax, [rdi]
0x180172a42  mov     rax, [rax+10h]
0x180172a46  call    cs:__guard_dispatch_icall_fptr
0x180172a4c  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x180172a53  mov     edx, ebx; int
0x180172a55  lea     rcx, [rbp+var_28]; this
0x180172a59  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180172a5e  test    byte ptr [rbp+var_18], 1
0x180172a62  lea     rax, aClassBoostAsio_0; "class boost::asio::detail::win_thread::"...
0x180172a69  mov     [rbp+var_38], rax
0x180172a6d  mov     qword ptr [rbp+var_40], r13
0x180172a71  mov     dword ptr [rbp+var_30], 50h ; 'P'
0x180172a78  mov     dword ptr [rbp+var_30+4], 1Ah
0x180172a7f  jz      short loc_180172A96
0x180172a81  cmp     [rbp+var_18], 1
0x180172a86  jnz     loc_180172C1C
0x180172a8c  cmp     dword ptr [rbp+var_28], 0
0x180172a90  jnz     loc_180172C1C
0x180172a96  xor     r9d, r9d; lpName
0x180172a99  xor     r8d, r8d; bInitialState
0x180172a9c  xor     ecx, ecx; lpEventAttributes
0x180172a9e  lea     edx, [r9+1]; bManualReset
0x180172aa2  call    cs:__imp_CreateEventW
0x180172aa8  mov     [rdi+18h], rax
0x180172aac  test    rax, rax
0x180172aaf  jnz     short loc_180172B1D
0x180172ab1  call    cs:__imp_GetLastError
0x180172ab7  mov     rcx, [rdi+10h]; hObject
0x180172abb  mov     ebx, eax
0x180172abd  call    cs:__imp_CloseHandle
0x180172ac3  mov     rax, [rdi]
0x180172ac6  mov     rcx, rdi
0x180172ac9  mov     rax, [rax+10h]
0x180172acd  call    cs:__guard_dispatch_icall_fptr
0x180172ad3  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x180172ada  mov     edx, ebx; int
0x180172adc  lea     rcx, [rbp+var_40]; this
0x180172ae0  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180172ae5  test    byte ptr [rbp+var_30], 1
0x180172ae9  lea     rax, aClassBoostAsio_0; "class boost::asio::detail::win_thread::"...
0x180172af0  mov     [rbp+var_20], rax
0x180172af4  mov     qword ptr [rbp+var_28], r13
0x180172af8  mov     dword ptr [rbp+var_18], 5Bh ; '['
0x180172aff  mov     dword ptr [rbp+var_18+4], 1Ah
0x180172b06  jz      short loc_180172B1D
0x180172b08  cmp     [rbp+var_30], 1
0x180172b0d  jnz     loc_180172C31
0x180172b13  cmp     dword ptr [rbp+var_40], 0
0x180172b17  jnz     loc_180172C31
0x180172b1d  lea     rax, [rbp+var_10]
0x180172b21  mov     [rbp+var_10], 0
0x180172b28  mov     [rsp+70h+ThrdAddr], rax; ThrdAddr
0x180172b2d  lea     r8, ?win_thread_function@detail@asio@boost@@YAIPEAX@Z; StartAddress
0x180172b34  mov     r9, rdi; ArgList
0x180172b37  mov     [rsp+70h+InitFlag], 0; InitFlag
0x180172b3f  mov     edx, esi; StackSize
0x180172b41  xor     ecx, ecx; Security
0x180172b43  call    _beginthreadex
0x180172b48  mov     [rdi+8], rax
0x180172b4c  test    rax, rax
0x180172b4f  jnz     short loc_180172BBF
0x180172b51  call    cs:__imp_GetLastError
0x180172b57  mov     rcx, [rdi+10h]; hObject
0x180172b5b  mov     ebx, eax
0x180172b5d  call    cs:__imp_CloseHandle
0x180172b63  mov     rcx, [rdi+18h]; hObject
0x180172b67  call    cs:__imp_CloseHandle
0x180172b6d  mov     rax, [rdi]
0x180172b70  mov     rcx, rdi
0x180172b73  mov     rax, [rax+10h]
0x180172b77  call    cs:__guard_dispatch_icall_fptr
0x180172b7d  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x180172b84  mov     edx, ebx; int
0x180172b86  lea     rcx, [rbp+var_40]; this
0x180172b8a  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180172b8f  test    byte ptr [rbp+var_30], 1
0x180172b93  lea     rax, aClassBoostAsio_0; "class boost::asio::detail::win_thread::"...
0x180172b9a  mov     [rbp+var_20], rax
0x180172b9e  mov     qword ptr [rbp+var_28], r13
0x180172ba2  mov     dword ptr [rbp+var_18], 69h ; 'i'
0x180172ba9  mov     dword ptr [rbp+var_18+4], 1Ah
0x180172bb0  jz      short loc_180172BBF
0x180172bb2  cmp     [rbp+var_30], 1
0x180172bb7  jnz     short loc_180172C07
0x180172bb9  cmp     dword ptr [rbp+var_40], 0
0x180172bbd  jnz     short loc_180172C07
0x180172bbf  mov     rcx, [rdi+10h]; hHandle
0x180172bc3  test    rcx, rcx
0x180172bc6  jz      short loc_180172BE3
0x180172bc8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180172bcb  call    cs:__imp_WaitForSingleObject
0x180172bd1  mov     rcx, [rdi+10h]; hObject
0x180172bd5  call    cs:__imp_CloseHandle
0x180172bdb  mov     qword ptr [rdi+10h], 0
0x180172be3  mov     rax, rdi
0x180172be6  mov     rcx, [rbp+var_8]
0x180172bea  xor     rcx, rsp; StackCookie
0x180172bed  call    __security_check_cookie
0x180172bf2  lea     r11, [rsp+70h+var_s0]
0x180172bf7  mov     rbx, [r11+20h]
0x180172bfb  mov     rsi, [r11+38h]
0x180172bff  mov     rsp, r11
0x180172c02  pop     r13
0x180172c04  pop     rdi
0x180172c05  pop     rbp
0x180172c06  retn
0x180172c07  lea     r8, [rbp+var_28]; char *
0x180172c0b  lea     rdx, aThread; "thread"
0x180172c12  lea     rcx, [rbp+var_40]; this
0x180172c16  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x180172c1c  lea     r8, [rbp+var_40]; char *
0x180172c20  lea     rdx, aThreadEntryEve; "thread.entry_event"
0x180172c27  lea     rcx, [rbp+var_28]; this
0x180172c2b  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
0x180172c31  lea     r8, [rbp+var_28]; char *
0x180172c35  lea     rdx, aThreadExitEven; "thread.exit_event"
0x180172c3c  lea     rcx, [rbp+var_40]; this
0x180172c40  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
```
