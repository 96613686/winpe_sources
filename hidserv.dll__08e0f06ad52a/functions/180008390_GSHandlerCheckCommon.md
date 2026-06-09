# __GSHandlerCheckCommon

- ea: `0x180008390`
- end: `0x1800083f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000836c`

## callees

- `0x180008390`
- `0x180008450`

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
0x180008390  mov     r10, rcx
0x180008393  mov     r11, rdx
0x180008396  mov     ecx, [r8]
0x180008399  and     ecx, 0FFFFFFF8h
0x18000839c  test    byte ptr [r8], 4
0x1800083a0  jz      short loc_1800083B7
0x1800083a2  mov     eax, [r8+8]
0x1800083a6  movsxd  r9, dword ptr [r8+4]
0x1800083aa  neg     eax
0x1800083ac  movsxd  rdx, eax
0x1800083af  add     r9, r10
0x1800083b2  and     r9, rdx
0x1800083b5  jmp     short loc_1800083BA
0x1800083b7  mov     r9, r10
0x1800083ba  movsxd  rax, ecx
0x1800083bd  mov     rdx, [rax+r9]
0x1800083c1  mov     rax, [r11+10h]
0x1800083c5  mov     ecx, [rax+8]
0x1800083c8  mov     rax, [r11+8]
0x1800083cc  test    byte ptr [rcx+rax+3], 0Fh
0x1800083d1  jz      short loc_1800083E5
0x1800083d3  movzx   eax, byte ptr [rcx+rax+3]
0x1800083d8  mov     ecx, 0FFFFFFF0h
0x1800083dd  and     rax, rcx
0x1800083e0  add     rax, r10
0x1800083e3  jmp     short loc_1800083E8
0x1800083e5  mov     rax, r10
0x1800083e8  xor     rdx, rax
0x1800083eb  mov     rcx, rdx; StackCookie
0x1800083ee  jmp     __security_check_cookie
```
