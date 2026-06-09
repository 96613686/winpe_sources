# _com_raise_error(long,IErrorInfo *)

- ea: `0x18000dc14`
- end: `0x18000dc39`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000db68`
- `0x18000db7c`

## callees

- `0x1800020a5`
- `0x18000cf5c`

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
0x18000dc14  sub     rsp, 48h
0x18000dc18  mov     r8, rdx; struct IErrorInfo *
0x18000dc1b  mov     edx, ecx; int
0x18000dc1d  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000dc22  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18000dc27  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000dc2e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000dc33  call    _CxxThrowException_0
```
