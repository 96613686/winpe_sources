# __GSHandlerCheckCommon

- ea: `0x180004880`
- end: `0x1800048e3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000485c`

## callees

- `0x180004880`
- `0x180004930`

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
0x180004880  mov     r10, rcx
0x180004883  mov     r11, rdx
0x180004886  mov     ecx, [r8]
0x180004889  and     ecx, 0FFFFFFF8h
0x18000488c  test    byte ptr [r8], 4
0x180004890  jz      short loc_1800048A7
0x180004892  mov     eax, [r8+8]
0x180004896  movsxd  r9, dword ptr [r8+4]
0x18000489a  neg     eax
0x18000489c  movsxd  rdx, eax
0x18000489f  add     r9, r10
0x1800048a2  and     r9, rdx
0x1800048a5  jmp     short loc_1800048AA
0x1800048a7  mov     r9, r10
0x1800048aa  movsxd  rax, ecx
0x1800048ad  mov     rdx, [rax+r9]
0x1800048b1  mov     rax, [r11+10h]
0x1800048b5  mov     ecx, [rax+8]
0x1800048b8  mov     rax, [r11+8]
0x1800048bc  test    byte ptr [rcx+rax+3], 0Fh
0x1800048c1  jz      short loc_1800048D5
0x1800048c3  movzx   eax, byte ptr [rcx+rax+3]
0x1800048c8  mov     ecx, 0FFFFFFF0h
0x1800048cd  and     rax, rcx
0x1800048d0  add     rax, r10
0x1800048d3  jmp     short loc_1800048D8
0x1800048d5  mov     rax, r10
0x1800048d8  xor     rdx, rax
0x1800048db  mov     rcx, rdx; StackCookie
0x1800048de  jmp     __security_check_cookie
```
