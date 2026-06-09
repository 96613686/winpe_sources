# __GSHandlerCheckCommon

- ea: `0x140018288`
- end: `0x1400182eb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018264`

## callees

- `0x140018288`
- `0x140018350`

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
0x140018288  mov     r10, rcx
0x14001828b  mov     r11, rdx
0x14001828e  mov     ecx, [r8]
0x140018291  and     ecx, 0FFFFFFF8h
0x140018294  test    byte ptr [r8], 4
0x140018298  jz      short loc_1400182AF
0x14001829a  mov     eax, [r8+8]
0x14001829e  movsxd  r9, dword ptr [r8+4]
0x1400182a2  neg     eax
0x1400182a4  movsxd  rdx, eax
0x1400182a7  add     r9, r10
0x1400182aa  and     r9, rdx
0x1400182ad  jmp     short loc_1400182B2
0x1400182af  mov     r9, r10
0x1400182b2  movsxd  rax, ecx
0x1400182b5  mov     rdx, [rax+r9]
0x1400182b9  mov     rax, [r11+10h]
0x1400182bd  mov     ecx, [rax+8]
0x1400182c0  mov     rax, [r11+8]
0x1400182c4  test    byte ptr [rcx+rax+3], 0Fh
0x1400182c9  jz      short loc_1400182DD
0x1400182cb  movzx   eax, byte ptr [rcx+rax+3]
0x1400182d0  mov     ecx, 0FFFFFFF0h
0x1400182d5  and     rax, rcx
0x1400182d8  add     rax, r10
0x1400182db  jmp     short loc_1400182E0
0x1400182dd  mov     rax, r10
0x1400182e0  xor     rdx, rax
0x1400182e3  mov     rcx, rdx; StackCookie
0x1400182e6  jmp     __security_check_cookie
```
