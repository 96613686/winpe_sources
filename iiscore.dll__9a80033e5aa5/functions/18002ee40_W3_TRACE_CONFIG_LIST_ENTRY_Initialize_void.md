# W3_TRACE_CONFIG_LIST_ENTRY::Initialize(void)

- ea: `0x18002ee40`
- end: `0x18002eed4`
- name: `?Initialize@W3_TRACE_CONFIG_LIST_ENTRY@@SAJXZ`
- size: `148`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001bb94`

## callees

- `0x180019558`
- `0x18002ee40`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eeb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eeb0`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002ee8f`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18002ee8f`

## string_xrefs

- `0x18002ee85`: `W3_TRACE_CONFIG_LIST_ENTRY`

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
0x18002ee40  sub     rsp, 48h
0x18002ee44  mov     rax, cs:__security_cookie
0x18002ee4b  xor     rax, rsp
0x18002ee4e  mov     [rsp+48h+var_18], rax
0x18002ee53  mov     ecx, 100h; Size
0x18002ee58  mov     [rsp+48h+var_28], 1
0x18002ee60  mov     [rsp+48h+var_24], 64h ; 'd'
0x18002ee68  mov     [rsp+48h+var_20], 48h ; 'H'
0x18002ee70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ee75  test    rax, rax
0x18002ee78  jz      short loc_18002EEA5
0x18002ee7a  mov     r9d, 1
0x18002ee80  lea     r8, [rsp+48h+var_28]
0x18002ee85  lea     rdx, aW3TraceConfigL; "W3_TRACE_CONFIG_LIST_ENTRY"
0x18002ee8c  mov     rcx, rax
0x18002ee8f  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18002ee95  mov     cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x18002ee9c  test    rax, rax
0x18002ee9f  jz      short loc_18002EEB0
0x18002eea1  xor     eax, eax
0x18002eea3  jmp     short loc_18002EEC2
0x18002eea5  mov     cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x18002eeb0  call    cs:__imp_GetLastError
0x18002eeb6  test    eax, eax
0x18002eeb8  jle     short loc_18002EEC2
0x18002eeba  movzx   eax, ax
0x18002eebd  or      eax, 80070000h
0x18002eec2  mov     rcx, [rsp+48h+var_18]
0x18002eec7  xor     rcx, rsp; StackCookie
0x18002eeca  call    __security_check_cookie
0x18002eecf  add     rsp, 48h
0x18002eed3  retn
```
