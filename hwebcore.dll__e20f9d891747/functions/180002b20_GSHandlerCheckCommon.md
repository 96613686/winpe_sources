# __GSHandlerCheckCommon

- ea: `0x180002b20`
- end: `0x180002b83`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002afc`

## callees

- `0x180002b20`
- `0x180002be0`

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
0x180002b20  mov     r10, rcx
0x180002b23  mov     r11, rdx
0x180002b26  mov     ecx, [r8]
0x180002b29  and     ecx, 0FFFFFFF8h
0x180002b2c  test    byte ptr [r8], 4
0x180002b30  jz      short loc_180002B47
0x180002b32  mov     eax, [r8+8]
0x180002b36  movsxd  r9, dword ptr [r8+4]
0x180002b3a  neg     eax
0x180002b3c  movsxd  rdx, eax
0x180002b3f  add     r9, r10
0x180002b42  and     r9, rdx
0x180002b45  jmp     short loc_180002B4A
0x180002b47  mov     r9, r10
0x180002b4a  movsxd  rax, ecx
0x180002b4d  mov     rdx, [rax+r9]
0x180002b51  mov     rax, [r11+10h]
0x180002b55  mov     ecx, [rax+8]
0x180002b58  mov     rax, [r11+8]
0x180002b5c  test    byte ptr [rcx+rax+3], 0Fh
0x180002b61  jz      short loc_180002B75
0x180002b63  movzx   eax, byte ptr [rcx+rax+3]
0x180002b68  mov     ecx, 0FFFFFFF0h
0x180002b6d  and     rax, rcx
0x180002b70  add     rax, r10
0x180002b73  jmp     short loc_180002B78
0x180002b75  mov     rax, r10
0x180002b78  xor     rdx, rax
0x180002b7b  mov     rcx, rdx; StackCookie
0x180002b7e  jmp     __security_check_cookie
```
