# lldpSetMulticastGroup

- ea: `0x14000fa94`
- end: `0x14000fb23`
- name: `lldpSetMulticastGroup`
- size: `143`
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
__int64 __fastcall lldpSetMulticastGroup(__int64 a1, char a2)
{
  _QWORD v5[32]; // [rsp+20h] [rbp-118h] BYREF

  memset(v5, 0, 0xF8u);
  *(_QWORD *)((char *)v5 + 4) = 1;
  LODWORD(v5[6]) = 6;
  LODWORD(v5[4]) = 16843273 - (a2 != 0);
  v5[5] = &LLDP_DEST_MAC_NEAREST_BRIDGE;
  return lldpSendOidRequestAndWait(a1, (__int64)v5);
}

```

## disassembly

```asm
0x14000fa94  mov     [rsp+arg_8], rbx
0x14000fa99  push    rdi
0x14000fa9a  sub     rsp, 130h
0x14000faa1  mov     rax, cs:__security_cookie
0x14000faa8  xor     rax, rsp
0x14000faab  mov     [rsp+138h+var_18], rax
0x14000fab3  mov     bl, dl
0x14000fab5  mov     rdi, rcx
0x14000fab8  xor     edx, edx; Val
0x14000faba  lea     rcx, [rsp+138h+var_118]; void *
0x14000fabf  mov     r8d, 0F8h; Size
0x14000fac5  call    memset
0x14000faca  neg     bl
0x14000facc  mov     [rsp+138h+var_114], 1
0x14000fad5  lea     rdx, [rsp+138h+var_118]
0x14000fada  mov     [rsp+138h+var_E8], 6
0x14000fae2  sbb     eax, eax
0x14000fae4  mov     rcx, rdi
0x14000fae7  add     eax, 1010209h
0x14000faec  mov     [rsp+138h+var_F8], eax
0x14000faf0  lea     rax, LLDP_DEST_MAC_NEAREST_BRIDGE
0x14000faf7  mov     [rsp+138h+var_F0], rax
0x14000fafc  call    lldpSendOidRequestAndWait
0x14000fb01  mov     rcx, [rsp+138h+var_18]
0x14000fb09  xor     rcx, rsp; StackCookie
0x14000fb0c  call    __security_check_cookie
0x14000fb11  mov     rbx, [rsp+138h+arg_8]
0x14000fb19  add     rsp, 130h
0x14000fb20  pop     rdi
0x14000fb21  retn
```
