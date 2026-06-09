# __GSHandlerCheckCommon

- ea: `0x14001debc`
- end: `0x14001df1f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001de98`
- `0x14001df28`
- `0x14001df90`

## callees

- `0x14001debc`
- `0x14001e050`

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
0x14001debc  mov     r10, rcx
0x14001debf  mov     r11, rdx
0x14001dec2  mov     ecx, [r8]
0x14001dec5  and     ecx, 0FFFFFFF8h
0x14001dec8  test    byte ptr [r8], 4
0x14001decc  jz      short loc_14001DEE3
0x14001dece  mov     eax, [r8+8]
0x14001ded2  movsxd  r9, dword ptr [r8+4]
0x14001ded6  neg     eax
0x14001ded8  movsxd  rdx, eax
0x14001dedb  add     r9, r10
0x14001dede  and     r9, rdx
0x14001dee1  jmp     short loc_14001DEE6
0x14001dee3  mov     r9, r10
0x14001dee6  movsxd  rax, ecx
0x14001dee9  mov     rdx, [rax+r9]
0x14001deed  mov     rax, [r11+10h]
0x14001def1  mov     ecx, [rax+8]
0x14001def4  mov     rax, [r11+8]
0x14001def8  test    byte ptr [rcx+rax+3], 0Fh
0x14001defd  jz      short loc_14001DF11
0x14001deff  movzx   eax, byte ptr [rcx+rax+3]
0x14001df04  mov     ecx, 0FFFFFFF0h
0x14001df09  and     rax, rcx
0x14001df0c  add     rax, r10
0x14001df0f  jmp     short loc_14001DF14
0x14001df11  mov     rax, r10
0x14001df14  xor     rdx, rax
0x14001df17  mov     rcx, rdx; StackCookie
0x14001df1a  jmp     __security_check_cookie
```
