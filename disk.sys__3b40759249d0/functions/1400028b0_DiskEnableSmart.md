# DiskEnableSmart

- ea: `0x1400028b0`
- end: `0x14000292f`
- name: `DiskEnableSmart`
- size: `127`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011ee0`
- `0x140014b00`
- `0x140014d90`

## callees

- `0x140005bf0`
- `0x140012810`

## pseudocode

```c
NTSTATUS __fastcall DiskEnableSmart(__int64 a1)
{
  __int64 v2; // [rsp+40h] [rbp-58h] BYREF
  _OWORD Buffer[4]; // [rsp+48h] [rbp-50h] BYREF

  LODWORD(v2) = 61;
  memset(Buffer, 0, 61);
  return DiskPerformSmartCommand(a1, 1770756, 176, 216, 0, 0, (char *)Buffer, (int *)&v2);
}

```

## disassembly

```asm
0x1400028b0  sub     rsp, 98h
0x1400028b7  mov     rax, cs:__security_cookie
0x1400028be  xor     rax, rsp
0x1400028c1  mov     [rsp+98h+var_10], rax
0x1400028c9  xorps   xmm0, xmm0
0x1400028cc  mov     dword ptr [rsp+98h+var_58], 3Dh ; '='
0x1400028d4  lea     rax, [rsp+98h+var_58]
0x1400028d9  mov     r9b, 0D8h; int
0x1400028dc  mov     [rsp+98h+var_60], rax; __int64
0x1400028e1  mov     r8b, 0B0h; int
0x1400028e4  lea     rax, [rsp+98h+var_50]
0x1400028e9  mov     edx, 1B0504h; int
0x1400028ee  mov     [rsp+98h+Buffer], rax; Buffer
0x1400028f3  movups  xmmword ptr [rsp+98h+var_30], xmm0
0x1400028f8  mov     [rsp+98h+var_70], 0; char
0x1400028fd  mov     [rsp+98h+var_78], 0; char
0x140002902  movups  [rsp+98h+var_50], xmm0
0x140002907  movups  [rsp+98h+var_40], xmm0
0x14000290c  movups  xmmword ptr [rsp+98h+var_30+0Dh], xmm0
0x140002911  call    DiskPerformSmartCommand
0x140002916  mov     rcx, [rsp+98h+var_10]
0x14000291e  xor     rcx, rsp; StackCookie
0x140002921  call    __security_check_cookie
0x140002926  add     rsp, 98h
0x14000292d  retn
```
