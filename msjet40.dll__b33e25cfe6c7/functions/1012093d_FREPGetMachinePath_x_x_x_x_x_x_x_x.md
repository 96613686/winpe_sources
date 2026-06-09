# FREPGetMachinePath(x,x,x,x,x,x,x,x)

- ea: `0x1012093d`
- end: `0x10120c65`
- name: `_FREPGetMachinePath@32`
- size: `808`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int, int, STRSAFE_LPWSTR pszDest, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1011b930`

## callees

- `0x10016ed0`
- `0x10032700`
- `0x10045c22`
- `0x10045d00`
- `0x10046d06`
- `0x10050000`
- `0x1012066d`
- `0x10120814`
- `0x101208e5`
- `0x1012093d`
- `0x101214ae`
- `0x10121502`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120a13`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120b32`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120a13`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120b32`

## pseudocode

```c
int __fastcall FREPGetMachinePath(
        LPCWSTR lpFileName,
        WCHAR *a2,
        unsigned int a3,
        _WORD *a4,
        int a5,
        STRSAFE_LPWSTR pszDest,
        size_t a7,
        int *a8)
{
  DWORD v8; // eax
  wchar_t *v10; // eax
  int v11; // eax
  int Connection; // esi
  wchar_t *v13; // eax
  size_t v14; // esi
  int v15; // esi
  int v16; // esi
  int v17; // esi
  int v18; // esi
  DWORD nSize; // [esp+8h] [ebp-440h] BYREF
  int v21; // [esp+Ch] [ebp-43Ch] BYREF
  size_t cchDest; // [esp+10h] [ebp-438h]
  LPWSTR lpBuffer; // [esp+14h] [ebp-434h]
  LPCWSTR v24; // [esp+18h] [ebp-430h]
  CHAR MultiByteStr[4]; // [esp+1Ch] [ebp-42Ch] BYREF
  wchar_t *v26; // [esp+20h] [ebp-428h]
  int v27; // [esp+24h] [ebp-424h]
  CHAR v28[520]; // [esp+28h] [ebp-420h] BYREF
  WCHAR v29; // [esp+230h] [ebp-218h] BYREF
  wchar_t Str[260]; // [esp+234h] [ebp-214h] BYREF
  WCHAR WideCharStr[4]; // [esp+43Ch] [ebp-Ch] BYREF

  v8 = a3;
  *(_DWORD *)MultiByteStr = 49;
  if ( a3 > 0x31 )
    v8 = *(_DWORD *)MultiByteStr;
  nSize = v8;
  lpBuffer = a2;
  v24 = lpFileName;
  cchDest = a7;
  v21 = 520;
  v26 = 0;
  v27 = 0;
  WideCharStr[0] = 0;
  v29 = 0;
  if ( a3 && a2 )
    *a2 = 0;
  if ( a5 && a4 )
    *a4 = 0;
  if ( a7 && pszDest )
    *pszDest = 0;
  if ( IsUNCPath(lpFileName) )
  {
    WCSCPY2(cchDest);
    v24 = lpFileName + 2;
    v10 = _wcschr(lpFileName + 2, 0x5Cu);
    v26 = v10;
    if ( v10 )
    {
      *v10 = 0;
      WCSCPY2(a3);
      *v26 = 92;
      v11 = 0;
      v27 = 1;
LABEL_37:
      if ( a8 )
        *a8 = v11;
      if ( v11 )
      {
        if ( !ResolveLocalPathToRemoteName(a4, pszDest, cchDest) )
          *pszDest = 0;
      }
      else if ( !ResolveRemotePathToLocalName(pszDest, a4, a5) && a4 && a5 )
      {
        *a4 = 0;
      }
    }
  }
  else
  {
    if ( !IsDrivePath(lpFileName) )
      return v27;
    WideCharStr[0] = *lpFileName;
    WideCharStr[1] = lpFileName[1];
    WideCharStr[2] = 0;
    if ( !EnsureMPRLoaded() )
      return v27;
    if ( ErrWideToMultiByteCb(WideCharStr, MultiByteStr, 3) )
      return 0;
    if ( ErrWideToMultiByteCb(&v29, v28, 520) )
      return 0;
    Connection = g_fnMPRWNetGetConnection(g_fnMPRWNetGetConnection, MultiByteStr, v28, &v21);
    if ( !FMultiByteToWideN(MultiByteStr, WideCharStr, 3) || !FMultiByteToWideN(v28, &v29, 260) )
      return 0;
    if ( Connection )
    {
      v16 = Connection - 487;
      if ( v16 )
      {
        v17 = v16 - 716;
        if ( v17 )
        {
          v18 = v17 - 19;
          if ( v18 )
          {
            if ( v18 != 1028 )
              return v27;
          }
        }
      }
      if ( JetGetComputerNameW(lpBuffer, &nSize) )
      {
        WCSCPY2(a5);
        v11 = 1;
      }
      else
      {
        v11 = (int)v26;
      }
      v15 = v11;
      v27 = v11;
    }
    else
    {
      v13 = _wcschr(Str, 0x5Cu);
      v26 = v13;
      if ( v13 )
      {
        *v13 = 0;
        WCSCPY2(a3);
        *v26 = 92;
        v14 = cchDest;
        StringCchPrintfW(pszDest, cchDest, L"%s%s", &v29, v24 + 2);
        if ( v14 )
          pszDest[v14 - 1] = 0;
        v15 = 1;
        v27 = 1;
      }
      else
      {
        v15 = v27;
      }
      v11 = 0;
    }
    if ( v15 )
      goto LABEL_37;
  }
  return v27;
}

```

## disassembly

```asm
0x1012093d  mov     edi, edi
0x1012093f  push    ebp
0x10120940  mov     ebp, esp
0x10120942  sub     esp, 444h
0x10120948  mov     eax, ___security_cookie
0x1012094d  xor     eax, ebp
0x1012094f  mov     [ebp+var_4], eax
0x10120952  mov     eax, [ebp+arg_14]
0x10120955  mov     [ebp+var_444], eax
0x1012095b  mov     eax, [ebp+arg_0]
0x1012095e  cmp     eax, 31h ; '1'
0x10120961  push    ebx
0x10120962  mov     ebx, [ebp+arg_4]
0x10120965  mov     dword ptr [ebp+MultiByteStr], 31h ; '1'
0x1012096f  cmova   eax, dword ptr [ebp+MultiByteStr]
0x10120976  push    esi
0x10120977  mov     [ebp+nSize], eax
0x1012097d  mov     esi, ecx
0x1012097f  mov     ecx, [ebp+arg_10]
0x10120982  xor     eax, eax
0x10120984  push    edi
0x10120985  mov     edi, [ebp+pszDest]
0x10120988  mov     [ebp+lpBuffer], edx
0x1012098e  mov     [ebp+var_430], esi
0x10120994  mov     [ebp+cchDest], ecx
0x1012099a  mov     [ebp+var_43C], 208h
0x101209a4  mov     [ebp+var_428], 0
0x101209ae  mov     [ebp+var_424], 0
0x101209b8  mov     [ebp+WideCharStr], ax
0x101209bc  mov     [ebp+var_218], ax
0x101209c3  cmp     [ebp+arg_0], eax
0x101209c6  jz      short loc_101209CF
0x101209c8  test    edx, edx
0x101209ca  jz      short loc_101209CF
0x101209cc  mov     [edx], ax
0x101209cf  cmp     [ebp+arg_8], 0
0x101209d3  jz      short loc_101209DE
0x101209d5  test    ebx, ebx
0x101209d7  jz      short loc_101209DE
0x101209d9  xor     eax, eax
0x101209db  mov     [ebx], ax
0x101209de  test    ecx, ecx
0x101209e0  jz      short loc_101209EB
0x101209e2  test    edi, edi
0x101209e4  jz      short loc_101209EB
0x101209e6  xor     eax, eax
0x101209e8  mov     [edi], ax
0x101209eb  mov     ecx, esi; lpFileName
0x101209ed  call    _IsUNCPath@4; IsUNCPath(x)
0x101209f2  test    eax, eax
0x101209f4  jz      short loc_10120A5B
0x101209f6  push    [ebp+cchDest]
0x101209fc  mov     edx, esi
0x101209fe  mov     ecx, edi
0x10120a00  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120a05  lea     eax, [esi+4]
0x10120a08  push    5Ch ; '\'
0x10120a0a  pop     esi
0x10120a0b  push    esi; Ch
0x10120a0c  push    eax; Str
0x10120a0d  mov     [ebp+var_430], eax
0x10120a13  call    ds:__imp__wcschr
0x10120a19  mov     [ebp+var_428], eax
0x10120a1f  pop     ecx
0x10120a20  pop     ecx
0x10120a21  test    eax, eax
0x10120a23  jz      loc_10120C2C
0x10120a29  push    [ebp+arg_0]
0x10120a2c  mov     edx, [ebp+var_430]
0x10120a32  xor     ecx, ecx
0x10120a34  mov     [eax], cx
0x10120a37  mov     ecx, [ebp+lpBuffer]
0x10120a3d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120a42  mov     eax, [ebp+var_428]
0x10120a48  mov     [eax], si
0x10120a4b  xor     esi, esi
0x10120a4d  xor     eax, eax
0x10120a4f  inc     esi
0x10120a50  mov     [ebp+var_424], esi
0x10120a56  jmp     loc_10120C06
0x10120a5b  mov     ecx, esi
0x10120a5d  call    _IsDrivePath@4; IsDrivePath(x)
0x10120a62  test    eax, eax
0x10120a64  jz      loc_10120C2C
0x10120a6a  mov     ax, [esi]
0x10120a6d  mov     [ebp+WideCharStr], ax
0x10120a71  mov     ax, [esi+2]
0x10120a75  mov     [ebp+var_A], ax
0x10120a79  xor     eax, eax
0x10120a7b  mov     [ebp+var_8], ax
0x10120a7f  call    _EnsureMPRLoaded@0; EnsureMPRLoaded()
0x10120a84  test    eax, eax
0x10120a86  jz      loc_10120C2C
0x10120a8c  push    3
0x10120a8e  lea     edx, [ebp+MultiByteStr]
0x10120a94  lea     ecx, [ebp+WideCharStr]
0x10120a97  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x10120a9c  test    eax, eax
0x10120a9e  jnz     loc_10120C61
0x10120aa4  push    208h
0x10120aa9  lea     edx, [ebp+var_420]
0x10120aaf  lea     ecx, [ebp+var_218]
0x10120ab5  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x10120aba  test    eax, eax
0x10120abc  jnz     loc_10120C61
0x10120ac2  mov     esi, _g_fnMPRWNetGetConnection
0x10120ac8  lea     eax, [ebp+var_43C]
0x10120ace  push    eax
0x10120acf  lea     eax, [ebp+var_420]
0x10120ad5  mov     ecx, esi
0x10120ad7  push    eax; unsigned int
0x10120ad8  lea     eax, [ebp+MultiByteStr]
0x10120ade  push    eax; void *
0x10120adf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10120ae5  call    esi ; _g_fnMPRWNetGetConnection
0x10120ae7  push    3; int
0x10120ae9  lea     edx, [ebp+WideCharStr]; lpWideCharStr
0x10120aec  mov     esi, eax
0x10120aee  lea     ecx, [ebp+MultiByteStr]; lpMultiByteStr
0x10120af4  call    _FMultiByteToWideN@12; FMultiByteToWideN(x,x,x)
0x10120af9  test    eax, eax
0x10120afb  jz      loc_10120C61
0x10120b01  push    104h; int
0x10120b06  lea     edx, [ebp+var_218]; lpWideCharStr
0x10120b0c  lea     ecx, [ebp+var_420]; lpMultiByteStr
0x10120b12  call    _FMultiByteToWideN@12; FMultiByteToWideN(x,x,x)
0x10120b17  test    eax, eax
0x10120b19  jz      loc_10120C61
0x10120b1f  test    esi, esi
0x10120b21  jnz     loc_10120BAC
0x10120b27  push    5Ch ; '\'
0x10120b29  pop     esi
0x10120b2a  lea     eax, [ebp+Str]
0x10120b30  push    esi; Ch
0x10120b31  push    eax; Str
0x10120b32  call    ds:__imp__wcschr
0x10120b38  mov     [ebp+var_428], eax
0x10120b3e  pop     ecx
0x10120b3f  pop     ecx
0x10120b40  test    eax, eax
0x10120b42  jz      short loc_10120BA2
0x10120b44  push    [ebp+arg_0]
0x10120b47  xor     ecx, ecx
0x10120b49  lea     edx, [ebp+Str]
0x10120b4f  mov     [eax], cx
0x10120b52  mov     ecx, [ebp+lpBuffer]
0x10120b58  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120b5d  mov     eax, [ebp+var_428]
0x10120b63  mov     [eax], si
0x10120b66  mov     eax, [ebp+var_430]
0x10120b6c  mov     esi, [ebp+cchDest]
0x10120b72  add     eax, 4
0x10120b75  push    eax
0x10120b76  lea     eax, [ebp+var_218]
0x10120b7c  push    eax
0x10120b7d  push    offset aSS_0; "%s%s"
0x10120b82  push    esi; cchDest
0x10120b83  push    edi; pszDest
0x10120b84  call    _StringCchPrintfW
0x10120b89  add     esp, 14h
0x10120b8c  test    esi, esi
0x10120b8e  jz      short loc_10120B97
0x10120b90  xor     eax, eax
0x10120b92  mov     [edi+esi*2-2], ax
0x10120b97  xor     esi, esi
0x10120b99  inc     esi
0x10120b9a  mov     [ebp+var_424], esi
0x10120ba0  jmp     short loc_10120BA8
0x10120ba2  mov     esi, [ebp+var_424]
0x10120ba8  xor     eax, eax
0x10120baa  jmp     short loc_10120C02
0x10120bac  sub     esi, 1E7h
0x10120bb2  jz      short loc_10120BC9
0x10120bb4  sub     esi, 2CCh
0x10120bba  jz      short loc_10120BC9
0x10120bbc  sub     esi, 13h
0x10120bbf  jz      short loc_10120BC9
0x10120bc1  sub     esi, 404h
0x10120bc7  jnz     short loc_10120C2C
0x10120bc9  lea     eax, [ebp+nSize]
0x10120bcf  push    eax; nSize
0x10120bd0  push    [ebp+lpBuffer]; lpBuffer
0x10120bd6  call    _JetGetComputerNameW@8; JetGetComputerNameW(x,x)
0x10120bdb  test    eax, eax
0x10120bdd  jz      short loc_10120BF4
0x10120bdf  push    [ebp+arg_8]
0x10120be2  mov     edx, [ebp+var_430]
0x10120be8  mov     ecx, ebx
0x10120bea  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120bef  xor     eax, eax
0x10120bf1  inc     eax
0x10120bf2  jmp     short loc_10120BFA
0x10120bf4  mov     eax, [ebp+var_428]
0x10120bfa  mov     esi, eax
0x10120bfc  mov     [ebp+var_424], esi
0x10120c02  test    esi, esi
0x10120c04  jz      short loc_10120C2C
0x10120c06  mov     ecx, [ebp+var_444]
0x10120c0c  test    ecx, ecx
0x10120c0e  jz      short loc_10120C12
0x10120c10  mov     [ecx], eax
0x10120c12  test    eax, eax
0x10120c14  jz      short loc_10120C43
0x10120c16  push    [ebp+cchDest]
0x10120c1c  mov     edx, edi
0x10120c1e  mov     ecx, ebx
0x10120c20  call    _ResolveLocalPathToRemoteName@12; ResolveLocalPathToRemoteName(x,x,x)
0x10120c25  test    eax, eax
0x10120c27  jnz     short loc_10120C2C
0x10120c29  mov     [edi], ax
0x10120c2c  mov     eax, [ebp+var_424]
0x10120c32  mov     ecx, [ebp+var_4]
0x10120c35  pop     edi
0x10120c36  pop     esi
0x10120c37  xor     ecx, ebp; StackCookie
0x10120c39  pop     ebx
0x10120c3a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10120c3f  leave
0x10120c40  retn    18h
0x10120c43  push    [ebp+arg_8]
0x10120c46  mov     edx, ebx
0x10120c48  mov     ecx, edi
0x10120c4a  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x10120c4f  test    eax, eax
0x10120c51  jnz     short loc_10120C2C
0x10120c53  test    ebx, ebx
0x10120c55  jz      short loc_10120C2C
0x10120c57  cmp     [ebp+arg_8], eax
0x10120c5a  jz      short loc_10120C2C
0x10120c5c  mov     [ebx], ax
0x10120c5f  jmp     short loc_10120C2C
0x10120c61  xor     eax, eax
0x10120c63  jmp     short loc_10120C32
```
