# W3_FILE_INFO::InitializeStatic(void)

- ea: `0x18001c3ec`
- end: `0x18001c478`
- name: `?InitializeStatic@W3_FILE_INFO@@SAJXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013690`

## callees

- `0x180019558`
- `0x18001c3ec`
- `0x1800343f0`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001c43b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001c43b`

## pseudocode

```c
__int64 W3_FILE_INFO::InitializeStatic(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 792;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    W3_FILE_INFO::sm_pachW3FileInfo = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                        v0,
                                        "W3_FILE_INFO",
                                        (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                        1);
    return W3_FILE_INFO::sm_pachW3FileInfo == 0 ? 0x80070008 : 0;
  }
  else
  {
    W3_FILE_INFO::sm_pachW3FileInfo = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x18001c3ec  sub     rsp, 48h
0x18001c3f0  mov     rax, cs:__security_cookie
0x18001c3f7  xor     rax, rsp
0x18001c3fa  mov     [rsp+48h+var_18], rax
0x18001c3ff  mov     ecx, 100h; Size
0x18001c404  mov     [rsp+48h+var_28], 1
0x18001c40c  mov     [rsp+48h+var_24], 64h ; 'd'
0x18001c414  mov     [rsp+48h+var_20], 318h
0x18001c41c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c421  test    rax, rax
0x18001c424  jz      short loc_18001C456
0x18001c426  mov     r9d, 1
0x18001c42c  lea     r8, [rsp+48h+var_28]
0x18001c431  lea     rdx, aW3FileInfo; "W3_FILE_INFO"
0x18001c438  mov     rcx, rax
0x18001c43b  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18001c441  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18001c448  neg     rax
0x18001c44b  sbb     eax, eax
0x18001c44d  not     eax
0x18001c44f  and     eax, 80070008h
0x18001c454  jmp     short loc_18001C466
0x18001c456  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18001c461  mov     eax, 80070008h
0x18001c466  mov     rcx, [rsp+48h+var_18]
0x18001c46b  xor     rcx, rsp; StackCookie
0x18001c46e  call    __security_check_cookie
0x18001c473  add     rsp, 48h
0x18001c477  retn
```
