# __GSHandlerCheckCommon

- ea: `0x1800083ac`
- end: `0x18000840f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008388`

## callees

- `0x180004c40`
- `0x1800083ac`

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
0x1800083ac  mov     r10, rcx
0x1800083af  mov     r11, rdx
0x1800083b2  mov     ecx, [r8]
0x1800083b5  and     ecx, 0FFFFFFF8h
0x1800083b8  test    byte ptr [r8], 4
0x1800083bc  jz      short loc_1800083D3
0x1800083be  mov     eax, [r8+8]
0x1800083c2  movsxd  r9, dword ptr [r8+4]
0x1800083c6  neg     eax
0x1800083c8  movsxd  rdx, eax
0x1800083cb  add     r9, r10
0x1800083ce  and     r9, rdx
0x1800083d1  jmp     short loc_1800083D6
0x1800083d3  mov     r9, r10
0x1800083d6  movsxd  rax, ecx
0x1800083d9  mov     rdx, [rax+r9]
0x1800083dd  mov     rax, [r11+10h]
0x1800083e1  mov     ecx, [rax+8]
0x1800083e4  mov     rax, [r11+8]
0x1800083e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800083ed  jz      short loc_180008401
0x1800083ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800083f4  mov     ecx, 0FFFFFFF0h
0x1800083f9  and     rax, rcx
0x1800083fc  add     rax, r10
0x1800083ff  jmp     short loc_180008404
0x180008401  mov     rax, r10
0x180008404  xor     rdx, rax
0x180008407  mov     rcx, rdx; StackCookie
0x18000840a  jmp     __security_check_cookie
```
