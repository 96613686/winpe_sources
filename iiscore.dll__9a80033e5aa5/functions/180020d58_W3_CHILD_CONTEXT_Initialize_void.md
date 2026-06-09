# W3_CHILD_CONTEXT::Initialize(void)

- ea: `0x180020d58`
- end: `0x180020de4`
- name: `?Initialize@W3_CHILD_CONTEXT@@SAJXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001bb94`

## callees

- `0x180019558`
- `0x180020d58`
- `0x1800343f0`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180020da7`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180020da7`

## pseudocode

```c
__int64 W3_CHILD_CONTEXT::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 10208;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    W3_CHILD_CONTEXT::sm_pachCloneContexts = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                               v0,
                                               "W3_CHILD_CONTEXT",
                                               (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                               1);
    return W3_CHILD_CONTEXT::sm_pachCloneContexts == 0 ? 0x80070008 : 0;
  }
  else
  {
    W3_CHILD_CONTEXT::sm_pachCloneContexts = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180020d58  sub     rsp, 48h
0x180020d5c  mov     rax, cs:__security_cookie
0x180020d63  xor     rax, rsp
0x180020d66  mov     [rsp+48h+var_18], rax
0x180020d6b  mov     ecx, 100h; Size
0x180020d70  mov     [rsp+48h+var_28], 1
0x180020d78  mov     [rsp+48h+var_24], 64h ; 'd'
0x180020d80  mov     [rsp+48h+var_20], 27E0h
0x180020d88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d8d  test    rax, rax
0x180020d90  jz      short loc_180020DC2
0x180020d92  mov     r9d, 1
0x180020d98  lea     r8, [rsp+48h+var_28]
0x180020d9d  lea     rdx, aW3ChildContext; "W3_CHILD_CONTEXT"
0x180020da4  mov     rcx, rax
0x180020da7  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180020dad  mov     cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x180020db4  neg     rax
0x180020db7  sbb     eax, eax
0x180020db9  not     eax
0x180020dbb  and     eax, 80070008h
0x180020dc0  jmp     short loc_180020DD2
0x180020dc2  mov     cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x180020dcd  mov     eax, 80070008h
0x180020dd2  mov     rcx, [rsp+48h+var_18]
0x180020dd7  xor     rcx, rsp; StackCookie
0x180020dda  call    __security_check_cookie
0x180020ddf  add     rsp, 48h
0x180020de3  retn
```
