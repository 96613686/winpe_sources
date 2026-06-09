# __GSHandlerCheckCommon

- ea: `0x180023230`
- end: `0x180023293`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002320c`
- `0x18002329c`

## callees

- `0x180014130`
- `0x180023230`

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
0x180023230  mov     r10, rcx
0x180023233  mov     r11, rdx
0x180023236  mov     ecx, [r8]
0x180023239  and     ecx, 0FFFFFFF8h
0x18002323c  test    byte ptr [r8], 4
0x180023240  jz      short loc_180023257
0x180023242  mov     eax, [r8+8]
0x180023246  movsxd  r9, dword ptr [r8+4]
0x18002324a  neg     eax
0x18002324c  movsxd  rdx, eax
0x18002324f  add     r9, r10
0x180023252  and     r9, rdx
0x180023255  jmp     short loc_18002325A
0x180023257  mov     r9, r10
0x18002325a  movsxd  rax, ecx
0x18002325d  mov     rdx, [rax+r9]
0x180023261  mov     rax, [r11+10h]
0x180023265  mov     ecx, [rax+8]
0x180023268  mov     rax, [r11+8]
0x18002326c  test    byte ptr [rcx+rax+3], 0Fh
0x180023271  jz      short loc_180023285
0x180023273  movzx   eax, byte ptr [rcx+rax+3]
0x180023278  mov     ecx, 0FFFFFFF0h
0x18002327d  and     rax, rcx
0x180023280  add     rax, r10
0x180023283  jmp     short loc_180023288
0x180023285  mov     rax, r10
0x180023288  xor     rdx, rax
0x18002328b  mov     rcx, rdx; StackCookie
0x18002328e  jmp     __security_check_cookie
```
