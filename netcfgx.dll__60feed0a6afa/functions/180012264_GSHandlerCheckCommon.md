# __GSHandlerCheckCommon

- ea: `0x180012264`
- end: `0x1800122c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012240`
- `0x1800122d0`

## callees

- `0x180001f90`
- `0x180012264`

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
0x180012264  mov     r10, rcx
0x180012267  mov     r11, rdx
0x18001226a  mov     ecx, [r8]
0x18001226d  and     ecx, 0FFFFFFF8h
0x180012270  test    byte ptr [r8], 4
0x180012274  jz      short loc_18001228B
0x180012276  mov     eax, [r8+8]
0x18001227a  movsxd  r9, dword ptr [r8+4]
0x18001227e  neg     eax
0x180012280  movsxd  rdx, eax
0x180012283  add     r9, r10
0x180012286  and     r9, rdx
0x180012289  jmp     short loc_18001228E
0x18001228b  mov     r9, r10
0x18001228e  movsxd  rax, ecx
0x180012291  mov     rdx, [rax+r9]
0x180012295  mov     rax, [r11+10h]
0x180012299  mov     ecx, [rax+8]
0x18001229c  mov     rax, [r11+8]
0x1800122a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800122a5  jz      short loc_1800122B9
0x1800122a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800122ac  mov     ecx, 0FFFFFFF0h
0x1800122b1  and     rax, rcx
0x1800122b4  add     rax, r10
0x1800122b7  jmp     short loc_1800122BC
0x1800122b9  mov     rax, r10
0x1800122bc  xor     rdx, rax
0x1800122bf  mov     rcx, rdx; StackCookie
0x1800122c2  jmp     __security_check_cookie
```
