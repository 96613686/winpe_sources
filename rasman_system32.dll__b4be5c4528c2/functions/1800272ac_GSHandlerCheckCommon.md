# __GSHandlerCheckCommon

- ea: `0x1800272ac`
- end: `0x18002730f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027288`
- `0x180027318`

## callees

- `0x1800272ac`
- `0x1800273d0`

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
0x1800272ac  mov     r10, rcx
0x1800272af  mov     r11, rdx
0x1800272b2  mov     ecx, [r8]
0x1800272b5  and     ecx, 0FFFFFFF8h
0x1800272b8  test    byte ptr [r8], 4
0x1800272bc  jz      short loc_1800272D3
0x1800272be  mov     eax, [r8+8]
0x1800272c2  movsxd  r9, dword ptr [r8+4]
0x1800272c6  neg     eax
0x1800272c8  movsxd  rdx, eax
0x1800272cb  add     r9, r10
0x1800272ce  and     r9, rdx
0x1800272d1  jmp     short loc_1800272D6
0x1800272d3  mov     r9, r10
0x1800272d6  movsxd  rax, ecx
0x1800272d9  mov     rdx, [rax+r9]
0x1800272dd  mov     rax, [r11+10h]
0x1800272e1  mov     ecx, [rax+8]
0x1800272e4  mov     rax, [r11+8]
0x1800272e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800272ed  jz      short loc_180027301
0x1800272ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800272f4  mov     ecx, 0FFFFFFF0h
0x1800272f9  and     rax, rcx
0x1800272fc  add     rax, r10
0x1800272ff  jmp     short loc_180027304
0x180027301  mov     rax, r10
0x180027304  xor     rdx, rax
0x180027307  mov     rcx, rdx; StackCookie
0x18002730a  jmp     __security_check_cookie
```
