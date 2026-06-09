# [thunk]:ATL::CComObject<CServiceProvider>::AddRef`adjustor{16}' (void)

- ea: `0x180005a30`
- end: `0x180005a39`
- name: `?AddRef@?$CComObject@VCServiceProvider@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800059f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CServiceProvider>::AddRef(__int64 a1)
{
  return ATL::CComObject<CServiceProvider>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180005a30  sub     rcx, 10h
0x180005a34  jmp     ?AddRef@?$CComObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComObject<CServiceProvider>::AddRef(void)
```
