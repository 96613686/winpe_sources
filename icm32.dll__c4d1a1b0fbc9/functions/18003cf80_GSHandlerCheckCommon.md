# __GSHandlerCheckCommon

- ea: `0x18003cf80`
- end: `0x18003cfe3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003cf5c`

## callees

- `0x18003cf80`
- `0x18003d040`

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
0x18003cf80  mov     r10, rcx
0x18003cf83  mov     r11, rdx
0x18003cf86  mov     ecx, [r8]
0x18003cf89  and     ecx, 0FFFFFFF8h
0x18003cf8c  test    byte ptr [r8], 4
0x18003cf90  jz      short loc_18003CFA7
0x18003cf92  mov     eax, [r8+8]
0x18003cf96  movsxd  r9, dword ptr [r8+4]
0x18003cf9a  neg     eax
0x18003cf9c  movsxd  rdx, eax
0x18003cf9f  add     r9, r10
0x18003cfa2  and     r9, rdx
0x18003cfa5  jmp     short loc_18003CFAA
0x18003cfa7  mov     r9, r10
0x18003cfaa  movsxd  rax, ecx
0x18003cfad  mov     rdx, [rax+r9]
0x18003cfb1  mov     rax, [r11+10h]
0x18003cfb5  mov     ecx, [rax+8]
0x18003cfb8  mov     rax, [r11+8]
0x18003cfbc  test    byte ptr [rcx+rax+3], 0Fh
0x18003cfc1  jz      short loc_18003CFD5
0x18003cfc3  movzx   eax, byte ptr [rcx+rax+3]
0x18003cfc8  mov     ecx, 0FFFFFFF0h
0x18003cfcd  and     rax, rcx
0x18003cfd0  add     rax, r10
0x18003cfd3  jmp     short loc_18003CFD8
0x18003cfd5  mov     rax, r10
0x18003cfd8  xor     rdx, rax
0x18003cfdb  mov     rcx, rdx; StackCookie
0x18003cfde  jmp     __security_check_cookie
```
