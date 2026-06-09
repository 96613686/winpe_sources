# EapLm::Peer::LegacyEapMethodRuntime::GetRegistryConfigPath(void)

- ea: `0x180024090`
- end: `0x18002411c`
- name: `?GetRegistryConfigPath@LegacyEapMethodRuntime@Peer@EapLm@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800017a0`
- `0x1800034ec`
- `0x18000d098`
- `0x180015534`
- `0x180024090`

## string_xrefs

- `0x1800240b7`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`
- `0x1800240eb`: `LoadConfig`

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
    (__int64)v6);
  return a2;
}

```

## disassembly

```asm
0x180024090  push    rbx
0x180024092  sub     rsp, 260h
0x180024099  mov     rax, cs:__security_cookie
0x1800240a0  xor     rax, rsp
0x1800240a3  mov     [rsp+268h+var_18], rax
0x1800240ab  xor     eax, eax
0x1800240ad  mov     [rsp+268h+var_230], rdx
0x1800240b2  mov     [rsp+268h+var_228], ax
0x1800240b7  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ra"...
0x1800240be  movzx   eax, byte ptr [rcx+10h]
0x1800240c2  lea     r8, aSD; "%s\\%d"
0x1800240c9  mov     rbx, rdx
0x1800240cc  mov     [rsp+268h+var_248], eax
0x1800240d0  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x1800240d5  mov     edx, 104h; unsigned __int64
0x1800240da  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800240df  lea     rdx, [rsp+268h+var_228]; wchar_t *
0x1800240e4  test    eax, eax
0x1800240e6  jns     short loc_1800240F8
0x1800240e8  mov     r8d, eax; int
0x1800240eb  lea     rcx, aLoadconfig; "LoadConfig"
0x1800240f2  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800240f8  mov     rcx, rbx
0x1800240fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180024100  mov     rax, rbx
0x180024103  mov     rcx, [rsp+268h+var_18]
0x18002410b  xor     rcx, rsp; StackCookie
0x18002410e  call    __security_check_cookie
0x180024113  add     rsp, 260h
0x18002411a  pop     rbx
0x18002411b  retn
```
