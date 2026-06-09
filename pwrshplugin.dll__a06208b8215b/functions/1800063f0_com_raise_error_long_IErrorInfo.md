# _com_raise_error(long,IErrorInfo *)

- ea: `0x1800063f0`
- end: `0x180006410`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, struct IErrorInfo *, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062bc`

## callees

- `0x180001dfc`
- `0x180006318`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(__int64 a1, struct IErrorInfo *a2, struct IErrorInfo *a3)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, (__int64)a2, a3);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800063f0  sub     rsp, 48h
0x1800063f4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800063f9  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z
0x1800063fe  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180006405  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000640a  call    _CxxThrowException_0
```
