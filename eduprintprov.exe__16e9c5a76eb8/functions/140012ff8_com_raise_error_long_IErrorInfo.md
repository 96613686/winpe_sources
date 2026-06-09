# _com_raise_error(long,IErrorInfo *)

- ea: `0x140012ff8`
- end: `0x14001301d`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012ebc`

## callees

- `0x14000318c`
- `0x140012f20`

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
0x140012ff8  sub     rsp, 48h
0x140012ffc  mov     r8, rdx; struct IErrorInfo *
0x140012fff  mov     edx, ecx; int
0x140013001  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140013006  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x14001300b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x140013012  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140013017  call    _CxxThrowException_0
```
