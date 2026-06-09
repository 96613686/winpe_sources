# __GSHandlerCheckCommon

- ea: `0x140005910`
- end: `0x140005973`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400058ec`

## callees

- `0x140005910`
- `0x1400059b0`

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
0x140005910  mov     r10, rcx
0x140005913  mov     r11, rdx
0x140005916  mov     ecx, [r8]
0x140005919  and     ecx, 0FFFFFFF8h
0x14000591c  test    byte ptr [r8], 4
0x140005920  jz      short loc_140005937
0x140005922  mov     eax, [r8+8]
0x140005926  movsxd  r9, dword ptr [r8+4]
0x14000592a  neg     eax
0x14000592c  movsxd  rdx, eax
0x14000592f  add     r9, r10
0x140005932  and     r9, rdx
0x140005935  jmp     short loc_14000593A
0x140005937  mov     r9, r10
0x14000593a  movsxd  rax, ecx
0x14000593d  mov     rdx, [rax+r9]
0x140005941  mov     rax, [r11+10h]
0x140005945  mov     ecx, [rax+8]
0x140005948  mov     rax, [r11+8]
0x14000594c  test    byte ptr [rcx+rax+3], 0Fh
0x140005951  jz      short loc_140005965
0x140005953  movzx   eax, byte ptr [rcx+rax+3]
0x140005958  mov     ecx, 0FFFFFFF0h
0x14000595d  and     rax, rcx
0x140005960  add     rax, r10
0x140005963  jmp     short loc_140005968
0x140005965  mov     rax, r10
0x140005968  xor     rdx, rax
0x14000596b  mov     rcx, rdx; StackCookie
0x14000596e  jmp     __security_check_cookie
```
