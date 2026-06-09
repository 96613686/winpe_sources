# __GSHandlerCheckCommon

- ea: `0x180001d7c`
- end: `0x180001ddf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d58`

## callees

- `0x180001d7c`
- `0x180006030`

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
0x180001d7c  mov     r10, rcx
0x180001d7f  mov     r11, rdx
0x180001d82  mov     ecx, [r8]
0x180001d85  and     ecx, 0FFFFFFF8h
0x180001d88  test    byte ptr [r8], 4
0x180001d8c  jz      short loc_180001DA3
0x180001d8e  mov     eax, [r8+8]
0x180001d92  movsxd  r9, dword ptr [r8+4]
0x180001d96  neg     eax
0x180001d98  movsxd  rdx, eax
0x180001d9b  add     r9, r10
0x180001d9e  and     r9, rdx
0x180001da1  jmp     short loc_180001DA6
0x180001da3  mov     r9, r10
0x180001da6  movsxd  rax, ecx
0x180001da9  mov     rdx, [rax+r9]
0x180001dad  mov     rax, [r11+10h]
0x180001db1  mov     ecx, [rax+8]
0x180001db4  mov     rax, [r11+8]
0x180001db8  test    byte ptr [rcx+rax+3], 0Fh
0x180001dbd  jz      short loc_180001DD1
0x180001dbf  movzx   eax, byte ptr [rcx+rax+3]
0x180001dc4  mov     ecx, 0FFFFFFF0h
0x180001dc9  and     rax, rcx
0x180001dcc  add     rax, r10
0x180001dcf  jmp     short loc_180001DD4
0x180001dd1  mov     rax, r10
0x180001dd4  xor     rdx, rax
0x180001dd7  mov     rcx, rdx; StackCookie
0x180001dda  jmp     __security_check_cookie
```
