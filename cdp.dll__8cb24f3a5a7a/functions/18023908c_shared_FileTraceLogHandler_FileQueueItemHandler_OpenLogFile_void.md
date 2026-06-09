# shared::FileTraceLogHandler::FileQueueItemHandler::OpenLogFile(void)

- ea: `0x18023908c`
- end: `0x18023922b`
- name: `?OpenLogFile@FileQueueItemHandler@FileTraceLogHandler@shared@@AEAAXXZ`
- size: `415`
- prototype: `void __fastcall(shared::FileTraceLogHandler::FileQueueItemHandler *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180239070`

## callees

- `0x180008ec8`
- `0x18000b724`
- `0x180030190`
- `0x180065e74`
- `0x1800a11bc`
- `0x1800a4718`
- `0x1800d8168`
- `0x1800df1dc`
- `0x1801ca940`
- `0x1801f6fb0`
- `0x18023908c`
- `0x1802394e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180239176`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180239176`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x18023918e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x18023918e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180239136`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1802391c6`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180239136`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1802391c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall shared::FileTraceLogHandler::FileQueueItemHandler::OpenLogFile(HANDLE *this)
{
  _QWORD *v2; // rax
  __int64 File2; // rax
  const CHAR *v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rax
  _OWORD Src[2]; // [rsp+30h] [rbp-19h] BYREF
  LPCSTR lpPathName[4]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v9[32]; // [rsp+70h] [rbp+27h] BYREF

  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(Src[0]) = 0;
  shared::GetCDPReadWriteDirectory((__int64)lpPathName);
  std::string::operator=(Src, lpPathName);
  std::string::append(Src);
  if ( (unsigned __int8)cdp::FileHelpers::PathFileExists(Src) )
  {
    v2 = (_QWORD *)cdp::ToWstring(v9, Src);
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    File2 = CreateFile2(v2, 0x40000000, 3, 4, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this + 1,
      File2);
    std::wstring::_Tidy_deallocate(v9);
    if ( (char *)this[1] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      shared::FileTraceLogHandler::FileQueueItemHandler::TruncateIfNeeded((shared::FileTraceLogHandler::FileQueueItemHandler *)this);
      SetFilePointer(this[1], 0, 0, 2u);
    }
  }
  else
  {
    v4 = (const CHAR *)lpPathName;
    if ( lpPathName[3] > (LPCSTR)0xF )
      v4 = lpPathName[0];
    CreateDirectoryA(v4, 0);
    v5 = (_QWORD *)cdp::ToWstring(v9, Src);
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    v6 = CreateFile2(v5, 0x40000000, 3, 4, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this + 1,
      v6);
    std::wstring::_Tidy_deallocate(v9);
    if ( (char *)this[1] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      shared::FileTraceLogHandler::FileQueueItemHandler::WriteByteOrderMarker((shared::FileTraceLogHandler::FileQueueItemHandler *)this);
  }
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(lpPathName);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(Src);
}

```

## disassembly

```asm
0x18023908c  mov     [rsp-8+arg_8], rbx
0x180239091  mov     [rsp-8+arg_10], rdi
0x180239096  push    rbp
0x180239097  lea     rbp, [rsp-57h]
0x18023909c  sub     rsp, 0A0h
0x1802390a3  mov     rax, cs:__security_cookie
0x1802390aa  xor     rax, rsp
0x1802390ad  mov     [rbp+57h+var_10], rax
0x1802390b1  mov     rdi, rcx
0x1802390b4  xorps   xmm0, xmm0
0x1802390b7  movups  [rbp+57h+Src], xmm0
0x1802390bb  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1802390c3  movdqu  [rbp+57h+var_60], xmm1
0x1802390c8  mov     byte ptr [rbp+57h+Src], 0
0x1802390cc  lea     rcx, [rbp+57h+lpPathName]
0x1802390d0  call    ?GetCDPReadWriteDirectory@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; shared::GetCDPReadWriteDirectory(void)
0x1802390d5  nop
0x1802390d6  lea     rdx, [rbp+57h+lpPathName]
0x1802390da  lea     rcx, [rbp+57h+Src]
0x1802390de  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1802390e3  lea     rdx, aCdptracesLog; "\\CDPTraces.log"
0x1802390ea  lea     rcx, [rbp+57h+Src]; Src
0x1802390ee  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::append(char const * const)
0x1802390f3  lea     rcx, [rbp+57h+Src]
0x1802390f7  call    ?PathFileExists@FileHelpers@cdp@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::FileHelpers::PathFileExists(std::string const &)
0x1802390fc  test    al, al
0x1802390fe  jz      short loc_18023917E
0x180239100  lea     rdx, [rbp+57h+Src]
0x180239104  lea     rcx, [rbp+57h+var_30]
0x180239108  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x18023910d  cmp     qword ptr [rax+18h], 7
0x180239112  jbe     short loc_180239117
0x180239114  mov     rax, [rax]
0x180239117  lea     rbx, [rdi+8]
0x18023911b  mov     [rsp+0A0h+var_80], 0
0x180239124  mov     edx, 40000000h
0x180239129  mov     r9d, 4
0x18023912f  lea     r8d, [r9-1]
0x180239133  mov     rcx, rax
0x180239136  call    cs:__imp_CreateFile2
0x18023913c  mov     rdx, rax
0x18023913f  mov     rcx, rbx
0x180239142  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180239147  lea     rcx, [rbp+57h+var_30]
0x18023914b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180239150  mov     rax, [rbx]
0x180239153  dec     rax
0x180239156  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18023915a  ja      loc_1802391F7
0x180239160  mov     rcx, rdi; this
0x180239163  call    ?TruncateIfNeeded@FileQueueItemHandler@FileTraceLogHandler@shared@@AEAAXXZ; shared::FileTraceLogHandler::FileQueueItemHandler::TruncateIfNeeded(void)
0x180239168  mov     r9d, 2; dwMoveMethod
0x18023916e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180239171  xor     edx, edx; lDistanceToMove
0x180239173  mov     rcx, [rbx]; hFile
0x180239176  call    cs:__imp_SetFilePointer
0x18023917c  jmp     short loc_1802391F7
0x18023917e  lea     rcx, [rbp+57h+lpPathName]
0x180239182  cmp     [rbp+57h+var_38], 0Fh
0x180239187  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x18023918c  xor     edx, edx; lpSecurityAttributes
0x18023918e  call    cs:__imp_CreateDirectoryA
0x180239194  lea     rdx, [rbp+57h+Src]
0x180239198  lea     rcx, [rbp+57h+var_30]
0x18023919c  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1802391a1  cmp     qword ptr [rax+18h], 7
0x1802391a6  jbe     short loc_1802391AB
0x1802391a8  mov     rax, [rax]
0x1802391ab  mov     [rsp+0A0h+var_80], 0
0x1802391b4  mov     edx, 40000000h
0x1802391b9  mov     r9d, 4
0x1802391bf  lea     r8d, [r9-1]
0x1802391c3  mov     rcx, rax
0x1802391c6  call    cs:__imp_CreateFile2
0x1802391cc  mov     rdx, rax
0x1802391cf  lea     rcx, [rdi+8]
0x1802391d3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802391d8  lea     rcx, [rbp+57h+var_30]
0x1802391dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802391e1  mov     rax, [rdi+8]
0x1802391e5  dec     rax
0x1802391e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1802391ec  ja      short loc_1802391F7
0x1802391ee  mov     rcx, rdi; this
0x1802391f1  call    ?WriteByteOrderMarker@FileQueueItemHandler@FileTraceLogHandler@shared@@AEAAXXZ; shared::FileTraceLogHandler::FileQueueItemHandler::WriteByteOrderMarker(void)
0x1802391f6  nop
0x1802391f7  lea     rcx, [rbp+57h+lpPathName]; void *
0x1802391fb  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180239200  nop
0x180239201  lea     rcx, [rbp+57h+Src]; void *
0x180239205  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18023920a  mov     rcx, [rbp+57h+var_10]
0x18023920e  xor     rcx, rsp; StackCookie
0x180239211  call    __security_check_cookie
0x180239216  lea     r11, [rsp+0A0h+var_s0]
0x18023921e  mov     rbx, [r11+18h]
0x180239222  mov     rdi, [r11+20h]
0x180239226  mov     rsp, r11
0x180239229  pop     rbp
0x18023922a  retn
```
