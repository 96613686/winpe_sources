# __GSHandlerCheckCommon

- ea: `0x18000d810`
- end: `0x18000d873`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d7ec`

## callees

- `0x18000d810`
- `0x18000d8d0`

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
0x18000d810  mov     r10, rcx
0x18000d813  mov     r11, rdx
0x18000d816  mov     ecx, [r8]
0x18000d819  and     ecx, 0FFFFFFF8h
0x18000d81c  test    byte ptr [r8], 4
0x18000d820  jz      short loc_18000D837
0x18000d822  mov     eax, [r8+8]
0x18000d826  movsxd  r9, dword ptr [r8+4]
0x18000d82a  neg     eax
0x18000d82c  movsxd  rdx, eax
0x18000d82f  add     r9, r10
0x18000d832  and     r9, rdx
0x18000d835  jmp     short loc_18000D83A
0x18000d837  mov     r9, r10
0x18000d83a  movsxd  rax, ecx
0x18000d83d  mov     rdx, [rax+r9]
0x18000d841  mov     rax, [r11+10h]
0x18000d845  mov     ecx, [rax+8]
0x18000d848  mov     rax, [r11+8]
0x18000d84c  test    byte ptr [rcx+rax+3], 0Fh
0x18000d851  jz      short loc_18000D865
0x18000d853  movzx   eax, byte ptr [rcx+rax+3]
0x18000d858  mov     ecx, 0FFFFFFF0h
0x18000d85d  and     rax, rcx
0x18000d860  add     rax, r10
0x18000d863  jmp     short loc_18000D868
0x18000d865  mov     rax, r10
0x18000d868  xor     rdx, rax
0x18000d86b  mov     rcx, rdx; StackCookie
0x18000d86e  jmp     __security_check_cookie
```
