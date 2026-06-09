# __GSHandlerCheckCommon

- ea: `0x180005f6c`
- end: `0x180005fcf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f48`

## callees

- `0x180005f6c`
- `0x180005ff0`

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
0x180005f6c  mov     r10, rcx
0x180005f6f  mov     r11, rdx
0x180005f72  mov     ecx, [r8]
0x180005f75  and     ecx, 0FFFFFFF8h
0x180005f78  test    byte ptr [r8], 4
0x180005f7c  jz      short loc_180005F93
0x180005f7e  mov     eax, [r8+8]
0x180005f82  movsxd  r9, dword ptr [r8+4]
0x180005f86  neg     eax
0x180005f88  movsxd  rdx, eax
0x180005f8b  add     r9, r10
0x180005f8e  and     r9, rdx
0x180005f91  jmp     short loc_180005F96
0x180005f93  mov     r9, r10
0x180005f96  movsxd  rax, ecx
0x180005f99  mov     rdx, [rax+r9]
0x180005f9d  mov     rax, [r11+10h]
0x180005fa1  mov     ecx, [rax+8]
0x180005fa4  mov     rax, [r11+8]
0x180005fa8  test    byte ptr [rcx+rax+3], 0Fh
0x180005fad  jz      short loc_180005FC1
0x180005faf  movzx   eax, byte ptr [rcx+rax+3]
0x180005fb4  mov     ecx, 0FFFFFFF0h
0x180005fb9  and     rax, rcx
0x180005fbc  add     rax, r10
0x180005fbf  jmp     short loc_180005FC4
0x180005fc1  mov     rax, r10
0x180005fc4  xor     rdx, rax
0x180005fc7  mov     rcx, rdx; StackCookie
0x180005fca  jmp     __security_check_cookie
```
