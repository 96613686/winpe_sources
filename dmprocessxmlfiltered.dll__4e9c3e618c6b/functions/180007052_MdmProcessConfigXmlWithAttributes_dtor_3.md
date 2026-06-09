# MdmProcessConfigXmlWithAttributes$dtor$3

- ea: `0x180007052`
- end: `0x18000705e`
- name: `MdmProcessConfigXmlWithAttributes$dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003138`

## pseudocode

```c
__int64 __fastcall MdmProcessConfigXmlWithAttributes_dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IProvisioningDPU>::~CComPtr<IProvisioningDPU>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x180007052  lea     rcx, [rdx+38h]
0x180007059  jmp     ??1?$CComPtr@UIProvisioningDPU@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvisioningDPU>::~CComPtr<IProvisioningDPU>(void)
```
