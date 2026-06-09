# RemoteGetSystemDirectory

- ea: `0x180023968`
- end: `0x1800239d6`
- name: `RemoteGetSystemDirectory`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022ba0`

## callees

- `0x180023140`
- `0x180023968`
- `0x1800263ce`
- `0x180026400`

## pseudocode

```c
__int64 __fastcall RemoteGetSystemDirectory(_QWORD *a1)
{
  __int16 v3; // [rsp+30h] [rbp-228h] BYREF
  _BYTE v4[526]; // [rsp+32h] [rbp-226h] BYREF

  v3 = 0;
  memset_0(v4, 0, 0x208u);
  return (unsigned int)RasRpcGetSystemDirectory(*a1, &v3, 261);
}

```

## disassembly

```asm
0x180023968  push    rbx
0x18002396a  sub     rsp, 250h
0x180023971  mov     rax, cs:__security_cookie
0x180023978  xor     rax, rsp
0x18002397b  mov     [rsp+258h+var_18], rax
0x180023983  mov     rbx, rcx
0x180023986  xor     eax, eax
0x180023988  mov     [rsp+258h+var_228], ax
0x18002398d  xor     edx, edx; Val
0x18002398f  mov     r8d, 208h; Size
0x180023995  lea     rcx, [rsp+258h+var_226]; void *
0x18002399a  call    memset_0
0x18002399f  nop
0x1800239a0  mov     r8d, 105h
0x1800239a6  lea     rdx, [rsp+258h+var_228]
0x1800239ab  mov     rcx, [rbx]
0x1800239ae  call    RasRpcGetSystemDirectory
0x1800239b3  mov     [rsp+258h+var_238], eax
0x1800239b7  mov     eax, [rsp+258h+var_238]
0x1800239bb  jmp     short $+2
0x1800239bd  mov     rcx, [rsp+258h+var_18]
0x1800239c5  xor     rcx, rsp; StackCookie
0x1800239c8  call    __security_check_cookie
0x1800239cd  add     rsp, 250h
0x1800239d4  pop     rbx
0x1800239d5  retn
0x180026806  push    rbp
0x180026808  sub     rsp, 20h
0x18002680c  mov     rbp, rdx
0x18002680f  mov     rax, [rcx]
0x180026812  mov     ecx, [rax]
0x180026814  mov     [rbp+20h], ecx
0x180026817  mov     ecx, [rbp+20h]; ExceptionCode
0x18002681a  call    cs:__imp_I_RpcExceptionFilter
0x180026820  nop
0x180026821  add     rsp, 20h
0x180026825  pop     rbp
0x180026826  retn
```
