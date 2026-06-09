# TextOpenFile(x,x,x,x,x,x,x)

- ea: `0x1001fcd0`
- end: `0x1001ff75`
- name: `_TextOpenFile@28`
- size: `677`
- prototype: `int __stdcall(int, STRSAFE_LPCWSTR pszSrc, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x10010020`
- `0x10016bf0`

## callees

- `0x1000a590`
- `0x1000a8c0`
- `0x1000bf80`
- `0x1001db00`
- `0x1001fcd0`
- `0x1001ff80`
- `0x10020470`
- `0x10021060`
- `0x100215c0`
- `0x10029870`
- `0x1002a2b0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TextOpenFile(int a1, STRSAFE_LPCWSTR pszSrc, int a3, _DWORD *a4, int a5, WCHAR **a6, int a7)
{
  _DWORD *v7; // ebp
  int result; // eax
  int v9; // esi
  int *v10; // ebx
  WCHAR *v11; // edi
  int v12; // eax
  WCHAR *i; // edi
  char *v14; // esi
  int v15; // ecx
  int v16; // edx
  __int16 v17; // ax
  int v18; // ecx
  int v19; // eax
  _DWORD *v20; // ebp
  wchar_t *v21; // esi
  int v22; // ebx
  _DWORD *v23; // ebp
  int v24; // eax
  LPCWSTR lpFileName; // [esp+10h] [ebp-B4h] BYREF
  _DWORD *v26; // [esp+14h] [ebp-B0h]
  int v27; // [esp+18h] [ebp-ACh]
  int v28; // [esp+1Ch] [ebp-A8h]
  int v29; // [esp+20h] [ebp-A4h]
  int v30; // [esp+24h] [ebp-A0h] BYREF
  WCHAR **v31; // [esp+28h] [ebp-9Ch]
  _DWORD *v32; // [esp+2Ch] [ebp-98h]
  _DWORD *v33; // [esp+30h] [ebp-94h]
  int v34; // [esp+34h] [ebp-90h] BYREF
  int v35; // [esp+38h] [ebp-8Ch] BYREF
  WCHAR pszDest[66]; // [esp+3Ch] [ebp-88h] BYREF

  v7 = a4;
  v31 = a6;
  *a6 = 0;
  v32 = a4;
  v30 = 0;
  result = TextSetup(a1, pszSrc, (int)a4, (STRSAFE_LPWSTR *)&lpFileName);
  v9 = result;
  if ( !result )
  {
    v10 = a4 + 9;
    v11 = (WCHAR *)lpFileName;
    if ( a4[9] != 1200 )
    {
      v9 = TextDetectCodePageInfo(lpFileName, 0, (int)(a4 + 9), 0, 0, (int)&v30, (int)&v35, (int)&v34, a4[13]);
      if ( v9 )
        goto LABEL_50;
    }
    *((_DWORD *)v11 + 136) = a7;
    *((_DWORD *)v11 + 135) = 0;
    *((_DWORD *)v11 + 2992) = a5;
    a4[1] = (int)a4[3] <= 0;
    v9 = TextOpenImportFile(v11, (int)(v11 + 264), a4[13]);
    v29 = v9;
    if ( v9 )
      goto LABEL_50;
    v12 = a4[13];
    if ( v12 )
    {
      if ( v12 == 1 && (!a4[3] || !a4[2]) )
      {
        v9 = -5400;
        goto LABEL_50;
      }
    }
    else if ( !a4[3] )
    {
      v9 = TextColumnSetup(v11);
      v29 = v9;
      if ( v9 )
        goto LABEL_50;
    }
    if ( !a4[1] )
    {
      for ( i = (WCHAR *)a4[2]; i; i = *(WCHAR **)i )
      {
        if ( a4[13] != 3 )
          TranslateNames(*v10, i + 18, i + 18, 65);
        v14 = (char *)(i + 18);
        if ( !IsValidJETName(i + 18, 0x4B0u) )
        {
          MakeValidJetName(i + 18, pszDest, 65, *v10);
          v15 = 65;
          v16 = (char *)pszDest - v14;
          while ( v15 != -2147483581 )
          {
            v17 = *(_WORD *)&v14[v16];
            if ( !v17 )
              break;
            *(_WORD *)v14 = v17;
            v14 += 2;
            if ( !--v15 )
            {
              v14 -= 2;
              break;
            }
          }
          *(_WORD *)v14 = 0;
        }
      }
      v18 = 1;
      v19 = 0;
      while ( 1 )
      {
        v27 = v18;
        if ( v18 != 1 && v19 != 1 )
          break;
        if ( v18 > v7[3] )
          break;
        v20 = (_DWORD *)v7[2];
        v19 = 0;
        v28 = 0;
        v26 = v20;
        if ( v20 )
        {
          do
          {
            v21 = (wchar_t *)*v20;
            v22 = 1;
            if ( *v20 )
            {
              v33 = v20 + 9;
              v23 = v20 + 9;
              do
              {
                if ( DBlstrcmpi(v23, v21 + 18) )
                {
                  v19 = v28;
                }
                else
                {
                  AppendSuffix_0(v21 + 18, 0x41u, v22, 64);
                  v19 = 1;
                  ++v22;
                  v28 = 1;
                }
                v21 = *(wchar_t **)v21;
              }
              while ( v21 );
              v20 = v26;
            }
            v20 = (_DWORD *)*v20;
            v26 = v20;
          }
          while ( v20 );
          v18 = v27;
        }
        v7 = v32;
        ++v18;
      }
      v11 = (WCHAR *)lpFileName;
    }
    v9 = v29;
    v24 = -1;
    if ( a7 == 1 )
      v24 = a3;
    *((_DWORD *)v11 + 138) = v24;
    *v31 = v11;
LABEL_49:
    if ( !v9 )
      return v9;
LABEL_50:
    TextFreeResources(v11);
    return v9;
  }
  if ( result != -1011 )
  {
    v11 = (WCHAR *)lpFileName;
    goto LABEL_49;
  }
  return result;
}

```

## disassembly

```asm
0x1001fcd0  sub     esp, 0B4h
0x1001fcd6  mov     eax, ___security_cookie
0x1001fcdb  xor     eax, esp
0x1001fcdd  mov     [esp+0B4h+var_4], eax
0x1001fce4  mov     eax, [esp+0B4h+arg_14]
0x1001fceb  push    ebx
0x1001fcec  push    ebp
0x1001fced  mov     ebp, [esp+0BCh+arg_C]
0x1001fcf4  push    esi
0x1001fcf5  push    edi
0x1001fcf6  mov     [esp+0C4h+var_9C], eax
0x1001fcfa  mov     dword ptr [eax], 0
0x1001fd00  lea     eax, [esp+0C4h+lpFileName]
0x1001fd04  push    eax; int
0x1001fd05  push    ebp; int
0x1001fd06  push    [esp+0CCh+pszSrc]; pszSrc
0x1001fd0d  mov     [esp+0D0h+var_98], ebp
0x1001fd11  push    [esp+0D0h+arg_0]; int
0x1001fd18  mov     [esp+0D4h+var_A0], 0
0x1001fd20  call    TextSetup
0x1001fd25  mov     esi, eax
0x1001fd27  test    esi, esi
0x1001fd29  jz      short loc_1001FD3C
0x1001fd2b  cmp     esi, 0FFFFFC0Dh
0x1001fd31  jnz     loc_1001FF4A
0x1001fd37  jmp     loc_1001FF5A
0x1001fd3c  cmp     dword ptr [ebp+24h], 4B0h
0x1001fd43  lea     ebx, [ebp+24h]
0x1001fd46  mov     edi, [esp+0C4h+lpFileName]
0x1001fd4a  jz      short loc_1001FD75
0x1001fd4c  push    dword ptr [ebp+34h]; int
0x1001fd4f  lea     eax, [esp+0C8h+var_90]
0x1001fd53  push    eax; int
0x1001fd54  lea     eax, [esp+0CCh+var_8C]
0x1001fd58  push    eax; int
0x1001fd59  lea     eax, [esp+0D0h+var_A0]
0x1001fd5d  push    eax; int
0x1001fd5e  push    0; Locale
0x1001fd60  push    0; int
0x1001fd62  push    ebx; int
0x1001fd63  push    0; int
0x1001fd65  push    edi; lpFileName
0x1001fd66  call    _TextDetectCodePageInfo@36; TextDetectCodePageInfo(x,x,x,x,x,x,x,x,x)
0x1001fd6b  mov     esi, eax
0x1001fd6d  test    esi, esi
0x1001fd6f  jnz     loc_1001FF52
0x1001fd75  mov     eax, [esp+0C4h+arg_18]
0x1001fd7c  lea     ecx, [edi+210h]
0x1001fd82  mov     [ecx+10h], eax
0x1001fd85  mov     eax, [esp+0C4h+arg_10]
0x1001fd8c  mov     dword ptr [ecx+0Ch], 0
0x1001fd93  mov     [ecx+2CB0h], eax
0x1001fd99  cmp     dword ptr [ebp+0Ch], 0
0x1001fd9d  jle     short loc_1001FDA8
0x1001fd9f  mov     dword ptr [ebp+4], 0
0x1001fda6  jmp     short loc_1001FDAF
0x1001fda8  mov     dword ptr [ebp+4], 1
0x1001fdaf  push    dword ptr [ebp+34h]; int
0x1001fdb2  push    ecx; int
0x1001fdb3  push    edi; lpFileName
0x1001fdb4  call    TextOpenImportFile
0x1001fdb9  mov     esi, eax
0x1001fdbb  mov     [esp+0C4h+var_A4], esi
0x1001fdbf  test    esi, esi
0x1001fdc1  jnz     loc_1001FF52
0x1001fdc7  mov     eax, [ebp+34h]
0x1001fdca  test    eax, eax
0x1001fdcc  jnz     loc_1001FE5E
0x1001fdd2  cmp     [ebp+0Ch], eax
0x1001fdd5  jnz     short loc_1001FDEB
0x1001fdd7  push    edi
0x1001fdd8  call    _TextColumnSetup@4; TextColumnSetup(x)
0x1001fddd  mov     esi, eax
0x1001fddf  mov     [esp+0C4h+var_A4], eax
0x1001fde3  test    esi, esi
0x1001fde5  jnz     loc_1001FF52
0x1001fdeb  cmp     dword ptr [ebp+4], 0
0x1001fdef  jnz     loc_1001FF25
0x1001fdf5  mov     edi, [ebp+8]
0x1001fdf8  test    edi, edi
0x1001fdfa  jz      loc_1001FE93
0x1001fe00  cmp     dword ptr [ebp+34h], 3
0x1001fe04  jz      short loc_1001FE14
0x1001fe06  push    41h ; 'A'; int
0x1001fe08  lea     eax, [edi+24h]
0x1001fe0b  push    eax; lpWideCharStr
0x1001fe0c  push    eax; Src
0x1001fe0d  push    dword ptr [ebx]; int
0x1001fe0f  call    _TranslateNames@16; TranslateNames(x,x,x,x)
0x1001fe14  push    4B0h; CodePage
0x1001fe19  lea     esi, [edi+24h]
0x1001fe1c  push    esi; lpWideCharStr
0x1001fe1d  call    _IsValidJETName@8; IsValidJETName(x,x)
0x1001fe22  test    eax, eax
0x1001fe24  jnz     short loc_1001FE89
0x1001fe26  push    dword ptr [ebx]; CodePage
0x1001fe28  lea     eax, [esp+0C8h+pszDest]
0x1001fe2c  push    41h ; 'A'; cchWideChar
0x1001fe2e  push    eax; pszDest
0x1001fe2f  push    esi; lpWideCharStr
0x1001fe30  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x1001fe35  lea     edx, [esp+0C4h+pszDest]
0x1001fe39  mov     ecx, 41h ; 'A'
0x1001fe3e  sub     edx, esi
0x1001fe40  lea     eax, [ecx+7FFFFFBDh]
0x1001fe46  test    eax, eax
0x1001fe48  jz      short loc_1001FE7D
0x1001fe4a  movzx   eax, word ptr [edx+esi]
0x1001fe4e  test    ax, ax
0x1001fe51  jz      short loc_1001FE7D
0x1001fe53  mov     [esi], ax
0x1001fe56  add     esi, 2
0x1001fe59  dec     ecx
0x1001fe5a  jnz     short loc_1001FE40
0x1001fe5c  jmp     short loc_1001FE81
0x1001fe5e  cmp     eax, 1
0x1001fe61  jnz     short loc_1001FDEB
0x1001fe63  cmp     dword ptr [ebp+0Ch], 0
0x1001fe67  jz      short loc_1001FE73
0x1001fe69  cmp     dword ptr [ebp+8], 0
0x1001fe6d  jnz     loc_1001FDEB
0x1001fe73  mov     esi, 0FFFFEAE8h
0x1001fe78  jmp     loc_1001FF52
0x1001fe7d  test    ecx, ecx
0x1001fe7f  jnz     short loc_1001FE84
0x1001fe81  sub     esi, 2
0x1001fe84  xor     eax, eax
0x1001fe86  mov     [esi], ax
0x1001fe89  mov     edi, [edi]
0x1001fe8b  test    edi, edi
0x1001fe8d  jnz     loc_1001FE00
0x1001fe93  mov     ecx, 1
0x1001fe98  xor     eax, eax
0x1001fe9a  mov     [esp+0C4h+var_AC], ecx
0x1001fe9e  cmp     ecx, 1
0x1001fea1  jz      short loc_1001FEA8
0x1001fea3  cmp     eax, 1
0x1001fea6  jnz     short loc_1001FF21
0x1001fea8  cmp     ecx, [ebp+0Ch]
0x1001feab  jg      short loc_1001FF21
0x1001fead  mov     ebp, [ebp+8]
0x1001feb0  xor     eax, eax
0x1001feb2  mov     [esp+0C4h+var_A8], eax
0x1001feb6  mov     [esp+0C4h+var_B0], ebp
0x1001feba  test    ebp, ebp
0x1001febc  jz      short loc_1001FF17
0x1001febe  mov     edi, edi
0x1001fec0  mov     esi, [ebp+0]
0x1001fec3  mov     ebx, 1
0x1001fec8  test    esi, esi
0x1001feca  jz      short loc_1001FF08
0x1001fecc  lea     eax, [ebp+24h]
0x1001fecf  mov     [esp+0C4h+var_94], eax
0x1001fed3  mov     ebp, eax
0x1001fed5  lea     edi, [esi+24h]
0x1001fed8  push    edi
0x1001fed9  push    ebp
0x1001feda  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x1001fedf  test    eax, eax
0x1001fee1  jnz     short loc_1001FEFA
0x1001fee3  push    40h ; '@'; int
0x1001fee5  push    ebx; int
0x1001fee6  push    41h ; 'A'; cchDest
0x1001fee8  push    edi; pszDest
0x1001fee9  call    AppendSuffix_0
0x1001feee  mov     eax, 1
0x1001fef3  inc     ebx
0x1001fef4  mov     [esp+0C4h+var_A8], eax
0x1001fef8  jmp     short loc_1001FEFE
0x1001fefa  mov     eax, [esp+0C4h+var_A8]
0x1001fefe  mov     esi, [esi]
0x1001ff00  test    esi, esi
0x1001ff02  jnz     short loc_1001FED5
0x1001ff04  mov     ebp, [esp+0C4h+var_B0]
0x1001ff08  mov     ebp, [ebp+0]
0x1001ff0b  mov     [esp+0C4h+var_B0], ebp
0x1001ff0f  test    ebp, ebp
0x1001ff11  jnz     short loc_1001FEC0
0x1001ff13  mov     ecx, [esp+0C4h+var_AC]
0x1001ff17  mov     ebp, [esp+0C4h+var_98]
0x1001ff1b  inc     ecx
0x1001ff1c  jmp     loc_1001FE9A
0x1001ff21  mov     edi, [esp+0C4h+lpFileName]
0x1001ff25  mov     esi, [esp+0C4h+var_A4]
0x1001ff29  or      eax, 0FFFFFFFFh
0x1001ff2c  cmp     [esp+0C4h+arg_18], 1
0x1001ff34  cmovz   eax, [esp+0C4h+arg_8]
0x1001ff3c  mov     [edi+228h], eax
0x1001ff42  mov     eax, [esp+0C4h+var_9C]
0x1001ff46  mov     [eax], edi
0x1001ff48  jmp     short loc_1001FF4E
0x1001ff4a  mov     edi, [esp+0C4h+lpFileName]
0x1001ff4e  test    esi, esi
0x1001ff50  jz      short loc_1001FF58
0x1001ff52  push    edi
0x1001ff53  call    _TextFreeResources@4; TextFreeResources(x)
0x1001ff58  mov     eax, esi
0x1001ff5a  mov     ecx, [esp+0C4h+var_4]
0x1001ff61  pop     edi
0x1001ff62  pop     esi
0x1001ff63  pop     ebp
0x1001ff64  pop     ebx
0x1001ff65  xor     ecx, esp; StackCookie
0x1001ff67  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ff6c  add     esp, 0B4h
0x1001ff72  retn    1Ch
```
