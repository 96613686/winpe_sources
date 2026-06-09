# ProxyResolver::ProxyResolver(void)

- ea: `0x18002c8f4`
- end: `0x18002c9f9`
- name: `??0ProxyResolver@@QEAA@XZ`
- size: `261`
- prototype: `ProxyResolver *__fastcall(ProxyResolver *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c180`

## callees

- `0x18002c8f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c949`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c949`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c961`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c98f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c9a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c961`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c98f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c9a6`

## string_xrefs

- `0x18002c942`: `winhttp.dll`
- `0x18002c97e`: `WinHttpCreateProxyResolver`

## pseudocode

```c
ProxyResolver *__fastcall ProxyResolver::ProxyResolver(ProxyResolver *this)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rdi
  unsigned int (*ProcAddress)(void *, struct _WINHTTP_PROXY_RESULT *); // rax
  BOOL v5; // eax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  ModuleHandleW = GetModuleHandleW(L"winhttp.dll");
  v3 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    ProxyResolver::s_pfnWinhttpGetProxyForUrlEx = (unsigned int (*)(void *, const unsigned __int16 *, struct _WINHTTP_AUTOPROXY_OPTIONS *, unsigned __int64))GetProcAddress(ModuleHandleW, "WinHttpGetProxyForUrlEx");
    ProxyResolver::s_pfnWinhttpFreeProxyList = (unsigned int (*)(struct _WINHTTP_PROXY_RESULT *))GetProcAddress(
                                                                                                   v3,
                                                                                                   "WinHttpFreeProxyResult");
    ProxyResolver::s_pfnWinhttpCreateProxyResolver = (unsigned int (*)(void *, void **))GetProcAddress(
                                                                                          v3,
                                                                                          "WinHttpCreateProxyResolver");
    ProcAddress = (unsigned int (*)(void *, struct _WINHTTP_PROXY_RESULT *))GetProcAddress(v3, "WinHttpGetProxyResult");
    ProxyResolver::s_pfnWinhttpGetProxyResult = ProcAddress;
  }
  else
  {
    ProcAddress = ProxyResolver::s_pfnWinhttpGetProxyResult;
  }
  v5 = ProxyResolver::s_pfnWinhttpGetProxyForUrlEx
    && ProxyResolver::s_pfnWinhttpFreeProxyList
    && ProxyResolver::s_pfnWinhttpCreateProxyResolver
    && ProcAddress;
  *((_DWORD *)this + 3) = v5;
  return this;
}

```

## disassembly

```asm
0x18002c8f4  mov     [rsp+arg_0], rbx
0x18002c8f9  push    rdi
0x18002c8fa  sub     rsp, 20h
0x18002c8fe  mov     qword ptr [rcx], 0
0x18002c905  xorps   xmm0, xmm0
0x18002c908  mov     dword ptr [rcx+8], 0
0x18002c90f  xor     eax, eax
0x18002c911  mov     qword ptr [rcx+18h], 0
0x18002c919  mov     rbx, rcx
0x18002c91c  mov     qword ptr [rcx+50h], 0
0x18002c924  mov     dword ptr [rcx+58h], 0
0x18002c92b  mov     dword ptr [rcx+10h], 0
0x18002c932  movups  xmmword ptr [rcx+38h], xmm0
0x18002c936  mov     [rcx+48h], rax
0x18002c93a  movups  xmmword ptr [rcx+20h], xmm0
0x18002c93e  mov     [rcx+30h], rax
0x18002c942  lea     rcx, aWinhttpDll_0; "winhttp.dll"
0x18002c949  call    cs:__imp_GetModuleHandleW
0x18002c94f  mov     rdi, rax
0x18002c952  test    rax, rax
0x18002c955  jz      short loc_18002C9B5
0x18002c957  lea     rdx, aWinhttpgetprox_0; "WinHttpGetProxyForUrlEx"
0x18002c95e  mov     rcx, rax; hModule
0x18002c961  call    cs:__imp_GetProcAddress
0x18002c967  lea     rdx, aWinhttpfreepro; "WinHttpFreeProxyResult"
0x18002c96e  mov     rcx, rdi; hModule
0x18002c971  mov     cs:?s_pfnWinhttpGetProxyForUrlEx@ProxyResolver@@0P6AKPEAXPEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@_K@ZEA, rax; ulong (*ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(void *,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,unsigned __int64)
0x18002c978  call    cs:__imp_GetProcAddress
0x18002c97e  lea     rdx, aWinhttpcreatep; "WinHttpCreateProxyResolver"
0x18002c985  mov     rcx, rdi; hModule
0x18002c988  mov     cs:?s_pfnWinhttpFreeProxyList@ProxyResolver@@0P6AKPEAU_WINHTTP_PROXY_RESULT@@@ZEA, rax; ulong (*ProxyResolver::s_pfnWinhttpFreeProxyList)(_WINHTTP_PROXY_RESULT *)
0x18002c98f  call    cs:__imp_GetProcAddress
0x18002c995  lea     rdx, aWinhttpgetprox_1; "WinHttpGetProxyResult"
0x18002c99c  mov     rcx, rdi; hModule
0x18002c99f  mov     cs:?s_pfnWinhttpCreateProxyResolver@ProxyResolver@@0P6AKPEAXPEAPEAX@ZEA, rax; ulong (*ProxyResolver::s_pfnWinhttpCreateProxyResolver)(void *,void * *)
0x18002c9a6  call    cs:__imp_GetProcAddress
0x18002c9ac  mov     cs:?s_pfnWinhttpGetProxyResult@ProxyResolver@@0P6AKPEAXPEAU_WINHTTP_PROXY_RESULT@@@ZEA, rax; ulong (*ProxyResolver::s_pfnWinhttpGetProxyResult)(void *,_WINHTTP_PROXY_RESULT *)
0x18002c9b3  jmp     short loc_18002C9BC
0x18002c9b5  mov     rax, cs:?s_pfnWinhttpGetProxyResult@ProxyResolver@@0P6AKPEAXPEAU_WINHTTP_PROXY_RESULT@@@ZEA; ulong (*ProxyResolver::s_pfnWinhttpGetProxyResult)(void *,_WINHTTP_PROXY_RESULT *)
0x18002c9bc  cmp     cs:?s_pfnWinhttpGetProxyForUrlEx@ProxyResolver@@0P6AKPEAXPEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@_K@ZEA, 0; ulong (*ProxyResolver::s_pfnWinhttpGetProxyForUrlEx)(void *,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,unsigned __int64)
0x18002c9c4  jz      short loc_18002C9E6
0x18002c9c6  cmp     cs:?s_pfnWinhttpFreeProxyList@ProxyResolver@@0P6AKPEAU_WINHTTP_PROXY_RESULT@@@ZEA, 0; ulong (*ProxyResolver::s_pfnWinhttpFreeProxyList)(_WINHTTP_PROXY_RESULT *)
0x18002c9ce  jz      short loc_18002C9E6
0x18002c9d0  cmp     cs:?s_pfnWinhttpCreateProxyResolver@ProxyResolver@@0P6AKPEAXPEAPEAX@ZEA, 0; ulong (*ProxyResolver::s_pfnWinhttpCreateProxyResolver)(void *,void * *)
0x18002c9d8  jz      short loc_18002C9E6
0x18002c9da  test    rax, rax
0x18002c9dd  jz      short loc_18002C9E6
0x18002c9df  mov     eax, 1
0x18002c9e4  jmp     short loc_18002C9E8
0x18002c9e6  xor     eax, eax
0x18002c9e8  mov     [rbx+0Ch], eax
0x18002c9eb  mov     rax, rbx
0x18002c9ee  mov     rbx, [rsp+28h+arg_0]
0x18002c9f3  add     rsp, 20h
0x18002c9f7  pop     rdi
0x18002c9f8  retn
```
