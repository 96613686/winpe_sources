# __GSHandlerCheckCommon

- ea: `0x180001590`
- end: `0x1800015f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000156c`

## callees

- `0x180001190`
- `0x180001590`

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
0x180001590  mov     r10, rcx
0x180001593  mov     r11, rdx
0x180001596  mov     ecx, [r8]
0x180001599  and     ecx, 0FFFFFFF8h
0x18000159c  test    byte ptr [r8], 4
0x1800015a0  jz      short loc_1800015B7
0x1800015a2  mov     eax, [r8+8]
0x1800015a6  movsxd  r9, dword ptr [r8+4]
0x1800015aa  neg     eax
0x1800015ac  movsxd  rdx, eax
0x1800015af  add     r9, r10
0x1800015b2  and     r9, rdx
0x1800015b5  jmp     short loc_1800015BA
0x1800015b7  mov     r9, r10
0x1800015ba  movsxd  rax, ecx
0x1800015bd  mov     rdx, [rax+r9]
0x1800015c1  mov     rax, [r11+10h]
0x1800015c5  mov     ecx, [rax+8]
0x1800015c8  mov     rax, [r11+8]
0x1800015cc  test    byte ptr [rcx+rax+3], 0Fh
0x1800015d1  jz      short loc_1800015E5
0x1800015d3  movzx   eax, byte ptr [rcx+rax+3]
0x1800015d8  mov     ecx, 0FFFFFFF0h
0x1800015dd  and     rax, rcx
0x1800015e0  add     rax, r10
0x1800015e3  jmp     short loc_1800015E8
0x1800015e5  mov     rax, r10
0x1800015e8  xor     rdx, rax
0x1800015eb  mov     rcx, rdx; StackCookie
0x1800015ee  jmp     __security_check_cookie
```
