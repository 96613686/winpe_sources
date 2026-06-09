# __GSHandlerCheckCommon

- ea: `0x14000f660`
- end: `0x14000f6c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f63c`

## callees

- `0x140001fa0`
- `0x14000f660`

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
0x14000f660  mov     r10, rcx
0x14000f663  mov     r11, rdx
0x14000f666  mov     ecx, [r8]
0x14000f669  and     ecx, 0FFFFFFF8h
0x14000f66c  test    byte ptr [r8], 4
0x14000f670  jz      short loc_14000F687
0x14000f672  mov     eax, [r8+8]
0x14000f676  movsxd  r9, dword ptr [r8+4]
0x14000f67a  neg     eax
0x14000f67c  movsxd  rdx, eax
0x14000f67f  add     r9, r10
0x14000f682  and     r9, rdx
0x14000f685  jmp     short loc_14000F68A
0x14000f687  mov     r9, r10
0x14000f68a  movsxd  rax, ecx
0x14000f68d  mov     rdx, [rax+r9]
0x14000f691  mov     rax, [r11+10h]
0x14000f695  mov     ecx, [rax+8]
0x14000f698  mov     rax, [r11+8]
0x14000f69c  test    byte ptr [rcx+rax+3], 0Fh
0x14000f6a1  jz      short loc_14000F6B5
0x14000f6a3  movzx   eax, byte ptr [rcx+rax+3]
0x14000f6a8  mov     ecx, 0FFFFFFF0h
0x14000f6ad  and     rax, rcx
0x14000f6b0  add     rax, r10
0x14000f6b3  jmp     short loc_14000F6B8
0x14000f6b5  mov     rax, r10
0x14000f6b8  xor     rdx, rax
0x14000f6bb  mov     rcx, rdx; StackCookie
0x14000f6be  jmp     __security_check_cookie
```
