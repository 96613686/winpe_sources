# __GSHandlerCheckCommon

- ea: `0x180009814`
- end: `0x180009877`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800097f0`
- `0x180009880`

## callees

- `0x180009814`
- `0x180009930`

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
0x180009814  mov     r10, rcx
0x180009817  mov     r11, rdx
0x18000981a  mov     ecx, [r8]
0x18000981d  and     ecx, 0FFFFFFF8h
0x180009820  test    byte ptr [r8], 4
0x180009824  jz      short loc_18000983B
0x180009826  mov     eax, [r8+8]
0x18000982a  movsxd  r9, dword ptr [r8+4]
0x18000982e  neg     eax
0x180009830  movsxd  rdx, eax
0x180009833  add     r9, r10
0x180009836  and     r9, rdx
0x180009839  jmp     short loc_18000983E
0x18000983b  mov     r9, r10
0x18000983e  movsxd  rax, ecx
0x180009841  mov     rdx, [rax+r9]
0x180009845  mov     rax, [r11+10h]
0x180009849  mov     ecx, [rax+8]
0x18000984c  mov     rax, [r11+8]
0x180009850  test    byte ptr [rcx+rax+3], 0Fh
0x180009855  jz      short loc_180009869
0x180009857  movzx   eax, byte ptr [rcx+rax+3]
0x18000985c  mov     ecx, 0FFFFFFF0h
0x180009861  and     rax, rcx
0x180009864  add     rax, r10
0x180009867  jmp     short loc_18000986C
0x180009869  mov     rax, r10
0x18000986c  xor     rdx, rax
0x18000986f  mov     rcx, rdx; StackCookie
0x180009872  jmp     __security_check_cookie
```
