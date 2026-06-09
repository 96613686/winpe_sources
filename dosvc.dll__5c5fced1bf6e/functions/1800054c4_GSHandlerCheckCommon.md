# __GSHandlerCheckCommon

- ea: `0x1800054c4`
- end: `0x180005527`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800054a0`
- `0x18000a60c`

## callees

- `0x180005020`
- `0x1800054c4`

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
0x1800054c4  mov     r10, rcx
0x1800054c7  mov     r11, rdx
0x1800054ca  mov     ecx, [r8]
0x1800054cd  and     ecx, 0FFFFFFF8h
0x1800054d0  test    byte ptr [r8], 4
0x1800054d4  jz      short loc_1800054EB
0x1800054d6  mov     eax, [r8+8]
0x1800054da  movsxd  r9, dword ptr [r8+4]
0x1800054de  neg     eax
0x1800054e0  movsxd  rdx, eax
0x1800054e3  add     r9, r10
0x1800054e6  and     r9, rdx
0x1800054e9  jmp     short loc_1800054EE
0x1800054eb  mov     r9, r10
0x1800054ee  movsxd  rax, ecx
0x1800054f1  mov     rdx, [rax+r9]
0x1800054f5  mov     rax, [r11+10h]
0x1800054f9  mov     ecx, [rax+8]
0x1800054fc  mov     rax, [r11+8]
0x180005500  test    byte ptr [rcx+rax+3], 0Fh
0x180005505  jz      short loc_180005519
0x180005507  movzx   eax, byte ptr [rcx+rax+3]
0x18000550c  mov     ecx, 0FFFFFFF0h
0x180005511  and     rax, rcx
0x180005514  add     rax, r10
0x180005517  jmp     short loc_18000551C
0x180005519  mov     rax, r10
0x18000551c  xor     rdx, rax
0x18000551f  mov     rcx, rdx; StackCookie
0x180005522  jmp     __security_check_cookie
```
