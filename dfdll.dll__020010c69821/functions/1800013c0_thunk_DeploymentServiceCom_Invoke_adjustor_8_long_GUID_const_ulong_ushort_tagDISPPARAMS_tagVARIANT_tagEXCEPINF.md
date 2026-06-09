# [thunk]:DeploymentServiceCom::Invoke`adjustor{8}' (long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800013c0`
- end: `0x1800013c9`
- name: `?Invoke@DeploymentServiceCom@@W7EAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001340`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::Invoke(
        __int64 a1,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  return DeploymentServiceCom::Invoke((DeploymentServiceCom *)(a1 - 8), a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x1800013c0  sub     rcx, 8; this
0x1800013c4  jmp     ?Invoke@DeploymentServiceCom@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; DeploymentServiceCom::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
```
