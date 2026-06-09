# __GSHandlerCheckCommon

- ea: `0x180008b34`
- end: `0x180008b97`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b10`

## callees

- `0x180008b34`
- `0x180008bf0`

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
0x180008b34  mov     r10, rcx
0x180008b37  mov     r11, rdx
0x180008b3a  mov     ecx, [r8]
0x180008b3d  and     ecx, 0FFFFFFF8h
0x180008b40  test    byte ptr [r8], 4
0x180008b44  jz      short loc_180008B5B
0x180008b46  mov     eax, [r8+8]
0x180008b4a  movsxd  r9, dword ptr [r8+4]
0x180008b4e  neg     eax
0x180008b50  movsxd  rdx, eax
0x180008b53  add     r9, r10
0x180008b56  and     r9, rdx
0x180008b59  jmp     short loc_180008B5E
0x180008b5b  mov     r9, r10
0x180008b5e  movsxd  rax, ecx
0x180008b61  mov     rdx, [rax+r9]
0x180008b65  mov     rax, [r11+10h]
0x180008b69  mov     ecx, [rax+8]
0x180008b6c  mov     rax, [r11+8]
0x180008b70  test    byte ptr [rcx+rax+3], 0Fh
0x180008b75  jz      short loc_180008B89
0x180008b77  movzx   eax, byte ptr [rcx+rax+3]
0x180008b7c  mov     ecx, 0FFFFFFF0h
0x180008b81  and     rax, rcx
0x180008b84  add     rax, r10
0x180008b87  jmp     short loc_180008B8C
0x180008b89  mov     rax, r10
0x180008b8c  xor     rdx, rax
0x180008b8f  mov     rcx, rdx; StackCookie
0x180008b92  jmp     __security_check_cookie
```
