# __GSHandlerCheckCommon

- ea: `0x1800262dc`
- end: `0x18002633f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800262b8`
- `0x180026348`

## callees

- `0x1800262dc`
- `0x180026400`

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
0x1800262dc  mov     r10, rcx
0x1800262df  mov     r11, rdx
0x1800262e2  mov     ecx, [r8]
0x1800262e5  and     ecx, 0FFFFFFF8h
0x1800262e8  test    byte ptr [r8], 4
0x1800262ec  jz      short loc_180026303
0x1800262ee  mov     eax, [r8+8]
0x1800262f2  movsxd  r9, dword ptr [r8+4]
0x1800262f6  neg     eax
0x1800262f8  movsxd  rdx, eax
0x1800262fb  add     r9, r10
0x1800262fe  and     r9, rdx
0x180026301  jmp     short loc_180026306
0x180026303  mov     r9, r10
0x180026306  movsxd  rax, ecx
0x180026309  mov     rdx, [rax+r9]
0x18002630d  mov     rax, [r11+10h]
0x180026311  mov     ecx, [rax+8]
0x180026314  mov     rax, [r11+8]
0x180026318  test    byte ptr [rcx+rax+3], 0Fh
0x18002631d  jz      short loc_180026331
0x18002631f  movzx   eax, byte ptr [rcx+rax+3]
0x180026324  mov     ecx, 0FFFFFFF0h
0x180026329  and     rax, rcx
0x18002632c  add     rax, r10
0x18002632f  jmp     short loc_180026334
0x180026331  mov     rax, r10
0x180026334  xor     rdx, rax
0x180026337  mov     rcx, rdx; StackCookie
0x18002633a  jmp     __security_check_cookie
```
