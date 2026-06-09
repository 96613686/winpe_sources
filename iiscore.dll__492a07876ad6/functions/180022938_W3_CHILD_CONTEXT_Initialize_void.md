# W3_CHILD_CONTEXT::Initialize(void)

- ea: `0x180022938`
- end: `0x1800229cb`
- name: `?Initialize@W3_CHILD_CONTEXT@@SAJXZ`
- size: `147`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d408`

## callees

- `0x18001ab30`
- `0x180022938`
- `0x180037790`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180022987`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180022987`

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
0x180022938  sub     rsp, 48h
0x18002293c  mov     rax, cs:__security_cookie
0x180022943  xor     rax, rsp
0x180022946  mov     [rsp+48h+var_18], rax
0x18002294b  mov     ecx, 100h; Size
0x180022950  mov     [rsp+48h+var_28], 1
0x180022958  mov     [rsp+48h+var_24], 64h ; 'd'
0x180022960  mov     [rsp+48h+var_20], 27E0h
0x180022968  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002296d  test    rax, rax
0x180022970  jz      short loc_1800229A8
0x180022972  mov     r9d, 1
0x180022978  lea     r8, [rsp+48h+var_28]
0x18002297d  lea     rdx, aW3ChildContext; "W3_CHILD_CONTEXT"
0x180022984  mov     rcx, rax
0x180022987  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18002298e  nop     dword ptr [rax+rax+00h]
0x180022993  mov     cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x18002299a  neg     rax
0x18002299d  sbb     eax, eax
0x18002299f  not     eax
0x1800229a1  and     eax, 80070008h
0x1800229a6  jmp     short loc_1800229B8
0x1800229a8  mov     cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x1800229b3  mov     eax, 80070008h
0x1800229b8  mov     rcx, [rsp+48h+var_18]
0x1800229bd  xor     rcx, rsp; StackCookie
0x1800229c0  call    __security_check_cookie
0x1800229c5  add     rsp, 48h
0x1800229c9  retn
```
