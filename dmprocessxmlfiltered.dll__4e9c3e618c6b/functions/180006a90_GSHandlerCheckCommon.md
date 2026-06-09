# __GSHandlerCheckCommon

- ea: `0x180006a90`
- end: `0x180006af3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a6c`
- `0x180006afc`

## callees

- `0x180001520`
- `0x180006a90`

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
0x180006a90  mov     r10, rcx
0x180006a93  mov     r11, rdx
0x180006a96  mov     ecx, [r8]
0x180006a99  and     ecx, 0FFFFFFF8h
0x180006a9c  test    byte ptr [r8], 4
0x180006aa0  jz      short loc_180006AB7
0x180006aa2  mov     eax, [r8+8]
0x180006aa6  movsxd  r9, dword ptr [r8+4]
0x180006aaa  neg     eax
0x180006aac  movsxd  rdx, eax
0x180006aaf  add     r9, r10
0x180006ab2  and     r9, rdx
0x180006ab5  jmp     short loc_180006ABA
0x180006ab7  mov     r9, r10
0x180006aba  movsxd  rax, ecx
0x180006abd  mov     rdx, [rax+r9]
0x180006ac1  mov     rax, [r11+10h]
0x180006ac5  mov     ecx, [rax+8]
0x180006ac8  mov     rax, [r11+8]
0x180006acc  test    byte ptr [rcx+rax+3], 0Fh
0x180006ad1  jz      short loc_180006AE5
0x180006ad3  movzx   eax, byte ptr [rcx+rax+3]
0x180006ad8  mov     ecx, 0FFFFFFF0h
0x180006add  and     rax, rcx
0x180006ae0  add     rax, r10
0x180006ae3  jmp     short loc_180006AE8
0x180006ae5  mov     rax, r10
0x180006ae8  xor     rdx, rax
0x180006aeb  mov     rcx, rdx; StackCookie
0x180006aee  jmp     __security_check_cookie
```
