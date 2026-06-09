# __GSHandlerCheckCommon

- ea: `0x140004c9c`
- end: `0x140004d0c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004c78`

## callees

- `0x140004c9c`
- `0x140004dd0`

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
0x140004c9c  sub     rsp, 28h
0x140004ca0  mov     eax, [r8]
0x140004ca3  mov     r10, rcx
0x140004ca6  mov     ecx, eax
0x140004ca8  mov     r11, rdx
0x140004cab  and     ecx, 0FFFFFFF8h
0x140004cae  test    al, 4
0x140004cb0  jz      short loc_140004CC7
0x140004cb2  mov     eax, [r8+8]
0x140004cb6  movsxd  r9, dword ptr [r8+4]
0x140004cba  neg     eax
0x140004cbc  movsxd  rdx, eax
0x140004cbf  add     r9, r10
0x140004cc2  and     r9, rdx
0x140004cc5  jmp     short loc_140004CCA
0x140004cc7  mov     r9, r10
0x140004cca  movsxd  rax, ecx
0x140004ccd  mov     rdx, [rax+r9]
0x140004cd1  mov     rax, [r11+10h]
0x140004cd5  mov     ecx, [rax+8]
0x140004cd8  mov     rax, [r11+8]
0x140004cdc  movzx   r8d, byte ptr [rcx+rax+3]
0x140004ce2  test    r8b, 0Fh
0x140004ce6  jz      short loc_140004CF8
0x140004ce8  mov     eax, r8d
0x140004ceb  mov     ecx, 0FFFFFFF0h
0x140004cf0  and     rax, rcx
0x140004cf3  add     rax, r10
0x140004cf6  jmp     short loc_140004CFB
0x140004cf8  mov     rax, r10
0x140004cfb  xor     rdx, rax
0x140004cfe  mov     rcx, rdx; StackCookie
0x140004d01  call    __security_check_cookie
0x140004d06  add     rsp, 28h
0x140004d0a  retn
```
