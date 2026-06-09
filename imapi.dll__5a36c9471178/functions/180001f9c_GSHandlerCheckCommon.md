# __GSHandlerCheckCommon

- ea: `0x180001f9c`
- end: `0x180001fff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f78`

## callees

- `0x180001f9c`
- `0x180018500`

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
0x180001f9c  mov     r10, rcx
0x180001f9f  mov     r11, rdx
0x180001fa2  mov     ecx, [r8]
0x180001fa5  and     ecx, 0FFFFFFF8h
0x180001fa8  test    byte ptr [r8], 4
0x180001fac  jz      short loc_180001FC3
0x180001fae  mov     eax, [r8+8]
0x180001fb2  movsxd  r9, dword ptr [r8+4]
0x180001fb6  neg     eax
0x180001fb8  movsxd  rdx, eax
0x180001fbb  add     r9, r10
0x180001fbe  and     r9, rdx
0x180001fc1  jmp     short loc_180001FC6
0x180001fc3  mov     r9, r10
0x180001fc6  movsxd  rax, ecx
0x180001fc9  mov     rdx, [rax+r9]
0x180001fcd  mov     rax, [r11+10h]
0x180001fd1  mov     ecx, [rax+8]
0x180001fd4  mov     rax, [r11+8]
0x180001fd8  test    byte ptr [rcx+rax+3], 0Fh
0x180001fdd  jz      short loc_180001FF1
0x180001fdf  movzx   eax, byte ptr [rcx+rax+3]
0x180001fe4  mov     ecx, 0FFFFFFF0h
0x180001fe9  and     rax, rcx
0x180001fec  add     rax, r10
0x180001fef  jmp     short loc_180001FF4
0x180001ff1  mov     rax, r10
0x180001ff4  xor     rdx, rax
0x180001ff7  mov     rcx, rdx; StackCookie
0x180001ffa  jmp     __security_check_cookie
```
