# __GSHandlerCheckCommon

- ea: `0x140005aac`
- end: `0x140005b1c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005a88`

## callees

- `0x140005aac`
- `0x140005bf0`

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
0x140005aac  sub     rsp, 28h
0x140005ab0  mov     eax, [r8]
0x140005ab3  mov     r10, rcx
0x140005ab6  mov     ecx, eax
0x140005ab8  mov     r11, rdx
0x140005abb  and     ecx, 0FFFFFFF8h
0x140005abe  test    al, 4
0x140005ac0  jz      short loc_140005AD7
0x140005ac2  mov     eax, [r8+8]
0x140005ac6  movsxd  r9, dword ptr [r8+4]
0x140005aca  neg     eax
0x140005acc  movsxd  rdx, eax
0x140005acf  add     r9, r10
0x140005ad2  and     r9, rdx
0x140005ad5  jmp     short loc_140005ADA
0x140005ad7  mov     r9, r10
0x140005ada  movsxd  rax, ecx
0x140005add  mov     rdx, [rax+r9]
0x140005ae1  mov     rax, [r11+10h]
0x140005ae5  mov     ecx, [rax+8]
0x140005ae8  mov     rax, [r11+8]
0x140005aec  movzx   r8d, byte ptr [rcx+rax+3]
0x140005af2  test    r8b, 0Fh
0x140005af6  jz      short loc_140005B08
0x140005af8  mov     eax, r8d
0x140005afb  mov     ecx, 0FFFFFFF0h
0x140005b00  and     rax, rcx
0x140005b03  add     rax, r10
0x140005b06  jmp     short loc_140005B0B
0x140005b08  mov     rax, r10
0x140005b0b  xor     rdx, rax
0x140005b0e  mov     rcx, rdx; StackCookie
0x140005b11  call    __security_check_cookie
0x140005b16  add     rsp, 28h
0x140005b1a  retn
```
