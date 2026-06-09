# __GSHandlerCheckCommon

- ea: `0x140030dec`
- end: `0x140030e5c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140030dc8`

## callees

- `0x140030dec`
- `0x140030f40`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x140030dec  sub     rsp, 28h
0x140030df0  mov     eax, [r8]
0x140030df3  mov     r10, rcx
0x140030df6  mov     ecx, eax
0x140030df8  mov     r11, rdx
0x140030dfb  and     ecx, 0FFFFFFF8h
0x140030dfe  test    al, 4
0x140030e00  jz      short loc_140030E17
0x140030e02  mov     eax, [r8+8]
0x140030e06  movsxd  r9, dword ptr [r8+4]
0x140030e0a  neg     eax
0x140030e0c  movsxd  rdx, eax
0x140030e0f  add     r9, r10
0x140030e12  and     r9, rdx
0x140030e15  jmp     short loc_140030E1A
0x140030e17  mov     r9, r10
0x140030e1a  movsxd  rax, ecx
0x140030e1d  mov     rdx, [rax+r9]
0x140030e21  mov     rax, [r11+10h]
0x140030e25  mov     ecx, [rax+8]
0x140030e28  mov     rax, [r11+8]
0x140030e2c  movzx   r8d, byte ptr [rcx+rax+3]
0x140030e32  test    r8b, 0Fh
0x140030e36  jz      short loc_140030E48
0x140030e38  mov     eax, r8d
0x140030e3b  mov     ecx, 0FFFFFFF0h
0x140030e40  and     rax, rcx
0x140030e43  add     rax, r10
0x140030e46  jmp     short loc_140030E4B
0x140030e48  mov     rax, r10
0x140030e4b  xor     rdx, rax
0x140030e4e  mov     rcx, rdx; StackCookie
0x140030e51  call    __security_check_cookie
0x140030e56  add     rsp, 28h
0x140030e5a  retn
```
