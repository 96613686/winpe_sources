# EapLm::Peer::BaseEapMethodRuntime::GetRegistryConfigPath(void)

- ea: `0x180029820`
- end: `0x180029898`
- name: `?GetRegistryConfigPath@BaseEapMethodRuntime@Peer@EapLm@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800017a0`
- `0x18000d098`
- `0x180015534`
- `0x180029820`
- `0x18002e67c`

## string_xrefs

- `0x18002985b`: `eapMethodRegPath`
- `0x180029862`: `LoadConfig`

## pseudocode

```c
const wchar_t *__fastcall EapLm::Peer::BaseEapMethodRuntime::GetRegistryConfigPath(
        const struct _EAP_METHOD_TYPE *a1,
        const wchar_t *a2)
{
  wchar_t v4[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( (int)EapLm::IEapMethod::ConstructMethodRegPath(a1 + 1, a2, v4) < 0 )
    EapHost::EapException::Throw(L"LoadConfig", L"eapMethodRegPath", -2147024809);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    (__int64)a2,
    (__int64)v4);
  return a2;
}

```

## disassembly

```asm
0x180029820  push    rbx
0x180029822  sub     rsp, 250h
0x180029829  mov     rax, cs:__security_cookie
0x180029830  xor     rax, rsp
0x180029833  mov     [rsp+258h+var_18], rax
0x18002983b  add     rcx, 10h; struct _EAP_METHOD_TYPE *
0x18002983f  mov     [rsp+258h+var_230], rdx
0x180029844  lea     r8, [rsp+258h+var_228]; wchar_t *
0x180029849  mov     rbx, rdx
0x18002984c  call    ?ConstructMethodRegPath@IEapMethod@EapLm@@SAJAEBU_EAP_METHOD_TYPE@@QEB_WPEA_WK@Z; EapLm::IEapMethod::ConstructMethodRegPath(_EAP_METHOD_TYPE const &,wchar_t const * const,wchar_t *,ulong)
0x180029851  test    eax, eax
0x180029853  jns     short loc_18002986F
0x180029855  mov     r8d, 80070057h; int
0x18002985b  lea     rdx, aEapmethodregpa; "eapMethodRegPath"
0x180029862  lea     rcx, aLoadconfig; "LoadConfig"
0x180029869  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x18002986f  lea     rdx, [rsp+258h+var_228]
0x180029874  mov     rcx, rbx
0x180029877  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18002987c  mov     rax, rbx
0x18002987f  mov     rcx, [rsp+258h+var_18]
0x180029887  xor     rcx, rsp; StackCookie
0x18002988a  call    __security_check_cookie
0x18002988f  add     rsp, 250h
0x180029896  pop     rbx
0x180029897  retn
```
