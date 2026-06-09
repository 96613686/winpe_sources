# __GSHandlerCheckCommon

- ea: `0x180001e3c`
- end: `0x180001eac`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e18`

## callees

- `0x180001e3c`
- `0x180001f70`

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
0x180001e3c  sub     rsp, 28h
0x180001e40  mov     eax, [r8]
0x180001e43  mov     r10, rcx
0x180001e46  mov     ecx, eax
0x180001e48  mov     r11, rdx
0x180001e4b  and     ecx, 0FFFFFFF8h
0x180001e4e  test    al, 4
0x180001e50  jz      short loc_180001E67
0x180001e52  mov     eax, [r8+8]
0x180001e56  movsxd  r9, dword ptr [r8+4]
0x180001e5a  neg     eax
0x180001e5c  movsxd  rdx, eax
0x180001e5f  add     r9, r10
0x180001e62  and     r9, rdx
0x180001e65  jmp     short loc_180001E6A
0x180001e67  mov     r9, r10
0x180001e6a  movsxd  rax, ecx
0x180001e6d  mov     rdx, [rax+r9]
0x180001e71  mov     rax, [r11+10h]
0x180001e75  mov     ecx, [rax+8]
0x180001e78  mov     rax, [r11+8]
0x180001e7c  movzx   r8d, byte ptr [rcx+rax+3]
0x180001e82  test    r8b, 0Fh
0x180001e86  jz      short loc_180001E98
0x180001e88  mov     eax, r8d
0x180001e8b  mov     ecx, 0FFFFFFF0h
0x180001e90  and     rax, rcx
0x180001e93  add     rax, r10
0x180001e96  jmp     short loc_180001E9B
0x180001e98  mov     rax, r10
0x180001e9b  xor     rdx, rax
0x180001e9e  mov     rcx, rdx; StackCookie
0x180001ea1  call    __security_check_cookie
0x180001ea6  add     rsp, 28h
0x180001eaa  retn
```
