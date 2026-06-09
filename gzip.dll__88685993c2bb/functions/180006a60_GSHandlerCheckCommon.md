# __GSHandlerCheckCommon

- ea: `0x180006a60`
- end: `0x180006ac3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a3c`

## callees

- `0x180006a60`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x180006a60  mov     r10, rcx
0x180006a63  mov     r11, rdx
0x180006a66  mov     ecx, [r8]
0x180006a69  and     ecx, 0FFFFFFF8h
0x180006a6c  test    byte ptr [r8], 4
0x180006a70  jz      short loc_180006A87
0x180006a72  mov     eax, [r8+8]
0x180006a76  movsxd  r9, dword ptr [r8+4]
0x180006a7a  neg     eax
0x180006a7c  movsxd  rdx, eax
0x180006a7f  add     r9, r10
0x180006a82  and     r9, rdx
0x180006a85  jmp     short loc_180006A8A
0x180006a87  mov     r9, r10
0x180006a8a  movsxd  rax, ecx
0x180006a8d  mov     rdx, [rax+r9]
0x180006a91  mov     rax, [r11+10h]
0x180006a95  mov     ecx, [rax+8]
0x180006a98  mov     rax, [r11+8]
0x180006a9c  test    byte ptr [rcx+rax+3], 0Fh
0x180006aa1  jz      short loc_180006AB5
0x180006aa3  movzx   eax, byte ptr [rcx+rax+3]
0x180006aa8  mov     ecx, 0FFFFFFF0h
0x180006aad  and     rax, rcx
0x180006ab0  add     rax, r10
0x180006ab3  jmp     short loc_180006AB8
0x180006ab5  mov     rax, r10
0x180006ab8  xor     rdx, rax
0x180006abb  mov     rcx, rdx; StackCookie
0x180006abe  jmp     __security_check_cookie
```
