# [thunk]:ATL::CComContainedObject<CServiceProvider>::Release`adjustor{16}' (void)

- ea: `0x1800084f0`
- end: `0x1800084f9`
- name: `?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800084c0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CServiceProvider>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CServiceProvider>::Release(a1 - 16);
}

```

## disassembly

```asm
0x1800084f0  sub     rcx, 10h
0x1800084f4  jmp     ?Release@?$CComContainedObject@VCServiceProvider@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CServiceProvider>::Release(void)
```
