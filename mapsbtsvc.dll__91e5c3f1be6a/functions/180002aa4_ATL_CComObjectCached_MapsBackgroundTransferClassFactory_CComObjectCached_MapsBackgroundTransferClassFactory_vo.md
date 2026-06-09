# ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::~CComObjectCached<MapsBackgroundTransferClassFactory>(void)

- ea: `0x180002aa4`
- end: `0x180002abe`
- name: `??1?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b28`

## callees

- `0x180002ac4`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::~CComObjectCached<MapsBackgroundTransferClassFactory>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 16));
}

```

## disassembly

```asm
0x180002aa4  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002aab  mov     dword ptr [rcx+8], 0C0000001h
0x180002ab2  mov     [rcx], rax
0x180002ab5  add     rcx, 10h; this
0x180002ab9  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
