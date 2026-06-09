# __GSHandlerCheckCommon

- ea: `0x1800026ac`
- end: `0x18000270f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002688`

## callees

- `0x1800026ac`
- `0x180012e00`

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
0x1800026ac  mov     r10, rcx
0x1800026af  mov     r11, rdx
0x1800026b2  mov     ecx, [r8]
0x1800026b5  and     ecx, 0FFFFFFF8h
0x1800026b8  test    byte ptr [r8], 4
0x1800026bc  jz      short loc_1800026D3
0x1800026be  mov     eax, [r8+8]
0x1800026c2  movsxd  r9, dword ptr [r8+4]
0x1800026c6  neg     eax
0x1800026c8  movsxd  rdx, eax
0x1800026cb  add     r9, r10
0x1800026ce  and     r9, rdx
0x1800026d1  jmp     short loc_1800026D6
0x1800026d3  mov     r9, r10
0x1800026d6  movsxd  rax, ecx
0x1800026d9  mov     rdx, [rax+r9]
0x1800026dd  mov     rax, [r11+10h]
0x1800026e1  mov     ecx, [rax+8]
0x1800026e4  mov     rax, [r11+8]
0x1800026e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800026ed  jz      short loc_180002701
0x1800026ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800026f4  mov     ecx, 0FFFFFFF0h
0x1800026f9  and     rax, rcx
0x1800026fc  add     rax, r10
0x1800026ff  jmp     short loc_180002704
0x180002701  mov     rax, r10
0x180002704  xor     rdx, rax
0x180002707  mov     rcx, rdx; StackCookie
0x18000270a  jmp     __security_check_cookie
```
