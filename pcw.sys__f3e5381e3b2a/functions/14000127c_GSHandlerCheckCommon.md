# __GSHandlerCheckCommon

- ea: `0x14000127c`
- end: `0x1400012ec`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001258`
- `0x1400012f4`

## callees

- `0x14000127c`
- `0x140001370`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14000127c  sub     rsp, 28h
0x140001280  mov     eax, [r8]
0x140001283  mov     r10, rcx
0x140001286  mov     ecx, eax
0x140001288  mov     r11, rdx
0x14000128b  and     ecx, 0FFFFFFF8h
0x14000128e  test    al, 4
0x140001290  jz      short loc_1400012A7
0x140001292  mov     eax, [r8+8]
0x140001296  movsxd  r9, dword ptr [r8+4]
0x14000129a  neg     eax
0x14000129c  movsxd  rdx, eax
0x14000129f  add     r9, r10
0x1400012a2  and     r9, rdx
0x1400012a5  jmp     short loc_1400012AA
0x1400012a7  mov     r9, r10
0x1400012aa  movsxd  rax, ecx
0x1400012ad  mov     rdx, [rax+r9]
0x1400012b1  mov     rax, [r11+10h]
0x1400012b5  mov     ecx, [rax+8]
0x1400012b8  mov     rax, [r11+8]
0x1400012bc  movzx   r8d, byte ptr [rcx+rax+3]
0x1400012c2  test    r8b, 0Fh
0x1400012c6  jz      short loc_1400012D8
0x1400012c8  mov     eax, r8d
0x1400012cb  mov     ecx, 0FFFFFFF0h
0x1400012d0  and     rax, rcx
0x1400012d3  add     rax, r10
0x1400012d6  jmp     short loc_1400012DB
0x1400012d8  mov     rax, r10
0x1400012db  xor     rdx, rax
0x1400012de  mov     rcx, rdx; StackCookie
0x1400012e1  call    __security_check_cookie
0x1400012e6  add     rsp, 28h
0x1400012ea  retn
```
