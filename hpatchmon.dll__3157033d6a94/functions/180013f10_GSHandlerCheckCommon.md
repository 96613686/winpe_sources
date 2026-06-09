# __GSHandlerCheckCommon

- ea: `0x180013f10`
- end: `0x180013f73`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013eec`
- `0x180013f7c`

## callees

- `0x180002270`
- `0x180013f10`

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
0x180013f10  mov     r10, rcx
0x180013f13  mov     r11, rdx
0x180013f16  mov     ecx, [r8]
0x180013f19  and     ecx, 0FFFFFFF8h
0x180013f1c  test    byte ptr [r8], 4
0x180013f20  jz      short loc_180013F37
0x180013f22  mov     eax, [r8+8]
0x180013f26  movsxd  r9, dword ptr [r8+4]
0x180013f2a  neg     eax
0x180013f2c  movsxd  rdx, eax
0x180013f2f  add     r9, r10
0x180013f32  and     r9, rdx
0x180013f35  jmp     short loc_180013F3A
0x180013f37  mov     r9, r10
0x180013f3a  movsxd  rax, ecx
0x180013f3d  mov     rdx, [rax+r9]
0x180013f41  mov     rax, [r11+10h]
0x180013f45  mov     ecx, [rax+8]
0x180013f48  mov     rax, [r11+8]
0x180013f4c  test    byte ptr [rcx+rax+3], 0Fh
0x180013f51  jz      short loc_180013F65
0x180013f53  movzx   eax, byte ptr [rcx+rax+3]
0x180013f58  mov     ecx, 0FFFFFFF0h
0x180013f5d  and     rax, rcx
0x180013f60  add     rax, r10
0x180013f63  jmp     short loc_180013F68
0x180013f65  mov     rax, r10
0x180013f68  xor     rdx, rax
0x180013f6b  mov     rcx, rdx; StackCookie
0x180013f6e  jmp     __security_check_cookie
```
