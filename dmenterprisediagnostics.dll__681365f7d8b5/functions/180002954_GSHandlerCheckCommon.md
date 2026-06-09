# __GSHandlerCheckCommon

- ea: `0x180002954`
- end: `0x1800029b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002930`
- `0x1800251b0`

## callees

- `0x180001800`
- `0x180002954`

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
0x180002954  mov     r10, rcx
0x180002957  mov     r11, rdx
0x18000295a  mov     ecx, [r8]
0x18000295d  and     ecx, 0FFFFFFF8h
0x180002960  test    byte ptr [r8], 4
0x180002964  jz      short loc_18000297B
0x180002966  mov     eax, [r8+8]
0x18000296a  movsxd  r9, dword ptr [r8+4]
0x18000296e  neg     eax
0x180002970  movsxd  rdx, eax
0x180002973  add     r9, r10
0x180002976  and     r9, rdx
0x180002979  jmp     short loc_18000297E
0x18000297b  mov     r9, r10
0x18000297e  movsxd  rax, ecx
0x180002981  mov     rdx, [rax+r9]
0x180002985  mov     rax, [r11+10h]
0x180002989  mov     ecx, [rax+8]
0x18000298c  mov     rax, [r11+8]
0x180002990  test    byte ptr [rcx+rax+3], 0Fh
0x180002995  jz      short loc_1800029A9
0x180002997  movzx   eax, byte ptr [rcx+rax+3]
0x18000299c  mov     ecx, 0FFFFFFF0h
0x1800029a1  and     rax, rcx
0x1800029a4  add     rax, r10
0x1800029a7  jmp     short loc_1800029AC
0x1800029a9  mov     rax, r10
0x1800029ac  xor     rdx, rax
0x1800029af  mov     rcx, rdx; StackCookie
0x1800029b2  jmp     __security_check_cookie
```
