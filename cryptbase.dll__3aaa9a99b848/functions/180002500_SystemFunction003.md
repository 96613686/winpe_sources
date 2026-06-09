# SystemFunction003

- ea: `0x180002500`
- end: `0x180002546`
- name: `SystemFunction003`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002350`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall SystemFunction003(_BYTE *a1, __int64 a2)
{
  _DWORD v3[2]; // [rsp+20h] [rbp-18h] BYREF

  qmemcpy(v3, "KGS!@#$%", sizeof(v3));
  return SystemFunction001((__int64)v3, a1, a2);
}

```

## disassembly

```asm
0x180002500  sub     rsp, 38h
0x180002504  mov     rax, cs:__security_cookie
0x18000250b  xor     rax, rsp
0x18000250e  mov     [rsp+38h+var_10], rax
0x180002513  mov     r8, rdx
0x180002516  mov     [rsp+38h+var_18], 2153474Bh
0x18000251e  mov     rdx, rcx
0x180002521  mov     [rsp+38h+var_14], 25242340h
0x180002529  lea     rcx, [rsp+38h+var_18]
0x18000252e  call    SystemFunction001
0x180002533  mov     rcx, [rsp+38h+var_10]
0x180002538  xor     rcx, rsp; StackCookie
0x18000253b  call    __security_check_cookie
0x180002540  add     rsp, 38h
0x180002544  retn
```
