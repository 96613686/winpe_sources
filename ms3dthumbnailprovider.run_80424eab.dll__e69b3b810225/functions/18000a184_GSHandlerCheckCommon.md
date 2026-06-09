# __GSHandlerCheckCommon

- ea: `0x18000a184`
- end: `0x18000a1e7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a160`
- `0x18000a1f0`

## callees

- `0x180001ef0`
- `0x18000a184`

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
0x18000a184  mov     r10, rcx
0x18000a187  mov     r11, rdx
0x18000a18a  mov     ecx, [r8]
0x18000a18d  and     ecx, 0FFFFFFF8h
0x18000a190  test    byte ptr [r8], 4
0x18000a194  jz      short loc_18000A1AB
0x18000a196  mov     eax, [r8+8]
0x18000a19a  movsxd  r9, dword ptr [r8+4]
0x18000a19e  neg     eax
0x18000a1a0  movsxd  rdx, eax
0x18000a1a3  add     r9, r10
0x18000a1a6  and     r9, rdx
0x18000a1a9  jmp     short loc_18000A1AE
0x18000a1ab  mov     r9, r10
0x18000a1ae  movsxd  rax, ecx
0x18000a1b1  mov     rdx, [rax+r9]
0x18000a1b5  mov     rax, [r11+10h]
0x18000a1b9  mov     ecx, [rax+8]
0x18000a1bc  mov     rax, [r11+8]
0x18000a1c0  test    byte ptr [rcx+rax+3], 0Fh
0x18000a1c5  jz      short loc_18000A1D9
0x18000a1c7  movzx   eax, byte ptr [rcx+rax+3]
0x18000a1cc  mov     ecx, 0FFFFFFF0h
0x18000a1d1  and     rax, rcx
0x18000a1d4  add     rax, r10
0x18000a1d7  jmp     short loc_18000A1DC
0x18000a1d9  mov     rax, r10
0x18000a1dc  xor     rdx, rax
0x18000a1df  mov     rcx, rdx; StackCookie
0x18000a1e2  jmp     __security_check_cookie
```
