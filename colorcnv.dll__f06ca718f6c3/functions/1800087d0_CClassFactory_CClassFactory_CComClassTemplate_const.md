# CClassFactory::CClassFactory(CComClassTemplate const *)

- ea: `0x1800087d0`
- end: `0x1800087f0`
- name: `??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z`
- size: `32`
- prototype: `CClassFactory *__fastcall(CClassFactory *__hidden this, const struct CComClassTemplate *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800086d0`
- `0x18000f070`

## pseudocode

```c
CClassFactory *__fastcall CClassFactory::CClassFactory(CClassFactory *this, const struct CComClassTemplate *a2)
{
  CClassFactory *result; // rax

  _InterlockedIncrement(&g_cActiveObjects);
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &CClassFactory::`vftable';
  result = this;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1800087d0  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800087d7  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800087de  mov     [rcx+8], rdx
0x1800087e2  mov     [rcx], rax
0x1800087e5  mov     rax, rcx
0x1800087e8  mov     dword ptr [rcx+10h], 0
0x1800087ef  retn
```
