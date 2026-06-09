# __GSHandlerCheckCommon

- ea: `0x180012644`
- end: `0x1800126a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012620`

## callees

- `0x180009270`
- `0x180012644`

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
0x180012644  mov     r10, rcx
0x180012647  mov     r11, rdx
0x18001264a  mov     ecx, [r8]
0x18001264d  and     ecx, 0FFFFFFF8h
0x180012650  test    byte ptr [r8], 4
0x180012654  jz      short loc_18001266B
0x180012656  mov     eax, [r8+8]
0x18001265a  movsxd  r9, dword ptr [r8+4]
0x18001265e  neg     eax
0x180012660  movsxd  rdx, eax
0x180012663  add     r9, r10
0x180012666  and     r9, rdx
0x180012669  jmp     short loc_18001266E
0x18001266b  mov     r9, r10
0x18001266e  movsxd  rax, ecx
0x180012671  mov     rdx, [rax+r9]
0x180012675  mov     rax, [r11+10h]
0x180012679  mov     ecx, [rax+8]
0x18001267c  mov     rax, [r11+8]
0x180012680  test    byte ptr [rcx+rax+3], 0Fh
0x180012685  jz      short loc_180012699
0x180012687  movzx   eax, byte ptr [rcx+rax+3]
0x18001268c  mov     ecx, 0FFFFFFF0h
0x180012691  and     rax, rcx
0x180012694  add     rax, r10
0x180012697  jmp     short loc_18001269C
0x180012699  mov     rax, r10
0x18001269c  xor     rdx, rax
0x18001269f  mov     rcx, rdx; StackCookie
0x1800126a2  jmp     __security_check_cookie
```
