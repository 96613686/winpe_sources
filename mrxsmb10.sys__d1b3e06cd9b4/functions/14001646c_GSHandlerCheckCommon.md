# __GSHandlerCheckCommon

- ea: `0x14001646c`
- end: `0x1400164dc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016448`
- `0x1400164e4`

## callees

- `0x14001646c`
- `0x140016560`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14001646c  sub     rsp, 28h
0x140016470  mov     eax, [r8]
0x140016473  mov     r10, rcx
0x140016476  mov     ecx, eax
0x140016478  mov     r11, rdx
0x14001647b  and     ecx, 0FFFFFFF8h
0x14001647e  test    al, 4
0x140016480  jz      short loc_140016497
0x140016482  mov     eax, [r8+8]
0x140016486  movsxd  r9, dword ptr [r8+4]
0x14001648a  neg     eax
0x14001648c  movsxd  rdx, eax
0x14001648f  add     r9, r10
0x140016492  and     r9, rdx
0x140016495  jmp     short loc_14001649A
0x140016497  mov     r9, r10
0x14001649a  movsxd  rax, ecx
0x14001649d  mov     rdx, [rax+r9]
0x1400164a1  mov     rax, [r11+10h]
0x1400164a5  mov     ecx, [rax+8]
0x1400164a8  mov     rax, [r11+8]
0x1400164ac  movzx   r8d, byte ptr [rcx+rax+3]
0x1400164b2  test    r8b, 0Fh
0x1400164b6  jz      short loc_1400164C8
0x1400164b8  mov     eax, r8d
0x1400164bb  mov     ecx, 0FFFFFFF0h
0x1400164c0  and     rax, rcx
0x1400164c3  add     rax, r10
0x1400164c6  jmp     short loc_1400164CB
0x1400164c8  mov     rax, r10
0x1400164cb  xor     rdx, rax
0x1400164ce  mov     rcx, rdx; StackCookie
0x1400164d1  call    __security_check_cookie
0x1400164d6  add     rsp, 28h
0x1400164da  retn
```
