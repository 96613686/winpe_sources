# TXTRenameColumn(x,x,x,x)

- ea: `0x1000fa40`
- end: `0x1000fc62`
- name: `_TXTRenameColumn@16`
- size: `546`
- prototype: `int __stdcall(int, int, void *Src, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000a1f0`
- `0x1000f030`
- `0x1000fa40`
- `0x10014460`
- `0x100146d0`
- `0x1002a2b0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TXTRenameColumn(int a1, int a2, _BYTE *Src, char *pszSrc)
{
  const wchar_t *v4; // ebx
  int v5; // eax
  int v6; // ebp
  int result; // eax
  _DWORD *v8; // esi
  int v9; // edx
  wchar_t *v10; // ecx
  wchar_t v11; // ax
  int v12; // edx
  wchar_t *v13; // ecx
  wchar_t v14; // ax
  int v15; // eax
  _WORD *v16; // ecx
  int v17; // edx
  char *v18; // esi
  __int16 v19; // ax
  int ValidFieldName; // [esp+Ch] [ebp-194h]
  wchar_t Source[66]; // [esp+10h] [ebp-190h] BYREF
  wchar_t Destination[66]; // [esp+94h] [ebp-10Ch] BYREF
  wchar_t v23[66]; // [esp+118h] [ebp-88h] BYREF

  v4 = (const wchar_t *)pszSrc;
  v5 = ISAMDBFindCursor(a1, a2);
  v6 = v5;
  if ( !v5 )
    return -1310;
  if ( (*(_BYTE *)(v5 + 20) & 2) == 0 )
    return -1309;
  if ( *(_BYTE *)(v5 + 28) == 1 )
    return -1809;
  v8 = *(_DWORD **)(v5 + 4);
  if ( !v8[220] )
    return -1308;
  if ( *(_DWORD *)(v8[1] + 8) )
  {
    v9 = 65;
    v10 = Source;
    while ( v9 != -2147483581 )
    {
      v11 = *(wchar_t *)((char *)v10 + pszSrc - (char *)Source);
      if ( !v11 )
        break;
      *v10++ = v11;
      if ( !--v9 )
      {
        --v10;
        break;
      }
    }
    v4 = (const wchar_t *)pszSrc;
    *v10 = 0;
  }
  else
  {
    TranslateNames(v8[12], pszSrc, Source, 65);
  }
  ValidFieldName = MakeValidFieldName(*(_DWORD *)(v6 + 8), Source, Destination, 0x41u, 0x4B0u);
  if ( ValidFieldName )
  {
    if ( *(_DWORD *)(v8[1] + 8) )
    {
      v12 = 65;
      v13 = Source;
      while ( v12 != -2147483581 )
      {
        v14 = *(wchar_t *)((char *)v13 + Src - (_BYTE *)Source);
        if ( !v14 )
          break;
        *v13++ = v14;
        if ( !--v12 )
        {
          --v13;
          break;
        }
      }
      *v13 = 0;
    }
    else
    {
      TranslateNames(v8[12], Src, Source, 65);
    }
    MakeValidFieldName(*(_DWORD *)(v6 + 8), Source, v23, 0x41u, 0x4B0u);
    if ( ISAMDBLocateColumn(v8, Destination) )
    {
      return -1508;
    }
    else
    {
      v15 = ISAMDBLocateColumn(v8, v23);
      if ( v15 )
      {
        v16 = (_WORD *)(v15 + 36);
        v17 = 65;
        v18 = (char *)&Destination[-18] - v15;
        while ( v17 != -2147483581 )
        {
          v19 = *(_WORD *)((char *)v16 + (_DWORD)v18);
          if ( !v19 )
            break;
          *v16++ = v19;
          if ( !--v17 )
          {
            --v16;
            break;
          }
        }
        result = 0;
        *v16 = 0;
        if ( ValidFieldName == 2 )
          return 5011;
      }
      else
      {
        return -1507;
      }
    }
  }
  else
  {
    ErrorSetExtendedInfoSz1(-8198, v4, 1);
    return -1002;
  }
  return result;
}

```

## disassembly

```asm
0x1000fa40  sub     esp, 194h
0x1000fa46  mov     eax, ___security_cookie
0x1000fa4b  xor     eax, esp
0x1000fa4d  mov     [esp+194h+var_4], eax
0x1000fa54  mov     eax, [esp+194h+arg_4]
0x1000fa5b  mov     ecx, [esp+194h+arg_0]
0x1000fa62  push    ebx
0x1000fa63  mov     ebx, [esp+198h+pszSrc]
0x1000fa6a  push    ebp
0x1000fa6b  push    edi
0x1000fa6c  mov     edi, [esp+1A0h+Src]
0x1000fa73  push    eax
0x1000fa74  push    ecx
0x1000fa75  mov     [esp+1A8h+var_194], ebx
0x1000fa79  call    _ISAMDBFindCursor@8; ISAMDBFindCursor(x,x)
0x1000fa7e  mov     ebp, eax
0x1000fa80  test    ebp, ebp
0x1000fa82  jnz     short loc_1000FA8E
0x1000fa84  mov     eax, 0FFFFFAE2h
0x1000fa89  jmp     loc_1000FC48
0x1000fa8e  test    byte ptr [ebp+14h], 2
0x1000fa92  push    esi
0x1000fa93  jnz     short loc_1000FA9F
0x1000fa95  mov     eax, 0FFFFFAE3h
0x1000fa9a  jmp     loc_1000FC47
0x1000fa9f  cmp     byte ptr [ebp+1Ch], 1
0x1000faa3  jnz     short loc_1000FAAF
0x1000faa5  mov     eax, 0FFFFF8EFh
0x1000faaa  jmp     loc_1000FC47
0x1000faaf  mov     esi, [ebp+4]
0x1000fab2  cmp     dword ptr [esi+370h], 0
0x1000fab9  jnz     short loc_1000FAC5
0x1000fabb  mov     eax, 0FFFFFAE4h
0x1000fac0  jmp     loc_1000FC47
0x1000fac5  mov     eax, [esi+4]
0x1000fac8  cmp     dword ptr [eax+8], 0
0x1000facc  lea     eax, [esp+1A4h+Source]
0x1000fad0  jnz     short loc_1000FAE0
0x1000fad2  push    41h ; 'A'; int
0x1000fad4  push    eax; lpWideCharStr
0x1000fad5  push    ebx; Src
0x1000fad6  push    dword ptr [esi+30h]; int
0x1000fad9  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x1000fade  jmp     short loc_1000FB1E
0x1000fae0  mov     edx, 41h ; 'A'
0x1000fae5  lea     ecx, [esp+1A4h+Source]
0x1000fae9  sub     ebx, eax
0x1000faeb  jmp     short loc_1000FAF0
0x1000faf0  lea     eax, [edx+7FFFFFBDh]
0x1000faf6  test    eax, eax
0x1000faf8  jz      short loc_1000FB0E
0x1000fafa  movzx   eax, word ptr [ebx+ecx]
0x1000fafe  test    ax, ax
0x1000fb01  jz      short loc_1000FB0E
0x1000fb03  mov     [ecx], ax
0x1000fb06  add     ecx, 2
0x1000fb09  dec     edx
0x1000fb0a  jnz     short loc_1000FAF0
0x1000fb0c  jmp     short loc_1000FB12
0x1000fb0e  test    edx, edx
0x1000fb10  jnz     short loc_1000FB15
0x1000fb12  sub     ecx, 2
0x1000fb15  mov     ebx, [esp+1A4h+var_194]
0x1000fb19  xor     eax, eax
0x1000fb1b  mov     [ecx], ax
0x1000fb1e  push    4B0h; CodePage
0x1000fb23  push    41h ; 'A'; cchDest
0x1000fb25  lea     eax, [esp+1ACh+Destination]
0x1000fb2c  push    eax; Destination
0x1000fb2d  lea     eax, [esp+1B0h+Source]
0x1000fb31  push    eax; Source
0x1000fb32  push    dword ptr [ebp+8]; int
0x1000fb35  call    _MakeValidFieldName@20; MakeValidFieldName(x,x,x,x,x)
0x1000fb3a  mov     [esp+1A4h+var_194], eax
0x1000fb3e  test    eax, eax
0x1000fb40  jnz     short loc_1000FB59
0x1000fb42  push    1; int
0x1000fb44  push    ebx; pszSrc
0x1000fb45  push    0FFFFDFFAh; int
0x1000fb4a  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x1000fb4f  mov     eax, 0FFFFFC16h
0x1000fb54  jmp     loc_1000FC47
0x1000fb59  mov     eax, [esi+4]
0x1000fb5c  cmp     dword ptr [eax+8], 0
0x1000fb60  lea     eax, [esp+1A4h+Source]
0x1000fb64  jnz     short loc_1000FB74
0x1000fb66  push    41h ; 'A'; int
0x1000fb68  push    eax; lpWideCharStr
0x1000fb69  push    edi; Src
0x1000fb6a  push    dword ptr [esi+30h]; int
0x1000fb6d  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x1000fb72  jmp     short loc_1000FBAA
0x1000fb74  mov     edx, 41h ; 'A'
0x1000fb79  lea     ecx, [esp+1A4h+Source]
0x1000fb7d  sub     edi, eax
0x1000fb7f  nop
0x1000fb80  lea     eax, [edx+7FFFFFBDh]
0x1000fb86  test    eax, eax
0x1000fb88  jz      short loc_1000FB9E
0x1000fb8a  movzx   eax, word ptr [edi+ecx]
0x1000fb8e  test    ax, ax
0x1000fb91  jz      short loc_1000FB9E
0x1000fb93  mov     [ecx], ax
0x1000fb96  add     ecx, 2
0x1000fb99  dec     edx
0x1000fb9a  jnz     short loc_1000FB80
0x1000fb9c  jmp     short loc_1000FBA2
0x1000fb9e  test    edx, edx
0x1000fba0  jnz     short loc_1000FBA5
0x1000fba2  sub     ecx, 2
0x1000fba5  xor     eax, eax
0x1000fba7  mov     [ecx], ax
0x1000fbaa  push    4B0h; CodePage
0x1000fbaf  push    41h ; 'A'; cchDest
0x1000fbb1  lea     eax, [esp+1ACh+var_88]
0x1000fbb8  push    eax; Destination
0x1000fbb9  lea     eax, [esp+1B0h+Source]
0x1000fbbd  push    eax; Source
0x1000fbbe  push    dword ptr [ebp+8]; int
0x1000fbc1  call    _MakeValidFieldName@20; MakeValidFieldName(x,x,x,x,x)
0x1000fbc6  lea     eax, [esp+1A4h+Destination]
0x1000fbcd  push    eax
0x1000fbce  push    esi
0x1000fbcf  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1000fbd4  test    eax, eax
0x1000fbd6  jz      short loc_1000FBDF
0x1000fbd8  mov     eax, 0FFFFFA1Ch
0x1000fbdd  jmp     short loc_1000FC47
0x1000fbdf  lea     eax, [esp+1A4h+var_88]
0x1000fbe6  push    eax
0x1000fbe7  push    esi
0x1000fbe8  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1000fbed  test    eax, eax
0x1000fbef  jnz     short loc_1000FBF8
0x1000fbf1  mov     eax, 0FFFFFA1Dh
0x1000fbf6  jmp     short loc_1000FC47
0x1000fbf8  lea     ecx, [eax+24h]
0x1000fbfb  mov     edx, 41h ; 'A'
0x1000fc00  lea     esi, [esp+1A4h+Destination]
0x1000fc07  sub     esi, ecx
0x1000fc09  lea     esp, [esp+0]
0x1000fc10  lea     eax, [edx+7FFFFFBDh]
0x1000fc16  test    eax, eax
0x1000fc18  jz      short loc_1000FC2E
0x1000fc1a  movzx   eax, word ptr [esi+ecx]
0x1000fc1e  test    ax, ax
0x1000fc21  jz      short loc_1000FC2E
0x1000fc23  mov     [ecx], ax
0x1000fc26  add     ecx, 2
0x1000fc29  dec     edx
0x1000fc2a  jnz     short loc_1000FC10
0x1000fc2c  jmp     short loc_1000FC32
0x1000fc2e  test    edx, edx
0x1000fc30  jnz     short loc_1000FC35
0x1000fc32  sub     ecx, 2
0x1000fc35  xor     eax, eax
0x1000fc37  cmp     [esp+1A4h+var_194], 2
0x1000fc3c  mov     [ecx], ax
0x1000fc3f  mov     ecx, 1393h
0x1000fc44  cmovz   eax, ecx
0x1000fc47  pop     esi
0x1000fc48  mov     ecx, [esp+1A0h+var_4]
0x1000fc4f  pop     edi
0x1000fc50  pop     ebp
0x1000fc51  pop     ebx
0x1000fc52  xor     ecx, esp; StackCookie
0x1000fc54  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fc59  add     esp, 194h
0x1000fc5f  retn    10h
```
