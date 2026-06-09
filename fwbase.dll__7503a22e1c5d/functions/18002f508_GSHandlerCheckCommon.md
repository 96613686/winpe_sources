# __GSHandlerCheckCommon

- ea: `0x18002f508`
- end: `0x18002f56b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f4e4`
- `0x18002f574`

## callees

- `0x18001e1d0`
- `0x18002f508`

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
0x18002f508  mov     r10, rcx
0x18002f50b  mov     r11, rdx
0x18002f50e  mov     ecx, [r8]
0x18002f511  and     ecx, 0FFFFFFF8h
0x18002f514  test    byte ptr [r8], 4
0x18002f518  jz      short loc_18002F52F
0x18002f51a  mov     eax, [r8+8]
0x18002f51e  movsxd  r9, dword ptr [r8+4]
0x18002f522  neg     eax
0x18002f524  movsxd  rdx, eax
0x18002f527  add     r9, r10
0x18002f52a  and     r9, rdx
0x18002f52d  jmp     short loc_18002F532
0x18002f52f  mov     r9, r10
0x18002f532  movsxd  rax, ecx
0x18002f535  mov     rdx, [rax+r9]
0x18002f539  mov     rax, [r11+10h]
0x18002f53d  mov     ecx, [rax+8]
0x18002f540  mov     rax, [r11+8]
0x18002f544  test    byte ptr [rcx+rax+3], 0Fh
0x18002f549  jz      short loc_18002F55D
0x18002f54b  movzx   eax, byte ptr [rcx+rax+3]
0x18002f550  mov     ecx, 0FFFFFFF0h
0x18002f555  and     rax, rcx
0x18002f558  add     rax, r10
0x18002f55b  jmp     short loc_18002F560
0x18002f55d  mov     rax, r10
0x18002f560  xor     rdx, rax
0x18002f563  mov     rcx, rdx; StackCookie
0x18002f566  jmp     __security_check_cookie
```
