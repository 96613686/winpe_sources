# __GSHandlerCheckCommon

- ea: `0x180013c94`
- end: `0x180013cf7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013c70`
- `0x180013d00`

## callees

- `0x180001540`
- `0x180013c94`

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
0x180013c94  mov     r10, rcx
0x180013c97  mov     r11, rdx
0x180013c9a  mov     ecx, [r8]
0x180013c9d  and     ecx, 0FFFFFFF8h
0x180013ca0  test    byte ptr [r8], 4
0x180013ca4  jz      short loc_180013CBB
0x180013ca6  mov     eax, [r8+8]
0x180013caa  movsxd  r9, dword ptr [r8+4]
0x180013cae  neg     eax
0x180013cb0  movsxd  rdx, eax
0x180013cb3  add     r9, r10
0x180013cb6  and     r9, rdx
0x180013cb9  jmp     short loc_180013CBE
0x180013cbb  mov     r9, r10
0x180013cbe  movsxd  rax, ecx
0x180013cc1  mov     rdx, [rax+r9]
0x180013cc5  mov     rax, [r11+10h]
0x180013cc9  mov     ecx, [rax+8]
0x180013ccc  mov     rax, [r11+8]
0x180013cd0  test    byte ptr [rcx+rax+3], 0Fh
0x180013cd5  jz      short loc_180013CE9
0x180013cd7  movzx   eax, byte ptr [rcx+rax+3]
0x180013cdc  mov     ecx, 0FFFFFFF0h
0x180013ce1  and     rax, rcx
0x180013ce4  add     rax, r10
0x180013ce7  jmp     short loc_180013CEC
0x180013ce9  mov     rax, r10
0x180013cec  xor     rdx, rax
0x180013cef  mov     rcx, rdx; StackCookie
0x180013cf2  jmp     __security_check_cookie
```
