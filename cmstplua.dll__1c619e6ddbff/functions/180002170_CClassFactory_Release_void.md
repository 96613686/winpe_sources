# CClassFactory::Release(void)

- ea: `0x180002170`
- end: `0x1800021a8`
- name: `?Release@CClassFactory@@UEAAKXZ`
- size: `56`
- prototype: `unsigned int __fastcall(CClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002170`

## import_xrefs

- `cmutil!CmFree` at `0x180002199`
- `cmutil!CmFree` at `0x180002199`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClassFactory::Release(CClassFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CClassFactory::`vftable';
    _InterlockedDecrement(&dword_180006640);
    CmFree(this);
  }
  return v1;
}

```

## disassembly

```asm
0x180002170  push    rbx
0x180002172  sub     rsp, 20h
0x180002176  or      ebx, 0FFFFFFFFh
0x180002179  lock xadd [rcx+8], ebx
0x18000217e  sub     ebx, 1
0x180002181  jnz     short loc_1800021A0
0x180002183  test    rcx, rcx
0x180002186  jz      short loc_1800021A0
0x180002188  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18000218f  mov     [rcx], rax
0x180002192  lock dec cs:dword_180006640
0x180002199  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x18000219f  nop
0x1800021a0  mov     eax, ebx
0x1800021a2  add     rsp, 20h
0x1800021a6  pop     rbx
0x1800021a7  retn
```
