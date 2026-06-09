# __GSHandlerCheckCommon

- ea: `0x140005c1c`
- end: `0x140005c7f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005bf8`
- `0x140005c88`

## callees

- `0x140001460`
- `0x140005c1c`

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
0x140005c1c  mov     r10, rcx
0x140005c1f  mov     r11, rdx
0x140005c22  mov     ecx, [r8]
0x140005c25  and     ecx, 0FFFFFFF8h
0x140005c28  test    byte ptr [r8], 4
0x140005c2c  jz      short loc_140005C43
0x140005c2e  mov     eax, [r8+8]
0x140005c32  movsxd  r9, dword ptr [r8+4]
0x140005c36  neg     eax
0x140005c38  movsxd  rdx, eax
0x140005c3b  add     r9, r10
0x140005c3e  and     r9, rdx
0x140005c41  jmp     short loc_140005C46
0x140005c43  mov     r9, r10
0x140005c46  movsxd  rax, ecx
0x140005c49  mov     rdx, [rax+r9]
0x140005c4d  mov     rax, [r11+10h]
0x140005c51  mov     ecx, [rax+8]
0x140005c54  mov     rax, [r11+8]
0x140005c58  test    byte ptr [rcx+rax+3], 0Fh
0x140005c5d  jz      short loc_140005C71
0x140005c5f  movzx   eax, byte ptr [rcx+rax+3]
0x140005c64  mov     ecx, 0FFFFFFF0h
0x140005c69  and     rax, rcx
0x140005c6c  add     rax, r10
0x140005c6f  jmp     short loc_140005C74
0x140005c71  mov     rax, r10
0x140005c74  xor     rdx, rax
0x140005c77  mov     rcx, rdx; StackCookie
0x140005c7a  jmp     __security_check_cookie
```
