# Windows::Compat::Inventory::AepicInvCache::GetNextItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong)

- ea: `0x18002c5a0`
- end: `0x18002c65b`
- name: `?GetNextItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJAEAPEAVInventoryCacheItem@234@PEAGK@Z`
- size: `187`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800066f0`
- `0x18002c5a0`
- `0x180066c10`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002c648`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002c648`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x18002c5cf`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x18002c5cf`

## string_xrefs

- `0x18002c5e2`: `InvCacheEnumerateItems failed. [%#x]`
- `0x18002c5f3`: `Windows::Compat::Inventory::AepicInvCache::GetNextItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::GetNextItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        struct Windows::Compat::Inventory::InventoryCacheItem **a2,
        unsigned __int16 *a3,
        int a4)
{
  __int64 v4; // rax
  int v6; // eax
  unsigned int v7; // ebx
  struct Windows::Compat::Inventory::InventoryCacheItem *v8; // rax
  __int64 v9; // rcx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  v4 = *((_QWORD *)this + 1);
  v11 = 0;
  v6 = InvCacheEnumerateItems(&v11, (char *)this + 16, a3, &v12, v4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                    0x10u,
                                                                    (const struct std::nothrow_t *)std::nothrow);
    if ( v8 )
    {
      v9 = v11;
      *(_QWORD *)v8 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
      *((_QWORD *)v8 + 1) = v9;
      *a2 = v8;
      return v7;
    }
    v7 = -2147024882;
  }
  else if ( v6 != -2147024637 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::GetNextItem",
      301,
      "InvCacheEnumerateItems failed. [%#x]",
      v6);
  }
  if ( v11 )
    InvCacheCloseHandle();
  return v7;
}

```

## disassembly

```asm
0x18002c5a0  mov     r11, rsp
0x18002c5a3  mov     [r11+10h], rbx
0x18002c5a7  mov     [r11+20h], r9d
0x18002c5ab  push    rdi
0x18002c5ac  sub     rsp, 40h
0x18002c5b0  mov     rax, [rcx+8]
0x18002c5b4  lea     r9, [r11+20h]
0x18002c5b8  mov     rdi, rdx
0x18002c5bb  mov     qword ptr [r11+8], 0
0x18002c5c3  lea     rdx, [rcx+10h]
0x18002c5c7  mov     [r11-28h], rax
0x18002c5cb  lea     rcx, [r11+8]
0x18002c5cf  call    cs:__imp_InvCacheEnumerateItems
0x18002c5d5  mov     ebx, eax
0x18002c5d7  test    eax, eax
0x18002c5d9  jns     short loc_18002C606
0x18002c5db  cmp     eax, 80070103h
0x18002c5e0  jz      short loc_18002C63E
0x18002c5e2  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x18002c5e9  mov     [rsp+48h+var_28], eax
0x18002c5ed  mov     r8d, 12Dh
0x18002c5f3  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Inventory::AepicInvCac"...
0x18002c5fa  mov     ecx, 1
0x18002c5ff  call    AslLogCallPrintf
0x18002c604  jmp     short loc_18002C63E
0x18002c606  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002c60d  mov     ecx, 10h; unsigned __int64
0x18002c612  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002c617  mov     [rsp+48h+var_18], rax
0x18002c61c  test    rax, rax
0x18002c61f  jz      short loc_18002C639
0x18002c621  mov     rcx, [rsp+48h+arg_0]
0x18002c626  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18002c62d  mov     [rax], rdx
0x18002c630  mov     [rax+8], rcx
0x18002c634  mov     [rdi], rax
0x18002c637  jmp     short loc_18002C64E
0x18002c639  mov     ebx, 8007000Eh
0x18002c63e  mov     rcx, [rsp+48h+arg_0]
0x18002c643  test    rcx, rcx
0x18002c646  jz      short loc_18002C64E
0x18002c648  call    cs:__imp_InvCacheCloseHandle
0x18002c64e  mov     eax, ebx
0x18002c650  mov     rbx, [rsp+48h+arg_8]
0x18002c655  add     rsp, 40h
0x18002c659  pop     rdi
0x18002c65a  retn
```
