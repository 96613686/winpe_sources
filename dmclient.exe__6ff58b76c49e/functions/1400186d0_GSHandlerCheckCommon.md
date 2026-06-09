# __GSHandlerCheckCommon

- ea: `0x1400186d0`
- end: `0x140018733`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400186ac`
- `0x14001873c`

## callees

- `0x1400186d0`
- `0x1400187e0`

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
0x1400186d0  mov     r10, rcx
0x1400186d3  mov     r11, rdx
0x1400186d6  mov     ecx, [r8]
0x1400186d9  and     ecx, 0FFFFFFF8h
0x1400186dc  test    byte ptr [r8], 4
0x1400186e0  jz      short loc_1400186F7
0x1400186e2  mov     eax, [r8+8]
0x1400186e6  movsxd  r9, dword ptr [r8+4]
0x1400186ea  neg     eax
0x1400186ec  movsxd  rdx, eax
0x1400186ef  add     r9, r10
0x1400186f2  and     r9, rdx
0x1400186f5  jmp     short loc_1400186FA
0x1400186f7  mov     r9, r10
0x1400186fa  movsxd  rax, ecx
0x1400186fd  mov     rdx, [rax+r9]
0x140018701  mov     rax, [r11+10h]
0x140018705  mov     ecx, [rax+8]
0x140018708  mov     rax, [r11+8]
0x14001870c  test    byte ptr [rcx+rax+3], 0Fh
0x140018711  jz      short loc_140018725
0x140018713  movzx   eax, byte ptr [rcx+rax+3]
0x140018718  mov     ecx, 0FFFFFFF0h
0x14001871d  and     rax, rcx
0x140018720  add     rax, r10
0x140018723  jmp     short loc_140018728
0x140018725  mov     rax, r10
0x140018728  xor     rdx, rax
0x14001872b  mov     rcx, rdx; StackCookie
0x14001872e  jmp     __security_check_cookie
```
