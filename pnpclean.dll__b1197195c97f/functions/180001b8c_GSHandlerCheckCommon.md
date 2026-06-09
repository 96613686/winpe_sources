# __GSHandlerCheckCommon

- ea: `0x180001b8c`
- end: `0x180001bef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001b68`

## callees

- `0x180001b8c`
- `0x180008e30`

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
0x180001b8c  mov     r10, rcx
0x180001b8f  mov     r11, rdx
0x180001b92  mov     ecx, [r8]
0x180001b95  and     ecx, 0FFFFFFF8h
0x180001b98  test    byte ptr [r8], 4
0x180001b9c  jz      short loc_180001BB3
0x180001b9e  mov     eax, [r8+8]
0x180001ba2  movsxd  r9, dword ptr [r8+4]
0x180001ba6  neg     eax
0x180001ba8  movsxd  rdx, eax
0x180001bab  add     r9, r10
0x180001bae  and     r9, rdx
0x180001bb1  jmp     short loc_180001BB6
0x180001bb3  mov     r9, r10
0x180001bb6  movsxd  rax, ecx
0x180001bb9  mov     rdx, [rax+r9]
0x180001bbd  mov     rax, [r11+10h]
0x180001bc1  mov     ecx, [rax+8]
0x180001bc4  mov     rax, [r11+8]
0x180001bc8  test    byte ptr [rcx+rax+3], 0Fh
0x180001bcd  jz      short loc_180001BE1
0x180001bcf  movzx   eax, byte ptr [rcx+rax+3]
0x180001bd4  mov     ecx, 0FFFFFFF0h
0x180001bd9  and     rax, rcx
0x180001bdc  add     rax, r10
0x180001bdf  jmp     short loc_180001BE4
0x180001be1  mov     rax, r10
0x180001be4  xor     rdx, rax
0x180001be7  mov     rcx, rdx; StackCookie
0x180001bea  jmp     __security_check_cookie
```
