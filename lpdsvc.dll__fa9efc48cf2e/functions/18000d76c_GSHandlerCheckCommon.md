# __GSHandlerCheckCommon

- ea: `0x18000d76c`
- end: `0x18000d7cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d748`

## callees

- `0x180001ce0`
- `0x18000d76c`

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
0x18000d76c  mov     r10, rcx
0x18000d76f  mov     r11, rdx
0x18000d772  mov     ecx, [r8]
0x18000d775  and     ecx, 0FFFFFFF8h
0x18000d778  test    byte ptr [r8], 4
0x18000d77c  jz      short loc_18000D793
0x18000d77e  mov     eax, [r8+8]
0x18000d782  movsxd  r9, dword ptr [r8+4]
0x18000d786  neg     eax
0x18000d788  movsxd  rdx, eax
0x18000d78b  add     r9, r10
0x18000d78e  and     r9, rdx
0x18000d791  jmp     short loc_18000D796
0x18000d793  mov     r9, r10
0x18000d796  movsxd  rax, ecx
0x18000d799  mov     rdx, [rax+r9]
0x18000d79d  mov     rax, [r11+10h]
0x18000d7a1  mov     ecx, [rax+8]
0x18000d7a4  mov     rax, [r11+8]
0x18000d7a8  test    byte ptr [rcx+rax+3], 0Fh
0x18000d7ad  jz      short loc_18000D7C1
0x18000d7af  movzx   eax, byte ptr [rcx+rax+3]
0x18000d7b4  mov     ecx, 0FFFFFFF0h
0x18000d7b9  and     rax, rcx
0x18000d7bc  add     rax, r10
0x18000d7bf  jmp     short loc_18000D7C4
0x18000d7c1  mov     rax, r10
0x18000d7c4  xor     rdx, rax
0x18000d7c7  mov     rcx, rdx; StackCookie
0x18000d7ca  jmp     __security_check_cookie
```
