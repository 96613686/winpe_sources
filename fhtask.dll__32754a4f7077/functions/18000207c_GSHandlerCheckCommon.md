# __GSHandlerCheckCommon

- ea: `0x18000207c`
- end: `0x1800020df`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002058`
- `0x180009940`

## callees

- `0x18000207c`
- `0x180009a00`

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
0x18000207c  mov     r10, rcx
0x18000207f  mov     r11, rdx
0x180002082  mov     ecx, [r8]
0x180002085  and     ecx, 0FFFFFFF8h
0x180002088  test    byte ptr [r8], 4
0x18000208c  jz      short loc_1800020A3
0x18000208e  mov     eax, [r8+8]
0x180002092  movsxd  r9, dword ptr [r8+4]
0x180002096  neg     eax
0x180002098  movsxd  rdx, eax
0x18000209b  add     r9, r10
0x18000209e  and     r9, rdx
0x1800020a1  jmp     short loc_1800020A6
0x1800020a3  mov     r9, r10
0x1800020a6  movsxd  rax, ecx
0x1800020a9  mov     rdx, [rax+r9]
0x1800020ad  mov     rax, [r11+10h]
0x1800020b1  mov     ecx, [rax+8]
0x1800020b4  mov     rax, [r11+8]
0x1800020b8  test    byte ptr [rcx+rax+3], 0Fh
0x1800020bd  jz      short loc_1800020D1
0x1800020bf  movzx   eax, byte ptr [rcx+rax+3]
0x1800020c4  mov     ecx, 0FFFFFFF0h
0x1800020c9  and     rax, rcx
0x1800020cc  add     rax, r10
0x1800020cf  jmp     short loc_1800020D4
0x1800020d1  mov     rax, r10
0x1800020d4  xor     rdx, rax
0x1800020d7  mov     rcx, rdx; StackCookie
0x1800020da  jmp     __security_check_cookie
```
