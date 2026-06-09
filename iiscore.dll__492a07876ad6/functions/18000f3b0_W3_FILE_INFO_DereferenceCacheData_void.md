# W3_FILE_INFO::DereferenceCacheData(void)

- ea: `0x18000f3b0`
- end: `0x18000f3ed`
- name: `?DereferenceCacheData@W3_FILE_INFO@@UEAAXXZ`
- size: `61`
- prototype: `void __fastcall(W3_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000f3b0`
- `0x18000f3f4`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f3da`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000f3da`

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
0x18000f3b0  push    rbx
0x18000f3b2  sub     rsp, 20h
0x18000f3b6  mov     rbx, rcx
0x18000f3b9  or      eax, 0FFFFFFFFh
0x18000f3bc  lock xadd [rcx+0Ch], eax
0x18000f3c1  cmp     eax, 1
0x18000f3c4  jnz     short loc_18000F3E6
0x18000f3c6  test    rcx, rcx
0x18000f3c9  jz      short loc_18000F3E6
0x18000f3cb  call    ??1W3_FILE_INFO@@AEAA@XZ; W3_FILE_INFO::~W3_FILE_INFO(void)
0x18000f3d0  mov     rcx, cs:?sm_pachW3FileInfo@W3_FILE_INFO@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILE_INFO::sm_pachW3FileInfo
0x18000f3d7  mov     rdx, rbx
0x18000f3da  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000f3e1  nop     dword ptr [rax+rax+00h]
0x18000f3e6  add     rsp, 20h
0x18000f3ea  pop     rbx
0x18000f3eb  retn
```
