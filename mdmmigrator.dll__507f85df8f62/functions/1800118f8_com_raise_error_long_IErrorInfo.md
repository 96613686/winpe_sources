# _com_raise_error(long,IErrorInfo *)

- ea: `0x1800118f8`
- end: `0x18001191d`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800117c8`

## callees

- `0x1800035fe`
- `0x180011828`

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
0x1800118f8  sub     rsp, 48h
0x1800118fc  mov     r8, rdx; struct IErrorInfo *
0x1800118ff  mov     edx, ecx; int
0x180011901  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011906  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18001190b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180011912  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011917  call    _CxxThrowException_0
```
