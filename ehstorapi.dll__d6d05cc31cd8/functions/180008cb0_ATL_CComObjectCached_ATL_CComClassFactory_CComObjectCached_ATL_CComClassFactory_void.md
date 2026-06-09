# ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)

- ea: `0x180008cb0`
- end: `0x180008cca`
- name: `??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008db8`

## callees

- `0x18000213c`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180008cb0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180008cb7  mov     dword ptr [rcx+8], 0C0000001h
0x180008cbe  mov     [rcx], rax
0x180008cc1  add     rcx, 10h; this
0x180008cc5  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
