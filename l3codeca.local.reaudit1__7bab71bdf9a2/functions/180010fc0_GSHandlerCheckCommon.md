# __GSHandlerCheckCommon

- ea: `0x180010fc0`
- end: `0x180011023`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010f9c`

## callees

- `0x180001400`
- `0x180010fc0`

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
0x180010fc0  mov     r10, rcx
0x180010fc3  mov     r11, rdx
0x180010fc6  mov     ecx, [r8]
0x180010fc9  and     ecx, 0FFFFFFF8h
0x180010fcc  test    byte ptr [r8], 4
0x180010fd0  jz      short loc_180010FE7
0x180010fd2  mov     eax, [r8+8]
0x180010fd6  movsxd  r9, dword ptr [r8+4]
0x180010fda  neg     eax
0x180010fdc  movsxd  rdx, eax
0x180010fdf  add     r9, r10
0x180010fe2  and     r9, rdx
0x180010fe5  jmp     short loc_180010FEA
0x180010fe7  mov     r9, r10
0x180010fea  movsxd  rax, ecx
0x180010fed  mov     rdx, [rax+r9]
0x180010ff1  mov     rax, [r11+10h]
0x180010ff5  mov     ecx, [rax+8]
0x180010ff8  mov     rax, [r11+8]
0x180010ffc  test    byte ptr [rcx+rax+3], 0Fh
0x180011001  jz      short loc_180011015
0x180011003  movzx   eax, byte ptr [rcx+rax+3]
0x180011008  mov     ecx, 0FFFFFFF0h
0x18001100d  and     rax, rcx
0x180011010  add     rax, r10
0x180011013  jmp     short loc_180011018
0x180011015  mov     rax, r10
0x180011018  xor     rdx, rax
0x18001101b  mov     rcx, rdx; StackCookie
0x18001101e  jmp     __security_check_cookie
```
