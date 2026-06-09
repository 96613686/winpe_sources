# __removelocaleref

- ea: `0x18002c15c`
- end: `0x18002c20b`
- name: `__removelocaleref`
- size: `175`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c350`
- `0x18002c6a0`
- `0x18002cfec`
- `0x18002d060`
- `0x18003deb0`

## callees

- `0x18002c15c`

## pseudocode

```c
__int64 __fastcall _removelocaleref(__int64 a1)
{
  volatile signed __int32 *v1; // rax
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rax
  volatile signed __int32 *v4; // rax
  __int64 i; // rdx
  __int64 v6; // rax
  volatile signed __int32 *v7; // r8
  volatile signed __int32 *v8; // r8

  if ( a1 )
  {
    _InterlockedAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
    v1 = *(volatile signed __int32 **)(a1 + 272);
    if ( v1 )
      _InterlockedAdd(v1, 0xFFFFFFFF);
    v2 = *(volatile signed __int32 **)(a1 + 288);
    if ( v2 )
      _InterlockedAdd(v2, 0xFFFFFFFF);
    v3 = *(volatile signed __int32 **)(a1 + 280);
    if ( v3 )
      _InterlockedAdd(v3, 0xFFFFFFFF);
    v4 = *(volatile signed __int32 **)(a1 + 304);
    if ( v4 )
      _InterlockedAdd(v4, 0xFFFFFFFF);
    for ( i = 0; i != 6; ++i )
    {
      v6 = 32 * i;
      if ( *(char **)(32 * i + a1 + 72) != "C" )
      {
        v7 = *(volatile signed __int32 **)(v6 + a1 + 88);
        if ( v7 )
          _InterlockedAdd(v7, 0xFFFFFFFF);
      }
      if ( *(_QWORD *)(v6 + a1 + 80) )
      {
        v8 = *(volatile signed __int32 **)(32 * (i + 3) + a1);
        if ( v8 )
          _InterlockedAdd(v8, 0xFFFFFFFF);
      }
    }
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 344) + 352LL), 0xFFFFFFFF);
  }
  return a1;
}

```

## disassembly

```asm
0x18002c15c  test    rcx, rcx
0x18002c15f  jz      loc_18002C207
0x18002c165  or      r9d, 0FFFFFFFFh
0x18002c169  lock add [rcx], r9d
0x18002c16d  mov     rax, [rcx+110h]
0x18002c174  test    rax, rax
0x18002c177  jz      short loc_18002C17D
0x18002c179  lock add [rax], r9d
0x18002c17d  mov     rax, [rcx+120h]
0x18002c184  test    rax, rax
0x18002c187  jz      short loc_18002C18D
0x18002c189  lock add [rax], r9d
0x18002c18d  mov     rax, [rcx+118h]
0x18002c194  test    rax, rax
0x18002c197  jz      short loc_18002C19D
0x18002c199  lock add [rax], r9d
0x18002c19d  mov     rax, [rcx+130h]
0x18002c1a4  test    rax, rax
0x18002c1a7  jz      short loc_18002C1AD
0x18002c1a9  lock add [rax], r9d
0x18002c1ad  xor     edx, edx
0x18002c1af  mov     rax, rdx
0x18002c1b2  lea     r8, __clocalestr; "C"
0x18002c1b9  shl     rax, 5
0x18002c1bd  cmp     [rax+rcx+48h], r8
0x18002c1c2  jz      short loc_18002C1D2
0x18002c1c4  mov     r8, [rax+rcx+58h]
0x18002c1c9  test    r8, r8
0x18002c1cc  jz      short loc_18002C1D2
0x18002c1ce  lock add [r8], r9d
0x18002c1d2  cmp     qword ptr [rax+rcx+50h], 0
0x18002c1d8  jz      short loc_18002C1EF
0x18002c1da  lea     rax, [rdx+3]
0x18002c1de  shl     rax, 5
0x18002c1e2  mov     r8, [rax+rcx]
0x18002c1e6  test    r8, r8
0x18002c1e9  jz      short loc_18002C1EF
0x18002c1eb  lock add [r8], r9d
0x18002c1ef  inc     rdx
0x18002c1f2  cmp     rdx, 6
0x18002c1f6  jnz     short loc_18002C1AF
0x18002c1f8  mov     rax, [rcx+158h]
0x18002c1ff  lock add [rax+160h], r9d
0x18002c207  mov     rax, rcx
0x18002c20a  retn
```
