# WriteNewSpec

- ea: `0x100133f0`
- end: `0x1001351b`
- name: `WriteNewSpec`
- size: `299`
- prototype: `int __stdcall(int, int, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x10012e70`

## callees

- `0x1000ad60`
- `0x1000b3f0`
- `0x1000b410`
- `0x1000b5f0`
- `0x1000b600`
- `0x1000bfb0`
- `0x100133f0`
- `0x1001c140`
- `0x1001c380`
- `0x1002b81a`

## pseudocode

```c
int __stdcall WriteNewSpec(int a1, int a2, STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *v3; // ecx
  int v4; // edx
  wchar_t v5; // ax
  int v6; // eax
  HANDLE hObject; // [esp+8h] [ebp-214h] BYREF
  wchar_t pszDest[262]; // [esp+Ch] [ebp-210h] BYREF

  v3 = pszDest;
  v4 = 261;
  while ( v4 != -2147483385 )
  {
    v5 = *(wchar_t *)((char *)v3 + a1 + 56 - (_DWORD)pszDest);
    if ( !v5 )
      break;
    *v3++ = v5;
    if ( !--v4 )
    {
      --v3;
      break;
    }
  }
  *v3 = 0;
  StringCchCatW(pszDest, 0x105u, pszSrc);
  v6 = wcscmp(pszSrc, L"export.ini");
  if ( v6 )
    v6 = v6 < 0 ? -1 : 1;
  if ( v6 )
    TextSpecDelete(pszDest, (LPCWCH)(a2 + 920), a2, 0);
  else
    DOSFileDelete(pszDest);
  if ( !IsUnicodeOS() && DOSFileExists(pszDest) )
  {
    DOSCreateFile(pszDest, (int)&hObject);
    DOSCloseFile(hObject);
  }
  return TextSpecWrite(pszDest, (LPCWCH)(a2 + 920), a2, 0);
}

```

## disassembly

```asm
0x100133f0  sub     esp, 214h
0x100133f6  mov     eax, ___security_cookie
0x100133fb  xor     eax, esp
0x100133fd  mov     [esp+214h+var_4], eax
0x10013404  push    esi
0x10013405  mov     esi, [esp+218h+arg_0]
0x1001340c  lea     ecx, [esp+218h+pszDest]
0x10013410  add     esi, 38h ; '8'
0x10013413  mov     eax, ecx
0x10013415  push    edi
0x10013416  mov     edi, [esp+21Ch+arg_4]
0x1001341d  mov     edx, 105h
0x10013422  sub     esi, eax
0x10013424  lea     eax, [edx+7FFFFEF9h]
0x1001342a  test    eax, eax
0x1001342c  jz      short loc_10013442
0x1001342e  movzx   eax, word ptr [esi+ecx]
0x10013432  test    ax, ax
0x10013435  jz      short loc_10013442
0x10013437  mov     [ecx], ax
0x1001343a  add     ecx, 2
0x1001343d  dec     edx
0x1001343e  jnz     short loc_10013424
0x10013440  jmp     short loc_10013446
0x10013442  test    edx, edx
0x10013444  jnz     short loc_10013449
0x10013446  sub     ecx, 2
0x10013449  mov     esi, [esp+21Ch+pszSrc]
0x10013450  xor     eax, eax
0x10013452  push    esi; pszSrc
0x10013453  mov     [ecx], ax
0x10013456  lea     eax, [esp+220h+pszDest]
0x1001345a  push    105h; cchDest
0x1001345f  push    eax; pszDest
0x10013460  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10013465  mov     eax, offset aExportIni; "export.ini"
0x1001346a  lea     ebx, [ebx+0]
0x10013470  mov     cx, [esi]
0x10013473  cmp     cx, [eax]
0x10013476  jnz     short loc_10013496
0x10013478  test    cx, cx
0x1001347b  jz      short loc_10013492
0x1001347d  mov     cx, [esi+2]
0x10013481  cmp     cx, [eax+2]
0x10013485  jnz     short loc_10013496
0x10013487  add     esi, 4
0x1001348a  add     eax, 4
0x1001348d  test    cx, cx
0x10013490  jnz     short loc_10013470
0x10013492  xor     eax, eax
0x10013494  jmp     short loc_1001349B
0x10013496  sbb     eax, eax
0x10013498  or      eax, 1
0x1001349b  test    eax, eax
0x1001349d  jnz     short loc_100134AB
0x1001349f  lea     eax, [esp+21Ch+pszDest]
0x100134a3  push    eax
0x100134a4  call    _DOSFileDelete@4; DOSFileDelete(x)
0x100134a9  jmp     short loc_100134BF
0x100134ab  push    0; int
0x100134ad  push    edi; int
0x100134ae  lea     eax, [edi+398h]
0x100134b4  push    eax; lpWideCharStr
0x100134b5  lea     eax, [esp+228h+pszDest]
0x100134b9  push    eax; lpFileName
0x100134ba  call    _TextSpecDelete@16; TextSpecDelete(x,x,x,x)
0x100134bf  call    _IsUnicodeOS@0; IsUnicodeOS()
0x100134c4  test    eax, eax
0x100134c6  jnz     short loc_100134EE
0x100134c8  lea     eax, [esp+21Ch+pszDest]
0x100134cc  push    eax; lpFileName
0x100134cd  call    _DOSFileExists@4; DOSFileExists(x)
0x100134d2  test    eax, eax
0x100134d4  jz      short loc_100134EE
0x100134d6  lea     eax, [esp+21Ch+hObject]
0x100134da  push    eax; int
0x100134db  lea     eax, [esp+220h+pszDest]
0x100134df  push    eax; lpFileName
0x100134e0  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x100134e5  push    [esp+21Ch+hObject]; hObject
0x100134e9  call    _DOSCloseFile@4; DOSCloseFile(x)
0x100134ee  push    0; int
0x100134f0  push    edi; int
0x100134f1  lea     eax, [edi+398h]
0x100134f7  push    eax; lpWideCharStr
0x100134f8  lea     eax, [esp+228h+pszDest]
0x100134fc  push    eax; lpFileName
0x100134fd  call    _TextSpecWrite@16; TextSpecWrite(x,x,x,x)
0x10013502  mov     ecx, [esp+21Ch+var_4]
0x10013509  pop     edi
0x1001350a  pop     esi
0x1001350b  xor     ecx, esp; StackCookie
0x1001350d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10013512  add     esp, 214h
0x10013518  retn    0Ch
```
