# __GSHandlerCheckCommon

- ea: `0x1800038ac`
- end: `0x18000390f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003888`
- `0x18002a028`
- `0x18002a090`

## callees

- `0x1800038ac`
- `0x18002a150`

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
0x1800038ac  mov     r10, rcx
0x1800038af  mov     r11, rdx
0x1800038b2  mov     ecx, [r8]
0x1800038b5  and     ecx, 0FFFFFFF8h
0x1800038b8  test    byte ptr [r8], 4
0x1800038bc  jz      short loc_1800038D3
0x1800038be  mov     eax, [r8+8]
0x1800038c2  movsxd  r9, dword ptr [r8+4]
0x1800038c6  neg     eax
0x1800038c8  movsxd  rdx, eax
0x1800038cb  add     r9, r10
0x1800038ce  and     r9, rdx
0x1800038d1  jmp     short loc_1800038D6
0x1800038d3  mov     r9, r10
0x1800038d6  movsxd  rax, ecx
0x1800038d9  mov     rdx, [rax+r9]
0x1800038dd  mov     rax, [r11+10h]
0x1800038e1  mov     ecx, [rax+8]
0x1800038e4  mov     rax, [r11+8]
0x1800038e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800038ed  jz      short loc_180003901
0x1800038ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800038f4  mov     ecx, 0FFFFFFF0h
0x1800038f9  and     rax, rcx
0x1800038fc  add     rax, r10
0x1800038ff  jmp     short loc_180003904
0x180003901  mov     rax, r10
0x180003904  xor     rdx, rax
0x180003907  mov     rcx, rdx; StackCookie
0x18000390a  jmp     __security_check_cookie
```
