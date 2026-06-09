# __GSHandlerCheckCommon

- ea: `0x140002c4c`
- end: `0x140002cbc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002c28`
- `0x140002cc4`

## callees

- `0x140002c4c`
- `0x140002df0`

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
0x140002c4c  sub     rsp, 28h
0x140002c50  mov     eax, [r8]
0x140002c53  mov     r10, rcx
0x140002c56  mov     ecx, eax
0x140002c58  mov     r11, rdx
0x140002c5b  and     ecx, 0FFFFFFF8h
0x140002c5e  test    al, 4
0x140002c60  jz      short loc_140002C77
0x140002c62  mov     eax, [r8+8]
0x140002c66  movsxd  r9, dword ptr [r8+4]
0x140002c6a  neg     eax
0x140002c6c  movsxd  rdx, eax
0x140002c6f  add     r9, r10
0x140002c72  and     r9, rdx
0x140002c75  jmp     short loc_140002C7A
0x140002c77  mov     r9, r10
0x140002c7a  movsxd  rax, ecx
0x140002c7d  mov     rdx, [rax+r9]
0x140002c81  mov     rax, [r11+10h]
0x140002c85  mov     ecx, [rax+8]
0x140002c88  mov     rax, [r11+8]
0x140002c8c  movzx   r8d, byte ptr [rcx+rax+3]
0x140002c92  test    r8b, 0Fh
0x140002c96  jz      short loc_140002CA8
0x140002c98  mov     eax, r8d
0x140002c9b  mov     ecx, 0FFFFFFF0h
0x140002ca0  and     rax, rcx
0x140002ca3  add     rax, r10
0x140002ca6  jmp     short loc_140002CAB
0x140002ca8  mov     rax, r10
0x140002cab  xor     rdx, rax
0x140002cae  mov     rcx, rdx; StackCookie
0x140002cb1  call    __security_check_cookie
0x140002cb6  add     rsp, 28h
0x140002cba  retn
```
