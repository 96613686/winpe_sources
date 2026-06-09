# __GSHandlerCheckCommon

- ea: `0x18001c944`
- end: `0x18001c9a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c920`
- `0x18001c9b0`

## callees

- `0x18001c944`
- `0x18001ca70`

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
0x18001c944  mov     r10, rcx
0x18001c947  mov     r11, rdx
0x18001c94a  mov     ecx, [r8]
0x18001c94d  and     ecx, 0FFFFFFF8h
0x18001c950  test    byte ptr [r8], 4
0x18001c954  jz      short loc_18001C96B
0x18001c956  mov     eax, [r8+8]
0x18001c95a  movsxd  r9, dword ptr [r8+4]
0x18001c95e  neg     eax
0x18001c960  movsxd  rdx, eax
0x18001c963  add     r9, r10
0x18001c966  and     r9, rdx
0x18001c969  jmp     short loc_18001C96E
0x18001c96b  mov     r9, r10
0x18001c96e  movsxd  rax, ecx
0x18001c971  mov     rdx, [rax+r9]
0x18001c975  mov     rax, [r11+10h]
0x18001c979  mov     ecx, [rax+8]
0x18001c97c  mov     rax, [r11+8]
0x18001c980  test    byte ptr [rcx+rax+3], 0Fh
0x18001c985  jz      short loc_18001C999
0x18001c987  movzx   eax, byte ptr [rcx+rax+3]
0x18001c98c  mov     ecx, 0FFFFFFF0h
0x18001c991  and     rax, rcx
0x18001c994  add     rax, r10
0x18001c997  jmp     short loc_18001C99C
0x18001c999  mov     rax, r10
0x18001c99c  xor     rdx, rax
0x18001c99f  mov     rcx, rdx; StackCookie
0x18001c9a2  jmp     __security_check_cookie
```
