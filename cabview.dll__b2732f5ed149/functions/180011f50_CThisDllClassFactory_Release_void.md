# CThisDllClassFactory::Release(void)

- ea: `0x180011f50`
- end: `0x180011f89`
- name: `?Release@CThisDllClassFactory@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CThisDllClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callees

- `0x180002644`
- `0x180011f50`

## pseudocode

```c
__int64 __fastcall CThisDllClassFactory::Release(CThisDllClassFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CThisDllClassFactory::`vftable';
    _InterlockedDecrement(&g_cRefThisDll);
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180011f50  push    rbx
0x180011f52  sub     rsp, 20h
0x180011f56  or      ebx, 0FFFFFFFFh
0x180011f59  lock xadd [rcx+8], ebx
0x180011f5e  sub     ebx, 1
0x180011f61  jnz     short loc_180011F81
0x180011f63  test    rcx, rcx
0x180011f66  jz      short loc_180011F81
0x180011f68  lea     rax, ??_7CThisDllClassFactory@@6B@; const CThisDllClassFactory::`vftable'
0x180011f6f  mov     [rcx], rax
0x180011f72  lea     edx, [rbx+20h]; unsigned __int64
0x180011f75  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180011f7c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011f81  mov     eax, ebx
0x180011f83  add     rsp, 20h
0x180011f87  pop     rbx
0x180011f88  retn
```
