# __GSHandlerCheckCommon

- ea: `0x180035770`
- end: `0x1800357d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003574c`
- `0x1800357dc`

## callees

- `0x180035770`
- `0x1800358a0`

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
0x180035770  mov     r10, rcx
0x180035773  mov     r11, rdx
0x180035776  mov     ecx, [r8]
0x180035779  and     ecx, 0FFFFFFF8h
0x18003577c  test    byte ptr [r8], 4
0x180035780  jz      short loc_180035797
0x180035782  mov     eax, [r8+8]
0x180035786  movsxd  r9, dword ptr [r8+4]
0x18003578a  neg     eax
0x18003578c  movsxd  rdx, eax
0x18003578f  add     r9, r10
0x180035792  and     r9, rdx
0x180035795  jmp     short loc_18003579A
0x180035797  mov     r9, r10
0x18003579a  movsxd  rax, ecx
0x18003579d  mov     rdx, [rax+r9]
0x1800357a1  mov     rax, [r11+10h]
0x1800357a5  mov     ecx, [rax+8]
0x1800357a8  mov     rax, [r11+8]
0x1800357ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800357b1  jz      short loc_1800357C5
0x1800357b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800357b8  mov     ecx, 0FFFFFFF0h
0x1800357bd  and     rax, rcx
0x1800357c0  add     rax, r10
0x1800357c3  jmp     short loc_1800357C8
0x1800357c5  mov     rax, r10
0x1800357c8  xor     rdx, rax
0x1800357cb  mov     rcx, rdx; StackCookie
0x1800357ce  jmp     __security_check_cookie
```
