# __GSHandlerCheckCommon

- ea: `0x18001e4e0`
- end: `0x18001e543`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e4bc`
- `0x18001e54c`

## callees

- `0x180001460`
- `0x18001e4e0`

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
0x18001e4e0  mov     r10, rcx
0x18001e4e3  mov     r11, rdx
0x18001e4e6  mov     ecx, [r8]
0x18001e4e9  and     ecx, 0FFFFFFF8h
0x18001e4ec  test    byte ptr [r8], 4
0x18001e4f0  jz      short loc_18001E507
0x18001e4f2  mov     eax, [r8+8]
0x18001e4f6  movsxd  r9, dword ptr [r8+4]
0x18001e4fa  neg     eax
0x18001e4fc  movsxd  rdx, eax
0x18001e4ff  add     r9, r10
0x18001e502  and     r9, rdx
0x18001e505  jmp     short loc_18001E50A
0x18001e507  mov     r9, r10
0x18001e50a  movsxd  rax, ecx
0x18001e50d  mov     rdx, [rax+r9]
0x18001e511  mov     rax, [r11+10h]
0x18001e515  mov     ecx, [rax+8]
0x18001e518  mov     rax, [r11+8]
0x18001e51c  test    byte ptr [rcx+rax+3], 0Fh
0x18001e521  jz      short loc_18001E535
0x18001e523  movzx   eax, byte ptr [rcx+rax+3]
0x18001e528  mov     ecx, 0FFFFFFF0h
0x18001e52d  and     rax, rcx
0x18001e530  add     rax, r10
0x18001e533  jmp     short loc_18001E538
0x18001e535  mov     rax, r10
0x18001e538  xor     rdx, rax
0x18001e53b  mov     rcx, rdx; StackCookie
0x18001e53e  jmp     __security_check_cookie
```
