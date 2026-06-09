# acmdFormatTagDetails

- ea: `0x180002750`
- end: `0x18000282c`
- name: `acmdFormatTagDetails`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x180002750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800027e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800027e6`

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
        v10 = 49;
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
      if ( v9 != 48 )
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
    *(_DWORD *)(a2 + 8) = 1;
    *(_DWORD *)(a2 + 12) = 16;
    *(_DWORD *)(a2 + 16) = 1;
    *(_DWORD *)(a2 + 20) = 8;
    *(_WORD *)(a2 + 24) = 0;
    goto LABEL_17;
  }
  if ( v11 != 48 )
    return 512;
  *(_DWORD *)(a2 + 8) = 49;
  *(_DWORD *)(a2 + 4) = 1;
  *(_DWORD *)(a2 + 16) = 1;
  *(_DWORD *)(a2 + 12) = 20;
  *(_DWORD *)(a2 + 20) = 4;
  LoadStringW(*(HINSTANCE *)(a1 + 20), 0x14u, (LPWSTR)(a2 + 24), 48);
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
0x180002750  push    rbx
0x180002752  sub     rsp, 20h
0x180002756  mov     rbx, rdx
0x180002759  mov     edx, 31h ; '1'
0x18000275e  mov     r10, rcx
0x180002761  lea     r11d, [rdx-1]
0x180002765  lea     r9d, [rdx-30h]
0x180002769  and     r8d, 0Fh
0x18000276d  jz      short loc_1800027A4
0x18000276f  sub     r8d, r9d
0x180002772  jz      short loc_18000279A
0x180002774  cmp     r8d, r9d
0x180002777  jz      short loc_180002781
0x180002779  lea     eax, [rdx-29h]
0x18000277c  jmp     loc_180002826
0x180002781  mov     ecx, [rbx+8]
0x180002784  test    ecx, ecx
0x180002786  jz      short loc_180002796
0x180002788  sub     ecx, r9d
0x18000278b  jz      short loc_18000279F
0x18000278d  cmp     ecx, r11d
0x180002790  jnz     loc_180002821
0x180002796  mov     eax, edx
0x180002798  jmp     short loc_1800027B7
0x18000279a  mov     ecx, [rbx+8]
0x18000279d  jmp     short loc_180002788
0x18000279f  mov     eax, r9d
0x1800027a2  jmp     short loc_1800027B7
0x1800027a4  cmp     dword ptr [rbx+4], 2
0x1800027a8  jnb     short loc_180002821
0x1800027aa  mov     eax, [rbx+4]
0x1800027ad  lea     rcx, gauFormatTagIndexToTag
0x1800027b4  mov     eax, [rcx+rax*4]
0x1800027b7  sub     eax, r9d
0x1800027ba  jz      short loc_1800027EE
0x1800027bc  cmp     eax, r11d
0x1800027bf  jnz     short loc_180002821
0x1800027c1  mov     [rbx+8], edx
0x1800027c4  lea     r8, [rbx+18h]; lpBuffer
0x1800027c8  mov     [rbx+4], r9d
0x1800027cc  mov     edx, 14h; uID
0x1800027d1  mov     [rbx+10h], r9d
0x1800027d5  mov     r9d, r11d; cchBufferMax
0x1800027d8  mov     [rbx+0Ch], edx
0x1800027db  mov     dword ptr [rbx+14h], 4
0x1800027e2  mov     rcx, [r10+14h]; hInstance
0x1800027e6  call    cs:__imp_LoadStringW
0x1800027ec  jmp     short loc_180002811
0x1800027ee  xor     eax, eax
0x1800027f0  mov     dword ptr [rbx+4], 0
0x1800027f7  mov     [rbx+8], r9d
0x1800027fb  mov     dword ptr [rbx+0Ch], 10h
0x180002802  mov     [rbx+10h], r9d
0x180002806  mov     dword ptr [rbx+14h], 8
0x18000280d  mov     [rbx+18h], ax
0x180002811  mov     eax, 78h ; 'x'
0x180002816  cmp     [rbx], eax
0x180002818  cmovb   eax, [rbx]
0x18000281b  mov     [rbx], eax
0x18000281d  xor     eax, eax
0x18000281f  jmp     short loc_180002826
0x180002821  mov     eax, 200h
0x180002826  add     rsp, 20h
0x18000282a  pop     rbx
0x18000282b  retn
```
