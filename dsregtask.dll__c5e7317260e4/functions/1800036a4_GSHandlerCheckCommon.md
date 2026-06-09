# __GSHandlerCheckCommon

- ea: `0x1800036a4`
- end: `0x180003707`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003680`

## callees

- `0x180001460`
- `0x1800036a4`

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
0x1800036a4  mov     r10, rcx
0x1800036a7  mov     r11, rdx
0x1800036aa  mov     ecx, [r8]
0x1800036ad  and     ecx, 0FFFFFFF8h
0x1800036b0  test    byte ptr [r8], 4
0x1800036b4  jz      short loc_1800036CB
0x1800036b6  mov     eax, [r8+8]
0x1800036ba  movsxd  r9, dword ptr [r8+4]
0x1800036be  neg     eax
0x1800036c0  movsxd  rdx, eax
0x1800036c3  add     r9, r10
0x1800036c6  and     r9, rdx
0x1800036c9  jmp     short loc_1800036CE
0x1800036cb  mov     r9, r10
0x1800036ce  movsxd  rax, ecx
0x1800036d1  mov     rdx, [rax+r9]
0x1800036d5  mov     rax, [r11+10h]
0x1800036d9  mov     ecx, [rax+8]
0x1800036dc  mov     rax, [r11+8]
0x1800036e0  test    byte ptr [rcx+rax+3], 0Fh
0x1800036e5  jz      short loc_1800036F9
0x1800036e7  movzx   eax, byte ptr [rcx+rax+3]
0x1800036ec  mov     ecx, 0FFFFFFF0h
0x1800036f1  and     rax, rcx
0x1800036f4  add     rax, r10
0x1800036f7  jmp     short loc_1800036FC
0x1800036f9  mov     rax, r10
0x1800036fc  xor     rdx, rax
0x1800036ff  mov     rcx, rdx; StackCookie
0x180003702  jmp     __security_check_cookie
```
