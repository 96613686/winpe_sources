# __GSHandlerCheckCommon

- ea: `0x140002c10`
- end: `0x140002c73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002bec`

## callees

- `0x140002c10`
- `0x140002cb0`

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
0x140002c10  mov     r10, rcx
0x140002c13  mov     r11, rdx
0x140002c16  mov     ecx, [r8]
0x140002c19  and     ecx, 0FFFFFFF8h
0x140002c1c  test    byte ptr [r8], 4
0x140002c20  jz      short loc_140002C37
0x140002c22  mov     eax, [r8+8]
0x140002c26  movsxd  r9, dword ptr [r8+4]
0x140002c2a  neg     eax
0x140002c2c  movsxd  rdx, eax
0x140002c2f  add     r9, r10
0x140002c32  and     r9, rdx
0x140002c35  jmp     short loc_140002C3A
0x140002c37  mov     r9, r10
0x140002c3a  movsxd  rax, ecx
0x140002c3d  mov     rdx, [rax+r9]
0x140002c41  mov     rax, [r11+10h]
0x140002c45  mov     ecx, [rax+8]
0x140002c48  mov     rax, [r11+8]
0x140002c4c  test    byte ptr [rcx+rax+3], 0Fh
0x140002c51  jz      short loc_140002C65
0x140002c53  movzx   eax, byte ptr [rcx+rax+3]
0x140002c58  mov     ecx, 0FFFFFFF0h
0x140002c5d  and     rax, rcx
0x140002c60  add     rax, r10
0x140002c63  jmp     short loc_140002C68
0x140002c65  mov     rax, r10
0x140002c68  xor     rdx, rax
0x140002c6b  mov     rcx, rdx; StackCookie
0x140002c6e  jmp     __security_check_cookie
```
