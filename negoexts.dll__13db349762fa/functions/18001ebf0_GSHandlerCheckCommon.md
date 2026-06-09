# __GSHandlerCheckCommon

- ea: `0x18001ebf0`
- end: `0x18001ec53`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ebcc`
- `0x18001ec5c`

## callees

- `0x18001ebf0`
- `0x18001ed20`

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
0x18001ebf0  mov     r10, rcx
0x18001ebf3  mov     r11, rdx
0x18001ebf6  mov     ecx, [r8]
0x18001ebf9  and     ecx, 0FFFFFFF8h
0x18001ebfc  test    byte ptr [r8], 4
0x18001ec00  jz      short loc_18001EC17
0x18001ec02  mov     eax, [r8+8]
0x18001ec06  movsxd  r9, dword ptr [r8+4]
0x18001ec0a  neg     eax
0x18001ec0c  movsxd  rdx, eax
0x18001ec0f  add     r9, r10
0x18001ec12  and     r9, rdx
0x18001ec15  jmp     short loc_18001EC1A
0x18001ec17  mov     r9, r10
0x18001ec1a  movsxd  rax, ecx
0x18001ec1d  mov     rdx, [rax+r9]
0x18001ec21  mov     rax, [r11+10h]
0x18001ec25  mov     ecx, [rax+8]
0x18001ec28  mov     rax, [r11+8]
0x18001ec2c  test    byte ptr [rcx+rax+3], 0Fh
0x18001ec31  jz      short loc_18001EC45
0x18001ec33  movzx   eax, byte ptr [rcx+rax+3]
0x18001ec38  mov     ecx, 0FFFFFFF0h
0x18001ec3d  and     rax, rcx
0x18001ec40  add     rax, r10
0x18001ec43  jmp     short loc_18001EC48
0x18001ec45  mov     rax, r10
0x18001ec48  xor     rdx, rax
0x18001ec4b  mov     rcx, rdx; StackCookie
0x18001ec4e  jmp     __security_check_cookie
```
