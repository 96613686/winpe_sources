# NsiRegisterChangeNotification

- ea: `0x180002fd0`
- end: `0x180003034`
- name: `NsiRegisterChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002690`
- `0x1800030e1`

## pseudocode

```c
ULONG __fastcall NsiRegisterChangeNotification(__int64 a1, int a2, __int64 a3, char a4, __int64 a5, __int64 a6)
{
  _QWORD OutputBuffer[2]; // [rsp+20h] [rbp-78h] BYREF
  int v12; // [rsp+30h] [rbp-68h]
  __int64 v13; // [rsp+38h] [rbp-60h]
  char v14; // [rsp+40h] [rbp-58h]
  __int64 v15; // [rsp+48h] [rbp-50h]
  __int64 v16; // [rsp+60h] [rbp-38h]

  memset_0(OutputBuffer, 0, 0x48u);
  v15 = a5;
  v16 = a6;
  OutputBuffer[1] = a1;
  v12 = a2;
  v13 = a3;
  v14 = a4;
  return NsiRegisterChangeNotificationEx(OutputBuffer);
}

```

## disassembly

```asm
0x180002fd0  push    rbx
0x180002fd2  push    rbp
0x180002fd3  push    rsi
0x180002fd4  push    rdi
0x180002fd5  sub     rsp, 78h
0x180002fd9  mov     edi, edx
0x180002fdb  mov     rsi, r8
0x180002fde  xor     edx, edx; Val
0x180002fe0  mov     rbx, rcx
0x180002fe3  lea     rcx, [rsp+98h+OutputBuffer]; void *
0x180002fe8  mov     bpl, r9b
0x180002feb  lea     r8d, [rdx+48h]; Size
0x180002fef  call    memset_0
0x180002ff4  mov     rax, [rsp+98h+arg_20]
0x180002ffc  lea     rcx, [rsp+98h+OutputBuffer]; OutputBuffer
0x180003001  mov     [rsp+98h+var_50], rax
0x180003006  mov     rax, [rsp+98h+arg_28]
0x18000300e  mov     [rsp+98h+var_38], rax
0x180003013  mov     [rsp+98h+var_70], rbx
0x180003018  mov     [rsp+98h+var_68], edi
0x18000301c  mov     [rsp+98h+var_60], rsi
0x180003021  mov     [rsp+98h+var_58], bpl
0x180003026  call    NsiRegisterChangeNotificationEx
0x18000302b  add     rsp, 78h
0x18000302f  pop     rdi
0x180003030  pop     rsi
0x180003031  pop     rbp
0x180003032  pop     rbx
0x180003033  retn
```
