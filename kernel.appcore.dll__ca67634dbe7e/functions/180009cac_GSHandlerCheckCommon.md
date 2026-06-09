# __GSHandlerCheckCommon

- ea: `0x180009cac`
- end: `0x180009d0f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009c88`
- `0x180009d18`

## callees

- `0x180009cac`
- `0x180009dd0`

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
0x180009cac  mov     r10, rcx
0x180009caf  mov     r11, rdx
0x180009cb2  mov     ecx, [r8]
0x180009cb5  and     ecx, 0FFFFFFF8h
0x180009cb8  test    byte ptr [r8], 4
0x180009cbc  jz      short loc_180009CD3
0x180009cbe  mov     eax, [r8+8]
0x180009cc2  movsxd  r9, dword ptr [r8+4]
0x180009cc6  neg     eax
0x180009cc8  movsxd  rdx, eax
0x180009ccb  add     r9, r10
0x180009cce  and     r9, rdx
0x180009cd1  jmp     short loc_180009CD6
0x180009cd3  mov     r9, r10
0x180009cd6  movsxd  rax, ecx
0x180009cd9  mov     rdx, [rax+r9]
0x180009cdd  mov     rax, [r11+10h]
0x180009ce1  mov     ecx, [rax+8]
0x180009ce4  mov     rax, [r11+8]
0x180009ce8  test    byte ptr [rcx+rax+3], 0Fh
0x180009ced  jz      short loc_180009D01
0x180009cef  movzx   eax, byte ptr [rcx+rax+3]
0x180009cf4  mov     ecx, 0FFFFFFF0h
0x180009cf9  and     rax, rcx
0x180009cfc  add     rax, r10
0x180009cff  jmp     short loc_180009D04
0x180009d01  mov     rax, r10
0x180009d04  xor     rdx, rax
0x180009d07  mov     rcx, rdx; StackCookie
0x180009d0a  jmp     __security_check_cookie
```
