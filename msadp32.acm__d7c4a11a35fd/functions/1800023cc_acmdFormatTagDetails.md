# acmdFormatTagDetails

- ea: `0x1800023cc`
- end: `0x1800024a0`
- name: `acmdFormatTagDetails`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cd0`

## callees

- `0x1800023cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000245f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000245f`

## pseudocode

```c
__int64 __fastcall acmdFormatTagDetails(__int64 a1, __int64 a2, char a3)
{
  int v5; // r8d
  int v6; // r8d
  int v8; // ecx
  int v9; // ecx
  int v10; // eax
  int v11; // eax
  int v12; // eax

  v5 = a3 & 0xF;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 8;
      v8 = *(_DWORD *)(a2 + 8);
      if ( !v8 )
      {
LABEL_8:
        v10 = 2;
        goto LABEL_13;
      }
    }
    else
    {
      v8 = *(_DWORD *)(a2 + 8);
    }
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 1 )
        return 512;
      goto LABEL_8;
    }
    v10 = 1;
  }
  else
  {
    if ( *(_DWORD *)(a2 + 4) >= 2u )
      return 512;
    v10 = *((_DWORD *)&gauFormatTagIndexToTag + *(unsigned int *)(a2 + 4));
  }
LABEL_13:
  v11 = v10 - 1;
  if ( !v11 )
  {
    *(_DWORD *)(a2 + 4) = 0;
    *(_DWORD *)(a2 + 12) = 16;
    *(_DWORD *)(a2 + 20) = 16;
    *(_DWORD *)(a2 + 8) = 1;
    *(_DWORD *)(a2 + 16) = 1;
    *(_WORD *)(a2 + 24) = 0;
    goto LABEL_17;
  }
  if ( v11 != 1 )
    return 512;
  *(_DWORD *)(a2 + 4) = 1;
  *(_DWORD *)(a2 + 16) = 1;
  *(_DWORD *)(a2 + 8) = 2;
  *(_DWORD *)(a2 + 12) = 50;
  *(_DWORD *)(a2 + 20) = 8;
  LoadStringW(*(HINSTANCE *)(a1 + 24), 0xAu, (LPWSTR)(a2 + 24), 48);
LABEL_17:
  v12 = 120;
  if ( *(_DWORD *)a2 < 0x78u )
    v12 = *(_DWORD *)a2;
  *(_DWORD *)a2 = v12;
  return 0;
}

```

## disassembly

```asm
0x1800023cc  push    rbx
0x1800023ce  sub     rsp, 20h
0x1800023d2  mov     rbx, rdx
0x1800023d5  mov     edx, 1
0x1800023da  mov     r10, rcx
0x1800023dd  and     r8d, 0Fh
0x1800023e1  jz      short loc_180002418
0x1800023e3  sub     r8d, edx
0x1800023e6  jz      short loc_18000240F
0x1800023e8  cmp     r8d, edx
0x1800023eb  jz      short loc_1800023F5
0x1800023ed  lea     eax, [rdx+7]
0x1800023f0  jmp     loc_18000249A
0x1800023f5  mov     ecx, [rbx+8]
0x1800023f8  test    ecx, ecx
0x1800023fa  jz      short loc_180002408
0x1800023fc  sub     ecx, edx
0x1800023fe  jz      short loc_180002414
0x180002400  cmp     ecx, edx
0x180002402  jnz     loc_180002495
0x180002408  mov     eax, 2
0x18000240d  jmp     short loc_18000242B
0x18000240f  mov     ecx, [rbx+8]
0x180002412  jmp     short loc_1800023FC
0x180002414  mov     eax, edx
0x180002416  jmp     short loc_18000242B
0x180002418  cmp     dword ptr [rbx+4], 2
0x18000241c  jnb     short loc_180002495
0x18000241e  mov     eax, [rbx+4]
0x180002421  lea     rcx, gauFormatTagIndexToTag
0x180002428  mov     eax, [rcx+rax*4]
0x18000242b  sub     eax, edx
0x18000242d  jz      short loc_180002467
0x18000242f  cmp     eax, edx
0x180002431  jnz     short loc_180002495
0x180002433  mov     [rbx+4], edx
0x180002436  lea     r8, [rbx+18h]; lpBuffer
0x18000243a  mov     [rbx+10h], edx
0x18000243d  mov     edx, 0Ah; uID
0x180002442  mov     dword ptr [rbx+8], 2
0x180002449  mov     dword ptr [rbx+0Ch], 32h ; '2'
0x180002450  mov     dword ptr [rbx+14h], 8
0x180002457  mov     rcx, [r10+18h]; hInstance
0x18000245b  lea     r9d, [rdx+26h]; cchBufferMax
0x18000245f  call    cs:__imp_LoadStringW
0x180002465  jmp     short loc_180002485
0x180002467  mov     eax, 10h
0x18000246c  mov     dword ptr [rbx+4], 0
0x180002473  mov     [rbx+0Ch], eax
0x180002476  mov     [rbx+14h], eax
0x180002479  xor     eax, eax
0x18000247b  mov     [rbx+8], edx
0x18000247e  mov     [rbx+10h], edx
0x180002481  mov     [rbx+18h], ax
0x180002485  mov     eax, 78h ; 'x'
0x18000248a  cmp     [rbx], eax
0x18000248c  cmovb   eax, [rbx]
0x18000248f  mov     [rbx], eax
0x180002491  xor     eax, eax
0x180002493  jmp     short loc_18000249A
0x180002495  mov     eax, 200h
0x18000249a  add     rsp, 20h
0x18000249e  pop     rbx
0x18000249f  retn
```
