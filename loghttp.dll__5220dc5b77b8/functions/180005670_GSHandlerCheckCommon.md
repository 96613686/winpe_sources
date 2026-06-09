# __GSHandlerCheckCommon

- ea: `0x180005670`
- end: `0x1800056d3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000564c`

## callees

- `0x180005670`
- `0x180005720`

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
0x180005670  mov     r10, rcx
0x180005673  mov     r11, rdx
0x180005676  mov     ecx, [r8]
0x180005679  and     ecx, 0FFFFFFF8h
0x18000567c  test    byte ptr [r8], 4
0x180005680  jz      short loc_180005697
0x180005682  mov     eax, [r8+8]
0x180005686  movsxd  r9, dword ptr [r8+4]
0x18000568a  neg     eax
0x18000568c  movsxd  rdx, eax
0x18000568f  add     r9, r10
0x180005692  and     r9, rdx
0x180005695  jmp     short loc_18000569A
0x180005697  mov     r9, r10
0x18000569a  movsxd  rax, ecx
0x18000569d  mov     rdx, [rax+r9]
0x1800056a1  mov     rax, [r11+10h]
0x1800056a5  mov     ecx, [rax+8]
0x1800056a8  mov     rax, [r11+8]
0x1800056ac  test    byte ptr [rcx+rax+3], 0Fh
0x1800056b1  jz      short loc_1800056C5
0x1800056b3  movzx   eax, byte ptr [rcx+rax+3]
0x1800056b8  mov     ecx, 0FFFFFFF0h
0x1800056bd  and     rax, rcx
0x1800056c0  add     rax, r10
0x1800056c3  jmp     short loc_1800056C8
0x1800056c5  mov     rax, r10
0x1800056c8  xor     rdx, rax
0x1800056cb  mov     rcx, rdx; StackCookie
0x1800056ce  jmp     __security_check_cookie
```
