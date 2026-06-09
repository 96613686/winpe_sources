# __GSHandlerCheckCommon

- ea: `0x18000fa94`
- end: `0x18000faf7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fa70`

## callees

- `0x18000fa94`
- `0x18000fb50`

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
0x18000fa94  mov     r10, rcx
0x18000fa97  mov     r11, rdx
0x18000fa9a  mov     ecx, [r8]
0x18000fa9d  and     ecx, 0FFFFFFF8h
0x18000faa0  test    byte ptr [r8], 4
0x18000faa4  jz      short loc_18000FABB
0x18000faa6  mov     eax, [r8+8]
0x18000faaa  movsxd  r9, dword ptr [r8+4]
0x18000faae  neg     eax
0x18000fab0  movsxd  rdx, eax
0x18000fab3  add     r9, r10
0x18000fab6  and     r9, rdx
0x18000fab9  jmp     short loc_18000FABE
0x18000fabb  mov     r9, r10
0x18000fabe  movsxd  rax, ecx
0x18000fac1  mov     rdx, [rax+r9]
0x18000fac5  mov     rax, [r11+10h]
0x18000fac9  mov     ecx, [rax+8]
0x18000facc  mov     rax, [r11+8]
0x18000fad0  test    byte ptr [rcx+rax+3], 0Fh
0x18000fad5  jz      short loc_18000FAE9
0x18000fad7  movzx   eax, byte ptr [rcx+rax+3]
0x18000fadc  mov     ecx, 0FFFFFFF0h
0x18000fae1  and     rax, rcx
0x18000fae4  add     rax, r10
0x18000fae7  jmp     short loc_18000FAEC
0x18000fae9  mov     rax, r10
0x18000faec  xor     rdx, rax
0x18000faef  mov     rcx, rdx; StackCookie
0x18000faf2  jmp     __security_check_cookie
```
