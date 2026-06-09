# mwFindAnyFreeBlockNode

- ea: `0x180001db8`
- end: `0x180001def`
- name: `mwFindAnyFreeBlockNode`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001288`
- `0x180001aa8`
- `0x18000276c`

## callees

- `0x180001db8`
- `0x180003a44`

## pseudocode

```c
__int64 __fastcall mwFindAnyFreeBlockNode(__int64 a1)
{
  unsigned int v1; // r8d
  __int64 result; // rax
  __int64 v3; // rdx

  v1 = *(_DWORD *)(a1 + 128);
  result = 0;
  v3 = *(_QWORD *)(a1 + 104);
  if ( !v1 )
    return mwAllocMoreBlockNodes(a1);
  while ( *(_DWORD *)(v3 + 4) != -1 || *(_DWORD *)(v3 + 8) )
  {
    v3 += 16;
    result = (unsigned int)(result + 1);
    if ( (unsigned int)result >= v1 )
      return mwAllocMoreBlockNodes(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180001db8  sub     rsp, 28h
0x180001dbc  mov     r8d, [rcx+80h]
0x180001dc3  xor     eax, eax
0x180001dc5  mov     rdx, [rcx+68h]
0x180001dc9  test    r8d, r8d
0x180001dcc  jz      short loc_180001DE5
0x180001dce  cmp     dword ptr [rdx+4], 0FFFFFFFFh
0x180001dd2  jnz     short loc_180001DDA
0x180001dd4  cmp     dword ptr [rdx+8], 0
0x180001dd8  jz      short loc_180001DEA
0x180001dda  add     rdx, 10h
0x180001dde  inc     eax
0x180001de0  cmp     eax, r8d
0x180001de3  jb      short loc_180001DCE
0x180001de5  call    mwAllocMoreBlockNodes
0x180001dea  add     rsp, 28h
0x180001dee  retn
```
