# __GSHandlerCheckCommon

- ea: `0x18000bf00`
- end: `0x18000bf63`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bedc`
- `0x18000bf6c`

## callees

- `0x18000bf00`
- `0x18000c030`

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
0x18000bf00  mov     r10, rcx
0x18000bf03  mov     r11, rdx
0x18000bf06  mov     ecx, [r8]
0x18000bf09  and     ecx, 0FFFFFFF8h
0x18000bf0c  test    byte ptr [r8], 4
0x18000bf10  jz      short loc_18000BF27
0x18000bf12  mov     eax, [r8+8]
0x18000bf16  movsxd  r9, dword ptr [r8+4]
0x18000bf1a  neg     eax
0x18000bf1c  movsxd  rdx, eax
0x18000bf1f  add     r9, r10
0x18000bf22  and     r9, rdx
0x18000bf25  jmp     short loc_18000BF2A
0x18000bf27  mov     r9, r10
0x18000bf2a  movsxd  rax, ecx
0x18000bf2d  mov     rdx, [rax+r9]
0x18000bf31  mov     rax, [r11+10h]
0x18000bf35  mov     ecx, [rax+8]
0x18000bf38  mov     rax, [r11+8]
0x18000bf3c  test    byte ptr [rcx+rax+3], 0Fh
0x18000bf41  jz      short loc_18000BF55
0x18000bf43  movzx   eax, byte ptr [rcx+rax+3]
0x18000bf48  mov     ecx, 0FFFFFFF0h
0x18000bf4d  and     rax, rcx
0x18000bf50  add     rax, r10
0x18000bf53  jmp     short loc_18000BF58
0x18000bf55  mov     rax, r10
0x18000bf58  xor     rdx, rax
0x18000bf5b  mov     rcx, rdx; StackCookie
0x18000bf5e  jmp     __security_check_cookie
```
