# TXTDeleteColumn(x,x,x)

- ea: `0x1000f8f0`
- end: `0x1000fa3d`
- name: `_TXTDeleteColumn@12`
- size: `333`
- prototype: `int __stdcall(int, int, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1000a1f0`
- `0x1000f030`
- `0x1000f8f0`
- `0x10013ff0`
- `0x10014460`
- `0x100146d0`
- `0x1002a2b0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TXTDeleteColumn(int a1, int a2, char *pszSrc)
{
  int v3; // eax
  int v4; // edi
  _DWORD *v6; // esi
  wchar_t *v7; // ecx
  int v8; // edx
  wchar_t v9; // ax
  wchar_t Source[256]; // [esp+8h] [ebp-404h] BYREF
  wchar_t Destination[256]; // [esp+208h] [ebp-204h] BYREF

  v3 = ISAMDBFindCursor(a1, a2);
  v4 = v3;
  if ( !v3 )
    return -1310;
  if ( (*(_BYTE *)(v3 + 20) & 2) == 0 )
    return -1309;
  if ( *(_BYTE *)(v3 + 28) == 1 )
    return -1809;
  v6 = *(_DWORD **)(v3 + 4);
  if ( !v6[220] )
    return -1308;
  if ( *(_DWORD *)(v6[1] + 8) )
  {
    v7 = Source;
    v8 = 256;
    while ( v8 != -2147483390 )
    {
      v9 = *(wchar_t *)((char *)v7 + pszSrc - (char *)Source);
      if ( !v9 )
        break;
      *v7++ = v9;
      if ( !--v8 )
      {
        --v7;
        break;
      }
    }
    *v7 = 0;
  }
  else
  {
    TranslateNames(v6[12], pszSrc, Source, 256);
  }
  if ( MakeValidFieldName(*(_DWORD *)(v4 + 8), Source, Destination, 0x100u, 0x4B0u) )
  {
    if ( ISAMDBLocateColumn(v6, Destination) )
    {
      ISAMDBDeleteColumn(v6, Destination);
      --v6[6];
      return 0;
    }
    else
    {
      return -1507;
    }
  }
  else
  {
    ErrorSetExtendedInfoSz1(-8198, (STRSAFE_LPCWSTR)pszSrc, 1);
    return -1002;
  }
}

```

## disassembly

```asm
0x1000f8f0  sub     esp, 404h
0x1000f8f6  mov     eax, ___security_cookie
0x1000f8fb  xor     eax, esp
0x1000f8fd  mov     [esp+404h+var_4], eax
0x1000f904  mov     eax, [esp+404h+arg_4]
0x1000f90b  mov     ecx, [esp+404h+arg_0]
0x1000f912  push    ebp
0x1000f913  mov     ebp, [esp+408h+pszSrc]
0x1000f91a  push    edi
0x1000f91b  push    eax
0x1000f91c  push    ecx
0x1000f91d  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1000f922  mov     edi, eax
0x1000f924  test    edi, edi
0x1000f926  jnz     short loc_1000F932
0x1000f928  mov     eax, 0FFFFFAE2h
0x1000f92d  jmp     loc_1000FA24
0x1000f932  test    byte ptr [edi+14h], 2
0x1000f936  push    esi
0x1000f937  jnz     short loc_1000F943
0x1000f939  mov     eax, 0FFFFFAE3h
0x1000f93e  jmp     loc_1000FA23
0x1000f943  cmp     byte ptr [edi+1Ch], 1
0x1000f947  jnz     short loc_1000F953
0x1000f949  mov     eax, 0FFFFF8EFh
0x1000f94e  jmp     loc_1000FA23
0x1000f953  mov     esi, [edi+4]
0x1000f956  cmp     dword ptr [esi+370h], 0
0x1000f95d  jnz     short loc_1000F969
0x1000f95f  mov     eax, 0FFFFFAE4h
0x1000f964  jmp     loc_1000FA23
0x1000f969  mov     eax, [esi+4]
0x1000f96c  cmp     dword ptr [eax+8], 0
0x1000f970  lea     eax, [esp+410h+Source]
0x1000f974  jnz     short loc_1000F987
0x1000f976  push    100h; int
0x1000f97b  push    eax; lpWideCharStr
0x1000f97c  push    ebp; Src
0x1000f97d  push    dword ptr [esi+30h]; int
0x1000f980  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x1000f985  jmp     short loc_1000F9C0
0x1000f987  push    ebx
0x1000f988  mov     ebx, ebp
0x1000f98a  lea     ecx, [esp+414h+Source]
0x1000f98e  mov     edx, 100h
0x1000f993  sub     ebx, eax
0x1000f995  lea     eax, [edx+7FFFFEFEh]
0x1000f99b  test    eax, eax
0x1000f99d  jz      short loc_1000F9B3
0x1000f99f  movzx   eax, word ptr [ebx+ecx]
0x1000f9a3  test    ax, ax
0x1000f9a6  jz      short loc_1000F9B3
0x1000f9a8  mov     [ecx], ax
0x1000f9ab  add     ecx, 2
0x1000f9ae  dec     edx
0x1000f9af  jnz     short loc_1000F995
0x1000f9b1  jmp     short loc_1000F9B7
0x1000f9b3  test    edx, edx
0x1000f9b5  jnz     short loc_1000F9BA
0x1000f9b7  sub     ecx, 2
0x1000f9ba  xor     eax, eax
0x1000f9bc  mov     [ecx], ax
0x1000f9bf  pop     ebx
0x1000f9c0  push    4B0h; CodePage
0x1000f9c5  push    100h; cchDest
0x1000f9ca  lea     eax, [esp+418h+Destination]
0x1000f9d1  push    eax; Destination
0x1000f9d2  lea     eax, [esp+41Ch+Source]
0x1000f9d6  push    eax; Source
0x1000f9d7  push    dword ptr [edi+8]; int
0x1000f9da  call    _MakeValidFieldName@20; MakeValidFieldName(x,x,x,x,x)
0x1000f9df  test    eax, eax
0x1000f9e1  jnz     short loc_1000F9F7
0x1000f9e3  push    1; int
0x1000f9e5  push    ebp; pszSrc
0x1000f9e6  push    0FFFFDFFAh; int
0x1000f9eb  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000f9f0  mov     eax, 0FFFFFC16h
0x1000f9f5  jmp     short loc_1000FA23
0x1000f9f7  lea     eax, [esp+410h+Destination]
0x1000f9fe  push    eax
0x1000f9ff  push    esi
0x1000fa00  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1000fa05  test    eax, eax
0x1000fa07  jnz     short loc_1000FA10
0x1000fa09  mov     eax, 0FFFFFA1Dh
0x1000fa0e  jmp     short loc_1000FA23
0x1000fa10  lea     eax, [esp+410h+Destination]
0x1000fa17  push    eax
0x1000fa18  push    esi
0x1000fa19  call    _ISAMDBDeleteColumn@8; ISAMDBDeleteColumn(x,x)
0x1000fa1e  dec     dword ptr [esi+18h]
0x1000fa21  xor     eax, eax
0x1000fa23  pop     esi
0x1000fa24  mov     ecx, [esp+40Ch+var_4]
0x1000fa2b  pop     edi
0x1000fa2c  pop     ebp
0x1000fa2d  xor     ecx, esp; StackCookie
0x1000fa2f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fa34  add     esp, 404h
0x1000fa3a  retn    0Ch
```
