# __GSHandlerCheckCommon

- ea: `0x18003238c`
- end: `0x1800323ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032368`

## callees

- `0x180001460`
- `0x18003238c`

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
0x18003238c  mov     r10, rcx
0x18003238f  mov     r11, rdx
0x180032392  mov     ecx, [r8]
0x180032395  and     ecx, 0FFFFFFF8h
0x180032398  test    byte ptr [r8], 4
0x18003239c  jz      short loc_1800323B3
0x18003239e  mov     eax, [r8+8]
0x1800323a2  movsxd  r9, dword ptr [r8+4]
0x1800323a6  neg     eax
0x1800323a8  movsxd  rdx, eax
0x1800323ab  add     r9, r10
0x1800323ae  and     r9, rdx
0x1800323b1  jmp     short loc_1800323B6
0x1800323b3  mov     r9, r10
0x1800323b6  movsxd  rax, ecx
0x1800323b9  mov     rdx, [rax+r9]
0x1800323bd  mov     rax, [r11+10h]
0x1800323c1  mov     ecx, [rax+8]
0x1800323c4  mov     rax, [r11+8]
0x1800323c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800323cd  jz      short loc_1800323E1
0x1800323cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800323d4  mov     ecx, 0FFFFFFF0h
0x1800323d9  and     rax, rcx
0x1800323dc  add     rax, r10
0x1800323df  jmp     short loc_1800323E4
0x1800323e1  mov     rax, r10
0x1800323e4  xor     rdx, rax
0x1800323e7  mov     rcx, rdx; StackCookie
0x1800323ea  jmp     __security_check_cookie
```
