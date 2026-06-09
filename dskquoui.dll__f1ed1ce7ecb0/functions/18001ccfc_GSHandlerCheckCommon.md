# __GSHandlerCheckCommon

- ea: `0x18001ccfc`
- end: `0x18001cd5f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ccd8`
- `0x18001cd68`

## callees

- `0x180001510`
- `0x18001ccfc`

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
0x18001ccfc  mov     r10, rcx
0x18001ccff  mov     r11, rdx
0x18001cd02  mov     ecx, [r8]
0x18001cd05  and     ecx, 0FFFFFFF8h
0x18001cd08  test    byte ptr [r8], 4
0x18001cd0c  jz      short loc_18001CD23
0x18001cd0e  mov     eax, [r8+8]
0x18001cd12  movsxd  r9, dword ptr [r8+4]
0x18001cd16  neg     eax
0x18001cd18  movsxd  rdx, eax
0x18001cd1b  add     r9, r10
0x18001cd1e  and     r9, rdx
0x18001cd21  jmp     short loc_18001CD26
0x18001cd23  mov     r9, r10
0x18001cd26  movsxd  rax, ecx
0x18001cd29  mov     rdx, [rax+r9]
0x18001cd2d  mov     rax, [r11+10h]
0x18001cd31  mov     ecx, [rax+8]
0x18001cd34  mov     rax, [r11+8]
0x18001cd38  test    byte ptr [rcx+rax+3], 0Fh
0x18001cd3d  jz      short loc_18001CD51
0x18001cd3f  movzx   eax, byte ptr [rcx+rax+3]
0x18001cd44  mov     ecx, 0FFFFFFF0h
0x18001cd49  and     rax, rcx
0x18001cd4c  add     rax, r10
0x18001cd4f  jmp     short loc_18001CD54
0x18001cd51  mov     rax, r10
0x18001cd54  xor     rdx, rax
0x18001cd57  mov     rcx, rdx; StackCookie
0x18001cd5a  jmp     __security_check_cookie
```
