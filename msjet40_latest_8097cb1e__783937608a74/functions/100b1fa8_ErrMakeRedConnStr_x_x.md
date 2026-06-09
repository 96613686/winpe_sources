# ErrMakeRedConnStr(x,x)

- ea: `0x100b1fa8`
- end: `0x100b217c`
- name: `_ErrMakeRedConnStr@8`
- size: `468`
- prototype: `int __thiscall(void *Src)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x100b272a`
- `0x100b5472`
- `0x100cd0e0`

## callees

- `0x10012af0`
- `0x1001ebc0`
- `0x10095f1d`
- `0x100b1fa8`
- `0x10124aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b201e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b2137`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b214e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b201e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b2137`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x100b214e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b200b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b203e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b200b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x100b203e`

## string_xrefs

- `0x100b2090`: `MS Access`
- `0x100b20de`: `MS Access`

## pseudocode

```c
int __fastcall ErrMakeRedConnStr(_WORD *Src, unsigned int a2)
{
  int v3; // edi
  _WORD *v4; // esi
  __int16 v6; // cx
  int v7; // esi
  __int16 v8; // dx
  int v9; // eax
  wchar_t *v10; // eax
  const wchar_t *v11; // eax
  bool v12; // zf
  int v13; // eax
  _WORD *v14; // ecx
  unsigned int v16; // ecx
  wchar_t *v18; // eax
  wchar_t *v19; // eax
  int v20; // [esp+8h] [ebp-Ch] BYREF
  wchar_t *Str; // [esp+Ch] [ebp-8h] BYREF
  unsigned int v22; // [esp+10h] [ebp-4h]

  v22 = a2;
  v3 = 0;
  if ( !Src )
    return v3;
  v4 = Src;
  while ( *v4++ )
    ;
  v6 = *Src;
  v7 = v4 - (Src + 1);
  v8 = 39;
  v9 = v7;
  if ( v6 == 39 || (v8 = 34, v6 == 34) )
  {
    if ( Src[v9 - 1] == v8 )
    {
      Src[v9 - 1] = 0;
      memmove(Src, Src + 1, v9 * 2 - 2);
      v7 -= 2;
    }
  }
  if ( _wcschr(Src, 0x3Bu) )
  {
    if ( *Src != 59 && WCSNICMP(9) && WCSNICMP(7) && WCSNICMP(7) )
      return v3;
    FindConnStrItem(&Str, &v20);
    if ( !v20 )
      return -3060;
    v18 = _wcsrchr(Str, 0x5Cu);
    if ( v18 )
      v19 = v18 + 1;
    else
      v19 = Str;
    Str = (wchar_t *)(_wcsrchr(v19, 0x2Eu) == 0);
    v16 = v22;
    if ( v7 + 4 * (int)Str + 1 <= v22 )
      goto LABEL_19;
    return -3054;
  }
  v10 = _wcsrchr(Src, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = Src;
  v12 = _wcschr(v11, 0x2Eu) == 0;
  Str = (wchar_t *)v12;
  v13 = 24;
  if ( !v12 )
    v13 = 20;
  if ( v7 + v13 > v22 )
    return -3054;
  v14 = Src;
  while ( *v14++ )
    ;
  memmove(Src + 19, Src, 2 * (v14 - (Src + 1)) + 2);
  v16 = v22;
  *(_DWORD *)Src = *(_DWORD *)L"MS Access";
  *((_DWORD *)Src + 1) = *(_DWORD *)L" Access";
  *((_DWORD *)Src + 2) = *(_DWORD *)L"ccess";
  *((_DWORD *)Src + 3) = *(_DWORD *)L"ess";
  Src[8] = wszAccess[8];
  Src[9] = 59;
  *((_DWORD *)Src + 5) = *(_DWORD *)L"DATABASE=";
  *((_DWORD *)Src + 6) = *(_DWORD *)L"TABASE=";
  *((_DWORD *)Src + 7) = *(_DWORD *)L"BASE=";
  *((_DWORD *)Src + 8) = *(_DWORD *)L"SE=";
  Src[18] = wszDbEq[8];
  v3 = 0;
LABEL_19:
  if ( Str )
    WCSCAT2(Src, L".mdb", v16);
  return v3;
}

```

## disassembly

```asm
0x100b1fa8  mov     edi, edi
0x100b1faa  push    ebp
0x100b1fab  mov     ebp, esp
0x100b1fad  sub     esp, 0Ch
0x100b1fb0  push    ebx
0x100b1fb1  mov     [ebp+var_4], edx
0x100b1fb4  mov     ebx, ecx
0x100b1fb6  xor     edx, edx
0x100b1fb8  push    edi
0x100b1fb9  mov     edi, edx
0x100b1fbb  test    ebx, ebx
0x100b1fbd  jz      loc_100B20CE
0x100b1fc3  push    esi
0x100b1fc4  mov     esi, ebx
0x100b1fc6  lea     ecx, [esi+2]
0x100b1fc9  mov     ax, [esi]
0x100b1fcc  add     esi, 2
0x100b1fcf  cmp     ax, dx
0x100b1fd2  jnz     short loc_100B1FC9
0x100b1fd4  sub     esi, ecx
0x100b1fd6  movzx   ecx, word ptr [ebx]
0x100b1fd9  sar     esi, 1
0x100b1fdb  push    27h ; '''
0x100b1fdd  pop     edx
0x100b1fde  lea     eax, [esi+esi]
0x100b1fe1  cmp     cx, dx
0x100b1fe4  jnz     short loc_100B202E
0x100b1fe6  cmp     [eax+ebx-2], dx
0x100b1feb  jnz     short loc_100B2008
0x100b1fed  xor     ecx, ecx
0x100b1fef  mov     [eax+ebx-2], cx
0x100b1ff4  add     eax, 0FFFFFFFEh
0x100b1ff7  push    eax; Size
0x100b1ff8  lea     eax, [ebx+2]
0x100b1ffb  push    eax; Src
0x100b1ffc  push    ebx; void *
0x100b1ffd  call    _memmove
0x100b2002  add     esp, 0Ch
0x100b2005  add     esi, 0FFFFFFFEh
0x100b2008  push    3Bh ; ';'; Ch
0x100b200a  push    ebx; Str
0x100b200b  call    ds:__imp__wcschr
0x100b2011  pop     ecx
0x100b2012  pop     ecx
0x100b2013  test    eax, eax
0x100b2015  jnz     loc_100B20D4
0x100b201b  push    5Ch ; '\'; Ch
0x100b201d  push    ebx; Str
0x100b201e  call    ds:__imp__wcsrchr
0x100b2024  pop     ecx
0x100b2025  pop     ecx
0x100b2026  test    eax, eax
0x100b2028  jnz     short loc_100B2038
0x100b202a  mov     eax, ebx
0x100b202c  jmp     short loc_100B203B
0x100b202e  push    22h ; '"'
0x100b2030  pop     edx
0x100b2031  cmp     cx, dx
0x100b2034  jnz     short loc_100B2008
0x100b2036  jmp     short loc_100B1FE6
0x100b2038  add     eax, 2
0x100b203b  push    2Eh ; '.'; Ch
0x100b203d  push    eax; Str
0x100b203e  call    ds:__imp__wcschr
0x100b2044  pop     ecx
0x100b2045  pop     ecx
0x100b2046  mov     ecx, eax
0x100b2048  xor     eax, eax
0x100b204a  test    ecx, ecx
0x100b204c  push    18h
0x100b204e  setz    al
0x100b2051  test    ecx, ecx
0x100b2053  mov     [ebp+Str], eax
0x100b2056  pop     eax
0x100b2057  push    14h
0x100b2059  pop     edx
0x100b205a  cmovnz  eax, edx
0x100b205d  add     eax, esi
0x100b205f  cmp     eax, [ebp+var_4]
0x100b2062  ja      loc_100B2172
0x100b2068  mov     ecx, ebx
0x100b206a  xor     esi, esi
0x100b206c  lea     edx, [ecx+2]
0x100b206f  mov     ax, [ecx]
0x100b2072  add     ecx, 2
0x100b2075  cmp     ax, si
0x100b2078  jnz     short loc_100B206F
0x100b207a  sub     ecx, edx
0x100b207c  sar     ecx, 1
0x100b207e  lea     eax, ds:2[ecx*2]
0x100b2085  push    eax; Size
0x100b2086  lea     eax, [ebx+26h]
0x100b2089  push    ebx; Src
0x100b208a  push    eax; void *
0x100b208b  call    _memmove
0x100b2090  mov     esi, offset _wszAccess; "MS Access"
0x100b2095  mov     ecx, [ebp+var_4]
0x100b2098  mov     edi, ebx
0x100b209a  add     esp, 0Ch
0x100b209d  movsd
0x100b209e  push    3Bh ; ';'
0x100b20a0  pop     eax
0x100b20a1  movsd
0x100b20a2  movsd
0x100b20a3  movsd
0x100b20a4  movsw
0x100b20a6  mov     [ebx+12h], ax
0x100b20aa  lea     edi, [ebx+14h]
0x100b20ad  mov     esi, offset _wszDbEq; "DATABASE="
0x100b20b2  movsd
0x100b20b3  movsd
0x100b20b4  movsd
0x100b20b5  movsd
0x100b20b6  movsw
0x100b20b8  xor     edi, edi
0x100b20ba  cmp     [ebp+Str], 0
0x100b20be  jz      short loc_100B20CD
0x100b20c0  push    ecx
0x100b20c1  mov     edx, offset _wszDefaultExt; ".mdb"
0x100b20c6  mov     ecx, ebx
0x100b20c8  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100b20cd  pop     esi
0x100b20ce  mov     eax, edi
0x100b20d0  pop     edi
0x100b20d1  pop     ebx
0x100b20d2  leave
0x100b20d3  retn
0x100b20d4  push    3Bh ; ';'
0x100b20d6  pop     eax
0x100b20d7  cmp     [ebx], ax
0x100b20da  jz      short loc_100B2112
0x100b20dc  push    9
0x100b20de  mov     edx, offset _wszAccess; "MS Access"
0x100b20e3  mov     ecx, ebx
0x100b20e5  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b20ea  test    eax, eax
0x100b20ec  jz      short loc_100B2112
0x100b20ee  push    7
0x100b20f0  mov     edx, offset aJet2X; "Jet 2.x"
0x100b20f5  mov     ecx, ebx
0x100b20f7  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b20fc  test    eax, eax
0x100b20fe  jz      short loc_100B2112
0x100b2100  push    7
0x100b2102  mov     edx, offset aJet3X; "Jet 3.x"
0x100b2107  mov     ecx, ebx
0x100b2109  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b210e  test    eax, eax
0x100b2110  jnz     short loc_100B20CD
0x100b2112  lea     eax, [ebp+var_C]
0x100b2115  mov     edx, offset _wszDbEq; "DATABASE="
0x100b211a  push    eax
0x100b211b  lea     eax, [ebp+Str]
0x100b211e  mov     ecx, ebx
0x100b2120  push    eax
0x100b2121  call    _FindConnStrItem@16; FindConnStrItem(x,x,x,x)
0x100b2126  cmp     [ebp+var_C], edi
0x100b2129  jnz     short loc_100B2132
0x100b212b  mov     edi, 0FFFFF40Ch
0x100b2130  jmp     short loc_100B20CD
0x100b2132  push    5Ch ; '\'; Ch
0x100b2134  push    [ebp+Str]; Str
0x100b2137  call    ds:__imp__wcsrchr
0x100b213d  pop     ecx
0x100b213e  pop     ecx
0x100b213f  test    eax, eax
0x100b2141  jnz     short loc_100B2148
0x100b2143  mov     eax, [ebp+Str]
0x100b2146  jmp     short loc_100B214B
0x100b2148  add     eax, 2
0x100b214b  push    2Eh ; '.'; Ch
0x100b214d  push    eax; Str
0x100b214e  call    ds:__imp__wcsrchr
0x100b2154  neg     eax
0x100b2156  pop     ecx
0x100b2157  sbb     eax, eax
0x100b2159  inc     eax
0x100b215a  mov     [ebp+Str], eax
0x100b215d  pop     ecx
0x100b215e  mov     ecx, [ebp+var_4]
0x100b2161  lea     eax, ds:1[eax*4]
0x100b2168  add     eax, esi
0x100b216a  cmp     eax, ecx
0x100b216c  jbe     loc_100B20BA
0x100b2172  mov     edi, 0FFFFF412h
0x100b2177  jmp     loc_100B20CD
```
