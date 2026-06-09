# ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(void)

- ea: `0x1800100c4`
- end: `0x1800100d6`
- name: `??1?$CComPtr@UILogonTrigger@@@ATL@@QEAA@XZ`
- size: `18`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800203c6`
- `0x18002049e`
- `0x18002050a`
- `0x18002051c`
- `0x18002052e`
- `0x180020540`
- `0x1800206ea`
- `0x180020700`
- `0x180020716`
- `0x180020786`
- `0x1800207aa`
- `0x1800207c0`
- `0x1800207d6`
- `0x1800208aa`
- `0x180020904`
- `0x18002091a`
- `0x180020930`

## callees

- `0x180008ab0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ILogonTrigger>::~CComPtr<ILogonTrigger>(__int64 a1)
{
  return ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(a1);
}

```

## disassembly

```asm
0x1800100c4  mov     [rsp+arg_0], rcx
0x1800100c9  sub     rsp, 28h
0x1800100cd  add     rsp, 28h
0x1800100d1  jmp     ??1?$CComPtrBase@UICertRequest2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ICertRequest2>::~CComPtrBase<ICertRequest2>(void)
```
