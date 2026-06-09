# _com_raise_error(long,IErrorInfo *)

- ea: `0x18000a360`
- end: `0x18000a382`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a238`

## callees

- `0x180001ce3`
- `0x18000a294`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2, struct IErrorInfo *a3, bool a4)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a3, a4);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18000a360  sub     rsp, 48h
0x18000a364  mov     edx, ecx; int
0x18000a366  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000a36b  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18000a370  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000a377  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000a37c  call    _CxxThrowException_0
```
