# __GSHandlerCheckCommon

- ea: `0x1800337c0`
- end: `0x180033823`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003379c`
- `0x180033ea8`

## callees

- `0x1800337c0`
- `0x180079760`

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
0x1800337c0  mov     r10, rcx
0x1800337c3  mov     r11, rdx
0x1800337c6  mov     ecx, [r8]
0x1800337c9  and     ecx, 0FFFFFFF8h
0x1800337cc  test    byte ptr [r8], 4
0x1800337d0  jz      short loc_1800337E7
0x1800337d2  mov     eax, [r8+8]
0x1800337d6  movsxd  r9, dword ptr [r8+4]
0x1800337da  neg     eax
0x1800337dc  movsxd  rdx, eax
0x1800337df  add     r9, r10
0x1800337e2  and     r9, rdx
0x1800337e5  jmp     short loc_1800337EA
0x1800337e7  mov     r9, r10
0x1800337ea  movsxd  rax, ecx
0x1800337ed  mov     rdx, [rax+r9]
0x1800337f1  mov     rax, [r11+10h]
0x1800337f5  mov     ecx, [rax+8]
0x1800337f8  mov     rax, [r11+8]
0x1800337fc  test    byte ptr [rcx+rax+3], 0Fh
0x180033801  jz      short loc_180033815
0x180033803  movzx   eax, byte ptr [rcx+rax+3]
0x180033808  mov     ecx, 0FFFFFFF0h
0x18003380d  and     rax, rcx
0x180033810  add     rax, r10
0x180033813  jmp     short loc_180033818
0x180033815  mov     rax, r10
0x180033818  xor     rdx, rax
0x18003381b  mov     rcx, rdx; StackCookie
0x18003381e  jmp     __security_check_cookie
```
