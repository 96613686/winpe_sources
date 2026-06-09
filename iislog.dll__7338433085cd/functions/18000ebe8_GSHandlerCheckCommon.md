# __GSHandlerCheckCommon

- ea: `0x18000ebe8`
- end: `0x18000ec4b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ebc4`

## callees

- `0x18000ebe8`
- `0x18000eca0`

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
0x18000ebe8  mov     r10, rcx
0x18000ebeb  mov     r11, rdx
0x18000ebee  mov     ecx, [r8]
0x18000ebf1  and     ecx, 0FFFFFFF8h
0x18000ebf4  test    byte ptr [r8], 4
0x18000ebf8  jz      short loc_18000EC0F
0x18000ebfa  mov     eax, [r8+8]
0x18000ebfe  movsxd  r9, dword ptr [r8+4]
0x18000ec02  neg     eax
0x18000ec04  movsxd  rdx, eax
0x18000ec07  add     r9, r10
0x18000ec0a  and     r9, rdx
0x18000ec0d  jmp     short loc_18000EC12
0x18000ec0f  mov     r9, r10
0x18000ec12  movsxd  rax, ecx
0x18000ec15  mov     rdx, [rax+r9]
0x18000ec19  mov     rax, [r11+10h]
0x18000ec1d  mov     ecx, [rax+8]
0x18000ec20  mov     rax, [r11+8]
0x18000ec24  test    byte ptr [rcx+rax+3], 0Fh
0x18000ec29  jz      short loc_18000EC3D
0x18000ec2b  movzx   eax, byte ptr [rcx+rax+3]
0x18000ec30  mov     ecx, 0FFFFFFF0h
0x18000ec35  and     rax, rcx
0x18000ec38  add     rax, r10
0x18000ec3b  jmp     short loc_18000EC40
0x18000ec3d  mov     rax, r10
0x18000ec40  xor     rdx, rax
0x18000ec43  mov     rcx, rdx; StackCookie
0x18000ec46  jmp     __security_check_cookie
```
