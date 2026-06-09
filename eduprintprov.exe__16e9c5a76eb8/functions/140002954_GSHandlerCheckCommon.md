# __GSHandlerCheckCommon

- ea: `0x140002954`
- end: `0x1400029b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002930`
- `0x14001306c`

## callees

- `0x140002600`
- `0x140002954`

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
0x140002954  mov     r10, rcx
0x140002957  mov     r11, rdx
0x14000295a  mov     ecx, [r8]
0x14000295d  and     ecx, 0FFFFFFF8h
0x140002960  test    byte ptr [r8], 4
0x140002964  jz      short loc_14000297B
0x140002966  mov     eax, [r8+8]
0x14000296a  movsxd  r9, dword ptr [r8+4]
0x14000296e  neg     eax
0x140002970  movsxd  rdx, eax
0x140002973  add     r9, r10
0x140002976  and     r9, rdx
0x140002979  jmp     short loc_14000297E
0x14000297b  mov     r9, r10
0x14000297e  movsxd  rax, ecx
0x140002981  mov     rdx, [rax+r9]
0x140002985  mov     rax, [r11+10h]
0x140002989  mov     ecx, [rax+8]
0x14000298c  mov     rax, [r11+8]
0x140002990  test    byte ptr [rcx+rax+3], 0Fh
0x140002995  jz      short loc_1400029A9
0x140002997  movzx   eax, byte ptr [rcx+rax+3]
0x14000299c  mov     ecx, 0FFFFFFF0h
0x1400029a1  and     rax, rcx
0x1400029a4  add     rax, r10
0x1400029a7  jmp     short loc_1400029AC
0x1400029a9  mov     rax, r10
0x1400029ac  xor     rdx, rax
0x1400029af  mov     rcx, rdx; StackCookie
0x1400029b2  jmp     __security_check_cookie
```
