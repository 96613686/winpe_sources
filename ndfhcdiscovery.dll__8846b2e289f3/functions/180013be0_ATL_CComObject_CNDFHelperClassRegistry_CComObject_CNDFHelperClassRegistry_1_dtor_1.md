# _ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$1

- ea: `0x180013be0`
- end: `0x180013bf0`
- name: `_ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000555c`

## pseudocode

```c
void __fastcall ATL::CComObject_CNDFHelperClassRegistry_::CComObject_CNDFHelperClassRegistry__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 48) + 8LL);
}

```

## disassembly

```asm
0x180013be0  mov     rcx, [rdx+30h]
0x180013be7  add     rcx, 8
0x180013beb  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
