# __GSHandlerCheckCommon

- ea: `0x18000d79c`
- end: `0x18000d7ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d778`
- `0x1800118f0`

## callees

- `0x18000d79c`
- `0x180011980`

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
0x18000d79c  mov     r10, rcx
0x18000d79f  mov     r11, rdx
0x18000d7a2  mov     ecx, [r8]
0x18000d7a5  and     ecx, 0FFFFFFF8h
0x18000d7a8  test    byte ptr [r8], 4
0x18000d7ac  jz      short loc_18000D7C3
0x18000d7ae  mov     eax, [r8+8]
0x18000d7b2  movsxd  r9, dword ptr [r8+4]
0x18000d7b6  neg     eax
0x18000d7b8  movsxd  rdx, eax
0x18000d7bb  add     r9, r10
0x18000d7be  and     r9, rdx
0x18000d7c1  jmp     short loc_18000D7C6
0x18000d7c3  mov     r9, r10
0x18000d7c6  movsxd  rax, ecx
0x18000d7c9  mov     rdx, [rax+r9]
0x18000d7cd  mov     rax, [r11+10h]
0x18000d7d1  mov     ecx, [rax+8]
0x18000d7d4  mov     rax, [r11+8]
0x18000d7d8  test    byte ptr [rcx+rax+3], 0Fh
0x18000d7dd  jz      short loc_18000D7F1
0x18000d7df  movzx   eax, byte ptr [rcx+rax+3]
0x18000d7e4  mov     ecx, 0FFFFFFF0h
0x18000d7e9  and     rax, rcx
0x18000d7ec  add     rax, r10
0x18000d7ef  jmp     short loc_18000D7F4
0x18000d7f1  mov     rax, r10
0x18000d7f4  xor     rdx, rax
0x18000d7f7  mov     rcx, rdx; StackCookie
0x18000d7fa  jmp     __security_check_cookie
```
