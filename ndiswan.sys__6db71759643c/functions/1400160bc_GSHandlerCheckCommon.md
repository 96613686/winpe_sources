# __GSHandlerCheckCommon

- ea: `0x1400160bc`
- end: `0x14001612c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016098`

## callees

- `0x1400160bc`
- `0x1400161f0`

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
0x1400160bc  sub     rsp, 28h
0x1400160c0  mov     eax, [r8]
0x1400160c3  mov     r10, rcx
0x1400160c6  mov     ecx, eax
0x1400160c8  mov     r11, rdx
0x1400160cb  and     ecx, 0FFFFFFF8h
0x1400160ce  test    al, 4
0x1400160d0  jz      short loc_1400160E7
0x1400160d2  mov     eax, [r8+8]
0x1400160d6  movsxd  r9, dword ptr [r8+4]
0x1400160da  neg     eax
0x1400160dc  movsxd  rdx, eax
0x1400160df  add     r9, r10
0x1400160e2  and     r9, rdx
0x1400160e5  jmp     short loc_1400160EA
0x1400160e7  mov     r9, r10
0x1400160ea  movsxd  rax, ecx
0x1400160ed  mov     rdx, [rax+r9]
0x1400160f1  mov     rax, [r11+10h]
0x1400160f5  mov     ecx, [rax+8]
0x1400160f8  mov     rax, [r11+8]
0x1400160fc  movzx   r8d, byte ptr [rcx+rax+3]
0x140016102  test    r8b, 0Fh
0x140016106  jz      short loc_140016118
0x140016108  mov     eax, r8d
0x14001610b  mov     ecx, 0FFFFFFF0h
0x140016110  and     rax, rcx
0x140016113  add     rax, r10
0x140016116  jmp     short loc_14001611B
0x140016118  mov     rax, r10
0x14001611b  xor     rdx, rax
0x14001611e  mov     rcx, rdx; StackCookie
0x140016121  call    __security_check_cookie
0x140016126  add     rsp, 28h
0x14001612a  retn
```
