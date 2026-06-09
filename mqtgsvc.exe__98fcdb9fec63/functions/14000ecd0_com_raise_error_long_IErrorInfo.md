# _com_raise_error(long,IErrorInfo *)

- ea: `0x14000ecd0`
- end: `0x14000ecf5`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ec24`
- `0x14000ec38`

## callees

- `0x140001cc6`
- `0x14000ce4c`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a2);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x14000ecd0  sub     rsp, 48h
0x14000ecd4  mov     r8, rdx; struct IErrorInfo *
0x14000ecd7  mov     edx, ecx; int
0x14000ecd9  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000ecde  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x14000ece3  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x14000ecea  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000ecef  call    _CxxThrowException_0
```
