# ATL::CComClassFactory::CComClassFactory(void)

- ea: `0x180001b48`
- end: `0x180001b71`
- name: `??0CComClassFactory@ATL@@QEAA@XZ`
- size: `41`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b24`

## pseudocode

```c
ATL::CComClassFactory *__fastcall ATL::CComClassFactory::CComClassFactory(ATL::CComClassFactory *this)
{
  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
  return this;
}

```

## disassembly

```asm
0x180001b48  mov     dword ptr [rcx+8], 0
0x180001b4f  xor     eax, eax
0x180001b51  xorps   xmm0, xmm0
0x180001b54  movups  xmmword ptr [rcx+10h], xmm0
0x180001b58  movups  xmmword ptr [rcx+20h], xmm0
0x180001b5c  mov     [rcx+30h], rax
0x180001b60  mov     [rcx+38h], al
0x180001b63  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180001b6a  mov     [rcx], rax
0x180001b6d  mov     rax, rcx
0x180001b70  retn
```
