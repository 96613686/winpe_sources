# __GSHandlerCheckCommon

- ea: `0x18000309c`
- end: `0x1800030ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003078`
- `0x1800189cc`

## callees

- `0x18000309c`
- `0x180018a80`

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
0x18000309c  mov     r10, rcx
0x18000309f  mov     r11, rdx
0x1800030a2  mov     ecx, [r8]
0x1800030a5  and     ecx, 0FFFFFFF8h
0x1800030a8  test    byte ptr [r8], 4
0x1800030ac  jz      short loc_1800030C3
0x1800030ae  mov     eax, [r8+8]
0x1800030b2  movsxd  r9, dword ptr [r8+4]
0x1800030b6  neg     eax
0x1800030b8  movsxd  rdx, eax
0x1800030bb  add     r9, r10
0x1800030be  and     r9, rdx
0x1800030c1  jmp     short loc_1800030C6
0x1800030c3  mov     r9, r10
0x1800030c6  movsxd  rax, ecx
0x1800030c9  mov     rdx, [rax+r9]
0x1800030cd  mov     rax, [r11+10h]
0x1800030d1  mov     ecx, [rax+8]
0x1800030d4  mov     rax, [r11+8]
0x1800030d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800030dd  jz      short loc_1800030F1
0x1800030df  movzx   eax, byte ptr [rcx+rax+3]
0x1800030e4  mov     ecx, 0FFFFFFF0h
0x1800030e9  and     rax, rcx
0x1800030ec  add     rax, r10
0x1800030ef  jmp     short loc_1800030F4
0x1800030f1  mov     rax, r10
0x1800030f4  xor     rdx, rax
0x1800030f7  mov     rcx, rdx; StackCookie
0x1800030fa  jmp     __security_check_cookie
```
