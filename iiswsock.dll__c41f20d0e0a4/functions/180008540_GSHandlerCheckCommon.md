# __GSHandlerCheckCommon

- ea: `0x180008540`
- end: `0x1800085a3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000851c`

## callees

- `0x180008540`
- `0x180008600`

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
0x180008540  mov     r10, rcx
0x180008543  mov     r11, rdx
0x180008546  mov     ecx, [r8]
0x180008549  and     ecx, 0FFFFFFF8h
0x18000854c  test    byte ptr [r8], 4
0x180008550  jz      short loc_180008567
0x180008552  mov     eax, [r8+8]
0x180008556  movsxd  r9, dword ptr [r8+4]
0x18000855a  neg     eax
0x18000855c  movsxd  rdx, eax
0x18000855f  add     r9, r10
0x180008562  and     r9, rdx
0x180008565  jmp     short loc_18000856A
0x180008567  mov     r9, r10
0x18000856a  movsxd  rax, ecx
0x18000856d  mov     rdx, [rax+r9]
0x180008571  mov     rax, [r11+10h]
0x180008575  mov     ecx, [rax+8]
0x180008578  mov     rax, [r11+8]
0x18000857c  test    byte ptr [rcx+rax+3], 0Fh
0x180008581  jz      short loc_180008595
0x180008583  movzx   eax, byte ptr [rcx+rax+3]
0x180008588  mov     ecx, 0FFFFFFF0h
0x18000858d  and     rax, rcx
0x180008590  add     rax, r10
0x180008593  jmp     short loc_180008598
0x180008595  mov     rax, r10
0x180008598  xor     rdx, rax
0x18000859b  mov     rcx, rdx; StackCookie
0x18000859e  jmp     __security_check_cookie
```
