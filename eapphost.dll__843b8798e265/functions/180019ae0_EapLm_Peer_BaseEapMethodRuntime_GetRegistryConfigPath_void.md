# EapLm::Peer::BaseEapMethodRuntime::GetRegistryConfigPath(void)

- ea: `0x180019ae0`
- end: `0x180019bad`
- name: `?GetRegistryConfigPath@BaseEapMethodRuntime@Peer@EapLm@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180002af0`
- `0x1800094d0`
- `0x180012a28`
- `0x180019ae0`
- `0x18001e7c0`

## string_xrefs

- `0x180019b76`: `LoadConfig`
- `0x180019b07`: `System\CurrentControlSet\Services\EapHost\Methods`
- `0x180019b6f`: `eapMethodRegPath`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::BaseEapMethodRuntime::GetRegistryConfigPath(__int64 a1, __int64 a2)
{
  int v3; // edx
  int v4; // eax
  wchar_t v6[264]; // [rsp+50h] [rbp-228h] BYREF

  v3 = *(unsigned __int8 *)(a1 + 16);
  if ( (_BYTE)v3 == 0xFE )
    v4 = StringCchPrintfW(
           v6,
           0x104u,
           L"%s\\%d\\%d\\%d\\%d",
           L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
           *(_DWORD *)(a1 + 28),
           v3,
           *(_DWORD *)(a1 + 20),
           *(_DWORD *)(a1 + 24));
  else
    v4 = StringCchPrintfW(
           v6,
           0x104u,
           L"%s\\%d\\%d",
           L"System\\CurrentControlSet\\Services\\EapHost\\Methods",
           *(_DWORD *)(a1 + 28),
           *(unsigned __int8 *)(a1 + 16));
  if ( v4 < 0 )
    EapHost::EapException::Throw(L"LoadConfig", L"eapMethodRegPath", -2147024809);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    a2,
    v6);
  return a2;
}

```

## disassembly

```asm
0x180019ae0  push    rbx
0x180019ae2  sub     rsp, 270h
0x180019ae9  mov     rax, cs:__security_cookie
0x180019af0  xor     rax, rsp
0x180019af3  mov     [rsp+278h+var_18], rax
0x180019afb  mov     rbx, rdx
0x180019afe  mov     [rsp+278h+var_230], rdx
0x180019b03  movzx   edx, byte ptr [rcx+10h]
0x180019b07  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ea"...
0x180019b0e  cmp     dl, 0FEh
0x180019b11  jnz     short loc_180019B44
0x180019b13  mov     eax, [rcx+18h]
0x180019b16  lea     r8, aSDDDD; "%s\\%d\\%d\\%d\\%d"
0x180019b1d  mov     [rsp+278h+var_240], eax
0x180019b21  mov     eax, [rcx+14h]
0x180019b24  mov     [rsp+278h+var_248], eax
0x180019b28  mov     eax, [rcx+1Ch]
0x180019b2b  lea     rcx, [rsp+278h+var_228]; wchar_t *
0x180019b30  mov     [rsp+278h+var_250], edx
0x180019b34  mov     edx, 104h; unsigned __int64
0x180019b39  mov     [rsp+278h+var_258], eax
0x180019b3d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180019b42  jmp     short loc_180019B65
0x180019b44  mov     eax, [rcx+1Ch]
0x180019b47  lea     r8, aSDD; "%s\\%d\\%d"
0x180019b4e  mov     [rsp+278h+var_250], edx
0x180019b52  lea     rcx, [rsp+278h+var_228]; wchar_t *
0x180019b57  mov     edx, 104h; unsigned __int64
0x180019b5c  mov     [rsp+278h+var_258], eax
0x180019b60  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180019b65  test    eax, eax
0x180019b67  jns     short loc_180019B83
0x180019b69  mov     r8d, 80070057h; int
0x180019b6f  lea     rdx, aEapmethodregpa; "eapMethodRegPath"
0x180019b76  lea     rcx, aLoadconfig; "LoadConfig"
0x180019b7d  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019b83  lea     rdx, [rsp+278h+var_228]
0x180019b88  mov     rcx, rbx
0x180019b8b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x180019b90  mov     rax, rbx
0x180019b93  mov     rcx, [rsp+278h+var_18]
0x180019b9b  xor     rcx, rsp; StackCookie
0x180019b9e  call    __security_check_cookie
0x180019ba3  add     rsp, 270h
0x180019baa  pop     rbx
0x180019bab  retn
```
