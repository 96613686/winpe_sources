# W3_FILE_INFO::DereferenceCacheData(void)

- ea: `0x18000e750`
- end: `0x18000e786`
- name: `?DereferenceCacheData@W3_FILE_INFO@@UEAAXXZ`
- size: `54`
- prototype: `void __fastcall(W3_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e750`
- `0x18000e78c`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e77a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000e77a`

## pseudocode

```c
void __fastcall W3_FILE_INFO::DereferenceCacheData(W3_FILE_INFO *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      W3_FILE_INFO::~W3_FILE_INFO(this);
      ALLOC_CACHE_HANDLER::Free(W3_FILE_INFO::sm_pachW3FileInfo, this);
    }
  }
}

```

## disassembly

```asm
0x18000e750  push    rbx
0x18000e752  sub     rsp, 20h
0x18000e756  mov     rbx, rcx
0x18000e759  or      eax, 0FFFFFFFFh
0x18000e75c  lock xadd [rcx+0Ch], eax
0x18000e761  cmp     eax, 1
0x18000e764  jnz     short loc_18000E780
0x18000e766  test    rcx, rcx
0x18000e769  jz      short loc_18000E780
0x18000e76b  call    ??1W3_FILE_INFO@@AEAA@XZ; W3_FILE_INFO::~W3_FILE_INFO(void)
0x18000e770  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18000e777  mov     rdx, rbx
0x18000e77a  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000e780  add     rsp, 20h
0x18000e784  pop     rbx
0x18000e785  retn
```
