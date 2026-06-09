# __GSHandlerCheckCommon

- ea: `0x140005dac`
- end: `0x140005e1c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005d88`
- `0x140005e24`

## callees

- `0x140005dac`
- `0x140005f70`

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
0x140005dac  sub     rsp, 28h
0x140005db0  mov     eax, [r8]
0x140005db3  mov     r10, rcx
0x140005db6  mov     ecx, eax
0x140005db8  mov     r11, rdx
0x140005dbb  and     ecx, 0FFFFFFF8h
0x140005dbe  test    al, 4
0x140005dc0  jz      short loc_140005DD7
0x140005dc2  mov     eax, [r8+8]
0x140005dc6  movsxd  r9, dword ptr [r8+4]
0x140005dca  neg     eax
0x140005dcc  movsxd  rdx, eax
0x140005dcf  add     r9, r10
0x140005dd2  and     r9, rdx
0x140005dd5  jmp     short loc_140005DDA
0x140005dd7  mov     r9, r10
0x140005dda  movsxd  rax, ecx
0x140005ddd  mov     rdx, [rax+r9]
0x140005de1  mov     rax, [r11+10h]
0x140005de5  mov     ecx, [rax+8]
0x140005de8  mov     rax, [r11+8]
0x140005dec  movzx   r8d, byte ptr [rcx+rax+3]
0x140005df2  test    r8b, 0Fh
0x140005df6  jz      short loc_140005E08
0x140005df8  mov     eax, r8d
0x140005dfb  mov     ecx, 0FFFFFFF0h
0x140005e00  and     rax, rcx
0x140005e03  add     rax, r10
0x140005e06  jmp     short loc_140005E0B
0x140005e08  mov     rax, r10
0x140005e0b  xor     rdx, rax
0x140005e0e  mov     rcx, rdx; StackCookie
0x140005e11  call    __security_check_cookie
0x140005e16  add     rsp, 28h
0x140005e1a  retn
```
