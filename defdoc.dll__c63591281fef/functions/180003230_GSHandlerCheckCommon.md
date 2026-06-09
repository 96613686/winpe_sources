# __GSHandlerCheckCommon

- ea: `0x180003230`
- end: `0x180003293`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000320c`

## callees

- `0x180003230`
- `0x1800032d0`

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
0x180003230  mov     r10, rcx
0x180003233  mov     r11, rdx
0x180003236  mov     ecx, [r8]
0x180003239  and     ecx, 0FFFFFFF8h
0x18000323c  test    byte ptr [r8], 4
0x180003240  jz      short loc_180003257
0x180003242  mov     eax, [r8+8]
0x180003246  movsxd  r9, dword ptr [r8+4]
0x18000324a  neg     eax
0x18000324c  movsxd  rdx, eax
0x18000324f  add     r9, r10
0x180003252  and     r9, rdx
0x180003255  jmp     short loc_18000325A
0x180003257  mov     r9, r10
0x18000325a  movsxd  rax, ecx
0x18000325d  mov     rdx, [rax+r9]
0x180003261  mov     rax, [r11+10h]
0x180003265  mov     ecx, [rax+8]
0x180003268  mov     rax, [r11+8]
0x18000326c  test    byte ptr [rcx+rax+3], 0Fh
0x180003271  jz      short loc_180003285
0x180003273  movzx   eax, byte ptr [rcx+rax+3]
0x180003278  mov     ecx, 0FFFFFFF0h
0x18000327d  and     rax, rcx
0x180003280  add     rax, r10
0x180003283  jmp     short loc_180003288
0x180003285  mov     rax, r10
0x180003288  xor     rdx, rax
0x18000328b  mov     rcx, rdx; StackCookie
0x18000328e  jmp     __security_check_cookie
```
