# __GSHandlerCheckCommon

- ea: `0x140005e3c`
- end: `0x140005eac`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005e18`
- `0x140005eb4`

## callees

- `0x140005e3c`
- `0x140005f30`

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
0x140005e3c  sub     rsp, 28h
0x140005e40  mov     eax, [r8]
0x140005e43  mov     r10, rcx
0x140005e46  mov     ecx, eax
0x140005e48  mov     r11, rdx
0x140005e4b  and     ecx, 0FFFFFFF8h
0x140005e4e  test    al, 4
0x140005e50  jz      short loc_140005E67
0x140005e52  mov     eax, [r8+8]
0x140005e56  movsxd  r9, dword ptr [r8+4]
0x140005e5a  neg     eax
0x140005e5c  movsxd  rdx, eax
0x140005e5f  add     r9, r10
0x140005e62  and     r9, rdx
0x140005e65  jmp     short loc_140005E6A
0x140005e67  mov     r9, r10
0x140005e6a  movsxd  rax, ecx
0x140005e6d  mov     rdx, [rax+r9]
0x140005e71  mov     rax, [r11+10h]
0x140005e75  mov     ecx, [rax+8]
0x140005e78  mov     rax, [r11+8]
0x140005e7c  movzx   r8d, byte ptr [rcx+rax+3]
0x140005e82  test    r8b, 0Fh
0x140005e86  jz      short loc_140005E98
0x140005e88  mov     eax, r8d
0x140005e8b  mov     ecx, 0FFFFFFF0h
0x140005e90  and     rax, rcx
0x140005e93  add     rax, r10
0x140005e96  jmp     short loc_140005E9B
0x140005e98  mov     rax, r10
0x140005e9b  xor     rdx, rax
0x140005e9e  mov     rcx, rdx; StackCookie
0x140005ea1  call    __security_check_cookie
0x140005ea6  add     rsp, 28h
0x140005eaa  retn
```
