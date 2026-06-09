# __GSHandlerCheckCommon

- ea: `0x180002c84`
- end: `0x180002ce7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002c60`
- `0x180002cf0`

## callees

- `0x180002c84`
- `0x180002da0`

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
0x180002c84  mov     r10, rcx
0x180002c87  mov     r11, rdx
0x180002c8a  mov     ecx, [r8]
0x180002c8d  and     ecx, 0FFFFFFF8h
0x180002c90  test    byte ptr [r8], 4
0x180002c94  jz      short loc_180002CAB
0x180002c96  mov     eax, [r8+8]
0x180002c9a  movsxd  r9, dword ptr [r8+4]
0x180002c9e  neg     eax
0x180002ca0  movsxd  rdx, eax
0x180002ca3  add     r9, r10
0x180002ca6  and     r9, rdx
0x180002ca9  jmp     short loc_180002CAE
0x180002cab  mov     r9, r10
0x180002cae  movsxd  rax, ecx
0x180002cb1  mov     rdx, [rax+r9]
0x180002cb5  mov     rax, [r11+10h]
0x180002cb9  mov     ecx, [rax+8]
0x180002cbc  mov     rax, [r11+8]
0x180002cc0  test    byte ptr [rcx+rax+3], 0Fh
0x180002cc5  jz      short loc_180002CD9
0x180002cc7  movzx   eax, byte ptr [rcx+rax+3]
0x180002ccc  mov     ecx, 0FFFFFFF0h
0x180002cd1  and     rax, rcx
0x180002cd4  add     rax, r10
0x180002cd7  jmp     short loc_180002CDC
0x180002cd9  mov     rax, r10
0x180002cdc  xor     rdx, rax
0x180002cdf  mov     rcx, rdx; StackCookie
0x180002ce2  jmp     __security_check_cookie
```
