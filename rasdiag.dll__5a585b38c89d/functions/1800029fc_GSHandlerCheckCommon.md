# __GSHandlerCheckCommon

- ea: `0x1800029fc`
- end: `0x180002a5f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800029d8`
- `0x18000de54`

## callees

- `0x1800029fc`
- `0x18000df10`

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
0x1800029fc  mov     r10, rcx
0x1800029ff  mov     r11, rdx
0x180002a02  mov     ecx, [r8]
0x180002a05  and     ecx, 0FFFFFFF8h
0x180002a08  test    byte ptr [r8], 4
0x180002a0c  jz      short loc_180002A23
0x180002a0e  mov     eax, [r8+8]
0x180002a12  movsxd  r9, dword ptr [r8+4]
0x180002a16  neg     eax
0x180002a18  movsxd  rdx, eax
0x180002a1b  add     r9, r10
0x180002a1e  and     r9, rdx
0x180002a21  jmp     short loc_180002A26
0x180002a23  mov     r9, r10
0x180002a26  movsxd  rax, ecx
0x180002a29  mov     rdx, [rax+r9]
0x180002a2d  mov     rax, [r11+10h]
0x180002a31  mov     ecx, [rax+8]
0x180002a34  mov     rax, [r11+8]
0x180002a38  test    byte ptr [rcx+rax+3], 0Fh
0x180002a3d  jz      short loc_180002A51
0x180002a3f  movzx   eax, byte ptr [rcx+rax+3]
0x180002a44  mov     ecx, 0FFFFFFF0h
0x180002a49  and     rax, rcx
0x180002a4c  add     rax, r10
0x180002a4f  jmp     short loc_180002A54
0x180002a51  mov     rax, r10
0x180002a54  xor     rdx, rax
0x180002a57  mov     rcx, rdx; StackCookie
0x180002a5a  jmp     __security_check_cookie
```
