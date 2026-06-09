# __GSHandlerCheckCommon

- ea: `0x180004fb0`
- end: `0x180005013`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f8c`

## callees

- `0x180001400`
- `0x180004fb0`

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
0x180004fb0  mov     r10, rcx
0x180004fb3  mov     r11, rdx
0x180004fb6  mov     ecx, [r8]
0x180004fb9  and     ecx, 0FFFFFFF8h
0x180004fbc  test    byte ptr [r8], 4
0x180004fc0  jz      short loc_180004FD7
0x180004fc2  mov     eax, [r8+8]
0x180004fc6  movsxd  r9, dword ptr [r8+4]
0x180004fca  neg     eax
0x180004fcc  movsxd  rdx, eax
0x180004fcf  add     r9, r10
0x180004fd2  and     r9, rdx
0x180004fd5  jmp     short loc_180004FDA
0x180004fd7  mov     r9, r10
0x180004fda  movsxd  rax, ecx
0x180004fdd  mov     rdx, [rax+r9]
0x180004fe1  mov     rax, [r11+10h]
0x180004fe5  mov     ecx, [rax+8]
0x180004fe8  mov     rax, [r11+8]
0x180004fec  test    byte ptr [rcx+rax+3], 0Fh
0x180004ff1  jz      short loc_180005005
0x180004ff3  movzx   eax, byte ptr [rcx+rax+3]
0x180004ff8  mov     ecx, 0FFFFFFF0h
0x180004ffd  and     rax, rcx
0x180005000  add     rax, r10
0x180005003  jmp     short loc_180005008
0x180005005  mov     rax, r10
0x180005008  xor     rdx, rax
0x18000500b  mov     rcx, rdx; StackCookie
0x18000500e  jmp     __security_check_cookie
```
