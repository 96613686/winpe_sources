# Windows::Compat::Inventory::AepicInvCache::`scalar deleting destructor'(uint)

- ea: `0x1800276c0`
- end: `0x180027732`
- name: `??_GAepicInvCache@Inventory@Compat@Windows@@UEAAPEAXI@Z`
- size: `114`
- prototype: `void *__fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006210`
- `0x1800276c0`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800276e2`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800276f9`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800276e2`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800276f9`

## pseudocode

```c
Windows::Compat::Inventory::AepicInvCache *__fastcall Windows::Compat::Inventory::AepicInvCache::`scalar deleting destructor'(
        Windows::Compat::Inventory::AepicInvCache *this,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &Windows::Compat::Inventory::AepicInvCache::`vftable';
  v4 = *((_QWORD *)this + 1);
  if ( v4 )
  {
    InvCacheCloseHandle(v4);
    *((_QWORD *)this + 1) = 0;
  }
  v5 = *((_QWORD *)this + 2);
  if ( v5 )
  {
    InvCacheCloseHandle(v5);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &Windows::Compat::Inventory::InventoryCache::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800276c0  mov     [rsp+arg_0], rbx
0x1800276c5  push    rdi
0x1800276c6  sub     rsp, 20h
0x1800276ca  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x1800276d1  mov     rbx, rcx
0x1800276d4  mov     [rcx], rax
0x1800276d7  mov     edi, edx
0x1800276d9  mov     rcx, [rcx+8]
0x1800276dd  test    rcx, rcx
0x1800276e0  jz      short loc_1800276F0
0x1800276e2  call    cs:__imp_InvCacheCloseHandle
0x1800276e8  mov     qword ptr [rbx+8], 0
0x1800276f0  mov     rcx, [rbx+10h]
0x1800276f4  test    rcx, rcx
0x1800276f7  jz      short loc_180027707
0x1800276f9  call    cs:__imp_InvCacheCloseHandle
0x1800276ff  mov     qword ptr [rbx+10h], 0
0x180027707  lea     rax, ??_7InventoryCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InventoryCache::`vftable'
0x18002770e  mov     [rbx], rax
0x180027711  test    dil, 1
0x180027715  jz      short loc_180027724
0x180027717  mov     edx, 20h ; ' '
0x18002771c  mov     rcx, rbx; Block
0x18002771f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180027724  mov     rax, rbx
0x180027727  mov     rbx, [rsp+28h+arg_0]
0x18002772c  add     rsp, 20h
0x180027730  pop     rdi
0x180027731  retn
```
