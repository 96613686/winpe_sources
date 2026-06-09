# __GSHandlerCheckCommon

- ea: `0x1800030c4`
- end: `0x180003127`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030a0`

## callees

- `0x1800030c4`
- `0x180003150`

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
0x1800030c4  mov     r10, rcx
0x1800030c7  mov     r11, rdx
0x1800030ca  mov     ecx, [r8]
0x1800030cd  and     ecx, 0FFFFFFF8h
0x1800030d0  test    byte ptr [r8], 4
0x1800030d4  jz      short loc_1800030EB
0x1800030d6  mov     eax, [r8+8]
0x1800030da  movsxd  r9, dword ptr [r8+4]
0x1800030de  neg     eax
0x1800030e0  movsxd  rdx, eax
0x1800030e3  add     r9, r10
0x1800030e6  and     r9, rdx
0x1800030e9  jmp     short loc_1800030EE
0x1800030eb  mov     r9, r10
0x1800030ee  movsxd  rax, ecx
0x1800030f1  mov     rdx, [rax+r9]
0x1800030f5  mov     rax, [r11+10h]
0x1800030f9  mov     ecx, [rax+8]
0x1800030fc  mov     rax, [r11+8]
0x180003100  test    byte ptr [rcx+rax+3], 0Fh
0x180003105  jz      short loc_180003119
0x180003107  movzx   eax, byte ptr [rcx+rax+3]
0x18000310c  mov     ecx, 0FFFFFFF0h
0x180003111  and     rax, rcx
0x180003114  add     rax, r10
0x180003117  jmp     short loc_18000311C
0x180003119  mov     rax, r10
0x18000311c  xor     rdx, rax
0x18000311f  mov     rcx, rdx; StackCookie
0x180003122  jmp     __security_check_cookie
```
