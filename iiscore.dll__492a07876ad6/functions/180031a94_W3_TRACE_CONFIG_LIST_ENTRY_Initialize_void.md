# W3_TRACE_CONFIG_LIST_ENTRY::Initialize(void)

- ea: `0x180031a94`
- end: `0x180031b35`
- name: `?Initialize@W3_TRACE_CONFIG_LIST_ENTRY@@SAJXZ`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d408`

## callees

- `0x18001ab30`
- `0x180031a94`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031b0a`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180031ae3`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180031ae3`

## string_xrefs

- `0x180031ad9`: `W3_TRACE_CONFIG_LIST_ENTRY`

## pseudocode

```c
signed int W3_TRACE_CONFIG_LIST_ENTRY::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  signed int result; // eax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 72;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                                                  v0,
                                                                  "W3_TRACE_CONFIG_LIST_ENTRY",
                                                                  (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                                                  1);
    if ( W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries )
      return 0;
  }
  else
  {
    W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries = 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180031a94  sub     rsp, 48h
0x180031a98  mov     rax, cs:__security_cookie
0x180031a9f  xor     rax, rsp
0x180031aa2  mov     [rsp+48h+var_18], rax
0x180031aa7  mov     ecx, 100h; Size
0x180031aac  mov     [rsp+48h+var_28], 1
0x180031ab4  mov     [rsp+48h+var_24], 64h ; 'd'
0x180031abc  mov     [rsp+48h+var_20], 48h ; 'H'
0x180031ac4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031ac9  test    rax, rax
0x180031acc  jz      short loc_180031AFF
0x180031ace  mov     r9d, 1
0x180031ad4  lea     r8, [rsp+48h+var_28]
0x180031ad9  lea     rdx, aW3TraceConfigL; "W3_TRACE_CONFIG_LIST_ENTRY"
0x180031ae0  mov     rcx, rax
0x180031ae3  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180031aea  nop     dword ptr [rax+rax+00h]
0x180031aef  mov     cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x180031af6  test    rax, rax
0x180031af9  jz      short loc_180031B0A
0x180031afb  xor     eax, eax
0x180031afd  jmp     short loc_180031B22
0x180031aff  mov     cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x180031b0a  call    cs:__imp_GetLastError
0x180031b11  nop     dword ptr [rax+rax+00h]
0x180031b16  test    eax, eax
0x180031b18  jle     short loc_180031B22
0x180031b1a  movzx   eax, ax
0x180031b1d  or      eax, 80070000h
0x180031b22  mov     rcx, [rsp+48h+var_18]
0x180031b27  xor     rcx, rsp; StackCookie
0x180031b2a  call    __security_check_cookie
0x180031b2f  add     rsp, 48h
0x180031b33  retn
```
