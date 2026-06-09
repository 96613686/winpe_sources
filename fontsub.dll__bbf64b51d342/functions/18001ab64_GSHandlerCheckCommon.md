# __GSHandlerCheckCommon

- ea: `0x18001ab64`
- end: `0x18001abc7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ab40`

## callees

- `0x18001ab64`
- `0x18001ac90`

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
0x18001ab64  mov     r10, rcx
0x18001ab67  mov     r11, rdx
0x18001ab6a  mov     ecx, [r8]
0x18001ab6d  and     ecx, 0FFFFFFF8h
0x18001ab70  test    byte ptr [r8], 4
0x18001ab74  jz      short loc_18001AB8B
0x18001ab76  mov     eax, [r8+8]
0x18001ab7a  movsxd  r9, dword ptr [r8+4]
0x18001ab7e  neg     eax
0x18001ab80  movsxd  rdx, eax
0x18001ab83  add     r9, r10
0x18001ab86  and     r9, rdx
0x18001ab89  jmp     short loc_18001AB8E
0x18001ab8b  mov     r9, r10
0x18001ab8e  movsxd  rax, ecx
0x18001ab91  mov     rdx, [rax+r9]
0x18001ab95  mov     rax, [r11+10h]
0x18001ab99  mov     ecx, [rax+8]
0x18001ab9c  mov     rax, [r11+8]
0x18001aba0  test    byte ptr [rcx+rax+3], 0Fh
0x18001aba5  jz      short loc_18001ABB9
0x18001aba7  movzx   eax, byte ptr [rcx+rax+3]
0x18001abac  mov     ecx, 0FFFFFFF0h
0x18001abb1  and     rax, rcx
0x18001abb4  add     rax, r10
0x18001abb7  jmp     short loc_18001ABBC
0x18001abb9  mov     rax, r10
0x18001abbc  xor     rdx, rax
0x18001abbf  mov     rcx, rdx; StackCookie
0x18001abc2  jmp     __security_check_cookie
```
