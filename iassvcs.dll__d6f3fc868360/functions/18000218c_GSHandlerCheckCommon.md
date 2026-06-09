# __GSHandlerCheckCommon

- ea: `0x18000218c`
- end: `0x1800021ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002168`
- `0x18001812c`

## callees

- `0x18000218c`
- `0x1800181e0`

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
0x18000218c  mov     r10, rcx
0x18000218f  mov     r11, rdx
0x180002192  mov     ecx, [r8]
0x180002195  and     ecx, 0FFFFFFF8h
0x180002198  test    byte ptr [r8], 4
0x18000219c  jz      short loc_1800021B3
0x18000219e  mov     eax, [r8+8]
0x1800021a2  movsxd  r9, dword ptr [r8+4]
0x1800021a6  neg     eax
0x1800021a8  movsxd  rdx, eax
0x1800021ab  add     r9, r10
0x1800021ae  and     r9, rdx
0x1800021b1  jmp     short loc_1800021B6
0x1800021b3  mov     r9, r10
0x1800021b6  movsxd  rax, ecx
0x1800021b9  mov     rdx, [rax+r9]
0x1800021bd  mov     rax, [r11+10h]
0x1800021c1  mov     ecx, [rax+8]
0x1800021c4  mov     rax, [r11+8]
0x1800021c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800021cd  jz      short loc_1800021E1
0x1800021cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800021d4  mov     ecx, 0FFFFFFF0h
0x1800021d9  and     rax, rcx
0x1800021dc  add     rax, r10
0x1800021df  jmp     short loc_1800021E4
0x1800021e1  mov     rax, r10
0x1800021e4  xor     rdx, rax
0x1800021e7  mov     rcx, rdx; StackCookie
0x1800021ea  jmp     __security_check_cookie
```
