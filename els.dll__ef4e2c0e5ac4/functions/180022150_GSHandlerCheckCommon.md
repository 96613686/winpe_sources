# __GSHandlerCheckCommon

- ea: `0x180022150`
- end: `0x1800221b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002212c`
- `0x1800221bc`
- `0x180022224`

## callees

- `0x180022150`
- `0x1800222d0`

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
0x180022150  mov     r10, rcx
0x180022153  mov     r11, rdx
0x180022156  mov     ecx, [r8]
0x180022159  and     ecx, 0FFFFFFF8h
0x18002215c  test    byte ptr [r8], 4
0x180022160  jz      short loc_180022177
0x180022162  mov     eax, [r8+8]
0x180022166  movsxd  r9, dword ptr [r8+4]
0x18002216a  neg     eax
0x18002216c  movsxd  rdx, eax
0x18002216f  add     r9, r10
0x180022172  and     r9, rdx
0x180022175  jmp     short loc_18002217A
0x180022177  mov     r9, r10
0x18002217a  movsxd  rax, ecx
0x18002217d  mov     rdx, [rax+r9]
0x180022181  mov     rax, [r11+10h]
0x180022185  mov     ecx, [rax+8]
0x180022188  mov     rax, [r11+8]
0x18002218c  test    byte ptr [rcx+rax+3], 0Fh
0x180022191  jz      short loc_1800221A5
0x180022193  movzx   eax, byte ptr [rcx+rax+3]
0x180022198  mov     ecx, 0FFFFFFF0h
0x18002219d  and     rax, rcx
0x1800221a0  add     rax, r10
0x1800221a3  jmp     short loc_1800221A8
0x1800221a5  mov     rax, r10
0x1800221a8  xor     rdx, rax
0x1800221ab  mov     rcx, rdx; StackCookie
0x1800221ae  jmp     __security_check_cookie
```
