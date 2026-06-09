# _com_raise_error(long,IErrorInfo *)

- ea: `0x1800137c0`
- end: `0x1800137e2`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800137b0`

## callees

- `0x180001e0e`
- `0x180002500`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2, struct IErrorInfo *a3)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a3);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800137c0  sub     rsp, 48h
0x1800137c4  mov     edx, ecx; int
0x1800137c6  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800137cb  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x1800137d0  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800137d7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800137dc  call    _CxxThrowException_0
```
