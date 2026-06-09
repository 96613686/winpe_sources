# CompareLinkInfoVolumes

- ea: `0x180005460`
- end: `0x1800054d1`
- name: `CompareLinkInfoVolumes`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003470`
- `0x1800043e4`
- `0x180005460`

## pseudocode

```c
__int64 __fastcall CompareLinkInfoVolumes(_DWORD *a1, __int64 a2)
{
  int v2; // eax

  v2 = a1[2] & 1;
  if ( v2 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
    return CompareVolumeIDs((__int64)a1 + (unsigned int)a1[3], a2 + *(unsigned int *)(a2 + 12));
  if ( (a1[2] & 2) != 0 && (*(_BYTE *)(a2 + 8) & 2) != 0 )
    return CompareCNRLinks((__int64)a1 + (unsigned int)a1[5], a2 + *(unsigned int *)(a2 + 20));
  return v2 != 0 ? -1 : 1;
}

```

## disassembly

```asm
0x180005460  xor     r8d, r8d
0x180005463  mov     r10, rcx
0x180005466  mov     r8b, 1
0x180005469  xor     ecx, ecx
0x18000546b  mov     r9, rdx
0x18000546e  mov     cl, r8b
0x180005471  test    r8d, r8d
0x180005474  jz      short loc_1800054CC
0x180005476  test    ecx, ecx
0x180005478  jz      short loc_1800054C5
0x18000547a  mov     eax, [r10+8]
0x18000547e  and     eax, 1
0x180005481  jz      short loc_18000549B
0x180005483  test    [rdx+8], r8b
0x180005487  jz      short loc_18000549B
0x180005489  mov     edx, [rdx+0Ch]
0x18000548c  mov     ecx, [r10+0Ch]
0x180005490  add     rdx, r9
0x180005493  add     rcx, r10
0x180005496  jmp     ?CompareVolumeIDs@@YA?AW4_comparisonresult@@PEBU_volumeid@@0@Z; CompareVolumeIDs(_volumeid const *,_volumeid const *)
0x18000549b  test    byte ptr [r10+8], 2
0x1800054a0  jz      short loc_1800054BA
0x1800054a2  test    byte ptr [rdx+8], 2
0x1800054a6  jz      short loc_1800054BA
0x1800054a8  mov     edx, [rdx+14h]
0x1800054ab  mov     ecx, [r10+14h]
0x1800054af  add     rdx, r9
0x1800054b2  add     rcx, r10
0x1800054b5  jmp     ?CompareCNRLinks@@YA?AW4_comparisonresult@@PEBU_cnrlink@@0@Z; CompareCNRLinks(_cnrlink const *,_cnrlink const *)
0x1800054ba  neg     eax
0x1800054bc  sbb     eax, eax
0x1800054be  and     eax, 0FFFFFFFEh
0x1800054c1  inc     eax
0x1800054c3  jmp     short locret_1800054D0
0x1800054c5  mov     eax, 1
0x1800054ca  jmp     short locret_1800054D0
0x1800054cc  neg     ecx
0x1800054ce  sbb     eax, eax
0x1800054d0  retn
```
