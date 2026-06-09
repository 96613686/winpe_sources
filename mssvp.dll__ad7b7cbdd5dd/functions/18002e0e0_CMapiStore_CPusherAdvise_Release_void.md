# CMapiStore::CPusherAdvise::Release(void)

- ea: `0x18002e0e0`
- end: `0x18002e12b`
- name: `?Release@CPusherAdvise@CMapiStore@@UEAAKXZ`
- size: `75`
- prototype: `unsigned int __fastcall(CMapiStore::CPusherAdvise *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180006640`
- `0x18002e0e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e10d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e10d`

## pseudocode

```c
__int64 __fastcall CMapiStore::CPusherAdvise::Release(CMapiStore::CPusherAdvise *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &CMapiStore::CPusherAdvise::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    operator delete(this, (const struct std::nothrow_t *)0x40);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e0e0  mov     [rsp+arg_0], rbx
0x18002e0e5  push    rdi
0x18002e0e6  sub     rsp, 20h
0x18002e0ea  mov     rbx, rcx
0x18002e0ed  or      edi, 0FFFFFFFFh
0x18002e0f0  lock xadd [rcx+8], edi
0x18002e0f5  sub     edi, 1
0x18002e0f8  jnz     short loc_18002E11E
0x18002e0fa  test    rcx, rcx
0x18002e0fd  jz      short loc_18002E11E
0x18002e0ff  lea     rax, ??_7CPusherAdvise@CMapiStore@@6B@; const CMapiStore::CPusherAdvise::`vftable'
0x18002e106  mov     [rcx], rax
0x18002e109  add     rcx, 10h; lpCriticalSection
0x18002e10d  call    cs:__imp_DeleteCriticalSection
0x18002e113  lea     edx, [rdi+40h]; struct std::nothrow_t *
0x18002e116  mov     rcx, rbx; void *
0x18002e119  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e11e  mov     rbx, [rsp+28h+arg_0]
0x18002e123  mov     eax, edi
0x18002e125  add     rsp, 20h
0x18002e129  pop     rdi
0x18002e12a  retn
```
