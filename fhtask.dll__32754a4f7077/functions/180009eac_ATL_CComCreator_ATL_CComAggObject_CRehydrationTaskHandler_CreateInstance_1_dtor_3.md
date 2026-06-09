# _ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$3

- ea: `0x180009eac`
- end: `0x180009ebc`
- name: `_ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002350`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 40) + 8LL);
}

```

## disassembly

```asm
0x180009eac  mov     rcx, [rdx+28h]
0x180009eb3  add     rcx, 8
0x180009eb7  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
