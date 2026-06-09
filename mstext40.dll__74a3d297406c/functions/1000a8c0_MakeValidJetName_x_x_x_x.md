# MakeValidJetName(x,x,x,x)

- ea: `0x1000a8c0`
- end: `0x1000aa2e`
- name: `_MakeValidJetName@16`
- size: `366`
- prototype: `int __stdcall(LPCWCH lpWideCharStr, LPWSTR pszDest, int cchWideChar, UINT CodePage)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x100130e0`
- `0x100131b0`
- `0x10016d90`
- `0x10016fc0`
- `0x100170e0`
- `0x10017670`
- `0x100178b0`
- `0x10018200`
- `0x1001c680`
- `0x1001fcd0`
- `0x10026190`

## callees

- `0x1000a8c0`
- `0x1000ae20`
- `0x1000b070`
- `0x1000b200`
- `0x10029170`

## import_xrefs

- `KERNEL32!GetOEMCP` at `0x1000a924`
- `KERNEL32!GetOEMCP` at `0x1000a924`
- `KERNEL32!GetACP` at `0x1000a90a`
- `KERNEL32!GetACP` at `0x1000a90a`
- `KERNEL32!WideCharToMultiByte` at `0x1000a975`
- `KERNEL32!WideCharToMultiByte` at `0x1000a975`
- `KERNEL32!MultiByteToWideChar` at `0x1000a98a`
- `KERNEL32!MultiByteToWideChar` at `0x1000a98a`

## pseudocode

```c
int __stdcall MakeValidJetName(LPCWCH lpWideCharStr, LPWSTR pszDest, int cchWideChar, UINT CodePage)
{
  const wchar_t *v4; // ecx
  size_t v5; // ebp
  int v6; // ebx
  int v7; // esi
  UINT v8; // edi
  UINT ACP; // eax
  CHAR *v11; // ebp
  int v12; // eax
  LPWSTR v13; // esi
  _WORD *v14; // eax
  unsigned int v15; // ecx
  __int16 v16; // cx
  int v17; // [esp+Ch] [ebp-4h]

  v4 = lpWideCharStr;
  v5 = cchWideChar;
  v6 = cchWideChar;
  v17 = 1;
  v7 = wcslen(lpWideCharStr);
  if ( v7 <= 64 )
  {
    if ( v7 < 0 )
      return 0;
  }
  else
  {
    v17 = 2;
    v7 = 64;
  }
  v8 = CodePage;
  switch ( CodePage )
  {
    case 0u:
      ACP = GetACP();
LABEL_11:
      v4 = lpWideCharStr;
      v8 = ACP;
      break;
    case 1u:
      ACP = GetOEMCP();
      goto LABEL_11;
    case 2u:
      ACP = GetDefaultCodePage();
      goto LABEL_11;
  }
  if ( v8 == 1200 )
  {
    v13 = pszDest;
    StringCchCopyW(pszDest, cchWideChar, v4);
  }
  else
  {
    v11 = (CHAR *)MemAllocate(2 * v7 + 2);
    if ( !v11 )
      return -1011;
    v12 = WideCharToMultiByte(v8, 0, lpWideCharStr, v7, v11, 2 * v7, 0, 0);
    v13 = pszDest;
    v11[v12] = 0;
    pszDest[MultiByteToWideChar(v8, 0, v11, v12, pszDest, cchWideChar)] = 0;
    MemFree(v11);
    v5 = cchWideChar;
  }
  v14 = v13;
  if ( !*v13 )
    goto LABEL_32;
  while ( v6 )
  {
    v15 = (unsigned __int16)*v14;
    if ( v15 == 46 )
    {
      *v14 = 35;
    }
    else if ( v15 == 91 )
    {
      *v14 = 40;
    }
    else
    {
      if ( v15 == 93 )
      {
        v16 = 41;
      }
      else
      {
        if ( v15 >= 0x20 && v15 != 33 && v15 != 96 )
          goto LABEL_30;
        v16 = 95;
        v17 = 2;
      }
      *v14 = v16;
    }
LABEL_30:
    ++v14;
    --v6;
    if ( !*v14 )
      break;
  }
  if ( !*v13 )
LABEL_32:
    StringCchCopyW(v13, v5, L"NoName");
  return v17;
}

```

## disassembly

```asm
0x1000a8c0  push    ecx
0x1000a8c1  mov     ecx, [esp+4+lpWideCharStr]
0x1000a8c5  push    ebx
0x1000a8c6  push    ebp
0x1000a8c7  mov     ebp, [esp+0Ch+cchWideChar]
0x1000a8cb  mov     ebx, ebp
0x1000a8cd  push    esi
0x1000a8ce  mov     esi, ecx
0x1000a8d0  mov     [esp+10h+var_4], 1
0x1000a8d8  lea     edx, [esi+2]
0x1000a8db  jmp     short loc_1000A8E0
0x1000a8e0  mov     ax, [esi]
0x1000a8e3  add     esi, 2
0x1000a8e6  test    ax, ax
0x1000a8e9  jnz     short loc_1000A8E0
0x1000a8eb  sub     esi, edx
0x1000a8ed  sar     esi, 1
0x1000a8ef  cmp     esi, 40h ; '@'
0x1000a8f2  jle     short loc_1000A912
0x1000a8f4  mov     [esp+10h+var_4], 2
0x1000a8fc  mov     esi, 40h ; '@'
0x1000a901  push    edi
0x1000a902  mov     edi, [esp+14h+CodePage]
0x1000a906  test    edi, edi
0x1000a908  jnz     short loc_1000A91F
0x1000a90a  call    ds:__imp__GetACP@0; GetACP()
0x1000a910  jmp     short loc_1000A936
0x1000a912  test    esi, esi
0x1000a914  jns     short loc_1000A901
0x1000a916  pop     esi
0x1000a917  pop     ebp
0x1000a918  xor     eax, eax
0x1000a91a  pop     ebx
0x1000a91b  pop     ecx
0x1000a91c  retn    10h
0x1000a91f  cmp     edi, 1
0x1000a922  jnz     short loc_1000A92C
0x1000a924  call    ds:__imp__GetOEMCP@0; GetOEMCP()
0x1000a92a  jmp     short loc_1000A936
0x1000a92c  cmp     edi, 2
0x1000a92f  jnz     short loc_1000A93C
0x1000a931  call    _GetDefaultCodePage@0; GetDefaultCodePage()
0x1000a936  mov     ecx, [esp+14h+lpWideCharStr]
0x1000a93a  mov     edi, eax
0x1000a93c  cmp     edi, 4B0h
0x1000a942  jz      short loc_1000A9A0
0x1000a944  lea     eax, ds:2[esi*2]
0x1000a94b  push    eax; Size
0x1000a94c  call    _MemAllocate@4; MemAllocate(x)
0x1000a951  mov     ebp, eax
0x1000a953  test    ebp, ebp
0x1000a955  jnz     short loc_1000A964
0x1000a957  pop     edi
0x1000a958  pop     esi
0x1000a959  pop     ebp
0x1000a95a  mov     eax, 0FFFFFC0Dh
0x1000a95f  pop     ebx
0x1000a960  pop     ecx
0x1000a961  retn    10h
0x1000a964  push    0; lpUsedDefaultChar
0x1000a966  push    0; lpDefaultChar
0x1000a968  lea     eax, [esi+esi]
0x1000a96b  push    eax; cbMultiByte
0x1000a96c  push    ebp; lpMultiByteStr
0x1000a96d  push    esi; cchWideChar
0x1000a96e  push    [esp+28h+lpWideCharStr]; lpWideCharStr
0x1000a972  push    0; dwFlags
0x1000a974  push    edi; CodePage
0x1000a975  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000a97b  mov     esi, [esp+14h+pszDest]
0x1000a97f  push    ebx; cchWideChar
0x1000a980  push    esi; lpWideCharStr
0x1000a981  push    eax; cbMultiByte
0x1000a982  push    ebp; lpMultiByteStr
0x1000a983  push    0; dwFlags
0x1000a985  push    edi; CodePage
0x1000a986  mov     byte ptr [eax+ebp], 0
0x1000a98a  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1000a990  xor     ecx, ecx
0x1000a992  push    ebp
0x1000a993  mov     [esi+eax*2], cx
0x1000a997  call    _MemFree@4; MemFree(x)
0x1000a99c  mov     ebp, ebx
0x1000a99e  jmp     short loc_1000A9AC
0x1000a9a0  mov     esi, [esp+14h+pszDest]
0x1000a9a4  push    ecx; pszSrc
0x1000a9a5  push    ebp; cchDest
0x1000a9a6  push    esi; pszDest
0x1000a9a7  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000a9ac  cmp     word ptr [esi], 0
0x1000a9b0  mov     eax, esi
0x1000a9b2  jz      short loc_1000AA16
0x1000a9b4  mov     edx, 23h ; '#'
0x1000a9b9  lea     edi, [edx+5]
0x1000a9bc  lea     esp, [esp+0]
0x1000a9c0  test    ebx, ebx
0x1000a9c2  jz      short loc_1000AA10
0x1000a9c4  movzx   ecx, word ptr [eax]
0x1000a9c7  cmp     ecx, 2Eh ; '.'
0x1000a9ca  jnz     short loc_1000A9D1
0x1000a9cc  mov     [eax], dx
0x1000a9cf  jmp     short loc_1000AA06
0x1000a9d1  cmp     ecx, 5Bh ; '['
0x1000a9d4  jnz     short loc_1000A9DB
0x1000a9d6  mov     [eax], di
0x1000a9d9  jmp     short loc_1000AA06
0x1000a9db  cmp     ecx, 5Dh ; ']'
0x1000a9de  jnz     short loc_1000A9E7
0x1000a9e0  mov     ecx, 29h ; ')'
0x1000a9e5  jmp     short loc_1000AA03
0x1000a9e7  cmp     ecx, 20h ; ' '
0x1000a9ea  jb      short loc_1000A9F6
0x1000a9ec  cmp     ecx, 21h ; '!'
0x1000a9ef  jz      short loc_1000A9F6
0x1000a9f1  cmp     ecx, 60h ; '`'
0x1000a9f4  jnz     short loc_1000AA06
0x1000a9f6  mov     ecx, 5Fh ; '_'
0x1000a9fb  mov     [esp+14h+var_4], 2
0x1000aa03  mov     [eax], cx
0x1000aa06  add     eax, 2
0x1000aa09  dec     ebx
0x1000aa0a  cmp     word ptr [eax], 0
0x1000aa0e  jnz     short loc_1000A9C0
0x1000aa10  cmp     word ptr [esi], 0
0x1000aa14  jnz     short loc_1000AA22
0x1000aa16  push    offset aNoname; "NoName"
0x1000aa1b  push    ebp; cchDest
0x1000aa1c  push    esi; pszDest
0x1000aa1d  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000aa22  mov     eax, [esp+14h+var_4]
0x1000aa26  pop     edi
0x1000aa27  pop     esi
0x1000aa28  pop     ebp
0x1000aa29  pop     ebx
0x1000aa2a  pop     ecx
0x1000aa2b  retn    10h
```
