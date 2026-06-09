# __GSHandlerCheckCommon

- ea: `0x1400194f8`
- end: `0x14001955b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400194d4`
- `0x140019564`

## callees

- `0x1400194f8`
- `0x140019610`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1400194f8  mov     r10, rcx
0x1400194fb  mov     r11, rdx
0x1400194fe  mov     ecx, [r8]
0x140019501  and     ecx, 0FFFFFFF8h
0x140019504  test    byte ptr [r8], 4
0x140019508  jz      short loc_14001951F
0x14001950a  mov     eax, [r8+8]
0x14001950e  movsxd  r9, dword ptr [r8+4]
0x140019512  neg     eax
0x140019514  movsxd  rdx, eax
0x140019517  add     r9, r10
0x14001951a  and     r9, rdx
0x14001951d  jmp     short loc_140019522
0x14001951f  mov     r9, r10
0x140019522  movsxd  rax, ecx
0x140019525  mov     rdx, [rax+r9]
0x140019529  mov     rax, [r11+10h]
0x14001952d  mov     ecx, [rax+8]
0x140019530  mov     rax, [r11+8]
0x140019534  test    byte ptr [rcx+rax+3], 0Fh
0x140019539  jz      short loc_14001954D
0x14001953b  movzx   eax, byte ptr [rcx+rax+3]
0x140019540  mov     ecx, 0FFFFFFF0h
0x140019545  and     rax, rcx
0x140019548  add     rax, r10
0x14001954b  jmp     short loc_140019550
0x14001954d  mov     rax, r10
0x140019550  xor     rdx, rax
0x140019553  mov     rcx, rdx; StackCookie
0x140019556  jmp     __security_check_cookie
```
