# __GSHandlerCheckCommon

- ea: `0x180003bbc`
- end: `0x180003c1f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b98`

## callees

- `0x180003bbc`
- `0x180003c70`

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
0x180003bbc  mov     r10, rcx
0x180003bbf  mov     r11, rdx
0x180003bc2  mov     ecx, [r8]
0x180003bc5  and     ecx, 0FFFFFFF8h
0x180003bc8  test    byte ptr [r8], 4
0x180003bcc  jz      short loc_180003BE3
0x180003bce  mov     eax, [r8+8]
0x180003bd2  movsxd  r9, dword ptr [r8+4]
0x180003bd6  neg     eax
0x180003bd8  movsxd  rdx, eax
0x180003bdb  add     r9, r10
0x180003bde  and     r9, rdx
0x180003be1  jmp     short loc_180003BE6
0x180003be3  mov     r9, r10
0x180003be6  movsxd  rax, ecx
0x180003be9  mov     rdx, [rax+r9]
0x180003bed  mov     rax, [r11+10h]
0x180003bf1  mov     ecx, [rax+8]
0x180003bf4  mov     rax, [r11+8]
0x180003bf8  test    byte ptr [rcx+rax+3], 0Fh
0x180003bfd  jz      short loc_180003C11
0x180003bff  movzx   eax, byte ptr [rcx+rax+3]
0x180003c04  mov     ecx, 0FFFFFFF0h
0x180003c09  and     rax, rcx
0x180003c0c  add     rax, r10
0x180003c0f  jmp     short loc_180003C14
0x180003c11  mov     rax, r10
0x180003c14  xor     rdx, rax
0x180003c17  mov     rcx, rdx; StackCookie
0x180003c1a  jmp     __security_check_cookie
```
