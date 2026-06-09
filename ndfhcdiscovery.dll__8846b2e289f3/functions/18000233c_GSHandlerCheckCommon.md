# __GSHandlerCheckCommon

- ea: `0x18000233c`
- end: `0x18000239f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002318`
- `0x180013610`

## callees

- `0x18000233c`
- `0x1800136b0`

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
0x18000233c  mov     r10, rcx
0x18000233f  mov     r11, rdx
0x180002342  mov     ecx, [r8]
0x180002345  and     ecx, 0FFFFFFF8h
0x180002348  test    byte ptr [r8], 4
0x18000234c  jz      short loc_180002363
0x18000234e  mov     eax, [r8+8]
0x180002352  movsxd  r9, dword ptr [r8+4]
0x180002356  neg     eax
0x180002358  movsxd  rdx, eax
0x18000235b  add     r9, r10
0x18000235e  and     r9, rdx
0x180002361  jmp     short loc_180002366
0x180002363  mov     r9, r10
0x180002366  movsxd  rax, ecx
0x180002369  mov     rdx, [rax+r9]
0x18000236d  mov     rax, [r11+10h]
0x180002371  mov     ecx, [rax+8]
0x180002374  mov     rax, [r11+8]
0x180002378  test    byte ptr [rcx+rax+3], 0Fh
0x18000237d  jz      short loc_180002391
0x18000237f  movzx   eax, byte ptr [rcx+rax+3]
0x180002384  mov     ecx, 0FFFFFFF0h
0x180002389  and     rax, rcx
0x18000238c  add     rax, r10
0x18000238f  jmp     short loc_180002394
0x180002391  mov     rax, r10
0x180002394  xor     rdx, rax
0x180002397  mov     rcx, rdx; StackCookie
0x18000239a  jmp     __security_check_cookie
```
