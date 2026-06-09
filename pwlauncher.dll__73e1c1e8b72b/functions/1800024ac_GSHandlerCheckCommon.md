# __GSHandlerCheckCommon

- ea: `0x1800024ac`
- end: `0x18000250f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002488`
- `0x18000fd60`

## callees

- `0x1800024ac`
- `0x18000fe10`

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
0x1800024ac  mov     r10, rcx
0x1800024af  mov     r11, rdx
0x1800024b2  mov     ecx, [r8]
0x1800024b5  and     ecx, 0FFFFFFF8h
0x1800024b8  test    byte ptr [r8], 4
0x1800024bc  jz      short loc_1800024D3
0x1800024be  mov     eax, [r8+8]
0x1800024c2  movsxd  r9, dword ptr [r8+4]
0x1800024c6  neg     eax
0x1800024c8  movsxd  rdx, eax
0x1800024cb  add     r9, r10
0x1800024ce  and     r9, rdx
0x1800024d1  jmp     short loc_1800024D6
0x1800024d3  mov     r9, r10
0x1800024d6  movsxd  rax, ecx
0x1800024d9  mov     rdx, [rax+r9]
0x1800024dd  mov     rax, [r11+10h]
0x1800024e1  mov     ecx, [rax+8]
0x1800024e4  mov     rax, [r11+8]
0x1800024e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800024ed  jz      short loc_180002501
0x1800024ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800024f4  mov     ecx, 0FFFFFFF0h
0x1800024f9  and     rax, rcx
0x1800024fc  add     rax, r10
0x1800024ff  jmp     short loc_180002504
0x180002501  mov     rax, r10
0x180002504  xor     rdx, rax
0x180002507  mov     rcx, rdx; StackCookie
0x18000250a  jmp     __security_check_cookie
```
