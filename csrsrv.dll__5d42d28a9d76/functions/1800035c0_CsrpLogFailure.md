# CsrpLogFailure

- ea: `0x1800035c0`
- end: `0x180003636`
- name: `CsrpLogFailure`
- size: `118`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180001540`
- `0x1800019b0`
- `0x180001c50`
- `0x1800021f0`
- `0x180002a00`
- `0x180002c90`
- `0x1800034d0`
- `0x180003f20`
- `0x1800042b0`
- `0x180004a20`
- `0x180005180`
- `0x180007b70`
- `0x180008780`
- `0x1800090cc`
- `0x180009190`
- `0x180009fd0`
- `0x18000a2b0`
- `0x18000a85c`

## callees

- `0x180008290`
- `0x18000ab61`
- `0x18000ab80`

## pseudocode

```c
__int64 __fastcall CsrpLogFailure(STRSAFE_LPCSTR pszSrc)
{
  _BYTE v3[208]; // [rsp+20h] [rbp-E8h] BYREF

  memset_0(v3, 0, 0xCCu);
  return CsrpInternalLogFailure(pszSrc);
}

```

## disassembly

```asm
0x1800035c0  mov     [rsp+arg_8], rbx
0x1800035c5  mov     [rsp+arg_10], rsi
0x1800035ca  push    rdi
0x1800035cb  sub     rsp, 100h
0x1800035d2  mov     rax, cs:__security_cookie
0x1800035d9  xor     rax, rsp
0x1800035dc  mov     [rsp+108h+var_18], rax
0x1800035e4  mov     ebx, r8d
0x1800035e7  mov     edi, edx
0x1800035e9  mov     rsi, rcx
0x1800035ec  xor     edx, edx; Val
0x1800035ee  mov     r8d, 0CCh; Size
0x1800035f4  lea     rcx, [rsp+108h+var_E8]; void *
0x1800035f9  call    memset_0
0x1800035fe  lea     r9, [rsp+108h+var_E8]
0x180003603  mov     r8d, ebx
0x180003606  mov     edx, edi
0x180003608  mov     rcx, rsi; pszSrc
0x18000360b  call    CsrpInternalLogFailure
0x180003610  mov     rcx, [rsp+108h+var_18]
0x180003618  xor     rcx, rsp; StackCookie
0x18000361b  call    __security_check_cookie
0x180003620  lea     r11, [rsp+108h+var_8]
0x180003628  mov     rbx, [r11+18h]
0x18000362c  mov     rsi, [r11+20h]
0x180003630  mov     rsp, r11
0x180003633  pop     rdi
0x180003634  retn
```
