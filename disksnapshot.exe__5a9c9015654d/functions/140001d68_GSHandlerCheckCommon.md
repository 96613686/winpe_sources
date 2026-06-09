# __GSHandlerCheckCommon

- ea: `0x140001d68`
- end: `0x140001dcb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001d44`
- `0x14000c480`

## callees

- `0x140001c50`
- `0x140001d68`

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
0x140001d68  mov     r10, rcx
0x140001d6b  mov     r11, rdx
0x140001d6e  mov     ecx, [r8]
0x140001d71  and     ecx, 0FFFFFFF8h
0x140001d74  test    byte ptr [r8], 4
0x140001d78  jz      short loc_140001D8F
0x140001d7a  mov     eax, [r8+8]
0x140001d7e  movsxd  r9, dword ptr [r8+4]
0x140001d82  neg     eax
0x140001d84  movsxd  rdx, eax
0x140001d87  add     r9, r10
0x140001d8a  and     r9, rdx
0x140001d8d  jmp     short loc_140001D92
0x140001d8f  mov     r9, r10
0x140001d92  movsxd  rax, ecx
0x140001d95  mov     rdx, [rax+r9]
0x140001d99  mov     rax, [r11+10h]
0x140001d9d  mov     ecx, [rax+8]
0x140001da0  mov     rax, [r11+8]
0x140001da4  test    byte ptr [rcx+rax+3], 0Fh
0x140001da9  jz      short loc_140001DBD
0x140001dab  movzx   eax, byte ptr [rcx+rax+3]
0x140001db0  mov     ecx, 0FFFFFFF0h
0x140001db5  and     rax, rcx
0x140001db8  add     rax, r10
0x140001dbb  jmp     short loc_140001DC0
0x140001dbd  mov     rax, r10
0x140001dc0  xor     rdx, rax
0x140001dc3  mov     rcx, rdx; StackCookie
0x140001dc6  jmp     __security_check_cookie
```
