# Windows::Compat::Inventory::AepicInvCache::GetNextItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong)

- ea: `0x180025f80`
- end: `0x18002603b`
- name: `?GetNextItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJAEAPEAVInventoryCacheItem@234@PEAGK@Z`
- size: `187`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000514c`
- `0x1800152d0`
- `0x180025f80`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180026028`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180026028`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x180025faf`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x180025faf`

## string_xrefs

- `0x180025fc2`: `InvCacheEnumerateItems failed. [%#x]`
- `0x180025fd3`: `Windows::Compat::Inventory::AepicInvCache::GetNextItem`

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
                                                                    (const struct std::nothrow_t *)&std::nothrow);
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
0x180025f80  mov     r11, rsp
0x180025f83  mov     [r11+10h], rbx
0x180025f87  mov     [r11+20h], r9d
0x180025f8b  push    rdi
0x180025f8c  sub     rsp, 40h
0x180025f90  mov     rax, [rcx+8]
0x180025f94  lea     r9, [r11+20h]
0x180025f98  mov     rdi, rdx
0x180025f9b  mov     qword ptr [r11+8], 0
0x180025fa3  lea     rdx, [rcx+10h]
0x180025fa7  mov     [r11-28h], rax
0x180025fab  lea     rcx, [r11+8]
0x180025faf  call    cs:__imp_InvCacheEnumerateItems
0x180025fb5  mov     ebx, eax
0x180025fb7  test    eax, eax
0x180025fb9  jns     short loc_180025FE6
0x180025fbb  cmp     eax, 80070103h
0x180025fc0  jz      short loc_18002601E
0x180025fc2  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x180025fc9  mov     [rsp+48h+var_28], eax
0x180025fcd  mov     r8d, 12Dh
0x180025fd3  lea     rdx, aWindowsCompatI_29; "Windows::Compat::Inventory::AepicInvCac"...
0x180025fda  mov     ecx, 1
0x180025fdf  call    AslLogCallPrintf
0x180025fe4  jmp     short loc_18002601E
0x180025fe6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025fed  mov     ecx, 10h; unsigned __int64
0x180025ff2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025ff7  mov     [rsp+48h+var_18], rax
0x180025ffc  test    rax, rax
0x180025fff  jz      short loc_180026019
0x180026001  mov     rcx, [rsp+48h+arg_0]
0x180026006  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18002600d  mov     [rax], rdx
0x180026010  mov     [rax+8], rcx
0x180026014  mov     [rdi], rax
0x180026017  jmp     short loc_18002602E
0x180026019  mov     ebx, 8007000Eh
0x18002601e  mov     rcx, [rsp+48h+arg_0]
0x180026023  test    rcx, rcx
0x180026026  jz      short loc_18002602E
0x180026028  call    cs:__imp_InvCacheCloseHandle
0x18002602e  mov     eax, ebx
0x180026030  mov     rbx, [rsp+48h+arg_8]
0x180026035  add     rsp, 40h
0x180026039  pop     rdi
0x18002603a  retn
```
