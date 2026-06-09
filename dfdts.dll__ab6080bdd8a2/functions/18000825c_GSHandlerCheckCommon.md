# __GSHandlerCheckCommon

- ea: `0x18000825c`
- end: `0x1800082bf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008238`
- `0x1800082c8`

## callees

- `0x18000825c`
- `0x180008370`

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
0x18000825c  mov     r10, rcx
0x18000825f  mov     r11, rdx
0x180008262  mov     ecx, [r8]
0x180008265  and     ecx, 0FFFFFFF8h
0x180008268  test    byte ptr [r8], 4
0x18000826c  jz      short loc_180008283
0x18000826e  mov     eax, [r8+8]
0x180008272  movsxd  r9, dword ptr [r8+4]
0x180008276  neg     eax
0x180008278  movsxd  rdx, eax
0x18000827b  add     r9, r10
0x18000827e  and     r9, rdx
0x180008281  jmp     short loc_180008286
0x180008283  mov     r9, r10
0x180008286  movsxd  rax, ecx
0x180008289  mov     rdx, [rax+r9]
0x18000828d  mov     rax, [r11+10h]
0x180008291  mov     ecx, [rax+8]
0x180008294  mov     rax, [r11+8]
0x180008298  test    byte ptr [rcx+rax+3], 0Fh
0x18000829d  jz      short loc_1800082B1
0x18000829f  movzx   eax, byte ptr [rcx+rax+3]
0x1800082a4  mov     ecx, 0FFFFFFF0h
0x1800082a9  and     rax, rcx
0x1800082ac  add     rax, r10
0x1800082af  jmp     short loc_1800082B4
0x1800082b1  mov     rax, r10
0x1800082b4  xor     rdx, rax
0x1800082b7  mov     rcx, rdx; StackCookie
0x1800082ba  jmp     __security_check_cookie
```
