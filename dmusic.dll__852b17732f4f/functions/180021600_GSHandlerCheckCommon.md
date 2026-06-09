# __GSHandlerCheckCommon

- ea: `0x180021600`
- end: `0x180021663`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800215dc`
- `0x18002166c`
- `0x1800216d4`

## callees

- `0x1800016d0`
- `0x180021600`

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
0x180021600  mov     r10, rcx
0x180021603  mov     r11, rdx
0x180021606  mov     ecx, [r8]
0x180021609  and     ecx, 0FFFFFFF8h
0x18002160c  test    byte ptr [r8], 4
0x180021610  jz      short loc_180021627
0x180021612  mov     eax, [r8+8]
0x180021616  movsxd  r9, dword ptr [r8+4]
0x18002161a  neg     eax
0x18002161c  movsxd  rdx, eax
0x18002161f  add     r9, r10
0x180021622  and     r9, rdx
0x180021625  jmp     short loc_18002162A
0x180021627  mov     r9, r10
0x18002162a  movsxd  rax, ecx
0x18002162d  mov     rdx, [rax+r9]
0x180021631  mov     rax, [r11+10h]
0x180021635  mov     ecx, [rax+8]
0x180021638  mov     rax, [r11+8]
0x18002163c  test    byte ptr [rcx+rax+3], 0Fh
0x180021641  jz      short loc_180021655
0x180021643  movzx   eax, byte ptr [rcx+rax+3]
0x180021648  mov     ecx, 0FFFFFFF0h
0x18002164d  and     rax, rcx
0x180021650  add     rax, r10
0x180021653  jmp     short loc_180021658
0x180021655  mov     rax, r10
0x180021658  xor     rdx, rax
0x18002165b  mov     rcx, rdx; StackCookie
0x18002165e  jmp     __security_check_cookie
```
