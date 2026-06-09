# __GSHandlerCheckCommon

- ea: `0x140007e8c`
- end: `0x140007efc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007e68`

## callees

- `0x140007e8c`
- `0x140007fc0`

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
0x140007e8c  sub     rsp, 28h
0x140007e90  mov     eax, [r8]
0x140007e93  mov     r10, rcx
0x140007e96  mov     ecx, eax
0x140007e98  mov     r11, rdx
0x140007e9b  and     ecx, 0FFFFFFF8h
0x140007e9e  test    al, 4
0x140007ea0  jz      short loc_140007EB7
0x140007ea2  mov     eax, [r8+8]
0x140007ea6  movsxd  r9, dword ptr [r8+4]
0x140007eaa  neg     eax
0x140007eac  movsxd  rdx, eax
0x140007eaf  add     r9, r10
0x140007eb2  and     r9, rdx
0x140007eb5  jmp     short loc_140007EBA
0x140007eb7  mov     r9, r10
0x140007eba  movsxd  rax, ecx
0x140007ebd  mov     rdx, [rax+r9]
0x140007ec1  mov     rax, [r11+10h]
0x140007ec5  mov     ecx, [rax+8]
0x140007ec8  mov     rax, [r11+8]
0x140007ecc  movzx   r8d, byte ptr [rcx+rax+3]
0x140007ed2  test    r8b, 0Fh
0x140007ed6  jz      short loc_140007EE8
0x140007ed8  mov     eax, r8d
0x140007edb  mov     ecx, 0FFFFFFF0h
0x140007ee0  and     rax, rcx
0x140007ee3  add     rax, r10
0x140007ee6  jmp     short loc_140007EEB
0x140007ee8  mov     rax, r10
0x140007eeb  xor     rdx, rax
0x140007eee  mov     rcx, rdx; StackCookie
0x140007ef1  call    __security_check_cookie
0x140007ef6  add     rsp, 28h
0x140007efa  retn
```
