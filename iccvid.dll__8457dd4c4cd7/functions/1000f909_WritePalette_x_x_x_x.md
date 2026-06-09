# WritePalette(x,x,x,x)

- ea: `0x1000f909`
- end: `0x1000fa22`
- name: `_WritePalette@16`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100100bf`

## callees

- `0x1000f909`
- `0x1001358d`

## import_xrefs

- `GDI32!GetSystemPaletteEntries` at `0x1000f953`
- `GDI32!GetSystemPaletteEntries` at `0x1000f953`

## pseudocode

```c
int __fastcall WritePalette(int a1, HDC a2, int a3, _DWORD *a4)
{
  char v4; // bl
  int v6; // eax
  _DWORD *v7; // edi
  int result; // eax
  int v9; // edx
  unsigned int v10; // esi
  _BYTE *v11; // ecx
  int v12; // edx
  int v13; // [esp+10h] [ebp-4h]

  v4 = 1;
  if ( a3 == 1 && (v6 = *(_DWORD *)(a1 + 96), v6 > 0) )
  {
    v7 = a4;
    result = (int)memcpy((char *)a4 + *a4, *(const void **)(a1 + 100), 4 * v6);
    v9 = *(_DWORD *)(a1 + 96);
  }
  else
  {
    v7 = a4;
    GetSystemPaletteEntries(a2, 0, 0x100u, (LPPALETTEENTRY)((char *)a4 + *a4));
    v10 = 0;
    HIBYTE(v13) = 0;
    v11 = (char *)v7 + *v7;
    do
    {
      BYTE2(v13) = *v11;
      BYTE1(v13) = v11[1];
      LOBYTE(v13) = v11[2];
      result = v13;
      *(_DWORD *)v11 = v13;
      v11 += 4;
      ++v10;
    }
    while ( v10 < 0xA );
    if ( a3 == 1 )
    {
      v10 = 10;
      v12 = 0;
      do
      {
        result = stdPAL8[v12];
        *(_DWORD *)v11 = result;
        v11 += 4;
        ++v10;
        ++v12;
      }
      while ( v10 < 0xE7 );
    }
    else
    {
      while ( v10 < 0xF6 )
      {
        result = ((v10 << 8) - 2442) / 0xEC;
        *v11 = result;
        v11[1] = result;
        v11[2] = result;
        v11 += 4;
        ++v10;
      }
    }
    *(_WORD *)((char *)&v13 + 1) = 0;
    while ( 1 )
    {
      LOBYTE(v13) = v4;
      if ( v10 >= 0xF6 )
        break;
      result = v13;
      *(_DWORD *)v11 = v13;
      v11 += 4;
      ++v4;
      ++v10;
    }
    v9 = 256;
    while ( v10 < 0x100 )
    {
      ++v10;
      BYTE2(v13) = *v11;
      BYTE1(v13) = v11[1];
      LOBYTE(v13) = v11[2];
      result = v13;
      *(_DWORD *)v11 = v13;
      v11 += 4;
    }
  }
  v7[8] = v9;
  return result;
}

```

## disassembly

```asm
0x1000f909  mov     edi, edi
0x1000f90b  push    ebp
0x1000f90c  mov     ebp, esp
0x1000f90e  push    ecx
0x1000f90f  push    ecx
0x1000f910  push    ebx
0x1000f911  xor     ebx, ebx
0x1000f913  push    esi
0x1000f914  inc     ebx
0x1000f915  mov     esi, ecx
0x1000f917  push    edi
0x1000f918  cmp     [ebp+arg_0], ebx
0x1000f91b  jnz     short loc_1000F943
0x1000f91d  mov     eax, [esi+60h]
0x1000f920  test    eax, eax
0x1000f922  jle     short loc_1000F943
0x1000f924  mov     edi, [ebp+arg_4]
0x1000f927  shl     eax, 2
0x1000f92a  push    eax; Size
0x1000f92b  push    dword ptr [esi+64h]; Src
0x1000f92e  mov     eax, [edi]
0x1000f930  add     eax, edi
0x1000f932  push    eax; void *
0x1000f933  call    _memcpy
0x1000f938  mov     edx, [esi+60h]
0x1000f93b  add     esp, 0Ch
0x1000f93e  jmp     loc_1000FA18
0x1000f943  mov     edi, [ebp+arg_4]
0x1000f946  mov     eax, [edi]
0x1000f948  add     eax, edi
0x1000f94a  push    eax; pPalEntries
0x1000f94b  push    100h; cEntries
0x1000f950  push    0; iStart
0x1000f952  push    edx; hdc
0x1000f953  call    ds:__imp__GetSystemPaletteEntries@16; GetSystemPaletteEntries(x,x,x,x)
0x1000f959  mov     ecx, [edi]
0x1000f95b  xor     esi, esi
0x1000f95d  mov     byte ptr [ebp+var_4+3], 0
0x1000f961  add     ecx, edi
0x1000f963  mov     al, [ecx]
0x1000f965  mov     byte ptr [ebp+var_4+2], al
0x1000f968  mov     al, [ecx+1]
0x1000f96b  mov     byte ptr [ebp+var_4+1], al
0x1000f96e  mov     al, [ecx+2]
0x1000f971  mov     byte ptr [ebp+var_4], al
0x1000f974  mov     eax, [ebp+var_4]
0x1000f977  mov     [ecx], eax
0x1000f979  add     ecx, 4
0x1000f97c  inc     esi
0x1000f97d  cmp     esi, 0Ah
0x1000f980  jb      short loc_1000F963
0x1000f982  mov     edx, 0F6h
0x1000f987  cmp     [ebp+arg_0], ebx
0x1000f98a  jnz     short loc_1000F9D5
0x1000f98c  push    0Ah
0x1000f98e  pop     esi
0x1000f98f  xor     edx, edx
0x1000f991  mov     eax, ds:_stdPAL8[edx*4]
0x1000f998  mov     [ecx], eax
0x1000f99a  add     ecx, 4
0x1000f99d  inc     esi
0x1000f99e  inc     edx
0x1000f99f  cmp     esi, 0E7h
0x1000f9a5  jb      short loc_1000F991
0x1000f9a7  mov     edx, 0F6h
0x1000f9ac  jmp     short loc_1000F9D9
0x1000f9ae  mov     eax, esi
0x1000f9b0  mov     [ebp+var_8], 0ECh
0x1000f9b7  shl     eax, 8
0x1000f9ba  xor     edx, edx
0x1000f9bc  sub     eax, 98Ah
0x1000f9c1  div     [ebp+var_8]
0x1000f9c4  mov     edx, 0F6h
0x1000f9c9  mov     [ecx], al
0x1000f9cb  mov     [ecx+1], al
0x1000f9ce  mov     [ecx+2], al
0x1000f9d1  add     ecx, 4
0x1000f9d4  inc     esi
0x1000f9d5  cmp     esi, edx
0x1000f9d7  jb      short loc_1000F9AE
0x1000f9d9  mov     word ptr [ebp+var_4+1], 0
0x1000f9df  jmp     short loc_1000F9EC
0x1000f9e1  mov     eax, [ebp+var_4]
0x1000f9e4  mov     [ecx], eax
0x1000f9e6  add     ecx, 4
0x1000f9e9  inc     bl
0x1000f9eb  inc     esi
0x1000f9ec  mov     byte ptr [ebp+var_4], bl
0x1000f9ef  cmp     esi, edx
0x1000f9f1  jb      short loc_1000F9E1
0x1000f9f3  mov     edx, 100h
0x1000f9f8  jmp     short loc_1000FA14
0x1000f9fa  mov     al, [ecx]
0x1000f9fc  inc     esi
0x1000f9fd  mov     byte ptr [ebp+var_4+2], al
0x1000fa00  mov     al, [ecx+1]
0x1000fa03  mov     byte ptr [ebp+var_4+1], al
0x1000fa06  mov     al, [ecx+2]
0x1000fa09  mov     byte ptr [ebp+var_4], al
0x1000fa0c  mov     eax, [ebp+var_4]
0x1000fa0f  mov     [ecx], eax
0x1000fa11  lea     ecx, [ecx+4]
0x1000fa14  cmp     esi, edx
0x1000fa16  jb      short loc_1000F9FA
0x1000fa18  mov     [edi+20h], edx
0x1000fa1b  pop     edi
0x1000fa1c  pop     esi
0x1000fa1d  pop     ebx
0x1000fa1e  leave
0x1000fa1f  retn    8
```
