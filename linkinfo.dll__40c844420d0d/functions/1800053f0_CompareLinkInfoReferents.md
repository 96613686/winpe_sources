# CompareLinkInfoReferents

- ea: `0x1800053f0`
- end: `0x180005457`
- name: `CompareLinkInfoReferents`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800043e4`
- `0x180004eb0`
- `0x1800053f0`

## pseudocode

```c
__int64 __fastcall CompareLinkInfoReferents(__int64 a1, __int64 a2)
{
  int v2; // eax

  v2 = *(_DWORD *)(a1 + 8) & 1;
  if ( v2 && (*(_BYTE *)(a2 + 8) & 1) != 0 )
    return CompareILinkInfoLocalData(a1, a2);
  if ( (*(_BYTE *)(a1 + 8) & 2) != 0 && (*(_BYTE *)(a2 + 8) & 2) != 0 )
    return CompareCNRLinks(a1 + *(unsigned int *)(a1 + 20), a2 + *(unsigned int *)(a2 + 20));
  return v2 != 0 ? -1 : 1;
}

```

## disassembly

```asm
0x1800053f0  xor     r8d, r8d
0x1800053f3  mov     r10, rcx
0x1800053f6  mov     r8b, 1
0x1800053f9  xor     ecx, ecx
0x1800053fb  mov     r9, rdx
0x1800053fe  mov     cl, r8b
0x180005401  test    r8d, r8d
0x180005404  jz      short loc_180005452
0x180005406  test    ecx, ecx
0x180005408  jz      short loc_18000544B
0x18000540a  mov     eax, [r10+8]
0x18000540e  and     eax, 1
0x180005411  jz      short loc_180005419
0x180005413  test    [rdx+8], r8b
0x180005417  jnz     short loc_180005443
0x180005419  test    byte ptr [r10+8], 2
0x18000541e  jz      short loc_180005438
0x180005420  test    byte ptr [rdx+8], 2
0x180005424  jz      short loc_180005438
0x180005426  mov     edx, [rdx+14h]
0x180005429  mov     ecx, [r10+14h]
0x18000542d  add     rdx, r9
0x180005430  add     rcx, r10
0x180005433  jmp     ?CompareCNRLinks@@YA?AW4_comparisonresult@@PEBU_cnrlink@@0@Z; CompareCNRLinks(_cnrlink const *,_cnrlink const *)
0x180005438  neg     eax
0x18000543a  sbb     eax, eax
0x18000543c  and     eax, 0FFFFFFFEh
0x18000543f  inc     eax
0x180005441  jmp     short locret_180005456
0x180005443  mov     rcx, r10
0x180005446  jmp     ?CompareILinkInfoLocalData@@YA?AW4_comparisonresult@@PEBU_ilinkinfoW@@0@Z; CompareILinkInfoLocalData(_ilinkinfoW const *,_ilinkinfoW const *)
0x18000544b  mov     eax, 1
0x180005450  jmp     short locret_180005456
0x180005452  neg     ecx
0x180005454  sbb     eax, eax
0x180005456  retn
```
