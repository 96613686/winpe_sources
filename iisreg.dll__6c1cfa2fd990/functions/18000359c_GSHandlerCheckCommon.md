# __GSHandlerCheckCommon

- ea: `0x18000359c`
- end: `0x1800035ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003578`

## callees

- `0x18000359c`
- `0x180003650`

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
0x18000359c  mov     r10, rcx
0x18000359f  mov     r11, rdx
0x1800035a2  mov     ecx, [r8]
0x1800035a5  and     ecx, 0FFFFFFF8h
0x1800035a8  test    byte ptr [r8], 4
0x1800035ac  jz      short loc_1800035C3
0x1800035ae  mov     eax, [r8+8]
0x1800035b2  movsxd  r9, dword ptr [r8+4]
0x1800035b6  neg     eax
0x1800035b8  movsxd  rdx, eax
0x1800035bb  add     r9, r10
0x1800035be  and     r9, rdx
0x1800035c1  jmp     short loc_1800035C6
0x1800035c3  mov     r9, r10
0x1800035c6  movsxd  rax, ecx
0x1800035c9  mov     rdx, [rax+r9]
0x1800035cd  mov     rax, [r11+10h]
0x1800035d1  mov     ecx, [rax+8]
0x1800035d4  mov     rax, [r11+8]
0x1800035d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800035dd  jz      short loc_1800035F1
0x1800035df  movzx   eax, byte ptr [rcx+rax+3]
0x1800035e4  mov     ecx, 0FFFFFFF0h
0x1800035e9  and     rax, rcx
0x1800035ec  add     rax, r10
0x1800035ef  jmp     short loc_1800035F4
0x1800035f1  mov     rax, r10
0x1800035f4  xor     rdx, rax
0x1800035f7  mov     rcx, rdx; StackCookie
0x1800035fa  jmp     __security_check_cookie
```
