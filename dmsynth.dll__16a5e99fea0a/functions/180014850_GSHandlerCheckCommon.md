# __GSHandlerCheckCommon

- ea: `0x180014850`
- end: `0x1800148b3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001482c`

## callees

- `0x1800014f0`
- `0x180014850`

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
0x180014850  mov     r10, rcx
0x180014853  mov     r11, rdx
0x180014856  mov     ecx, [r8]
0x180014859  and     ecx, 0FFFFFFF8h
0x18001485c  test    byte ptr [r8], 4
0x180014860  jz      short loc_180014877
0x180014862  mov     eax, [r8+8]
0x180014866  movsxd  r9, dword ptr [r8+4]
0x18001486a  neg     eax
0x18001486c  movsxd  rdx, eax
0x18001486f  add     r9, r10
0x180014872  and     r9, rdx
0x180014875  jmp     short loc_18001487A
0x180014877  mov     r9, r10
0x18001487a  movsxd  rax, ecx
0x18001487d  mov     rdx, [rax+r9]
0x180014881  mov     rax, [r11+10h]
0x180014885  mov     ecx, [rax+8]
0x180014888  mov     rax, [r11+8]
0x18001488c  test    byte ptr [rcx+rax+3], 0Fh
0x180014891  jz      short loc_1800148A5
0x180014893  movzx   eax, byte ptr [rcx+rax+3]
0x180014898  mov     ecx, 0FFFFFFF0h
0x18001489d  and     rax, rcx
0x1800148a0  add     rax, r10
0x1800148a3  jmp     short loc_1800148A8
0x1800148a5  mov     rax, r10
0x1800148a8  xor     rdx, rax
0x1800148ab  mov     rcx, rdx; StackCookie
0x1800148ae  jmp     __security_check_cookie
```
