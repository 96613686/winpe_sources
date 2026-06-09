# __GSHandlerCheckCommon

- ea: `0x18000b044`
- end: `0x18000b0a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b020`

## callees

- `0x18000b044`
- `0x18000b100`

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
0x18000b044  mov     r10, rcx
0x18000b047  mov     r11, rdx
0x18000b04a  mov     ecx, [r8]
0x18000b04d  and     ecx, 0FFFFFFF8h
0x18000b050  test    byte ptr [r8], 4
0x18000b054  jz      short loc_18000B06B
0x18000b056  mov     eax, [r8+8]
0x18000b05a  movsxd  r9, dword ptr [r8+4]
0x18000b05e  neg     eax
0x18000b060  movsxd  rdx, eax
0x18000b063  add     r9, r10
0x18000b066  and     r9, rdx
0x18000b069  jmp     short loc_18000B06E
0x18000b06b  mov     r9, r10
0x18000b06e  movsxd  rax, ecx
0x18000b071  mov     rdx, [rax+r9]
0x18000b075  mov     rax, [r11+10h]
0x18000b079  mov     ecx, [rax+8]
0x18000b07c  mov     rax, [r11+8]
0x18000b080  test    byte ptr [rcx+rax+3], 0Fh
0x18000b085  jz      short loc_18000B099
0x18000b087  movzx   eax, byte ptr [rcx+rax+3]
0x18000b08c  mov     ecx, 0FFFFFFF0h
0x18000b091  and     rax, rcx
0x18000b094  add     rax, r10
0x18000b097  jmp     short loc_18000B09C
0x18000b099  mov     rax, r10
0x18000b09c  xor     rdx, rax
0x18000b09f  mov     rcx, rdx; StackCookie
0x18000b0a2  jmp     __security_check_cookie
```
