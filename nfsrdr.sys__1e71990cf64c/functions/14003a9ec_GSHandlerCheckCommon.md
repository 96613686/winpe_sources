# __GSHandlerCheckCommon

- ea: `0x14003a9ec`
- end: `0x14003aa5c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003a9c8`
- `0x14003aa64`

## callees

- `0x14003a9ec`
- `0x14003aba0`

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
0x14003a9ec  sub     rsp, 28h
0x14003a9f0  mov     eax, [r8]
0x14003a9f3  mov     r10, rcx
0x14003a9f6  mov     ecx, eax
0x14003a9f8  mov     r11, rdx
0x14003a9fb  and     ecx, 0FFFFFFF8h
0x14003a9fe  test    al, 4
0x14003aa00  jz      short loc_14003AA17
0x14003aa02  mov     eax, [r8+8]
0x14003aa06  movsxd  r9, dword ptr [r8+4]
0x14003aa0a  neg     eax
0x14003aa0c  movsxd  rdx, eax
0x14003aa0f  add     r9, r10
0x14003aa12  and     r9, rdx
0x14003aa15  jmp     short loc_14003AA1A
0x14003aa17  mov     r9, r10
0x14003aa1a  movsxd  rax, ecx
0x14003aa1d  mov     rdx, [rax+r9]
0x14003aa21  mov     rax, [r11+10h]
0x14003aa25  mov     ecx, [rax+8]
0x14003aa28  mov     rax, [r11+8]
0x14003aa2c  movzx   r8d, byte ptr [rcx+rax+3]
0x14003aa32  test    r8b, 0Fh
0x14003aa36  jz      short loc_14003AA48
0x14003aa38  mov     eax, r8d
0x14003aa3b  mov     ecx, 0FFFFFFF0h
0x14003aa40  and     rax, rcx
0x14003aa43  add     rax, r10
0x14003aa46  jmp     short loc_14003AA4B
0x14003aa48  mov     rax, r10
0x14003aa4b  xor     rdx, rax
0x14003aa4e  mov     rcx, rdx; StackCookie
0x14003aa51  call    __security_check_cookie
0x14003aa56  add     rsp, 28h
0x14003aa5a  retn
```
