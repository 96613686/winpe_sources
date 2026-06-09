# _ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$2

- ea: `0x180009eec`
- end: `0x180009efc`
- name: `_ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002350`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComObject_CRehydrationTaskHandler___::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 104) + 8LL);
}

```

## disassembly

```asm
0x180009eec  mov     rcx, [rdx+68h]
0x180009ef3  add     rcx, 8
0x180009ef7  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
