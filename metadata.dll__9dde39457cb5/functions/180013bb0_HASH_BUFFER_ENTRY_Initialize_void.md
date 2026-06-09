# HASH_BUFFER_ENTRY::Initialize(void)

- ea: `0x180013bb0`
- end: `0x180013c44`
- name: `?Initialize@HASH_BUFFER_ENTRY@@SAJXZ`
- size: `148`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fa58`

## callees

- `0x1800089c8`
- `0x180013bb0`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013c20`
- `KERNEL32!GetLastError` at `0x180013c20`
- `IisRTL!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180013bff`
- `IisRTL!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180013bff`

## pseudocode

```c
signed int HASH_BUFFER_ENTRY::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  signed int result; // eax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 0x4000;
  v2[2] = 40;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    HASH_BUFFER_ENTRY::sm_pach = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                   v0,
                                   "HASH_BUFFER_ENTRY",
                                   (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                   1);
    if ( HASH_BUFFER_ENTRY::sm_pach )
      return 0;
  }
  else
  {
    HASH_BUFFER_ENTRY::sm_pach = 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180013bb0  sub     rsp, 48h
0x180013bb4  mov     rax, cs:__security_cookie
0x180013bbb  xor     rax, rsp
0x180013bbe  mov     [rsp+48h+var_18], rax
0x180013bc3  mov     ecx, 100h; Size
0x180013bc8  mov     [rsp+48h+var_28], 1
0x180013bd0  mov     [rsp+48h+var_24], 4000h
0x180013bd8  mov     [rsp+48h+var_20], 28h ; '('
0x180013be0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013be5  test    rax, rax
0x180013be8  jz      short loc_180013C15
0x180013bea  mov     r9d, 1
0x180013bf0  lea     r8, [rsp+48h+var_28]
0x180013bf5  lea     rdx, aHashBufferEntr; "HASH_BUFFER_ENTRY"
0x180013bfc  mov     rcx, rax
0x180013bff  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180013c05  mov     cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x180013c0c  test    rax, rax
0x180013c0f  jz      short loc_180013C20
0x180013c11  xor     eax, eax
0x180013c13  jmp     short loc_180013C32
0x180013c15  mov     cs:?sm_pach@HASH_BUFFER_ENTRY@@2PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * HASH_BUFFER_ENTRY::sm_pach
0x180013c20  call    cs:__imp_GetLastError
0x180013c26  test    eax, eax
0x180013c28  jle     short loc_180013C32
0x180013c2a  movzx   eax, ax
0x180013c2d  or      eax, 80070000h
0x180013c32  mov     rcx, [rsp+48h+var_18]
0x180013c37  xor     rcx, rsp; StackCookie
0x180013c3a  call    __security_check_cookie
0x180013c3f  add     rsp, 48h
0x180013c43  retn
```
