# __GSHandlerCheckCommon

- ea: `0x180026468`
- end: `0x1800264cb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026444`
- `0x1800264d4`

## callees

- `0x180026468`
- `0x1800265b0`

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
0x180026468  mov     r10, rcx
0x18002646b  mov     r11, rdx
0x18002646e  mov     ecx, [r8]
0x180026471  and     ecx, 0FFFFFFF8h
0x180026474  test    byte ptr [r8], 4
0x180026478  jz      short loc_18002648F
0x18002647a  mov     eax, [r8+8]
0x18002647e  movsxd  r9, dword ptr [r8+4]
0x180026482  neg     eax
0x180026484  movsxd  rdx, eax
0x180026487  add     r9, r10
0x18002648a  and     r9, rdx
0x18002648d  jmp     short loc_180026492
0x18002648f  mov     r9, r10
0x180026492  movsxd  rax, ecx
0x180026495  mov     rdx, [rax+r9]
0x180026499  mov     rax, [r11+10h]
0x18002649d  mov     ecx, [rax+8]
0x1800264a0  mov     rax, [r11+8]
0x1800264a4  test    byte ptr [rcx+rax+3], 0Fh
0x1800264a9  jz      short loc_1800264BD
0x1800264ab  movzx   eax, byte ptr [rcx+rax+3]
0x1800264b0  mov     ecx, 0FFFFFFF0h
0x1800264b5  and     rax, rcx
0x1800264b8  add     rax, r10
0x1800264bb  jmp     short loc_1800264C0
0x1800264bd  mov     rax, r10
0x1800264c0  xor     rdx, rax
0x1800264c3  mov     rcx, rdx; StackCookie
0x1800264c6  jmp     __security_check_cookie
```
