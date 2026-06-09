# COMPRESSION_BUFFER::Initialize(void)

- ea: `0x180001220`
- end: `0x1800012a1`
- name: `?Initialize@COMPRESSION_BUFFER@@SAJXZ`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001220`
- `0x180004210`
- `0x180004c10`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180001273`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180001273`

## string_xrefs

- `0x180001269`: `COMPRESSION_BUFFER`

## pseudocode

```c
__int64 COMPRESSION_BUFFER::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  ALLOC_CACHE_HANDLER *v1; // rax
  unsigned int v2; // ecx
  __int64 result; // rax
  _DWORD v4[4]; // [rsp+20h] [rbp-28h] BYREF

  v4[0] = 1;
  v4[1] = 100;
  v4[2] = 4016;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
           v0,
           "COMPRESSION_BUFFER",
           (const struct ALLOC_CACHE_CONFIGURATION *)v4,
           1);
    v2 = 0;
    COMPRESSION_BUFFER::allocHandler = v1;
    if ( !v1 )
      return (unsigned int)-2147024888;
    return v2;
  }
  else
  {
    result = 2147942408LL;
    COMPRESSION_BUFFER::allocHandler = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001220  sub     rsp, 48h
0x180001224  mov     rax, cs:__security_cookie
0x18000122b  xor     rax, rsp
0x18000122e  mov     [rsp+48h+var_18], rax
0x180001233  mov     ecx, 100h; Size
0x180001238  mov     [rsp+48h+var_28], 1
0x180001240  mov     [rsp+48h+var_24], 64h ; 'd'
0x180001248  mov     [rsp+48h+var_20], 0FB0h
0x180001250  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001255  test    rax, rax
0x180001258  jz      loc_180004FB0
0x18000125e  mov     r9d, 1
0x180001264  lea     r8, [rsp+48h+var_28]
0x180001269  lea     rdx, aCompressionBuf; "COMPRESSION_BUFFER"
0x180001270  mov     rcx, rax
0x180001273  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180001279  xor     ecx, ecx
0x18000127b  mov     edx, 80070008h
0x180001280  test    rax, rax
0x180001283  mov     cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x18000128a  cmovz   ecx, edx
0x18000128d  mov     eax, ecx
0x18000128f  mov     rcx, [rsp+48h+var_18]
0x180001294  xor     rcx, rsp; StackCookie
0x180001297  call    __security_check_cookie
0x18000129c  add     rsp, 48h
0x1800012a0  retn
0x180004fb0  xor     ecx, ecx
0x180004fb2  mov     eax, 80070008h
0x180004fb7  mov     cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA, rcx; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x180004fbe  jmp     loc_18000128F
```
