# __GSHandlerCheckCommon

- ea: `0x18000ddd8`
- end: `0x18000de3b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ddb4`
- `0x18000de44`

## callees

- `0x180001780`
- `0x18000ddd8`

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
0x18000ddd8  mov     r10, rcx
0x18000dddb  mov     r11, rdx
0x18000ddde  mov     ecx, [r8]
0x18000dde1  and     ecx, 0FFFFFFF8h
0x18000dde4  test    byte ptr [r8], 4
0x18000dde8  jz      short loc_18000DDFF
0x18000ddea  mov     eax, [r8+8]
0x18000ddee  movsxd  r9, dword ptr [r8+4]
0x18000ddf2  neg     eax
0x18000ddf4  movsxd  rdx, eax
0x18000ddf7  add     r9, r10
0x18000ddfa  and     r9, rdx
0x18000ddfd  jmp     short loc_18000DE02
0x18000ddff  mov     r9, r10
0x18000de02  movsxd  rax, ecx
0x18000de05  mov     rdx, [rax+r9]
0x18000de09  mov     rax, [r11+10h]
0x18000de0d  mov     ecx, [rax+8]
0x18000de10  mov     rax, [r11+8]
0x18000de14  test    byte ptr [rcx+rax+3], 0Fh
0x18000de19  jz      short loc_18000DE2D
0x18000de1b  movzx   eax, byte ptr [rcx+rax+3]
0x18000de20  mov     ecx, 0FFFFFFF0h
0x18000de25  and     rax, rcx
0x18000de28  add     rax, r10
0x18000de2b  jmp     short loc_18000DE30
0x18000de2d  mov     rax, r10
0x18000de30  xor     rdx, rax
0x18000de33  mov     rcx, rdx; StackCookie
0x18000de36  jmp     __security_check_cookie
```
