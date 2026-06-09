# __GSHandlerCheckCommon

- ea: `0x180011a74`
- end: `0x180011ad7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011a50`
- `0x180011ae0`

## callees

- `0x180011a74`
- `0x180011ba0`

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
0x180011a74  mov     r10, rcx
0x180011a77  mov     r11, rdx
0x180011a7a  mov     ecx, [r8]
0x180011a7d  and     ecx, 0FFFFFFF8h
0x180011a80  test    byte ptr [r8], 4
0x180011a84  jz      short loc_180011A9B
0x180011a86  mov     eax, [r8+8]
0x180011a8a  movsxd  r9, dword ptr [r8+4]
0x180011a8e  neg     eax
0x180011a90  movsxd  rdx, eax
0x180011a93  add     r9, r10
0x180011a96  and     r9, rdx
0x180011a99  jmp     short loc_180011A9E
0x180011a9b  mov     r9, r10
0x180011a9e  movsxd  rax, ecx
0x180011aa1  mov     rdx, [rax+r9]
0x180011aa5  mov     rax, [r11+10h]
0x180011aa9  mov     ecx, [rax+8]
0x180011aac  mov     rax, [r11+8]
0x180011ab0  test    byte ptr [rcx+rax+3], 0Fh
0x180011ab5  jz      short loc_180011AC9
0x180011ab7  movzx   eax, byte ptr [rcx+rax+3]
0x180011abc  mov     ecx, 0FFFFFFF0h
0x180011ac1  and     rax, rcx
0x180011ac4  add     rax, r10
0x180011ac7  jmp     short loc_180011ACC
0x180011ac9  mov     rax, r10
0x180011acc  xor     rdx, rax
0x180011acf  mov     rcx, rdx; StackCookie
0x180011ad2  jmp     __security_check_cookie
```
