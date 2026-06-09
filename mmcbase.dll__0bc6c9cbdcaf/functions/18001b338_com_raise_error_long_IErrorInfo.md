# _com_raise_error(long,IErrorInfo *)

- ea: `0x18001b338`
- end: `0x18001b36b`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004e20`

## callees

- `0x18000a4ec`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(__int64 a1, struct IErrorInfo *a2)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  __int128 v4; // [rsp+30h] [rbp-18h]

  v3 = -2147467261;
  pExceptionObject = &_com_error::`vftable';
  v4 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x18001b338  sub     rsp, 48h
0x18001b33c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001b343  mov     [rsp+48h+var_20], 80004003h
0x18001b34b  xorps   xmm0, xmm0
0x18001b34e  mov     [rsp+48h+pExceptionObject], rax
0x18001b353  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18001b35a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001b35f  movdqu  [rsp+48h+var_18], xmm0
0x18001b365  call    _CxxThrowException_0
```
