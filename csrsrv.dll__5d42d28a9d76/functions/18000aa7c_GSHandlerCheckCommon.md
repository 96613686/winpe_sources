# __GSHandlerCheckCommon

- ea: `0x18000aa7c`
- end: `0x18000aadf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aa58`
- `0x18000aae8`

## callees

- `0x18000aa7c`
- `0x18000ab80`

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
0x18000aa7c  mov     r10, rcx
0x18000aa7f  mov     r11, rdx
0x18000aa82  mov     ecx, [r8]
0x18000aa85  and     ecx, 0FFFFFFF8h
0x18000aa88  test    byte ptr [r8], 4
0x18000aa8c  jz      short loc_18000AAA3
0x18000aa8e  mov     eax, [r8+8]
0x18000aa92  movsxd  r9, dword ptr [r8+4]
0x18000aa96  neg     eax
0x18000aa98  movsxd  rdx, eax
0x18000aa9b  add     r9, r10
0x18000aa9e  and     r9, rdx
0x18000aaa1  jmp     short loc_18000AAA6
0x18000aaa3  mov     r9, r10
0x18000aaa6  movsxd  rax, ecx
0x18000aaa9  mov     rdx, [rax+r9]
0x18000aaad  mov     rax, [r11+10h]
0x18000aab1  mov     ecx, [rax+8]
0x18000aab4  mov     rax, [r11+8]
0x18000aab8  test    byte ptr [rcx+rax+3], 0Fh
0x18000aabd  jz      short loc_18000AAD1
0x18000aabf  movzx   eax, byte ptr [rcx+rax+3]
0x18000aac4  mov     ecx, 0FFFFFFF0h
0x18000aac9  and     rax, rcx
0x18000aacc  add     rax, r10
0x18000aacf  jmp     short loc_18000AAD4
0x18000aad1  mov     rax, r10
0x18000aad4  xor     rdx, rax
0x18000aad7  mov     rcx, rdx; StackCookie
0x18000aada  jmp     __security_check_cookie
```
