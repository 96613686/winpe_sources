# EapLm::Peer::LegacyEapMethodRuntime::GetRegistryConfigPath(void)

- ea: `0x1800136f0`
- end: `0x18001377c`
- name: `?GetRegistryConfigPath@LegacyEapMethodRuntime@Peer@EapLm@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180002a90`
- `0x180009118`
- `0x1800122a8`
- `0x1800136f0`
- `0x18001dcbc`

## string_xrefs

- `0x180013717`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x18001374b`: `LoadConfig`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::LegacyEapMethodRuntime::GetRegistryConfigPath(__int64 a1, __int64 a2)
{
  int v3; // eax
  int v5; // [rsp+20h] [rbp-248h]
  wchar_t v6[264]; // [rsp+40h] [rbp-228h] BYREF

  v6[0] = 0;
  v5 = *(unsigned __int8 *)(a1 + 16);
  v3 = StringCchPrintfW(v6, 0x104u, L"%s\\%d", L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP", v5);
  if ( v3 < 0 )
    EapHost::EapException::Throw(L"LoadConfig", v6, v3);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    a2,
    v6);
  return a2;
}

```

## disassembly

```asm
0x1800136f0  push    rbx
0x1800136f2  sub     rsp, 260h
0x1800136f9  mov     rax, cs:__security_cookie
0x180013700  xor     rax, rsp
0x180013703  mov     [rsp+268h+var_18], rax
0x18001370b  xor     eax, eax
0x18001370d  mov     [rsp+268h+var_230], rdx
0x180013712  mov     [rsp+268h+var_228], ax
0x180013717  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x18001371e  movzx   eax, byte ptr [rcx+10h]
0x180013722  lea     r8, aSD; "%s\\%d"
0x180013729  mov     rbx, rdx
0x18001372c  mov     [rsp+268h+var_248], eax
0x180013730  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x180013735  mov     edx, 104h; unsigned __int64
0x18001373a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001373f  lea     rdx, [rsp+268h+var_228]; wchar_t *
0x180013744  test    eax, eax
0x180013746  jns     short loc_180013758
0x180013748  mov     r8d, eax; int
0x18001374b  lea     rcx, aLoadconfig; "LoadConfig"
0x180013752  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180013758  mov     rcx, rbx
0x18001375b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180013760  mov     rax, rbx
0x180013763  mov     rcx, [rsp+268h+var_18]
0x18001376b  xor     rcx, rsp; StackCookie
0x18001376e  call    __security_check_cookie
0x180013773  add     rsp, 260h
0x18001377a  pop     rbx
0x18001377b  retn
```
