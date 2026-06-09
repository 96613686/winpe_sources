# EapLm::Peer::LegacyEapMethodRuntime::GetRegistryConfigPath(void)

- ea: `0x180013ee0`
- end: `0x180013f6d`
- name: `?GetRegistryConfigPath@LegacyEapMethodRuntime@Peer@EapLm@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180002af0`
- `0x1800094d0`
- `0x180012a28`
- `0x180013ee0`
- `0x18001e7c0`

## string_xrefs

- `0x180013f07`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x180013f3b`: `LoadConfig`

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
0x180013ee0  push    rbx
0x180013ee2  sub     rsp, 260h
0x180013ee9  mov     rax, cs:__security_cookie
0x180013ef0  xor     rax, rsp
0x180013ef3  mov     [rsp+268h+var_18], rax
0x180013efb  xor     eax, eax
0x180013efd  mov     [rsp+268h+var_230], rdx
0x180013f02  mov     [rsp+268h+var_228], ax
0x180013f07  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x180013f0e  movzx   eax, byte ptr [rcx+10h]
0x180013f12  lea     r8, aSD; "%s\\%d"
0x180013f19  mov     rbx, rdx
0x180013f1c  mov     [rsp+268h+var_248], eax
0x180013f20  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x180013f25  mov     edx, 104h; unsigned __int64
0x180013f2a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013f2f  lea     rdx, [rsp+268h+var_228]; wchar_t *
0x180013f34  test    eax, eax
0x180013f36  jns     short loc_180013F48
0x180013f38  mov     r8d, eax; int
0x180013f3b  lea     rcx, aLoadconfig; "LoadConfig"
0x180013f42  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180013f48  mov     rcx, rbx
0x180013f4b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180013f50  mov     rax, rbx
0x180013f53  mov     rcx, [rsp+268h+var_18]
0x180013f5b  xor     rcx, rsp; StackCookie
0x180013f5e  call    __security_check_cookie
0x180013f63  add     rsp, 260h
0x180013f6a  pop     rbx
0x180013f6b  retn
```
