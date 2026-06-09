# _DeleteLocalManagementEnrollment_::_1_::dtor$0

- ea: `0x180006c38`
- end: `0x180006c44`
- name: `_DeleteLocalManagementEnrollment_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005e94`

## pseudocode

```c
__int64 __fastcall DeleteLocalManagementEnrollment_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnrollEngine>::~CComPtr<IEnrollEngine>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x180006c38  lea     rcx, [rdx+38h]
0x180006c3f  jmp     ??1?$CComPtr@UIEnrollEngine@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnrollEngine>::~CComPtr<IEnrollEngine>(void)
```
