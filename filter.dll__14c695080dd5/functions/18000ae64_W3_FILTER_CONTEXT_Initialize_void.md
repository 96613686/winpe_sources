# W3_FILTER_CONTEXT::Initialize(void)

- ea: `0x18000ae64`
- end: `0x18000aefb`
- name: `?Initialize@W3_FILTER_CONTEXT@@SAJXZ`
- size: `151`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ad78`

## callees

- `0x1800088bc`
- `0x18000ae64`
- `0x18000c970`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000aebe`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18000aebe`

## pseudocode

```c
__int64 W3_FILTER_CONTEXT::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  W3_FILTER_CONTEXT::sm_pTraceLog = 0;
  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 520;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    W3_FILTER_CONTEXT::sm_pachFilterContexts = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                                 v0,
                                                 "W3_FILTER_CONTEXT",
                                                 (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                                 1);
    return W3_FILTER_CONTEXT::sm_pachFilterContexts == 0 ? 0x80070008 : 0;
  }
  else
  {
    W3_FILTER_CONTEXT::sm_pachFilterContexts = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x18000ae64  sub     rsp, 48h
0x18000ae68  mov     rax, cs:__security_cookie
0x18000ae6f  xor     rax, rsp
0x18000ae72  mov     [rsp+48h+var_18], rax
0x18000ae77  mov     ecx, 100h; Size
0x18000ae7c  mov     cs:?sm_pTraceLog@W3_FILTER_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * W3_FILTER_CONTEXT::sm_pTraceLog
0x18000ae87  mov     [rsp+48h+var_28], 1
0x18000ae8f  mov     [rsp+48h+var_24], 64h ; 'd'
0x18000ae97  mov     [rsp+48h+var_20], 208h
0x18000ae9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aea4  test    rax, rax
0x18000aea7  jz      short loc_18000AED9
0x18000aea9  mov     r9d, 1
0x18000aeaf  lea     r8, [rsp+48h+var_28]
0x18000aeb4  lea     rdx, aW3FilterContex_1; "W3_FILTER_CONTEXT"
0x18000aebb  mov     rcx, rax
0x18000aebe  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000aec4  mov     cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x18000aecb  neg     rax
0x18000aece  sbb     eax, eax
0x18000aed0  not     eax
0x18000aed2  and     eax, 80070008h
0x18000aed7  jmp     short loc_18000AEE9
0x18000aed9  mov     cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x18000aee4  mov     eax, 80070008h
0x18000aee9  mov     rcx, [rsp+48h+var_18]
0x18000aeee  xor     rcx, rsp; StackCookie
0x18000aef1  call    __security_check_cookie
0x18000aef6  add     rsp, 48h
0x18000aefa  retn
```
