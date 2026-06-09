# DrDevice::OnSetSdInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x1400054f0`
- end: `0x140005509`
- name: `?OnSetSdInfoCompletion@DrDevice@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`

## pseudocode

```c
__int64 __fastcall DrDevice::OnSetSdInfoCompletion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        volatile signed __int32 **a5)
{
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return 3221225862LL;
}

```

## disassembly

```asm
0x1400054f0  sub     rsp, 28h
0x1400054f4  mov     rcx, [rsp+28h+arg_20]
0x1400054f9  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400054fe  mov     eax, 0C0000186h
0x140005503  add     rsp, 28h
0x140005507  retn
```
