# HTMLOpenFile(x,x,x,x,x)

- ea: `0x10026190`
- end: `0x100264f2`
- name: `_HTMLOpenFile@20`
- size: `866`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, void *Src, int, int)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x10011d90`

## callees

- `0x1000a8c0`
- `0x1000b070`
- `0x1000b200`
- `0x1001d260`
- `0x1001d270`
- `0x1001d2d0`
- `0x1001d2f0`
- `0x1001d440`
- `0x1001d570`
- `0x10025a80`
- `0x10025c60`
- `0x10026190`
- `0x100277a0`
- `0x1002b81a`
- `0x1002c490`
- `0x1002d9e1`

## pseudocode

```c
int __stdcall HTMLOpenFile(WCHAR *lpFileName, int a2, void *Src, int a4, _DWORD *a5)
{
  _DWORD *v5; // eax
  _DWORD *v6; // ebp
  int v7; // edx
  int v9; // eax
  unsigned __int16 *v10; // ecx
  int v11; // edx
  unsigned __int16 v12; // ax
  int v13; // eax
  int v14; // edx
  unsigned __int16 v15; // ax
  char *v16; // esi
  int v17; // edx
  unsigned __int16 *v18; // eax
  int v19; // ecx
  int v20; // esi
  unsigned int v21; // esi
  _DWORD *v22; // edi
  int v23; // edx
  const WCHAR *v24; // eax
  wchar_t *v25; // ecx
  int v26; // edx
  wchar_t v27; // ax
  int v28; // eax
  int v29; // eax
  int v30; // ecx
  _DWORD *v31; // ebx
  _DWORD *v32; // esi
  int v33; // edi
  int i; // [esp+Ch] [ebp-2A0h]
  int v35; // [esp+10h] [ebp-29Ch]
  wchar_t String1[66]; // [esp+18h] [ebp-294h] BYREF
  unsigned __int16 v37[261]; // [esp+9Ch] [ebp-210h] BYREF
  char v38; // [esp+2A6h] [ebp-6h] BYREF

  v5 = (_DWORD *)MemAllocate(0x1044u);
  v6 = v5;
  if ( !v5 )
    return -1011;
  memset(v5, 0, 0x1044u);
  v6[10] = a4;
  v7 = TextStorageCreate();
  v6[7] = v7;
  if ( !v7 )
  {
    MemFree(v6);
    return -1011;
  }
  if ( a2 )
  {
    v9 = TextStoragePut(v7, Src, wcslen((const unsigned __int16 *)Src), 0);
    v10 = v37;
    v6[8] = v9;
    v11 = 261;
    while ( v11 != -2147483385 )
    {
      v12 = *(unsigned __int16 *)((char *)v10 + (_BYTE *)Src - (_BYTE *)v37);
      if ( !v12 )
        break;
      *v10++ = v12;
      if ( !--v11 )
        goto LABEL_17;
    }
  }
  else
  {
    v13 = TextStoragePut(v7, lpFileName, wcslen(lpFileName), 0);
    v10 = v37;
    v6[8] = v13;
    v14 = 261;
    while ( v14 != -2147483385 )
    {
      v15 = *(unsigned __int16 *)((char *)v10 + (char *)lpFileName - (char *)v37);
      if ( !v15 )
        break;
      *v10++ = v15;
      if ( !--v14 )
      {
LABEL_17:
        --v10;
        break;
      }
    }
  }
  v16 = 0;
  *v10 = 0;
  v17 = 261;
  v18 = v37;
  if ( !v37[0] )
    goto LABEL_28;
  do
  {
    if ( !v17 )
      break;
    v19 = *v18;
    if ( v19 == 92 || v19 == 47 || v19 == 58 )
      v16 = (char *)(v18 + 1);
    ++v18;
    --v17;
  }
  while ( *v18 );
  if ( v16 )
  {
    if ( v16 < &v38 )
      *(_WORD *)v16 = 0;
  }
  else
  {
LABEL_28:
    v37[0] = 0;
  }
  v6[9] = TextStoragePut(v6[7], v37, wcslen(v37), 0);
  v20 = BFOpenFile(lpFileName, 0, (int)v6);
  if ( v20 )
    goto LABEL_32;
  dword_10041B70 = 0;
  v20 = ParseHTML(v6);
  if ( v20 )
  {
    BFCloseFile(*v6);
    FreeTables(v6);
LABEL_32:
    TextStorageDestroy(v6[7]);
    MemFree(v6);
    v21 = -v20;
    if ( v21 >= 0x10 )
      return -5016;
    else
      return dword_100038B8[v21];
  }
  v22 = (_DWORD *)v6[3];
  v23 = 0;
  for ( i = 0; v22; v22 = (_DWORD *)*v22 )
  {
    i = v23 + 1;
    v24 = (const WCHAR *)TextStorageGet(v6[7], v22[1]);
    MakeValidJetName(v24, String1, 65, 0x4B0u);
    if ( !_wcsicmp(String1, L"NoName") )
    {
      v25 = String1;
      v26 = 65;
      while ( v26 != -2147483581 )
      {
        v27 = *(wchar_t *)((char *)v25 + (char *)L"Table" - (char *)String1);
        if ( !v27 )
          break;
        *v25++ = v27;
        if ( !--v26 )
        {
          --v25;
          break;
        }
      }
      *v25 = 0;
    }
    v28 = TextStoragePut(v6[7], String1, wcslen(String1), 0);
    v23 = i;
    v22[1] = v28;
  }
  v29 = 1;
  v30 = 0;
  while ( 1 )
  {
    v35 = v29;
    if ( v29 != 1 && v30 != 1 )
      break;
    if ( v29 > v23 )
      break;
    v31 = (_DWORD *)v6[3];
    if ( v31 )
    {
      do
      {
        v32 = (_DWORD *)*v31;
        v33 = 1;
        if ( *v31 )
        {
          do
          {
            if ( v31[1] == v32[1] )
            {
              AppendSuffix_1(v6, v32, v33++, 64);
              v30 = 1;
            }
            v32 = (_DWORD *)*v32;
          }
          while ( v32 );
        }
        v31 = (_DWORD *)*v31;
      }
      while ( v31 );
      v29 = v35;
      v23 = i;
    }
    ++v29;
  }
  *a5 = v6;
  return 0;
}

```

## disassembly

```asm
0x10026190  sub     esp, 2A0h
0x10026196  mov     eax, ___security_cookie
0x1002619b  xor     eax, esp
0x1002619d  mov     [esp+2A0h+var_4], eax
0x100261a4  mov     eax, [esp+2A0h+arg_10]
0x100261ab  push    ebx
0x100261ac  mov     ebx, [esp+2A4h+lpFileName]
0x100261b3  push    ebp
0x100261b4  push    esi
0x100261b5  mov     esi, [esp+2ACh+Src]
0x100261bc  push    1044h; Size
0x100261c1  mov     [esp+2B0h+var_298], eax
0x100261c5  call    _MemAllocate@4; MemAllocate(x)
0x100261ca  mov     ebp, eax
0x100261cc  test    ebp, ebp
0x100261ce  jz      short loc_100261FE
0x100261d0  push    1044h; Size
0x100261d5  push    0; Val
0x100261d7  push    ebp; void *
0x100261d8  call    _memset
0x100261dd  mov     eax, [esp+2B8h+arg_C]
0x100261e4  add     esp, 0Ch
0x100261e7  mov     [ebp+28h], eax
0x100261ea  call    _TextStorageCreate@0; TextStorageCreate()
0x100261ef  mov     edx, eax
0x100261f1  mov     [ebp+1Ch], edx
0x100261f4  test    edx, edx
0x100261f6  jnz     short loc_10026208
0x100261f8  push    ebp
0x100261f9  call    _MemFree@4; MemFree(x)
0x100261fe  mov     eax, 0FFFFFC0Dh
0x10026203  jmp     loc_100264D8
0x10026208  cmp     [esp+2ACh+arg_4], 0
0x10026210  push    edi
0x10026211  jz      short loc_1002626E
0x10026213  mov     ecx, esi
0x10026215  lea     edi, [ecx+2]
0x10026218  jmp     short loc_10026220
0x10026220  mov     ax, [ecx]
0x10026223  add     ecx, 2
0x10026226  test    ax, ax
0x10026229  jnz     short loc_10026220
0x1002622b  sub     ecx, edi
0x1002622d  push    0; char
0x1002622f  sar     ecx, 1
0x10026231  push    ecx; int
0x10026232  push    esi; Src
0x10026233  push    edx; int
0x10026234  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x10026239  lea     ecx, [esp+2B0h+var_210]
0x10026240  mov     [ebp+20h], eax
0x10026243  mov     eax, ecx
0x10026245  mov     edx, 105h
0x1002624a  sub     esi, eax
0x1002624c  lea     esp, [esp+0]
0x10026250  lea     eax, [edx+7FFFFEF9h]
0x10026256  test    eax, eax
0x10026258  jz      short loc_100262BF
0x1002625a  movzx   eax, word ptr [esi+ecx]
0x1002625e  test    ax, ax
0x10026261  jz      short loc_100262BF
0x10026263  mov     [ecx], ax
0x10026266  add     ecx, 2
0x10026269  dec     edx
0x1002626a  jnz     short loc_10026250
0x1002626c  jmp     short loc_100262C3
0x1002626e  mov     ecx, ebx
0x10026270  lea     esi, [ecx+2]
0x10026273  mov     ax, [ecx]
0x10026276  add     ecx, 2
0x10026279  test    ax, ax
0x1002627c  jnz     short loc_10026273
0x1002627e  sub     ecx, esi
0x10026280  push    0; char
0x10026282  sar     ecx, 1
0x10026284  push    ecx; int
0x10026285  push    ebx; Src
0x10026286  push    edx; int
0x10026287  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x1002628c  lea     ecx, [esp+2B0h+var_210]
0x10026293  mov     [ebp+20h], eax
0x10026296  mov     esi, ebx
0x10026298  mov     eax, ecx
0x1002629a  mov     edx, 105h
0x1002629f  sub     esi, eax
0x100262a1  lea     eax, [edx+7FFFFEF9h]
0x100262a7  test    eax, eax
0x100262a9  jz      short loc_100262BF
0x100262ab  movzx   eax, word ptr [esi+ecx]
0x100262af  test    ax, ax
0x100262b2  jz      short loc_100262BF
0x100262b4  mov     [ecx], ax
0x100262b7  add     ecx, 2
0x100262ba  dec     edx
0x100262bb  jnz     short loc_100262A1
0x100262bd  jmp     short loc_100262C3
0x100262bf  test    edx, edx
0x100262c1  jnz     short loc_100262C6
0x100262c3  sub     ecx, 2
0x100262c6  xor     eax, eax
0x100262c8  xor     esi, esi
0x100262ca  mov     [ecx], ax
0x100262cd  mov     edx, 105h
0x100262d2  lea     eax, [esp+2B0h+var_210]
0x100262d9  cmp     [esp+2B0h+var_210], si
0x100262e1  jz      short loc_1002631C
0x100262e3  test    edx, edx
0x100262e5  jz      short loc_10026306
0x100262e7  movzx   ecx, word ptr [eax]
0x100262ea  cmp     ecx, 5Ch ; '\'
0x100262ed  jz      short loc_100262F9
0x100262ef  cmp     ecx, 2Fh ; '/'
0x100262f2  jz      short loc_100262F9
0x100262f4  cmp     ecx, 3Ah ; ':'
0x100262f7  jnz     short loc_100262FC
0x100262f9  lea     esi, [eax+2]
0x100262fc  add     eax, 2
0x100262ff  dec     edx
0x10026300  cmp     word ptr [eax], 0
0x10026304  jnz     short loc_100262E3
0x10026306  test    esi, esi
0x10026308  jz      short loc_1002631C
0x1002630a  lea     eax, [esp+2B0h+var_6]
0x10026311  cmp     esi, eax
0x10026313  jnb     short loc_10026326
0x10026315  xor     eax, eax
0x10026317  mov     [esi], ax
0x1002631a  jmp     short loc_10026326
0x1002631c  xor     eax, eax
0x1002631e  mov     [esp+2B0h+var_210], ax
0x10026326  lea     ecx, [esp+2B0h+var_210]
0x1002632d  lea     edx, [ecx+2]
0x10026330  mov     ax, [ecx]
0x10026333  add     ecx, 2
0x10026336  test    ax, ax
0x10026339  jnz     short loc_10026330
0x1002633b  sub     ecx, edx
0x1002633d  lea     eax, [esp+2B0h+var_210]
0x10026344  push    0; char
0x10026346  sar     ecx, 1
0x10026348  push    ecx; int
0x10026349  push    eax; Src
0x1002634a  push    dword ptr [ebp+1Ch]; int
0x1002634d  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x10026352  push    ebp; int
0x10026353  push    0; int
0x10026355  push    ebx; lpFileName
0x10026356  mov     [ebp+24h], eax
0x10026359  call    _BFOpenFile@12; BFOpenFile(x,x,x)
0x1002635e  mov     esi, eax
0x10026360  test    esi, esi
0x10026362  jnz     short loc_10026383
0x10026364  push    ebp
0x10026365  mov     dword_10041B70, eax
0x1002636a  call    ParseHTML
0x1002636f  mov     esi, eax
0x10026371  test    esi, esi
0x10026373  jz      short loc_100263B0
0x10026375  push    dword ptr [ebp+0]
0x10026378  call    _BFCloseFile@4; BFCloseFile(x)
0x1002637d  push    ebp
0x1002637e  call    FreeTables
0x10026383  push    dword ptr [ebp+1Ch]
0x10026386  call    _TextStorageDestroy@4; TextStorageDestroy(x)
0x1002638b  push    ebp
0x1002638c  call    _MemFree@4; MemFree(x)
0x10026391  neg     esi
0x10026393  js      short loc_100263A6
0x10026395  cmp     esi, 0Fh
0x10026398  ja      short loc_100263A6
0x1002639a  mov     eax, ds:dword_100038B8[esi*4]
0x100263a1  jmp     loc_100264D7
0x100263a6  mov     eax, 0FFFFEC68h
0x100263ab  jmp     loc_100264D7
0x100263b0  mov     edi, [ebp+0Ch]
0x100263b3  xor     edx, edx
0x100263b5  mov     [esp+2B0h+var_2A0], edx
0x100263b9  test    edi, edi
0x100263bb  jz      loc_10026471
0x100263c1  push    4B0h; CodePage
0x100263c6  push    41h ; 'A'; cchWideChar
0x100263c8  lea     eax, [esp+2B8h+String1]
0x100263cc  inc     edx
0x100263cd  push    eax; pszDest
0x100263ce  push    dword ptr [edi+4]
0x100263d1  mov     [esp+2C0h+var_2A0], edx
0x100263d5  push    dword ptr [ebp+1Ch]
0x100263d8  call    _TextStorageGet@8; TextStorageGet(x,x)
0x100263dd  push    eax; lpWideCharStr
0x100263de  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x100263e3  lea     eax, [esp+2B0h+String1]
0x100263e7  push    offset aNoname; "NoName"
0x100263ec  push    eax; String1
0x100263ed  call    __wcsicmp
0x100263f2  add     esp, 8
0x100263f5  test    eax, eax
0x100263f7  jnz     short loc_1002643A
0x100263f9  lea     ecx, [esp+2B0h+String1]
0x100263fd  mov     esi, offset aTable_1; "Table"
0x10026402  lea     edx, [eax+41h]
0x10026405  mov     eax, ecx
0x10026407  sub     esi, eax
0x10026409  lea     esp, [esp+0]
0x10026410  lea     eax, [edx+7FFFFFBDh]
0x10026416  test    eax, eax
0x10026418  jz      short loc_1002642E
0x1002641a  movzx   eax, word ptr [esi+ecx]
0x1002641e  test    ax, ax
0x10026421  jz      short loc_1002642E
0x10026423  mov     [ecx], ax
0x10026426  add     ecx, 2
0x10026429  dec     edx
0x1002642a  jnz     short loc_10026410
0x1002642c  jmp     short loc_10026432
0x1002642e  test    edx, edx
0x10026430  jnz     short loc_10026435
0x10026432  sub     ecx, 2
0x10026435  xor     eax, eax
0x10026437  mov     [ecx], ax
0x1002643a  lea     ecx, [esp+2B0h+String1]
0x1002643e  lea     edx, [ecx+2]
0x10026441  mov     ax, [ecx]
0x10026444  add     ecx, 2
0x10026447  test    ax, ax
0x1002644a  jnz     short loc_10026441
0x1002644c  sub     ecx, edx
0x1002644e  lea     eax, [esp+2B0h+String1]
0x10026452  push    0; char
0x10026454  sar     ecx, 1
0x10026456  push    ecx; int
0x10026457  push    eax; Src
0x10026458  push    dword ptr [ebp+1Ch]; int
0x1002645b  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x10026460  mov     edx, [esp+2B0h+var_2A0]
0x10026464  mov     [edi+4], eax
0x10026467  mov     edi, [edi]
0x10026469  test    edi, edi
0x1002646b  jnz     loc_100263C1
0x10026471  mov     eax, 1
0x10026476  xor     ecx, ecx
0x10026478  mov     [esp+2B0h+var_29C], eax
0x1002647c  cmp     eax, 1
0x1002647f  jz      short loc_10026486
0x10026481  cmp     ecx, 1
0x10026484  jnz     short loc_100264CF
0x10026486  cmp     eax, edx
0x10026488  jg      short loc_100264CF
0x1002648a  mov     ebx, [ebp+0Ch]
0x1002648d  test    ebx, ebx
0x1002648f  jz      short loc_100264CC
0x10026491  mov     esi, [ebx]
0x10026493  mov     edi, 1
0x10026498  test    esi, esi
0x1002649a  jz      short loc_100264BE
0x1002649c  lea     esp, [esp+0]
0x100264a0  mov     eax, [ebx+4]
0x100264a3  cmp     eax, [esi+4]
0x100264a6  jnz     short loc_100264B8
0x100264a8  push    40h ; '@'
0x100264aa  push    edi
0x100264ab  push    esi
0x100264ac  push    ebp
0x100264ad  call    AppendSuffix_1
0x100264b2  inc     edi
0x100264b3  mov     ecx, 1
0x100264b8  mov     esi, [esi]
0x100264ba  test    esi, esi
0x100264bc  jnz     short loc_100264A0
0x100264be  mov     ebx, [ebx]
0x100264c0  test    ebx, ebx
0x100264c2  jnz     short loc_10026491
0x100264c4  mov     eax, [esp+2B0h+var_29C]
0x100264c8  mov     edx, [esp+2B0h+var_2A0]
0x100264cc  inc     eax
0x100264cd  jmp     short loc_10026478
0x100264cf  mov     eax, [esp+2B0h+var_298]
0x100264d3  mov     [eax], ebp
0x100264d5  xor     eax, eax
0x100264d7  pop     edi
0x100264d8  mov     ecx, [esp+2ACh+var_4]
0x100264df  pop     esi
0x100264e0  pop     ebp
0x100264e1  pop     ebx
0x100264e2  xor     ecx, esp; StackCookie
0x100264e4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100264e9  add     esp, 2A0h
0x100264ef  retn    14h
```
