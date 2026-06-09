# CompareVolumeIDs(_volumeid const *,_volumeid const *)

- ea: `0x180003470`
- end: `0x18000349d`
- name: `?CompareVolumeIDs@@YA?AW4_comparisonresult@@PEBU_volumeid@@0@Z`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001b60`
- `0x180004eb0`
- `0x180005460`

## callees

- `0x180003470`

## pseudocode

```c
__int64 __fastcall CompareVolumeIDs(__int64 a1, __int64 a2)
{
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // edx

  v3 = *(_DWORD *)(a2 + 4);
  if ( *(_DWORD *)(a1 + 4) >= v3 )
  {
    if ( *(_DWORD *)(a1 + 4) > v3 )
      return 1;
    v4 = *(_DWORD *)(a2 + 8);
    v5 = *(_DWORD *)(a1 + 8);
    if ( v5 >= v4 )
      return v5 > v4;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180003470  mov     rax, rcx
0x180003473  mov     ecx, [rdx+4]
0x180003476  cmp     [rax+4], ecx
0x180003479  jb      short loc_180003497
0x18000347b  ja      short loc_180003490
0x18000347d  mov     ecx, [rdx+8]
0x180003480  mov     edx, [rax+8]
0x180003483  cmp     edx, ecx
0x180003485  jb      short loc_180003497
0x180003487  xor     eax, eax
0x180003489  cmp     edx, ecx
0x18000348b  setnbe  al
0x18000348e  retn
0x180003490  mov     eax, 1
0x180003495  retn
0x180003497  mov     eax, 0FFFFFFFFh
0x18000349c  retn
```
