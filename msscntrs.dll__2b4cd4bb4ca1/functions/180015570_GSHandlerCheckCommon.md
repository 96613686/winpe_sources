# __GSHandlerCheckCommon

- ea: `0x180015570`
- end: `0x1800155d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001554c`
- `0x1800155dc`

## callees

- `0x1800024a0`
- `0x180015570`

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
0x180015570  mov     r10, rcx
0x180015573  mov     r11, rdx
0x180015576  mov     ecx, [r8]
0x180015579  and     ecx, 0FFFFFFF8h
0x18001557c  test    byte ptr [r8], 4
0x180015580  jz      short loc_180015597
0x180015582  mov     eax, [r8+8]
0x180015586  movsxd  r9, dword ptr [r8+4]
0x18001558a  neg     eax
0x18001558c  movsxd  rdx, eax
0x18001558f  add     r9, r10
0x180015592  and     r9, rdx
0x180015595  jmp     short loc_18001559A
0x180015597  mov     r9, r10
0x18001559a  movsxd  rax, ecx
0x18001559d  mov     rdx, [rax+r9]
0x1800155a1  mov     rax, [r11+10h]
0x1800155a5  mov     ecx, [rax+8]
0x1800155a8  mov     rax, [r11+8]
0x1800155ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800155b1  jz      short loc_1800155C5
0x1800155b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800155b8  mov     ecx, 0FFFFFFF0h
0x1800155bd  and     rax, rcx
0x1800155c0  add     rax, r10
0x1800155c3  jmp     short loc_1800155C8
0x1800155c5  mov     rax, r10
0x1800155c8  xor     rdx, rax
0x1800155cb  mov     rcx, rdx; StackCookie
0x1800155ce  jmp     __security_check_cookie
```
