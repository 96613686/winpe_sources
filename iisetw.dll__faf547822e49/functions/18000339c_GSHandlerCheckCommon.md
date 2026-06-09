# __GSHandlerCheckCommon

- ea: `0x18000339c`
- end: `0x1800033ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003378`

## callees

- `0x18000339c`
- `0x180003430`

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
0x18000339c  mov     r10, rcx
0x18000339f  mov     r11, rdx
0x1800033a2  mov     ecx, [r8]
0x1800033a5  and     ecx, 0FFFFFFF8h
0x1800033a8  test    byte ptr [r8], 4
0x1800033ac  jz      short loc_1800033C3
0x1800033ae  mov     eax, [r8+8]
0x1800033b2  movsxd  r9, dword ptr [r8+4]
0x1800033b6  neg     eax
0x1800033b8  movsxd  rdx, eax
0x1800033bb  add     r9, r10
0x1800033be  and     r9, rdx
0x1800033c1  jmp     short loc_1800033C6
0x1800033c3  mov     r9, r10
0x1800033c6  movsxd  rax, ecx
0x1800033c9  mov     rdx, [rax+r9]
0x1800033cd  mov     rax, [r11+10h]
0x1800033d1  mov     ecx, [rax+8]
0x1800033d4  mov     rax, [r11+8]
0x1800033d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800033dd  jz      short loc_1800033F1
0x1800033df  movzx   eax, byte ptr [rcx+rax+3]
0x1800033e4  mov     ecx, 0FFFFFFF0h
0x1800033e9  and     rax, rcx
0x1800033ec  add     rax, r10
0x1800033ef  jmp     short loc_1800033F4
0x1800033f1  mov     rax, r10
0x1800033f4  xor     rdx, rax
0x1800033f7  mov     rcx, rdx; StackCookie
0x1800033fa  jmp     __security_check_cookie
```
