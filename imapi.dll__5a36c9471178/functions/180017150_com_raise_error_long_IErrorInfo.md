# _com_raise_error(long,IErrorInfo *)

- ea: `0x180017150`
- end: `0x180017170`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017020`

## callees

- `0x18001707c`
- `0x180018495`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(__int64 a1, struct IErrorInfo *a2, struct IErrorInfo *a3, bool a4)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, (int)a2, a3, a4);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180017150  sub     rsp, 48h
0x180017154  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180017159  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z
0x18001715e  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180017165  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001716a  call    _CxxThrowException_0
```
