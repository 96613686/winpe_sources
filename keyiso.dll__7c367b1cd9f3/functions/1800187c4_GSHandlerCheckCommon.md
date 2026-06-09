# __GSHandlerCheckCommon

- ea: `0x1800187c4`
- end: `0x180018827`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800187a0`
- `0x180018830`

## callees

- `0x1800187c4`
- `0x180018950`

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
0x1800187c4  mov     r10, rcx
0x1800187c7  mov     r11, rdx
0x1800187ca  mov     ecx, [r8]
0x1800187cd  and     ecx, 0FFFFFFF8h
0x1800187d0  test    byte ptr [r8], 4
0x1800187d4  jz      short loc_1800187EB
0x1800187d6  mov     eax, [r8+8]
0x1800187da  movsxd  r9, dword ptr [r8+4]
0x1800187de  neg     eax
0x1800187e0  movsxd  rdx, eax
0x1800187e3  add     r9, r10
0x1800187e6  and     r9, rdx
0x1800187e9  jmp     short loc_1800187EE
0x1800187eb  mov     r9, r10
0x1800187ee  movsxd  rax, ecx
0x1800187f1  mov     rdx, [rax+r9]
0x1800187f5  mov     rax, [r11+10h]
0x1800187f9  mov     ecx, [rax+8]
0x1800187fc  mov     rax, [r11+8]
0x180018800  test    byte ptr [rcx+rax+3], 0Fh
0x180018805  jz      short loc_180018819
0x180018807  movzx   eax, byte ptr [rcx+rax+3]
0x18001880c  mov     ecx, 0FFFFFFF0h
0x180018811  and     rax, rcx
0x180018814  add     rax, r10
0x180018817  jmp     short loc_18001881C
0x180018819  mov     rax, r10
0x18001881c  xor     rdx, rax
0x18001881f  mov     rcx, rdx; StackCookie
0x180018822  jmp     __security_check_cookie
```
