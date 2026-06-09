# __GSHandlerCheckCommon

- ea: `0x14001a6e8`
- end: `0x14001a74b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a6c4`
- `0x14001a754`

## callees

- `0x140001570`
- `0x14001a6e8`

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
0x14001a6e8  mov     r10, rcx
0x14001a6eb  mov     r11, rdx
0x14001a6ee  mov     ecx, [r8]
0x14001a6f1  and     ecx, 0FFFFFFF8h
0x14001a6f4  test    byte ptr [r8], 4
0x14001a6f8  jz      short loc_14001A70F
0x14001a6fa  mov     eax, [r8+8]
0x14001a6fe  movsxd  r9, dword ptr [r8+4]
0x14001a702  neg     eax
0x14001a704  movsxd  rdx, eax
0x14001a707  add     r9, r10
0x14001a70a  and     r9, rdx
0x14001a70d  jmp     short loc_14001A712
0x14001a70f  mov     r9, r10
0x14001a712  movsxd  rax, ecx
0x14001a715  mov     rdx, [rax+r9]
0x14001a719  mov     rax, [r11+10h]
0x14001a71d  mov     ecx, [rax+8]
0x14001a720  mov     rax, [r11+8]
0x14001a724  test    byte ptr [rcx+rax+3], 0Fh
0x14001a729  jz      short loc_14001A73D
0x14001a72b  movzx   eax, byte ptr [rcx+rax+3]
0x14001a730  mov     ecx, 0FFFFFFF0h
0x14001a735  and     rax, rcx
0x14001a738  add     rax, r10
0x14001a73b  jmp     short loc_14001A740
0x14001a73d  mov     rax, r10
0x14001a740  xor     rdx, rax
0x14001a743  mov     rcx, rdx; StackCookie
0x14001a746  jmp     __security_check_cookie
```
