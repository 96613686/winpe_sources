# handle_beginning_of_uncompressed_block

- ea: `0x180012df4`
- end: `0x180012e5c`
- name: `handle_beginning_of_uncompressed_block`
- size: `104`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000548c`

## callees

- `0x180012df4`

## pseudocode

```c
__int64 __fastcall handle_beginning_of_uncompressed_block(__int64 a1)
{
  unsigned __int8 *v2; // rcx
  __int64 i; // r9

  *(_QWORD *)(a1 + 11016) -= 2LL;
  v2 = *(unsigned __int8 **)(a1 + 11016);
  if ( (unsigned __int64)(v2 + 12) >= *(_QWORD *)(a1 + 11024) )
    return 0;
  for ( i = 0; i != 3; ++i )
  {
    *(_DWORD *)(a1 + 4 * i + 16) = *v2 | ((v2[1] | (*((unsigned __int16 *)v2 + 1) << 8)) << 8);
    v2 = (unsigned __int8 *)(*(_QWORD *)(a1 + 11016) + 4LL);
    *(_QWORD *)(a1 + 11016) = v2;
  }
  return 1;
}

```

## disassembly

```asm
0x180012df4  add     qword ptr [rcx+2B08h], 0FFFFFFFFFFFFFFFEh
0x180012dfc  mov     r8, rcx
0x180012dff  mov     rcx, [rcx+2B08h]
0x180012e06  lea     rax, [rcx+0Ch]
0x180012e0a  cmp     rax, [r8+2B10h]
0x180012e11  jnb     short loc_180012E59
0x180012e13  xor     r9d, r9d
0x180012e16  movzx   eax, byte ptr [rcx+2]
0x180012e1a  movzx   edx, byte ptr [rcx+3]
0x180012e1e  shl     edx, 8
0x180012e21  or      edx, eax
0x180012e23  movzx   eax, byte ptr [rcx+1]
0x180012e27  movzx   ecx, byte ptr [rcx]
0x180012e2a  shl     edx, 8
0x180012e2d  or      edx, eax
0x180012e2f  shl     edx, 8
0x180012e32  or      edx, ecx
0x180012e34  mov     [r8+r9*4+10h], edx
0x180012e39  inc     r9
0x180012e3c  mov     rcx, [r8+2B08h]
0x180012e43  add     rcx, 4
0x180012e47  mov     [r8+2B08h], rcx
0x180012e4e  cmp     r9, 3
0x180012e52  jnz     short loc_180012E16
0x180012e54  lea     eax, [r9-2]
0x180012e58  retn
0x180012e59  xor     eax, eax
0x180012e5b  retn
```
