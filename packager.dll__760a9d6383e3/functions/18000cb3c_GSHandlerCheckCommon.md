# __GSHandlerCheckCommon

- ea: `0x18000cb3c`
- end: `0x18000cb9f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb18`

## callees

- `0x18000cb3c`
- `0x18000cbf0`

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
0x18000cb3c  mov     r10, rcx
0x18000cb3f  mov     r11, rdx
0x18000cb42  mov     ecx, [r8]
0x18000cb45  and     ecx, 0FFFFFFF8h
0x18000cb48  test    byte ptr [r8], 4
0x18000cb4c  jz      short loc_18000CB63
0x18000cb4e  mov     eax, [r8+8]
0x18000cb52  movsxd  r9, dword ptr [r8+4]
0x18000cb56  neg     eax
0x18000cb58  movsxd  rdx, eax
0x18000cb5b  add     r9, r10
0x18000cb5e  and     r9, rdx
0x18000cb61  jmp     short loc_18000CB66
0x18000cb63  mov     r9, r10
0x18000cb66  movsxd  rax, ecx
0x18000cb69  mov     rdx, [rax+r9]
0x18000cb6d  mov     rax, [r11+10h]
0x18000cb71  mov     ecx, [rax+8]
0x18000cb74  mov     rax, [r11+8]
0x18000cb78  test    byte ptr [rcx+rax+3], 0Fh
0x18000cb7d  jz      short loc_18000CB91
0x18000cb7f  movzx   eax, byte ptr [rcx+rax+3]
0x18000cb84  mov     ecx, 0FFFFFFF0h
0x18000cb89  and     rax, rcx
0x18000cb8c  add     rax, r10
0x18000cb8f  jmp     short loc_18000CB94
0x18000cb91  mov     rax, r10
0x18000cb94  xor     rdx, rax
0x18000cb97  mov     rcx, rdx; StackCookie
0x18000cb9a  jmp     __security_check_cookie
```
