# PathPartGet(x,x,x,x)

- ea: `0x1000bfc0`
- end: `0x1000c143`
- name: `_PathPartGet@16`
- size: `387`
- prototype: `int __stdcall(wchar_t *FullPath, int, STRSAFE_LPWSTR pszDest, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10010020`

## callees

- `0x1000ad60`
- `0x1000bfc0`
- `0x1002b81a`
- `0x1002c520`

## pseudocode

```c
STRSAFE_LPWSTR __stdcall PathPartGet(wchar_t *FullPath, char a2, STRSAFE_LPWSTR pszDest, unsigned int a4)
{
  size_t v4; // esi
  char v5; // dl
  int v6; // ecx
  wchar_t *v7; // eax
  int v8; // ecx
  wchar_t *v9; // eax
  int v10; // ecx
  wchar_t *v11; // eax
  int v12; // ecx
  wchar_t *v13; // eax
  wchar_t Drive[10]; // [esp+Ch] [ebp-618h] BYREF
  wchar_t Dir[256]; // [esp+20h] [ebp-604h] BYREF
  wchar_t Filename[256]; // [esp+220h] [ebp-404h] BYREF
  wchar_t Ext[256]; // [esp+420h] [ebp-204h] BYREF

  v4 = (a4 >> 1) - 1;
  _wsplitpath_s(FullPath, Drive, 9u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
  v5 = a2;
  *pszDest = 0;
  if ( (a2 & 1) != 0 )
  {
    v6 = 8;
    v7 = Drive;
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
        goto LABEL_7;
    }
    if ( 8 - v6 > v4 )
      goto LABEL_8;
LABEL_7:
    StringCchCatW(pszDest, v4, Drive);
    v5 = a2;
  }
LABEL_8:
  if ( (v5 & 2) != 0 )
  {
    v8 = 255;
    v9 = Dir;
    while ( *v9 )
    {
      ++v9;
      if ( !--v8 )
        goto LABEL_14;
    }
    if ( 255 - v8 > v4 )
      goto LABEL_15;
LABEL_14:
    StringCchCatW(pszDest, v4, Dir);
    v5 = a2;
  }
LABEL_15:
  if ( (v5 & 4) != 0 )
  {
    v10 = 255;
    v11 = Filename;
    while ( *v11 )
    {
      ++v11;
      if ( !--v10 )
        goto LABEL_21;
    }
    if ( 255 - v10 > v4 )
      goto LABEL_22;
LABEL_21:
    StringCchCatW(pszDest, v4, Filename);
    v5 = a2;
  }
LABEL_22:
  if ( (v5 & 8) != 0 )
  {
    v12 = 255;
    v13 = Ext;
    while ( *v13 )
    {
      ++v13;
      if ( !--v12 )
        goto LABEL_28;
    }
    if ( 255 - v12 > v4 )
      return pszDest;
LABEL_28:
    StringCchCatW(pszDest, v4, Ext);
  }
  return pszDest;
}

```

## disassembly

```asm
0x1000bfc0  sub     esp, 618h
0x1000bfc6  mov     eax, ___security_cookie
0x1000bfcb  xor     eax, esp
0x1000bfcd  mov     [esp+618h+var_4], eax
0x1000bfd4  mov     eax, [esp+618h+FullPath]
0x1000bfdb  lea     ecx, [esp+618h+Ext]
0x1000bfe2  push    ebx
0x1000bfe3  push    esi
0x1000bfe4  mov     esi, [esp+620h+arg_C]
0x1000bfeb  push    edi
0x1000bfec  mov     edi, [esp+624h+pszDest]
0x1000bff3  push    100h; ExtCount
0x1000bff8  push    ecx; Ext
0x1000bff9  push    100h; FilenameCount
0x1000bffe  lea     ecx, [esp+630h+Filename]
0x1000c005  shr     esi, 1
0x1000c007  push    ecx; Filename
0x1000c008  push    100h; DirCount
0x1000c00d  lea     ecx, [esp+638h+Dir]
0x1000c011  dec     esi
0x1000c012  push    ecx; Dir
0x1000c013  push    9; DriveCount
0x1000c015  lea     ecx, [esp+640h+Drive]
0x1000c019  push    ecx; Drive
0x1000c01a  push    eax; FullPath
0x1000c01b  call    __wsplitpath_s
0x1000c020  mov     edx, [esp+648h+arg_4]
0x1000c027  xor     eax, eax
0x1000c029  add     esp, 24h
0x1000c02c  mov     [edi], ax
0x1000c02f  test    dl, 1
0x1000c032  jz      short loc_1000C070
0x1000c034  lea     ecx, [eax+8]
0x1000c037  lea     eax, [esp+624h+Drive]
0x1000c03b  jmp     short loc_1000C040
0x1000c040  cmp     word ptr [eax], 0
0x1000c044  jz      short loc_1000C04E
0x1000c046  add     eax, 2
0x1000c049  dec     ecx
0x1000c04a  jnz     short loc_1000C040
0x1000c04c  jmp     short loc_1000C05D
0x1000c04e  test    ecx, ecx
0x1000c050  jz      short loc_1000C05D
0x1000c052  mov     eax, 8
0x1000c057  sub     eax, ecx
0x1000c059  cmp     eax, esi
0x1000c05b  ja      short loc_1000C070
0x1000c05d  lea     eax, [esp+624h+Drive]
0x1000c061  push    eax; pszSrc
0x1000c062  push    esi; cchDest
0x1000c063  push    edi; pszDest
0x1000c064  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c069  mov     edx, [esp+624h+arg_4]
0x1000c070  mov     ebx, 0FFh
0x1000c075  test    dl, 2
0x1000c078  jz      short loc_1000C0AD
0x1000c07a  mov     ecx, ebx
0x1000c07c  lea     eax, [esp+624h+Dir]
0x1000c080  cmp     word ptr [eax], 0
0x1000c084  jz      short loc_1000C08E
0x1000c086  add     eax, 2
0x1000c089  dec     ecx
0x1000c08a  jnz     short loc_1000C080
0x1000c08c  jmp     short loc_1000C09A
0x1000c08e  test    ecx, ecx
0x1000c090  jz      short loc_1000C09A
0x1000c092  mov     eax, ebx
0x1000c094  sub     eax, ecx
0x1000c096  cmp     eax, esi
0x1000c098  ja      short loc_1000C0AD
0x1000c09a  lea     eax, [esp+624h+Dir]
0x1000c09e  push    eax; pszSrc
0x1000c09f  push    esi; cchDest
0x1000c0a0  push    edi; pszDest
0x1000c0a1  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c0a6  mov     edx, [esp+624h+arg_4]
0x1000c0ad  test    dl, 4
0x1000c0b0  jz      short loc_1000C0F0
0x1000c0b2  mov     ecx, ebx
0x1000c0b4  lea     eax, [esp+624h+Filename]
0x1000c0bb  jmp     short loc_1000C0C0
0x1000c0c0  cmp     word ptr [eax], 0
0x1000c0c4  jz      short loc_1000C0CE
0x1000c0c6  add     eax, 2
0x1000c0c9  dec     ecx
0x1000c0ca  jnz     short loc_1000C0C0
0x1000c0cc  jmp     short loc_1000C0DA
0x1000c0ce  test    ecx, ecx
0x1000c0d0  jz      short loc_1000C0DA
0x1000c0d2  mov     eax, ebx
0x1000c0d4  sub     eax, ecx
0x1000c0d6  cmp     eax, esi
0x1000c0d8  ja      short loc_1000C0F0
0x1000c0da  lea     eax, [esp+624h+Filename]
0x1000c0e1  push    eax; pszSrc
0x1000c0e2  push    esi; cchDest
0x1000c0e3  push    edi; pszDest
0x1000c0e4  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c0e9  mov     edx, [esp+624h+arg_4]
0x1000c0f0  test    dl, 8
0x1000c0f3  jz      short loc_1000C127
0x1000c0f5  mov     ecx, ebx
0x1000c0f7  lea     eax, [esp+624h+Ext]
0x1000c0fe  mov     edi, edi
0x1000c100  cmp     word ptr [eax], 0
0x1000c104  jz      short loc_1000C10E
0x1000c106  add     eax, 2
0x1000c109  dec     ecx
0x1000c10a  jnz     short loc_1000C100
0x1000c10c  jmp     short loc_1000C118
0x1000c10e  test    ecx, ecx
0x1000c110  jz      short loc_1000C118
0x1000c112  sub     ebx, ecx
0x1000c114  cmp     ebx, esi
0x1000c116  ja      short loc_1000C127
0x1000c118  lea     eax, [esp+624h+Ext]
0x1000c11f  push    eax; pszSrc
0x1000c120  push    esi; cchDest
0x1000c121  push    edi; pszDest
0x1000c122  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c127  mov     ecx, [esp+624h+var_4]
0x1000c12e  mov     eax, edi
0x1000c130  pop     edi
0x1000c131  pop     esi
0x1000c132  pop     ebx
0x1000c133  xor     ecx, esp; StackCookie
0x1000c135  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000c13a  add     esp, 618h
0x1000c140  retn    10h
```
