# __GSHandlerCheckCommon

- ea: `0x140005abc`
- end: `0x140005b2c`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005a98`
- `0x140005b34`

## callees

- `0x140005abc`
- `0x140005bb0`

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
0x140005abc  sub     rsp, 28h
0x140005ac0  mov     eax, [r8]
0x140005ac3  mov     r10, rcx
0x140005ac6  mov     ecx, eax
0x140005ac8  mov     r11, rdx
0x140005acb  and     ecx, 0FFFFFFF8h
0x140005ace  test    al, 4
0x140005ad0  jz      short loc_140005AE7
0x140005ad2  mov     eax, [r8+8]
0x140005ad6  movsxd  r9, dword ptr [r8+4]
0x140005ada  neg     eax
0x140005adc  movsxd  rdx, eax
0x140005adf  add     r9, r10
0x140005ae2  and     r9, rdx
0x140005ae5  jmp     short loc_140005AEA
0x140005ae7  mov     r9, r10
0x140005aea  movsxd  rax, ecx
0x140005aed  mov     rdx, [rax+r9]
0x140005af1  mov     rax, [r11+10h]
0x140005af5  mov     ecx, [rax+8]
0x140005af8  mov     rax, [r11+8]
0x140005afc  movzx   r8d, byte ptr [rcx+rax+3]
0x140005b02  test    r8b, 0Fh
0x140005b06  jz      short loc_140005B18
0x140005b08  mov     eax, r8d
0x140005b0b  mov     ecx, 0FFFFFFF0h
0x140005b10  and     rax, rcx
0x140005b13  add     rax, r10
0x140005b16  jmp     short loc_140005B1B
0x140005b18  mov     rax, r10
0x140005b1b  xor     rdx, rax
0x140005b1e  mov     rcx, rdx; StackCookie
0x140005b21  call    __security_check_cookie
0x140005b26  add     rsp, 28h
0x140005b2a  retn
```
