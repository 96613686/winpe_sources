# _com_raise_error(long,IErrorInfo *)

- ea: `0x18002059c`
- end: `0x1800205c1`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002045c`

## callees

- `0x180003de8`
- `0x1800204c0`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2, __int64 a3, bool a4)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a2, a4);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18002059c  sub     rsp, 48h
0x1800205a0  mov     r8, rdx; struct IErrorInfo *
0x1800205a3  mov     edx, ecx; int
0x1800205a5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800205aa  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x1800205af  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800205b6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800205bb  call    _CxxThrowException_0
```
