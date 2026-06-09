# __GSHandlerCheckCommon

- ea: `0x1800056ac`
- end: `0x18000570f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005688`

## callees

- `0x1800056ac`
- `0x180005750`

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
0x1800056ac  mov     r10, rcx
0x1800056af  mov     r11, rdx
0x1800056b2  mov     ecx, [r8]
0x1800056b5  and     ecx, 0FFFFFFF8h
0x1800056b8  test    byte ptr [r8], 4
0x1800056bc  jz      short loc_1800056D3
0x1800056be  mov     eax, [r8+8]
0x1800056c2  movsxd  r9, dword ptr [r8+4]
0x1800056c6  neg     eax
0x1800056c8  movsxd  rdx, eax
0x1800056cb  add     r9, r10
0x1800056ce  and     r9, rdx
0x1800056d1  jmp     short loc_1800056D6
0x1800056d3  mov     r9, r10
0x1800056d6  movsxd  rax, ecx
0x1800056d9  mov     rdx, [rax+r9]
0x1800056dd  mov     rax, [r11+10h]
0x1800056e1  mov     ecx, [rax+8]
0x1800056e4  mov     rax, [r11+8]
0x1800056e8  test    byte ptr [rcx+rax+3], 0Fh
0x1800056ed  jz      short loc_180005701
0x1800056ef  movzx   eax, byte ptr [rcx+rax+3]
0x1800056f4  mov     ecx, 0FFFFFFF0h
0x1800056f9  and     rax, rcx
0x1800056fc  add     rax, r10
0x1800056ff  jmp     short loc_180005704
0x180005701  mov     rax, r10
0x180005704  xor     rdx, rax
0x180005707  mov     rcx, rdx; StackCookie
0x18000570a  jmp     __security_check_cookie
```
