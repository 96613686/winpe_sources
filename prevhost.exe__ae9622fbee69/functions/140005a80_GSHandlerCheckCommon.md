# __GSHandlerCheckCommon

- ea: `0x140005a80`
- end: `0x140005ae3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005a5c`

## callees

- `0x140001470`
- `0x140005a80`

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
0x140005a80  mov     r10, rcx
0x140005a83  mov     r11, rdx
0x140005a86  mov     ecx, [r8]
0x140005a89  and     ecx, 0FFFFFFF8h
0x140005a8c  test    byte ptr [r8], 4
0x140005a90  jz      short loc_140005AA7
0x140005a92  mov     eax, [r8+8]
0x140005a96  movsxd  r9, dword ptr [r8+4]
0x140005a9a  neg     eax
0x140005a9c  movsxd  rdx, eax
0x140005a9f  add     r9, r10
0x140005aa2  and     r9, rdx
0x140005aa5  jmp     short loc_140005AAA
0x140005aa7  mov     r9, r10
0x140005aaa  movsxd  rax, ecx
0x140005aad  mov     rdx, [rax+r9]
0x140005ab1  mov     rax, [r11+10h]
0x140005ab5  mov     ecx, [rax+8]
0x140005ab8  mov     rax, [r11+8]
0x140005abc  test    byte ptr [rcx+rax+3], 0Fh
0x140005ac1  jz      short loc_140005AD5
0x140005ac3  movzx   eax, byte ptr [rcx+rax+3]
0x140005ac8  mov     ecx, 0FFFFFFF0h
0x140005acd  and     rax, rcx
0x140005ad0  add     rax, r10
0x140005ad3  jmp     short loc_140005AD8
0x140005ad5  mov     rax, r10
0x140005ad8  xor     rdx, rax
0x140005adb  mov     rcx, rdx; StackCookie
0x140005ade  jmp     __security_check_cookie
```
