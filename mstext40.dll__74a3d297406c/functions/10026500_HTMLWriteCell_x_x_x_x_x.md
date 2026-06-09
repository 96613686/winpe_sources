# HTMLWriteCell(x,x,x,x,x)

- ea: `0x10026500`
- end: `0x100268be`
- name: `_HTMLWriteCell@20`
- size: `958`
- prototype: `int __stdcall(int, int, int, wchar_t *Str, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1001e1e0`

## callees

- `0x1000ad60`
- `0x10026500`
- `0x10028bb0`
- `0x10028ee0`
- `0x10028f80`
- `0x10029000`
- `0x1002b81a`
- `0x1002c32f`

## pseudocode

```c
int __stdcall HTMLWriteCell(int a1, int a2, char a3, wchar_t *Str, int a5)
{
  wchar_t *v5; // ecx
  wchar_t *v6; // esi
  int v7; // edi
  int v8; // edx
  wchar_t v9; // ax
  int v10; // ebx
  wchar_t v11; // ax
  int v12; // edx
  wchar_t v13; // ax
  int v14; // eax
  unsigned int v15; // eax
  int result; // eax
  wchar_t *v17; // eax
  wchar_t *v18; // eax
  int v19; // ecx
  unsigned __int16 *v20; // edi
  int v21; // esi
  int v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  int v25; // ecx
  wchar_t *v26; // [esp+10h] [ebp-94h]
  wchar_t *v27; // [esp+10h] [ebp-94h]
  int v28; // [esp+10h] [ebp-94h]
  wchar_t *v29; // [esp+14h] [ebp-90h]
  wchar_t *v30; // [esp+18h] [ebp-8Ch]
  wchar_t pszDest[64]; // [esp+20h] [ebp-84h] BYREF

  v5 = pszDest;
  v6 = Str;
  v7 = a1;
  v8 = 64;
  v26 = Str;
  if ( (a3 & 2) != 0 )
  {
    while ( v8 != -2147483582 )
    {
      v9 = *(wchar_t *)((char *)v5 + (char *)L"<TH" - (char *)pszDest);
      if ( !v9 )
        break;
      *v5++ = v9;
      if ( !--v8 )
        goto LABEL_21;
    }
  }
  else
  {
    v10 = (char *)L"<TD" - (char *)pszDest;
    while ( v8 != -2147483582 )
    {
      v11 = *(wchar_t *)((char *)v5 + v10);
      if ( !v11 )
        break;
      *v5++ = v11;
      if ( !--v8 )
      {
        --v5;
        break;
      }
    }
    *v5 = 0;
    if ( (a3 & 0x40) != 0 )
    {
      StringCchCatW(pszDest, 0x40u, L" DIR=RTL");
      goto LABEL_23;
    }
    if ( wcslen(Str) )
    {
      StringCchCatW(pszDest, 0x40u, L" DIR=LTR");
      goto LABEL_23;
    }
    v12 = 64;
    v5 = pszDest;
    while ( v12 != -2147483582 )
    {
      v13 = *(wchar_t *)((char *)v5 + v10);
      if ( !v13 )
        break;
      *v5++ = v13;
      if ( !--v12 )
      {
LABEL_21:
        --v5;
        break;
      }
    }
  }
  *v5 = 0;
LABEL_23:
  if ( (a3 & 4) != 0 )
  {
    StringCchCatW(pszDest, 0x40u, L" ALIGN=LEFT");
  }
  else if ( (a3 & 8) != 0 )
  {
    StringCchCatW(pszDest, 0x40u, L" ALIGN=RIGHT");
  }
  else if ( (a3 & 0x10) != 0 )
  {
    StringCchCatW(pszDest, 0x40u, L" ALIGN=CENTER");
  }
  StringCchCatW(pszDest, 0x40u, L">");
  v14 = TextWriteHTMLFile(a1, a2, pszDest, wcslen(pszDest), a5, 0);
  if ( v14 )
  {
    v15 = -v14;
    if ( v15 >= 0x10 )
      return -5016;
    result = dword_100038B8[v15];
    if ( result < 0 )
      return result;
  }
  if ( (a3 & 0x20) == 0 || (v17 = wcschr(Str, 0x23u), (v30 = v17) == 0) )
  {
    if ( *Str )
    {
      if ( wcschr(Str, 0xAu) )
      {
        if ( *Str )
        {
          while ( 2 )
          {
            v20 = v6;
            v21 = 0;
            while ( 1 )
            {
              v22 = TextWriteHTMLFile(a1, a2, v20, 1, a5, 2);
              if ( v22 )
                break;
              ++v21;
              ++v20;
              if ( v21 >= 1 )
                goto LABEL_59;
            }
            v23 = -v22;
            if ( v23 >= 0x10 )
              return -5016;
            result = dword_100038B8[v23];
            if ( result < 0 )
              return result;
LABEL_59:
            v7 = a1;
            if ( *v26 == 10 )
            {
              result = WriteString(a1, a2, L"<BR>", 0, a5);
              if ( result < 0 )
                return result;
            }
            v6 = v26 + 1;
            v26 = v6;
            if ( *v6 )
              continue;
            break;
          }
        }
      }
      else
      {
        result = WriteString(a1, a2, Str, 2, a5);
        if ( result < 0 )
          return result;
      }
    }
    goto LABEL_62;
  }
  v29 = v17 + 1;
  v27 = wcschr(v17 + 1, 0);
  v18 = wcschr(v29, 0x23u);
  if ( v18 )
  {
    v19 = v18[1];
    if ( !(_WORD)v19 || v19 == 35 )
      v27 = v18;
  }
  result = WriteString(a1, a2, L"<A HREF=\"", 0, a5);
  if ( result >= 0 )
  {
    v28 = ((char *)v27 - (char *)v30 - 2) >> 1;
    result = WriteURL(a1, a2, v29, v28, a5);
    if ( result >= 0 )
    {
      result = WriteString(a1, a2, L"\">", 0, a5);
      if ( result >= 0 )
      {
        if ( v30 - Str <= 0 )
        {
          result = WriteBytes(a1, a2, v29, v28, 0, a5);
          if ( result < 0 )
            return result;
        }
        else
        {
          result = WriteBytes(a1, a2, Str, v30 - Str, 2, a5);
          if ( result < 0 )
            return result;
        }
        result = WriteString(a1, a2, L"</A>", 0, a5);
        if ( result >= 0 )
        {
LABEL_62:
          if ( (a3 & 2) != 0 )
            v24 = WriteString(v7, a2, L"</TH>", 1, a5);
          else
            v24 = WriteString(v7, a2, L"</TD>", 1, a5);
          v25 = v24;
          result = 0;
          if ( v25 < 0 )
            return v25;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10026500  sub     esp, 94h
0x10026506  mov     eax, ___security_cookie
0x1002650b  xor     eax, esp
0x1002650d  mov     [esp+94h+var_4], eax
0x10026514  mov     eax, [esp+94h+arg_8]
0x1002651b  lea     ecx, [esp+94h+pszDest]
0x1002651f  push    ebx
0x10026520  push    ebp
0x10026521  push    esi
0x10026522  mov     esi, [esp+0A0h+Str]
0x10026529  and     eax, 2
0x1002652c  push    edi
0x1002652d  mov     edi, [esp+0A4h+arg_0]
0x10026534  mov     edx, 40h ; '@'
0x10026539  mov     [esp+0A4h+var_88], eax
0x1002653d  mov     eax, ecx
0x1002653f  mov     [esp+0A4h+var_90], edi
0x10026543  mov     [esp+0A4h+var_94], esi
0x10026547  jz      short loc_10026579
0x10026549  mov     ebx, offset aTh_2; "<TH"
0x1002654e  sub     ebx, eax
0x10026550  lea     eax, [edx+7FFFFFBEh]
0x10026556  test    eax, eax
0x10026558  jz      loc_1002661E
0x1002655e  movzx   eax, word ptr [ebx+ecx]
0x10026562  test    ax, ax
0x10026565  jz      loc_1002661E
0x1002656b  mov     [ecx], ax
0x1002656e  add     ecx, 2
0x10026571  dec     edx
0x10026572  jnz     short loc_10026550
0x10026574  jmp     loc_10026622
0x10026579  mov     ebx, offset aTd_1; "<TD"
0x1002657e  sub     ebx, eax
0x10026580  lea     eax, [edx+7FFFFFBEh]
0x10026586  test    eax, eax
0x10026588  jz      short loc_1002659E
0x1002658a  movzx   eax, word ptr [ebx+ecx]
0x1002658e  test    ax, ax
0x10026591  jz      short loc_1002659E
0x10026593  mov     [ecx], ax
0x10026596  add     ecx, 2
0x10026599  dec     edx
0x1002659a  jnz     short loc_10026580
0x1002659c  jmp     short loc_100265A2
0x1002659e  test    edx, edx
0x100265a0  jnz     short loc_100265A5
0x100265a2  sub     ecx, 2
0x100265a5  xor     eax, eax
0x100265a7  mov     [ecx], ax
0x100265aa  mov     eax, [esp+0A4h+arg_8]
0x100265b1  test    al, 40h
0x100265b3  jz      short loc_100265C8
0x100265b5  push    offset aDirRtl; " DIR=RTL"
0x100265ba  push    40h ; '@'; cchDest
0x100265bc  lea     eax, [esp+0ACh+pszDest]
0x100265c0  push    eax; pszDest
0x100265c1  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x100265c6  jmp     short loc_1002662A
0x100265c8  mov     ecx, esi
0x100265ca  lea     edx, [ecx+2]
0x100265cd  lea     ecx, [ecx+0]
0x100265d0  mov     ax, [ecx]
0x100265d3  add     ecx, 2
0x100265d6  test    ax, ax
0x100265d9  jnz     short loc_100265D0
0x100265db  sub     ecx, edx
0x100265dd  sar     ecx, 1
0x100265df  jz      short loc_100265F4
0x100265e1  push    offset aDirLtr; " DIR=LTR"
0x100265e6  push    40h ; '@'; cchDest
0x100265e8  lea     eax, [esp+0ACh+pszDest]
0x100265ec  push    eax; pszDest
0x100265ed  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x100265f2  jmp     short loc_1002662A
0x100265f4  mov     edx, 40h ; '@'
0x100265f9  lea     ecx, [esp+0A4h+pszDest]
0x100265fd  lea     ecx, [ecx+0]
0x10026600  lea     eax, [edx+7FFFFFBEh]
0x10026606  test    eax, eax
0x10026608  jz      short loc_1002661E
0x1002660a  movzx   eax, word ptr [ebx+ecx]
0x1002660e  test    ax, ax
0x10026611  jz      short loc_1002661E
0x10026613  mov     [ecx], ax
0x10026616  add     ecx, 2
0x10026619  dec     edx
0x1002661a  jnz     short loc_10026600
0x1002661c  jmp     short loc_10026622
0x1002661e  test    edx, edx
0x10026620  jnz     short loc_10026625
0x10026622  sub     ecx, 2
0x10026625  xor     eax, eax
0x10026627  mov     [ecx], ax
0x1002662a  mov     eax, [esp+0A4h+arg_8]
0x10026631  test    al, 4
0x10026633  jz      short loc_1002663C
0x10026635  push    offset aAlignLeft; " ALIGN=LEFT"
0x1002663a  jmp     short loc_10026650
0x1002663c  test    al, 8
0x1002663e  jz      short loc_10026647
0x10026640  push    offset aAlignRight; " ALIGN=RIGHT"
0x10026645  jmp     short loc_10026650
0x10026647  test    al, 10h
0x10026649  jz      short loc_1002665C
0x1002664b  push    offset aAlignCenter; " ALIGN=CENTER"
0x10026650  push    40h ; '@'; cchDest
0x10026652  lea     eax, [esp+0ACh+pszDest]
0x10026656  push    eax; pszDest
0x10026657  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1002665c  push    offset asc_10004C00; ">"
0x10026661  push    40h ; '@'; cchDest
0x10026663  lea     eax, [esp+0ACh+pszDest]
0x10026667  push    eax; pszDest
0x10026668  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1002666d  lea     ecx, [esp+0A4h+pszDest]
0x10026671  lea     edx, [ecx+2]
0x10026674  mov     ax, [ecx]
0x10026677  add     ecx, 2
0x1002667a  test    ax, ax
0x1002667d  jnz     short loc_10026674
0x1002667f  mov     ebx, [esp+0A4h+arg_10]
0x10026686  lea     eax, [esp+0A4h+pszDest]
0x1002668a  mov     ebp, [esp+0A4h+arg_4]
0x10026691  sub     ecx, edx
0x10026693  push    0; int
0x10026695  push    ebx; int
0x10026696  sar     ecx, 1
0x10026698  push    ecx; int
0x10026699  push    eax; void *
0x1002669a  push    ebp; int
0x1002669b  push    edi; int
0x1002669c  call    TextWriteHTMLFile
0x100266a1  test    eax, eax
0x100266a3  jz      short loc_100266C7
0x100266a5  neg     eax
0x100266a7  js      loc_10026799
0x100266ad  cmp     eax, 0Fh
0x100266b0  ja      loc_10026799
0x100266b6  mov     eax, ds:dword_100038B8[eax*4]
0x100266bd  test    eax, eax
0x100266bf  jz      short loc_100266C7
0x100266c1  js      loc_100268A3
0x100266c7  mov     eax, [esp+0A4h+arg_8]
0x100266ce  test    al, 20h
0x100266d0  jz      loc_100267D9
0x100266d6  push    23h ; '#'; Ch
0x100266d8  push    esi; Str
0x100266d9  call    _wcschr
0x100266de  add     esp, 8
0x100266e1  mov     [esp+0A4h+var_8C], eax
0x100266e5  test    eax, eax
0x100266e7  jz      loc_100267D9
0x100266ed  add     eax, 2
0x100266f0  push    0; Ch
0x100266f2  push    eax; Str
0x100266f3  mov     [esp+0ACh+var_90], eax
0x100266f7  call    _wcschr
0x100266fc  push    23h ; '#'; Ch
0x100266fe  push    [esp+0B0h+var_90]; Str
0x10026702  mov     [esp+0B4h+var_94], eax
0x10026706  call    _wcschr
0x1002670b  add     esp, 10h
0x1002670e  test    eax, eax
0x10026710  jz      short loc_10026724
0x10026712  movzx   ecx, word ptr [eax+2]
0x10026716  test    cx, cx
0x10026719  jz      short loc_10026720
0x1002671b  cmp     ecx, 23h ; '#'
0x1002671e  jnz     short loc_10026724
0x10026720  mov     [esp+0A4h+var_94], eax
0x10026724  push    ebx; int
0x10026725  push    0; int
0x10026727  push    offset aAHref; "<A HREF=\""
0x1002672c  push    ebp; int
0x1002672d  push    edi; int
0x1002672e  call    WriteString
0x10026733  test    eax, eax
0x10026735  js      loc_100268A3
0x1002673b  mov     eax, [esp+0A4h+var_94]
0x1002673f  sub     eax, [esp+0A4h+var_8C]
0x10026743  push    ebx; int
0x10026744  sub     eax, 2
0x10026747  sar     eax, 1
0x10026749  push    eax; int
0x1002674a  push    [esp+0ACh+var_90]; Str
0x1002674e  mov     [esp+0B0h+var_94], eax
0x10026752  push    ebp; int
0x10026753  push    edi; int
0x10026754  call    WriteURL
0x10026759  test    eax, eax
0x1002675b  js      loc_100268A3
0x10026761  push    ebx; int
0x10026762  push    0; int
0x10026764  push    offset asc_10004A50; "\">"
0x10026769  push    ebp; int
0x1002676a  push    edi; int
0x1002676b  call    WriteString
0x10026770  test    eax, eax
0x10026772  js      loc_100268A3
0x10026778  mov     eax, [esp+0A4h+var_8C]
0x1002677c  sub     eax, esi
0x1002677e  sar     eax, 1
0x10026780  push    ebx; int
0x10026781  test    eax, eax
0x10026783  jle     short loc_100267A3
0x10026785  push    2; int
0x10026787  push    eax; int
0x10026788  push    esi; void *
0x10026789  push    ebp; int
0x1002678a  push    edi; int
0x1002678b  call    WriteBytes
0x10026790  test    eax, eax
0x10026792  jns     short loc_100267BD
0x10026794  jmp     loc_100268A3
0x10026799  mov     eax, 0FFFFEC68h
0x1002679e  jmp     loc_100268A3
0x100267a3  mov     eax, [esp+0A8h+var_94]
0x100267a7  push    0; int
0x100267a9  push    eax; int
0x100267aa  push    [esp+0B0h+var_90]; void *
0x100267ae  push    ebp; int
0x100267af  push    edi; int
0x100267b0  call    WriteBytes
0x100267b5  test    eax, eax
0x100267b7  js      loc_100268A3
0x100267bd  push    ebx; int
0x100267be  push    0; int
0x100267c0  push    offset aA; "</A>"
0x100267c5  push    ebp; int
0x100267c6  push    edi; int
0x100267c7  call    WriteString
0x100267cc  test    eax, eax
0x100267ce  jns     loc_1002687D
0x100267d4  jmp     loc_100268A3
0x100267d9  cmp     word ptr [esi], 0
0x100267dd  jz      loc_1002687D
0x100267e3  push    0Ah; Ch
0x100267e5  push    esi; Str
0x100267e6  call    _wcschr
0x100267eb  add     esp, 8
0x100267ee  test    eax, eax
0x100267f0  jnz     short loc_10026806
0x100267f2  push    ebx; int
0x100267f3  push    2; int
0x100267f5  push    esi; void *
0x100267f6  push    ebp; int
0x100267f7  push    edi; int
0x100267f8  call    WriteString
0x100267fd  test    eax, eax
0x100267ff  jns     short loc_1002687D
0x10026801  jmp     loc_100268A3
0x10026806  cmp     word ptr [esi], 0
0x1002680a  jz      short loc_1002687D
0x1002680c  lea     esp, [esp+0]
0x10026810  mov     edi, esi
0x10026812  xor     esi, esi
0x10026814  push    2; int
0x10026816  push    ebx; int
0x10026817  push    1; int
0x10026819  push    edi; void *
0x1002681a  push    ebp; int
0x1002681b  push    [esp+0B8h+var_90]; int
0x1002681f  call    TextWriteHTMLFile
0x10026824  test    eax, eax
0x10026826  jnz     short loc_10026833
0x10026828  inc     esi
0x10026829  add     edi, 2
0x1002682c  cmp     esi, 1
0x1002682f  jl      short loc_10026814
0x10026831  jmp     short loc_1002684F
0x10026833  neg     eax
0x10026835  js      loc_10026799
0x1002683b  cmp     eax, 0Fh
0x1002683e  ja      loc_10026799
0x10026844  mov     eax, ds:dword_100038B8[eax*4]
0x1002684b  test    eax, eax
0x1002684d  js      short loc_100268A3
0x1002684f  mov     esi, [esp+0A4h+var_94]
0x10026853  mov     edi, [esp+0A4h+var_90]
0x10026857  cmp     word ptr [esi], 0Ah
0x1002685b  jnz     short loc_10026870
0x1002685d  push    ebx; int
0x1002685e  push    0; int
0x10026860  push    offset aBr; "<BR>"
0x10026865  push    ebp; int
0x10026866  push    edi; int
0x10026867  call    WriteString
0x1002686c  test    eax, eax
0x1002686e  js      short loc_100268A3
0x10026870  add     esi, 2
0x10026873  mov     [esp+0A4h+var_94], esi
0x10026877  cmp     word ptr [esi], 0
0x1002687b  jnz     short loc_10026810
0x1002687d  cmp     [esp+0A4h+var_88], 0
0x10026882  push    ebx; int
0x10026883  push    1; int
0x10026885  jz      short loc_1002688E
0x10026887  push    offset aTh_0; "</TH>"
0x1002688c  jmp     short loc_10026893
  ... truncated ...
```
