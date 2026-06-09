# __GSHandlerCheckCommon

- ea: `0x140002c3c`
- end: `0x140002cac`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002c18`

## callees

- `0x140002c3c`
- `0x140002d70`

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
0x140002c3c  sub     rsp, 28h
0x140002c40  mov     eax, [r8]
0x140002c43  mov     r10, rcx
0x140002c46  mov     ecx, eax
0x140002c48  mov     r11, rdx
0x140002c4b  and     ecx, 0FFFFFFF8h
0x140002c4e  test    al, 4
0x140002c50  jz      short loc_140002C67
0x140002c52  mov     eax, [r8+8]
0x140002c56  movsxd  r9, dword ptr [r8+4]
0x140002c5a  neg     eax
0x140002c5c  movsxd  rdx, eax
0x140002c5f  add     r9, r10
0x140002c62  and     r9, rdx
0x140002c65  jmp     short loc_140002C6A
0x140002c67  mov     r9, r10
0x140002c6a  movsxd  rax, ecx
0x140002c6d  mov     rdx, [rax+r9]
0x140002c71  mov     rax, [r11+10h]
0x140002c75  mov     ecx, [rax+8]
0x140002c78  mov     rax, [r11+8]
0x140002c7c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002c82  test    r8b, 0Fh
0x140002c86  jz      short loc_140002C98
0x140002c88  mov     eax, r8d
0x140002c8b  mov     ecx, 0FFFFFFF0h
0x140002c90  and     rax, rcx
0x140002c93  add     rax, r10
0x140002c96  jmp     short loc_140002C9B
0x140002c98  mov     rax, r10
0x140002c9b  xor     rdx, rax
0x140002c9e  mov     rcx, rdx; StackCookie
0x140002ca1  call    __security_check_cookie
0x140002ca6  add     rsp, 28h
0x140002caa  retn
```
