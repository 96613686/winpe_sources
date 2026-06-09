# Windows::Compat::Inventory::AepicInvCache::`scalar deleting destructor'(uint)

- ea: `0x180020fd0`
- end: `0x180021042`
- name: `??_GAepicInvCache@Inventory@Compat@Windows@@UEAAPEAXI@Z`
- size: `114`
- prototype: `void *__fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003100`
- `0x180020fd0`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180020ff2`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021009`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180020ff2`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021009`

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
    operator delete(this, (const struct std::nothrow_t *)0x20);
  return this;
}

```

## disassembly

```asm
0x180020fd0  mov     [rsp+arg_0], rbx
0x180020fd5  push    rdi
0x180020fd6  sub     rsp, 20h
0x180020fda  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x180020fe1  mov     rbx, rcx
0x180020fe4  mov     [rcx], rax
0x180020fe7  mov     edi, edx
0x180020fe9  mov     rcx, [rcx+8]
0x180020fed  test    rcx, rcx
0x180020ff0  jz      short loc_180021000
0x180020ff2  call    cs:__imp_InvCacheCloseHandle
0x180020ff8  mov     qword ptr [rbx+8], 0
0x180021000  mov     rcx, [rbx+10h]
0x180021004  test    rcx, rcx
0x180021007  jz      short loc_180021017
0x180021009  call    cs:__imp_InvCacheCloseHandle
0x18002100f  mov     qword ptr [rbx+10h], 0
0x180021017  lea     rax, ??_7InventoryCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InventoryCache::`vftable'
0x18002101e  mov     [rbx], rax
0x180021021  test    dil, 1
0x180021025  jz      short loc_180021034
0x180021027  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18002102c  mov     rcx, rbx; void *
0x18002102f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021034  mov     rax, rbx
0x180021037  mov     rbx, [rsp+28h+arg_0]
0x18002103c  add     rsp, 20h
0x180021040  pop     rdi
0x180021041  retn
```
