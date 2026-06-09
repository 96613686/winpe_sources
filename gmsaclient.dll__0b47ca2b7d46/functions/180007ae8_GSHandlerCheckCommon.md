# __GSHandlerCheckCommon

- ea: `0x180007ae8`
- end: `0x180007b4b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007ac4`
- `0x180007b54`

## callees

- `0x180001400`
- `0x180007ae8`

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
0x180007ae8  mov     r10, rcx
0x180007aeb  mov     r11, rdx
0x180007aee  mov     ecx, [r8]
0x180007af1  and     ecx, 0FFFFFFF8h
0x180007af4  test    byte ptr [r8], 4
0x180007af8  jz      short loc_180007B0F
0x180007afa  mov     eax, [r8+8]
0x180007afe  movsxd  r9, dword ptr [r8+4]
0x180007b02  neg     eax
0x180007b04  movsxd  rdx, eax
0x180007b07  add     r9, r10
0x180007b0a  and     r9, rdx
0x180007b0d  jmp     short loc_180007B12
0x180007b0f  mov     r9, r10
0x180007b12  movsxd  rax, ecx
0x180007b15  mov     rdx, [rax+r9]
0x180007b19  mov     rax, [r11+10h]
0x180007b1d  mov     ecx, [rax+8]
0x180007b20  mov     rax, [r11+8]
0x180007b24  test    byte ptr [rcx+rax+3], 0Fh
0x180007b29  jz      short loc_180007B3D
0x180007b2b  movzx   eax, byte ptr [rcx+rax+3]
0x180007b30  mov     ecx, 0FFFFFFF0h
0x180007b35  and     rax, rcx
0x180007b38  add     rax, r10
0x180007b3b  jmp     short loc_180007B40
0x180007b3d  mov     rax, r10
0x180007b40  xor     rdx, rax
0x180007b43  mov     rcx, rdx; StackCookie
0x180007b46  jmp     __security_check_cookie
```
