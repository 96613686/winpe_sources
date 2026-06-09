# __GSHandlerCheckCommon

- ea: `0x140006d8c`
- end: `0x140006def`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006d68`
- `0x140006df8`
- `0x140006e60`

## callees

- `0x140006d8c`
- `0x140006f10`

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
0x140006d8c  mov     r10, rcx
0x140006d8f  mov     r11, rdx
0x140006d92  mov     ecx, [r8]
0x140006d95  and     ecx, 0FFFFFFF8h
0x140006d98  test    byte ptr [r8], 4
0x140006d9c  jz      short loc_140006DB3
0x140006d9e  mov     eax, [r8+8]
0x140006da2  movsxd  r9, dword ptr [r8+4]
0x140006da6  neg     eax
0x140006da8  movsxd  rdx, eax
0x140006dab  add     r9, r10
0x140006dae  and     r9, rdx
0x140006db1  jmp     short loc_140006DB6
0x140006db3  mov     r9, r10
0x140006db6  movsxd  rax, ecx
0x140006db9  mov     rdx, [rax+r9]
0x140006dbd  mov     rax, [r11+10h]
0x140006dc1  mov     ecx, [rax+8]
0x140006dc4  mov     rax, [r11+8]
0x140006dc8  test    byte ptr [rcx+rax+3], 0Fh
0x140006dcd  jz      short loc_140006DE1
0x140006dcf  movzx   eax, byte ptr [rcx+rax+3]
0x140006dd4  mov     ecx, 0FFFFFFF0h
0x140006dd9  and     rax, rcx
0x140006ddc  add     rax, r10
0x140006ddf  jmp     short loc_140006DE4
0x140006de1  mov     rax, r10
0x140006de4  xor     rdx, rax
0x140006de7  mov     rcx, rdx; StackCookie
0x140006dea  jmp     __security_check_cookie
```
