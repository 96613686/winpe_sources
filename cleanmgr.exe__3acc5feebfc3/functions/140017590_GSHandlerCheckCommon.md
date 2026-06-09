# __GSHandlerCheckCommon

- ea: `0x140017590`
- end: `0x1400175f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001756c`
- `0x1400175fc`

## callees

- `0x1400029a0`
- `0x140017590`

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
0x140017590  mov     r10, rcx
0x140017593  mov     r11, rdx
0x140017596  mov     ecx, [r8]
0x140017599  and     ecx, 0FFFFFFF8h
0x14001759c  test    byte ptr [r8], 4
0x1400175a0  jz      short loc_1400175B7
0x1400175a2  mov     eax, [r8+8]
0x1400175a6  movsxd  r9, dword ptr [r8+4]
0x1400175aa  neg     eax
0x1400175ac  movsxd  rdx, eax
0x1400175af  add     r9, r10
0x1400175b2  and     r9, rdx
0x1400175b5  jmp     short loc_1400175BA
0x1400175b7  mov     r9, r10
0x1400175ba  movsxd  rax, ecx
0x1400175bd  mov     rdx, [rax+r9]
0x1400175c1  mov     rax, [r11+10h]
0x1400175c5  mov     ecx, [rax+8]
0x1400175c8  mov     rax, [r11+8]
0x1400175cc  test    byte ptr [rcx+rax+3], 0Fh
0x1400175d1  jz      short loc_1400175E5
0x1400175d3  movzx   eax, byte ptr [rcx+rax+3]
0x1400175d8  mov     ecx, 0FFFFFFF0h
0x1400175dd  and     rax, rcx
0x1400175e0  add     rax, r10
0x1400175e3  jmp     short loc_1400175E8
0x1400175e5  mov     rax, r10
0x1400175e8  xor     rdx, rax
0x1400175eb  mov     rcx, rdx; StackCookie
0x1400175ee  jmp     __security_check_cookie
```
