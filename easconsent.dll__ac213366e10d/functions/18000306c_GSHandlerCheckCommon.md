# __GSHandlerCheckCommon

- ea: `0x18000306c`
- end: `0x1800030cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003048`

## callees

- `0x18000306c`
- `0x180003100`

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
0x18000306c  mov     r10, rcx
0x18000306f  mov     r11, rdx
0x180003072  mov     ecx, [r8]
0x180003075  and     ecx, 0FFFFFFF8h
0x180003078  test    byte ptr [r8], 4
0x18000307c  jz      short loc_180003093
0x18000307e  mov     eax, [r8+8]
0x180003082  movsxd  r9, dword ptr [r8+4]
0x180003086  neg     eax
0x180003088  movsxd  rdx, eax
0x18000308b  add     r9, r10
0x18000308e  and     r9, rdx
0x180003091  jmp     short loc_180003096
0x180003093  mov     r9, r10
0x180003096  movsxd  rax, ecx
0x180003099  mov     rdx, [rax+r9]
0x18000309d  mov     rax, [r11+10h]
0x1800030a1  mov     ecx, [rax+8]
0x1800030a4  mov     rax, [r11+8]
0x1800030a8  test    byte ptr [rcx+rax+3], 0Fh
0x1800030ad  jz      short loc_1800030C1
0x1800030af  movzx   eax, byte ptr [rcx+rax+3]
0x1800030b4  mov     ecx, 0FFFFFFF0h
0x1800030b9  and     rax, rcx
0x1800030bc  add     rax, r10
0x1800030bf  jmp     short loc_1800030C4
0x1800030c1  mov     rax, r10
0x1800030c4  xor     rdx, rax
0x1800030c7  mov     rcx, rdx; StackCookie
0x1800030ca  jmp     __security_check_cookie
```
