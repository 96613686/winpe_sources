# calculateUpdatedEstimates

- ea: `0x180005cf8`
- end: `0x180005d7c`
- name: `calculateUpdatedEstimates`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002da0`

## callees

- `0x180003a60`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall calculateUpdatedEstimates(__int64 a1)
{
  __int64 v1; // rbx
  _WORD v3[288]; // [rsp+30h] [rbp-258h] BYREF

  v1 = *(_QWORD *)(a1 + 88);
  makeTree(288, 15, (_WORD *)(v1 + 553412), v3, v1 + 555140);
  return makeTree(32, 15, (_WORD *)(v1 + 555428), v3, v1 + 555620);
}

```

## disassembly

```asm
0x180005cf8  push    rbx
0x180005cfa  sub     rsp, 280h
0x180005d01  mov     rax, cs:__security_cookie
0x180005d08  xor     rax, rsp
0x180005d0b  mov     [rsp+288h+var_18], rax
0x180005d13  mov     rbx, [rcx+58h]
0x180005d17  lea     r9, [rsp+288h+var_258]
0x180005d1c  mov     edx, 0Fh
0x180005d21  mov     ecx, 120h
0x180005d26  lea     rax, [rbx+87884h]
0x180005d2d  lea     r8, [rbx+871C4h]
0x180005d34  mov     [rsp+288h+var_268], rax
0x180005d39  call    makeTree
0x180005d3e  mov     edx, 0Fh
0x180005d43  lea     rax, [rbx+87A64h]
0x180005d4a  lea     r8, [rbx+879A4h]
0x180005d51  mov     [rsp+288h+var_268], rax
0x180005d56  lea     r9, [rsp+288h+var_258]
0x180005d5b  lea     ecx, [rdx+11h]
0x180005d5e  call    makeTree
0x180005d63  mov     rcx, [rsp+288h+var_18]
0x180005d6b  xor     rcx, rsp; StackCookie
0x180005d6e  call    __security_check_cookie
0x180005d73  add     rsp, 280h
0x180005d7a  pop     rbx
0x180005d7b  retn
```
