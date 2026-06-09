# Windows::Compat::Inventory::AepicInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x18002e5b0`
- end: `0x18002e664`
- name: `?OpenItem@AepicInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800066f0`
- `0x18002e5b0`
- `0x180066c10`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002e651`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002e651`
- `AEPIC!__imp_InvCacheOpenItem` at `0x18002e5d8`
- `AEPIC!__imp_InvCacheOpenItem` at `0x18002e5d8`

## string_xrefs

- `0x18002e5fc`: `Windows::Compat::Inventory::AepicInvCache::OpenItem`
- `0x18002e5eb`: `InvCacheOpenItem failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::OpenItem(
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
  v4 = InvCacheOpenItem(&v9, *((_QWORD *)this + 1), a2, 1);
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
  else if ( v4 != -2147024894 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::AepicInvCache::OpenItem", 196, "InvCacheOpenItem failed [%#x]", v4);
  }
  if ( v9 )
    InvCacheCloseHandle(0);
  return v5;
}

```

## disassembly

```asm
0x18002e5b0  mov     [rsp+arg_8], rbx
0x18002e5b5  push    rdi
0x18002e5b6  sub     rsp, 30h
0x18002e5ba  mov     rdi, r8
0x18002e5bd  mov     [rsp+38h+arg_0], 0
0x18002e5c6  mov     r8, rdx
0x18002e5c9  mov     r9d, 1
0x18002e5cf  mov     rdx, [rcx+8]
0x18002e5d3  lea     rcx, [rsp+38h+arg_0]
0x18002e5d8  call    cs:__imp_InvCacheOpenItem
0x18002e5de  mov     ebx, eax
0x18002e5e0  test    eax, eax
0x18002e5e2  jns     short loc_18002E60F
0x18002e5e4  cmp     eax, 80070002h
0x18002e5e9  jz      short loc_18002E647
0x18002e5eb  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x18002e5f2  mov     [rsp+38h+var_18], eax
0x18002e5f6  mov     r8d, 0C4h
0x18002e5fc  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::AepicInvCac"...
0x18002e603  mov     ecx, 1
0x18002e608  call    AslLogCallPrintf
0x18002e60d  jmp     short loc_18002E647
0x18002e60f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e616  mov     ecx, 10h; unsigned __int64
0x18002e61b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e620  mov     [rsp+38h+arg_18], rax
0x18002e625  test    rax, rax
0x18002e628  jz      short loc_18002E642
0x18002e62a  mov     rcx, [rsp+38h+arg_0]
0x18002e62f  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18002e636  mov     [rax], rdx
0x18002e639  mov     [rax+8], rcx
0x18002e63d  mov     [rdi], rax
0x18002e640  jmp     short loc_18002E657
0x18002e642  mov     ebx, 8007000Eh
0x18002e647  cmp     [rsp+38h+arg_0], 0
0x18002e64d  jz      short loc_18002E657
0x18002e64f  xor     ecx, ecx
0x18002e651  call    cs:__imp_InvCacheCloseHandle
0x18002e657  mov     eax, ebx
0x18002e659  mov     rbx, [rsp+38h+arg_8]
0x18002e65e  add     rsp, 30h
0x18002e662  pop     rdi
0x18002e663  retn
```
