# Guard<ATL::CComObjectRootEx<ATL::CComMultiThreadModel>>::~Guard<ATL::CComObjectRootEx<ATL::CComMultiThreadModel>>(void)

- ea: `0x180016cb4`
- end: `0x180016cc2`
- name: `??1?$Guard@V?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@@@QEAA@XZ`
- size: `14`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018c0e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180016cbb`

## pseudocode

```c
void __fastcall Guard<ATL::CComObjectRootEx<ATL::CComMultiThreadModel>>::~Guard<ATL::CComObjectRootEx<ATL::CComMultiThreadModel>>(
        __int64 a1)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180016cb4  mov     rcx, [rcx]
0x180016cb7  add     rcx, 8
0x180016cbb  jmp     cs:__imp_LeaveCriticalSection
```
