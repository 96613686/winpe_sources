# __GSHandlerCheckCommon

- ea: `0x180007d90`
- end: `0x180007df3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007d6c`
- `0x180007dfc`

## callees

- `0x180001be0`
- `0x180007d90`

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
0x180007d90  mov     r10, rcx
0x180007d93  mov     r11, rdx
0x180007d96  mov     ecx, [r8]
0x180007d99  and     ecx, 0FFFFFFF8h
0x180007d9c  test    byte ptr [r8], 4
0x180007da0  jz      short loc_180007DB7
0x180007da2  mov     eax, [r8+8]
0x180007da6  movsxd  r9, dword ptr [r8+4]
0x180007daa  neg     eax
0x180007dac  movsxd  rdx, eax
0x180007daf  add     r9, r10
0x180007db2  and     r9, rdx
0x180007db5  jmp     short loc_180007DBA
0x180007db7  mov     r9, r10
0x180007dba  movsxd  rax, ecx
0x180007dbd  mov     rdx, [rax+r9]
0x180007dc1  mov     rax, [r11+10h]
0x180007dc5  mov     ecx, [rax+8]
0x180007dc8  mov     rax, [r11+8]
0x180007dcc  test    byte ptr [rcx+rax+3], 0Fh
0x180007dd1  jz      short loc_180007DE5
0x180007dd3  movzx   eax, byte ptr [rcx+rax+3]
0x180007dd8  mov     ecx, 0FFFFFFF0h
0x180007ddd  and     rax, rcx
0x180007de0  add     rax, r10
0x180007de3  jmp     short loc_180007DE8
0x180007de5  mov     rax, r10
0x180007de8  xor     rdx, rax
0x180007deb  mov     rcx, rdx; StackCookie
0x180007dee  jmp     __security_check_cookie
```
