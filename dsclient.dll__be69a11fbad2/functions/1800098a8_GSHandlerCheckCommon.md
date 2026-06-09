# __GSHandlerCheckCommon

- ea: `0x1800098a8`
- end: `0x18000990b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009884`

## callees

- `0x1800098a8`
- `0x180009950`

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
0x1800098a8  mov     r10, rcx
0x1800098ab  mov     r11, rdx
0x1800098ae  mov     ecx, [r8]
0x1800098b1  and     ecx, 0FFFFFFF8h
0x1800098b4  test    byte ptr [r8], 4
0x1800098b8  jz      short loc_1800098CF
0x1800098ba  mov     eax, [r8+8]
0x1800098be  movsxd  r9, dword ptr [r8+4]
0x1800098c2  neg     eax
0x1800098c4  movsxd  rdx, eax
0x1800098c7  add     r9, r10
0x1800098ca  and     r9, rdx
0x1800098cd  jmp     short loc_1800098D2
0x1800098cf  mov     r9, r10
0x1800098d2  movsxd  rax, ecx
0x1800098d5  mov     rdx, [rax+r9]
0x1800098d9  mov     rax, [r11+10h]
0x1800098dd  mov     ecx, [rax+8]
0x1800098e0  mov     rax, [r11+8]
0x1800098e4  test    byte ptr [rcx+rax+3], 0Fh
0x1800098e9  jz      short loc_1800098FD
0x1800098eb  movzx   eax, byte ptr [rcx+rax+3]
0x1800098f0  mov     ecx, 0FFFFFFF0h
0x1800098f5  and     rax, rcx
0x1800098f8  add     rax, r10
0x1800098fb  jmp     short loc_180009900
0x1800098fd  mov     rax, r10
0x180009900  xor     rdx, rax
0x180009903  mov     rcx, rdx; StackCookie
0x180009906  jmp     __security_check_cookie
```
