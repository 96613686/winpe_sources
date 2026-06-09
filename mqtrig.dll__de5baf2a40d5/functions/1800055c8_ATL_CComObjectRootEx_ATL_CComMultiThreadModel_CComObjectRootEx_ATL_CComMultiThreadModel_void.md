# ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)

- ea: `0x1800055c8`
- end: `0x1800055d1`
- name: `??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001eb1c`
- `0x18001f749`
- `0x180020390`

## callees

- `0x1800055fc`

## pseudocode

```c
void __fastcall ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(
        __int64 a1)
{
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((ATL::CComAutoDeleteCriticalSection *)(a1 + 8));
}

```

## disassembly

```asm
0x1800055c8  add     rcx, 8; this
0x1800055cc  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
