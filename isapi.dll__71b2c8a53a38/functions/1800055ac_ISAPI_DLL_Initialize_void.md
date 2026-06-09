# ISAPI_DLL::Initialize(void)

- ea: `0x1800055ac`
- end: `0x180005638`
- name: `?Initialize@ISAPI_DLL@@SAJXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001f2c`

## callees

- `0x180001020`
- `0x1800055ac`
- `0x1800124c0`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800055fb`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800055fb`

## string_xrefs

- `0x1800055f1`: `ISAPI_DLL`

## pseudocode

```c
__int64 ISAPI_DLL::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 320;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    ISAPI_DLL::sm_pachIsapiDlls = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                    v0,
                                    "ISAPI_DLL",
                                    (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                    1);
    return ISAPI_DLL::sm_pachIsapiDlls == 0 ? 0x80070008 : 0;
  }
  else
  {
    ISAPI_DLL::sm_pachIsapiDlls = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x1800055ac  sub     rsp, 48h
0x1800055b0  mov     rax, cs:__security_cookie
0x1800055b7  xor     rax, rsp
0x1800055ba  mov     [rsp+48h+var_18], rax
0x1800055bf  mov     ecx, 100h; Size
0x1800055c4  mov     [rsp+48h+var_28], 1
0x1800055cc  mov     [rsp+48h+var_24], 64h ; 'd'
0x1800055d4  mov     [rsp+48h+var_20], 140h
0x1800055dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800055e1  test    rax, rax
0x1800055e4  jz      short loc_180005616
0x1800055e6  mov     r9d, 1
0x1800055ec  lea     r8, [rsp+48h+var_28]
0x1800055f1  lea     rdx, aIsapiDll_0; "ISAPI_DLL"
0x1800055f8  mov     rcx, rax
0x1800055fb  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180005601  mov     cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * ISAPI_DLL::sm_pachIsapiDlls
0x180005608  neg     rax
0x18000560b  sbb     eax, eax
0x18000560d  not     eax
0x18000560f  and     eax, 80070008h
0x180005614  jmp     short loc_180005626
0x180005616  mov     cs:?sm_pachIsapiDlls@ISAPI_DLL@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ISAPI_DLL::sm_pachIsapiDlls
0x180005621  mov     eax, 80070008h
0x180005626  mov     rcx, [rsp+48h+var_18]
0x18000562b  xor     rcx, rsp; StackCookie
0x18000562e  call    __security_check_cookie
0x180005633  add     rsp, 48h
0x180005637  retn
```
