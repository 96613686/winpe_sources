# W3_FILE_INFO::InitializeStatic(void)

- ea: `0x18001dca0`
- end: `0x18001dd33`
- name: `?InitializeStatic@W3_FILE_INFO@@SAJXZ`
- size: `147`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800147d0`

## callees

- `0x18001ab30`
- `0x18001dca0`
- `0x180037790`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001dcef`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x18001dcef`

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
0x18001dca0  sub     rsp, 48h
0x18001dca4  mov     rax, cs:__security_cookie
0x18001dcab  xor     rax, rsp
0x18001dcae  mov     [rsp+48h+var_18], rax
0x18001dcb3  mov     ecx, 100h; Size
0x18001dcb8  mov     [rsp+48h+var_28], 1
0x18001dcc0  mov     [rsp+48h+var_24], 64h ; 'd'
0x18001dcc8  mov     [rsp+48h+var_20], 318h
0x18001dcd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dcd5  test    rax, rax
0x18001dcd8  jz      short loc_18001DD10
0x18001dcda  mov     r9d, 1
0x18001dce0  lea     r8, [rsp+48h+var_28]
0x18001dce5  lea     rdx, aW3FileInfo; "W3_FILE_INFO"
0x18001dcec  mov     rcx, rax
0x18001dcef  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18001dcf6  nop     dword ptr [rax+rax+00h]
0x18001dcfb  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18001dd02  neg     rax
0x18001dd05  sbb     eax, eax
0x18001dd07  not     eax
0x18001dd09  and     eax, 80070008h
0x18001dd0e  jmp     short loc_18001DD20
0x18001dd10  mov     cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18001dd1b  mov     eax, 80070008h
0x18001dd20  mov     rcx, [rsp+48h+var_18]
0x18001dd25  xor     rcx, rsp; StackCookie
0x18001dd28  call    __security_check_cookie
0x18001dd2d  add     rsp, 48h
0x18001dd31  retn
```
