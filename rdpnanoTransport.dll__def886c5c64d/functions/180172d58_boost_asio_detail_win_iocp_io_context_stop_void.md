# boost::asio::detail::win_iocp_io_context::stop(void)

- ea: `0x180172d58`
- end: `0x180172e06`
- name: `?stop@win_iocp_io_context@detail@asio@boost@@QEAAXXZ`
- size: `174`
- prototype: `void __fastcall(boost::asio::detail::win_iocp_io_context *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18015a8c8`
- `0x18015f520`
- `0x1801605e0`
- `0x1801659dc`
- `0x180165afc`
- `0x18016d5fc`
- `0x18016f980`
- `0x1801714ac`
- `0x180171db0`
- `0x180172050`
- `0x18017f4c0`
- `0x180181640`

## callees

- `0x180163f50`
- `0x18016dbe4`
- `0x180172d58`
- `0x18032f050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180172d93`
- `KERNEL32!GetLastError` at `0x180172d93`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180172d89`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180172d89`

## string_xrefs

- `0x180172db1`: `C:\__w\1\s\externals\vcpkg_installed\x64-windows-static\include\boost/asio/detail/impl/win_iocp_io_context.ipp`

## pseudocode

```c
void __fastcall boost::asio::detail::win_iocp_io_context::stop(boost::asio::detail::win_iocp_io_context *this)
{
  DWORD LastError; // eax
  const struct boost::source_location *v2; // r9
  char v3[8]; // [rsp+20h] [rbp-38h] BYREF
  const char *v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+34h] [rbp-24h]
  _DWORD v7[4]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v8; // [rsp+48h] [rbp-10h]

  if ( !_InterlockedExchange((volatile __int32 *)this + 15, 1)
    && !_InterlockedExchange((volatile __int32 *)this + 16, 1)
    && !PostQueuedCompletionStatus(*((HANDLE *)this + 6), 0, 0, 0) )
  {
    LastError = GetLastError();
    boost::system::error_code::error_code(
      (boost::system::error_code *)v7,
      LastError,
      (const struct boost::system::error_category *)&boost::system::detail::system_cat_holder<void>::instance);
    *(_QWORD *)v3 = "C:\\__w\\1\\s\\externals\\vcpkg_installed\\x64-windows-static\\include\\boost/asio/detail/impl/win_i"
                    "ocp_io_context.ipp";
    v4 = "void __cdecl boost::asio::detail::win_iocp_io_context::stop(void)";
    v5 = 309;
    v6 = 30;
    if ( (v8 & 1) != 0 && (v8 != 1 || v7[0]) )
      boost::asio::detail::do_throw_error(
        (boost::asio::detail *)v7,
        (const struct boost::system::error_code *)"pqcs",
        v3,
        v2);
  }
}

```

## disassembly

```asm
0x180172d58  mov     eax, 58h
0x180172d5d  call    _alloca_probe
0x180172d62  sub     rsp, rax
0x180172d65  mov     eax, 1
0x180172d6a  xchg    eax, [rcx+3Ch]
0x180172d6d  test    eax, eax
0x180172d6f  jnz     short loc_180172DEA
0x180172d71  mov     eax, 1
0x180172d76  xchg    eax, [rcx+40h]
0x180172d79  test    eax, eax
0x180172d7b  jnz     short loc_180172DEA
0x180172d7d  mov     rcx, [rcx+30h]; CompletionPort
0x180172d81  xor     r9d, r9d; lpOverlapped
0x180172d84  xor     r8d, r8d; dwCompletionKey
0x180172d87  xor     edx, edx; dwNumberOfBytesTransferred
0x180172d89  call    cs:__imp_PostQueuedCompletionStatus
0x180172d8f  test    eax, eax
0x180172d91  jnz     short loc_180172DEA
0x180172d93  call    cs:__imp_GetLastError
0x180172d99  mov     edx, eax; int
0x180172d9b  lea     r8, ?instance@?$system_cat_holder@X@detail@system@boost@@2Vsystem_error_category@234@B; struct boost::system::error_category *
0x180172da2  lea     rcx, [rsp+58h+var_20]; this
0x180172da7  call    ??0error_code@system@boost@@QEAA@HAEBVerror_category@12@@Z; boost::system::error_code::error_code(int,boost::system::error_category const &)
0x180172dac  test    byte ptr [rsp+58h+var_10], 1
0x180172db1  lea     rax, aCW1SExternalsV_8; "C:\\__w\\1\\s\\externals\\vcpkg_install"...
0x180172db8  mov     qword ptr [rsp+58h+var_38], rax
0x180172dbd  lea     rax, aVoidCdeclBoost_64; "void __cdecl boost::asio::detail::win_i"...
0x180172dc4  mov     [rsp+58h+var_30], rax
0x180172dc9  mov     [rsp+58h+var_28], 135h
0x180172dd1  mov     [rsp+58h+var_24], 1Eh
0x180172dd9  jz      short loc_180172DEA
0x180172ddb  cmp     [rsp+58h+var_10], 1
0x180172de1  jnz     short loc_180172DEF
0x180172de3  cmp     [rsp+58h+var_20], 0
0x180172de8  jnz     short loc_180172DEF
0x180172dea  add     rsp, 58h
0x180172dee  retn
0x180172def  lea     r8, [rsp+58h+var_38]; char *
0x180172df4  lea     rdx, aPqcs; "pqcs"
0x180172dfb  lea     rcx, [rsp+58h+var_20]; this
0x180172e00  call    ?do_throw_error@detail@asio@boost@@YAXAEBVerror_code@system@3@PEBDAEBUsource_location@3@@Z; boost::asio::detail::do_throw_error(boost::system::error_code const &,char const *,boost::source_location const &)
```
