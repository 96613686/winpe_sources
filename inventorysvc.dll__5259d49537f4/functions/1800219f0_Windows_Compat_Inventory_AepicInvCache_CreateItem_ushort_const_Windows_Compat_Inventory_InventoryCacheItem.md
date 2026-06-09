# Windows::Compat::Inventory::AepicInvCache::CreateItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x1800219f0`
- end: `0x180021a9a`
- name: `?CreateItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000514c`
- `0x1800152d0`
- `0x1800219f0`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021a87`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021a87`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180021a15`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180021a15`

## string_xrefs

- `0x180021a21`: `InvCacheOpenItem failed [%#x]`
- `0x180021a32`: `Windows::Compat::Inventory::AepicInvCache::CreateItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::CreateItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        struct Windows::Compat::Inventory::InventoryCacheItem **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  struct Windows::Compat::Inventory::InventoryCacheItem *v6; // rax
  __int64 v7; // rcx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  struct Windows::Compat::Inventory::InventoryCacheItem *v10; // [rsp+58h] [rbp+20h]

  v9 = 0;
  v4 = InvCacheOpenItem(&v9, *((_QWORD *)this + 1), a2, 0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                    0x10u,
                                                                    (const struct std::nothrow_t *)&std::nothrow);
    v10 = v6;
    if ( v6 )
    {
      v7 = v9;
      *(_QWORD *)v6 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
      *((_QWORD *)v6 + 1) = v7;
      *a3 = v6;
      return v5;
    }
    v5 = -2147024882;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::CreateItem",
      235,
      "InvCacheOpenItem failed [%#x]",
      v4);
  }
  if ( v9 )
    InvCacheCloseHandle();
  return v5;
}

```

## disassembly

```asm
0x1800219f0  mov     [rsp+arg_8], rbx
0x1800219f5  push    rdi
0x1800219f6  sub     rsp, 30h
0x1800219fa  mov     rdi, r8
0x1800219fd  mov     [rsp+38h+arg_0], 0
0x180021a06  mov     r8, rdx
0x180021a09  xor     r9d, r9d
0x180021a0c  mov     rdx, [rcx+8]
0x180021a10  lea     rcx, [rsp+38h+arg_0]
0x180021a15  call    cs:__imp_InvCacheOpenItem
0x180021a1b  mov     ebx, eax
0x180021a1d  test    eax, eax
0x180021a1f  jns     short loc_180021A45
0x180021a21  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x180021a28  mov     [rsp+38h+var_18], eax
0x180021a2c  mov     r8d, 0EBh
0x180021a32  lea     rdx, aWindowsCompatI_63; "Windows::Compat::Inventory::AepicInvCac"...
0x180021a39  mov     ecx, 1
0x180021a3e  call    AslLogCallPrintf
0x180021a43  jmp     short loc_180021A7D
0x180021a45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021a4c  mov     ecx, 10h; unsigned __int64
0x180021a51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021a56  mov     [rsp+38h+arg_18], rax
0x180021a5b  test    rax, rax
0x180021a5e  jz      short loc_180021A78
0x180021a60  mov     rcx, [rsp+38h+arg_0]
0x180021a65  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180021a6c  mov     [rax], rdx
0x180021a6f  mov     [rax+8], rcx
0x180021a73  mov     [rdi], rax
0x180021a76  jmp     short loc_180021A8D
0x180021a78  mov     ebx, 8007000Eh
0x180021a7d  mov     rcx, [rsp+38h+arg_0]
0x180021a82  test    rcx, rcx
0x180021a85  jz      short loc_180021A8D
0x180021a87  call    cs:__imp_InvCacheCloseHandle
0x180021a8d  mov     eax, ebx
0x180021a8f  mov     rbx, [rsp+38h+arg_8]
0x180021a94  add     rsp, 30h
0x180021a98  pop     rdi
0x180021a99  retn
```
