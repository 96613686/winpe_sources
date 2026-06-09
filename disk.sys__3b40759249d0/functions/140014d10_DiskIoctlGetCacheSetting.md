# DiskIoctlGetCacheSetting

- ea: `0x140014d10`
- end: `0x140014d7b`
- name: `DiskIoctlGetCacheSetting`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140014d10`

## pseudocode

```c
__int64 __fastcall DiskIoctlGetCacheSetting(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  __int64 result; // rax

  if ( *(_DWORD *)(a2[23] + 8LL) < 0xCu )
    return 3221225507LL;
  v2 = *(_QWORD *)(a1 + 64);
  v3 = a2[3];
  *(_QWORD *)v3 = 12;
  if ( (*(_DWORD *)(v2 + 876) & 0x80u) != 0 )
    *(_DWORD *)(v3 + 4) = 1;
  if ( (*(_DWORD *)(v2 + 876) & 0x40) != 0 )
    *(_DWORD *)(v3 + 4) = 2;
  result = 0;
  *(_BYTE *)(v3 + 8) = (*(_WORD *)(v2 + 640) & 0x10) != 0;
  a2[7] = 12;
  return result;
}

```

## disassembly

```asm
0x140014d10  mov     rax, [rdx+0B8h]
0x140014d17  cmp     dword ptr [rax+8], 0Ch
0x140014d1b  jb      short loc_140014D75
0x140014d1d  mov     r9, [rcx+40h]
0x140014d21  xor     r10d, r10d
0x140014d24  mov     r8, [rdx+18h]
0x140014d28  mov     qword ptr [r8], 0Ch
0x140014d2f  mov     eax, [r9+36Ch]
0x140014d36  test    al, al
0x140014d38  jns     short loc_140014D42
0x140014d3a  mov     dword ptr [r8+4], 1
0x140014d42  mov     ecx, [r9+36Ch]
0x140014d49  test    cl, 40h
0x140014d4c  jz      short loc_140014D56
0x140014d4e  mov     dword ptr [r8+4], 2
0x140014d56  movzx   ecx, word ptr [r9+280h]
0x140014d5e  mov     eax, r10d
0x140014d61  shr     cl, 4
0x140014d64  and     cl, 1
0x140014d67  mov     [r8+8], cl
0x140014d6b  mov     qword ptr [rdx+38h], 0Ch
0x140014d73  retn
0x140014d75  mov     eax, 0C0000023h
0x140014d7a  retn
```
