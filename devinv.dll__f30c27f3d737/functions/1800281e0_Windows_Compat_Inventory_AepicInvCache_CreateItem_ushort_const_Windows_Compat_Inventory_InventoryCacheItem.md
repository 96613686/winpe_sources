# Windows::Compat::Inventory::AepicInvCache::CreateItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x1800281e0`
- end: `0x18002828a`
- name: `?CreateItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800066f0`
- `0x1800281e0`
- `0x180066c10`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180028277`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180028277`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180028205`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180028205`

## string_xrefs

- `0x180028211`: `InvCacheOpenItem failed [%#x]`
- `0x180028222`: `Windows::Compat::Inventory::AepicInvCache::CreateItem`

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
                                                                    (const struct std::nothrow_t *)std::nothrow);
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
0x1800281e0  mov     [rsp+arg_8], rbx
0x1800281e5  push    rdi
0x1800281e6  sub     rsp, 30h
0x1800281ea  mov     rdi, r8
0x1800281ed  mov     [rsp+38h+arg_0], 0
0x1800281f6  mov     r8, rdx
0x1800281f9  xor     r9d, r9d
0x1800281fc  mov     rdx, [rcx+8]
0x180028200  lea     rcx, [rsp+38h+arg_0]
0x180028205  call    cs:__imp_InvCacheOpenItem
0x18002820b  mov     ebx, eax
0x18002820d  test    eax, eax
0x18002820f  jns     short loc_180028235
0x180028211  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x180028218  mov     [rsp+38h+var_18], eax
0x18002821c  mov     r8d, 0EBh
0x180028222  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::AepicInvCac"...
0x180028229  mov     ecx, 1
0x18002822e  call    AslLogCallPrintf
0x180028233  jmp     short loc_18002826D
0x180028235  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002823c  mov     ecx, 10h; unsigned __int64
0x180028241  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028246  mov     [rsp+38h+arg_18], rax
0x18002824b  test    rax, rax
0x18002824e  jz      short loc_180028268
0x180028250  mov     rcx, [rsp+38h+arg_0]
0x180028255  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18002825c  mov     [rax], rdx
0x18002825f  mov     [rax+8], rcx
0x180028263  mov     [rdi], rax
0x180028266  jmp     short loc_18002827D
0x180028268  mov     ebx, 8007000Eh
0x18002826d  mov     rcx, [rsp+38h+arg_0]
0x180028272  test    rcx, rcx
0x180028275  jz      short loc_18002827D
0x180028277  call    cs:__imp_InvCacheCloseHandle
0x18002827d  mov     eax, ebx
0x18002827f  mov     rbx, [rsp+38h+arg_8]
0x180028284  add     rsp, 30h
0x180028288  pop     rdi
0x180028289  retn
```
