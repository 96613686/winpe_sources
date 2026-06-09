# lldpSetPacketFilter

- ea: `0x14000fb2c`
- end: `0x14000fbaa`
- name: `lldpSetPacketFilter`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f9b4`
- `0x14001280c`

## callees

- `0x140006630`
- `0x140006b40`
- `0x1400123a0`

## pseudocode

```c
__int64 __fastcall lldpSetPacketFilter(__int64 a1, int a2)
{
  int v4; // [rsp+20h] [rbp-128h] BYREF
  _QWORD v5[32]; // [rsp+30h] [rbp-118h] BYREF

  v4 = a2;
  memset(v5, 0, 0xF8u);
  *(_QWORD *)((char *)v5 + 4) = 1;
  v5[5] = &v4;
  LODWORD(v5[4]) = 65806;
  LODWORD(v5[6]) = 4;
  return lldpSendOidRequestAndWait(a1, (__int64)v5);
}

```

## disassembly

```asm
0x14000fb2c  push    rbx
0x14000fb2e  sub     rsp, 140h
0x14000fb35  mov     rax, cs:__security_cookie
0x14000fb3c  xor     rax, rsp
0x14000fb3f  mov     [rsp+148h+var_18], rax
0x14000fb47  mov     rbx, rcx
0x14000fb4a  mov     [rsp+148h+var_128], edx
0x14000fb4e  xor     edx, edx; Val
0x14000fb50  lea     rcx, [rsp+148h+var_118]; void *
0x14000fb55  mov     r8d, 0F8h; Size
0x14000fb5b  call    memset
0x14000fb60  lea     rax, [rsp+148h+var_128]
0x14000fb65  mov     [rsp+148h+var_114], 1
0x14000fb6e  lea     rdx, [rsp+148h+var_118]
0x14000fb73  mov     [rsp+148h+var_F0], rax
0x14000fb78  mov     rcx, rbx
0x14000fb7b  mov     [rsp+148h+var_F8], 1010Eh
0x14000fb83  mov     [rsp+148h+var_E8], 4
0x14000fb8b  call    lldpSendOidRequestAndWait
0x14000fb90  mov     rcx, [rsp+148h+var_18]
0x14000fb98  xor     rcx, rsp; StackCookie
0x14000fb9b  call    __security_check_cookie
0x14000fba0  add     rsp, 140h
0x14000fba7  pop     rbx
0x14000fba8  retn
```
