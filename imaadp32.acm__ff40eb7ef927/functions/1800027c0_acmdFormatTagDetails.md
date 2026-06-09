# acmdFormatTagDetails

- ea: `0x1800027c0`
- end: `0x180002895`
- name: `acmdFormatTagDetails`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020b0`

## callees

- `0x1800027c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002857`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002857`

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
        v10 = 17;
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
      if ( v9 != 16 )
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
    *(_DWORD *)(a2 + 20) = 16;
    *(_WORD *)(a2 + 24) = 0;
    goto LABEL_17;
  }
  if ( v11 != 16 )
    return 512;
  *(_DWORD *)(a2 + 4) = 1;
  *(_DWORD *)(a2 + 16) = 1;
  *(_DWORD *)(a2 + 8) = 17;
  *(_DWORD *)(a2 + 12) = 20;
  *(_DWORD *)(a2 + 20) = 8;
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
0x1800027c0  push    rbx
0x1800027c2  sub     rsp, 20h
0x1800027c6  mov     rbx, rdx
0x1800027c9  mov     edx, 10h
0x1800027ce  mov     r10, rcx
0x1800027d1  lea     r9d, [rdx-0Fh]
0x1800027d5  lea     r11d, [rdx+1]
0x1800027d9  and     r8d, 0Fh
0x1800027dd  jz      short loc_180002814
0x1800027df  sub     r8d, r9d
0x1800027e2  jz      short loc_18000280A
0x1800027e4  cmp     r8d, r9d
0x1800027e7  jz      short loc_1800027F1
0x1800027e9  lea     eax, [rdx-8]
0x1800027ec  jmp     loc_18000288F
0x1800027f1  mov     ecx, [rbx+8]
0x1800027f4  test    ecx, ecx
0x1800027f6  jz      short loc_180002805
0x1800027f8  sub     ecx, r9d
0x1800027fb  jz      short loc_18000280F
0x1800027fd  cmp     ecx, edx
0x1800027ff  jnz     loc_18000288A
0x180002805  mov     eax, r11d
0x180002808  jmp     short loc_180002827
0x18000280a  mov     ecx, [rbx+8]
0x18000280d  jmp     short loc_1800027F8
0x18000280f  mov     eax, r9d
0x180002812  jmp     short loc_180002827
0x180002814  cmp     dword ptr [rbx+4], 2
0x180002818  jnb     short loc_18000288A
0x18000281a  mov     eax, [rbx+4]
0x18000281d  lea     rcx, gauFormatTagIndexToTag
0x180002824  mov     eax, [rcx+rax*4]
0x180002827  sub     eax, r9d
0x18000282a  jz      short loc_18000285F
0x18000282c  cmp     eax, edx
0x18000282e  jnz     short loc_18000288A
0x180002830  mov     edx, 14h; uID
0x180002835  mov     [rbx+4], r9d
0x180002839  mov     [rbx+10h], r9d
0x18000283d  lea     r8, [rbx+18h]; lpBuffer
0x180002841  mov     [rbx+8], r11d
0x180002845  mov     [rbx+0Ch], edx
0x180002848  mov     dword ptr [rbx+14h], 8
0x18000284f  lea     r9d, [rdx+1Ch]; cchBufferMax
0x180002853  mov     rcx, [r10+14h]; hInstance
0x180002857  call    cs:__imp_LoadStringW
0x18000285d  jmp     short loc_18000287A
0x18000285f  xor     eax, eax
0x180002861  mov     dword ptr [rbx+4], 0
0x180002868  mov     [rbx+8], r9d
0x18000286c  mov     [rbx+0Ch], edx
0x18000286f  mov     [rbx+10h], r9d
0x180002873  mov     [rbx+14h], edx
0x180002876  mov     [rbx+18h], ax
0x18000287a  mov     eax, 78h ; 'x'
0x18000287f  cmp     [rbx], eax
0x180002881  cmovb   eax, [rbx]
0x180002884  mov     [rbx], eax
0x180002886  xor     eax, eax
0x180002888  jmp     short loc_18000288F
0x18000288a  mov     eax, 200h
0x18000288f  add     rsp, 20h
0x180002893  pop     rbx
0x180002894  retn
```
