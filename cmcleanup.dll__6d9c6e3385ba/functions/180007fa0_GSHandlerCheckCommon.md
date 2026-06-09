# __GSHandlerCheckCommon

- ea: `0x180007fa0`
- end: `0x180008003`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f7c`
- `0x18000800c`

## callees

- `0x180001510`
- `0x180007fa0`

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
0x180007fa0  mov     r10, rcx
0x180007fa3  mov     r11, rdx
0x180007fa6  mov     ecx, [r8]
0x180007fa9  and     ecx, 0FFFFFFF8h
0x180007fac  test    byte ptr [r8], 4
0x180007fb0  jz      short loc_180007FC7
0x180007fb2  mov     eax, [r8+8]
0x180007fb6  movsxd  r9, dword ptr [r8+4]
0x180007fba  neg     eax
0x180007fbc  movsxd  rdx, eax
0x180007fbf  add     r9, r10
0x180007fc2  and     r9, rdx
0x180007fc5  jmp     short loc_180007FCA
0x180007fc7  mov     r9, r10
0x180007fca  movsxd  rax, ecx
0x180007fcd  mov     rdx, [rax+r9]
0x180007fd1  mov     rax, [r11+10h]
0x180007fd5  mov     ecx, [rax+8]
0x180007fd8  mov     rax, [r11+8]
0x180007fdc  test    byte ptr [rcx+rax+3], 0Fh
0x180007fe1  jz      short loc_180007FF5
0x180007fe3  movzx   eax, byte ptr [rcx+rax+3]
0x180007fe8  mov     ecx, 0FFFFFFF0h
0x180007fed  and     rax, rcx
0x180007ff0  add     rax, r10
0x180007ff3  jmp     short loc_180007FF8
0x180007ff5  mov     rax, r10
0x180007ff8  xor     rdx, rax
0x180007ffb  mov     rcx, rdx; StackCookie
0x180007ffe  jmp     __security_check_cookie
```
