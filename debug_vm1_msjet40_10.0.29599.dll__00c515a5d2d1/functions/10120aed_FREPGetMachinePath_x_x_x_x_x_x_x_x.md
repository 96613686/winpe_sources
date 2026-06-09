# FREPGetMachinePath(x,x,x,x,x,x,x,x)

- ea: `0x10120aed`
- end: `0x10120e15`
- name: `_FREPGetMachinePath@32`
- size: `808`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int, int, STRSAFE_LPWSTR pszDest, int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1011bae0`

## callees

- `0x10017010`
- `0x100328a0`
- `0x10045da2`
- `0x10045e80`
- `0x10046e86`
- `0x10050190`
- `0x1012081d`
- `0x101209c4`
- `0x10120a95`
- `0x10120aed`
- `0x1012165e`
- `0x101216b2`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120bc3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120ce2`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120bc3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10120ce2`

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
0x10120aed  mov     edi, edi
0x10120aef  push    ebp
0x10120af0  mov     ebp, esp
0x10120af2  sub     esp, 444h
0x10120af8  mov     eax, ___security_cookie
0x10120afd  xor     eax, ebp
0x10120aff  mov     [ebp+var_4], eax
0x10120b02  mov     eax, [ebp+arg_14]
0x10120b05  mov     [ebp+var_444], eax
0x10120b0b  mov     eax, [ebp+arg_0]
0x10120b0e  cmp     eax, 31h ; '1'
0x10120b11  push    ebx
0x10120b12  mov     ebx, [ebp+arg_4]
0x10120b15  mov     dword ptr [ebp+MultiByteStr], 31h ; '1'
0x10120b1f  cmova   eax, dword ptr [ebp+MultiByteStr]
0x10120b26  push    esi
0x10120b27  mov     [ebp+nSize], eax
0x10120b2d  mov     esi, ecx
0x10120b2f  mov     ecx, [ebp+arg_10]
0x10120b32  xor     eax, eax
0x10120b34  push    edi
0x10120b35  mov     edi, [ebp+pszDest]
0x10120b38  mov     [ebp+lpBuffer], edx
0x10120b3e  mov     [ebp+var_430], esi
0x10120b44  mov     [ebp+cchDest], ecx
0x10120b4a  mov     [ebp+var_43C], 208h
0x10120b54  mov     [ebp+var_428], 0
0x10120b5e  mov     [ebp+var_424], 0
0x10120b68  mov     [ebp+WideCharStr], ax
0x10120b6c  mov     [ebp+var_218], ax
0x10120b73  cmp     [ebp+arg_0], eax
0x10120b76  jz      short loc_10120B7F
0x10120b78  test    edx, edx
0x10120b7a  jz      short loc_10120B7F
0x10120b7c  mov     [edx], ax
0x10120b7f  cmp     [ebp+arg_8], 0
0x10120b83  jz      short loc_10120B8E
0x10120b85  test    ebx, ebx
0x10120b87  jz      short loc_10120B8E
0x10120b89  xor     eax, eax
0x10120b8b  mov     [ebx], ax
0x10120b8e  test    ecx, ecx
0x10120b90  jz      short loc_10120B9B
0x10120b92  test    edi, edi
0x10120b94  jz      short loc_10120B9B
0x10120b96  xor     eax, eax
0x10120b98  mov     [edi], ax
0x10120b9b  mov     ecx, esi; lpFileName
0x10120b9d  call    _IsUNCPath@4; IsUNCPath(x)
0x10120ba2  test    eax, eax
0x10120ba4  jz      short loc_10120C0B
0x10120ba6  push    [ebp+cchDest]
0x10120bac  mov     edx, esi
0x10120bae  mov     ecx, edi
0x10120bb0  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120bb5  lea     eax, [esi+4]
0x10120bb8  push    5Ch ; '\'
0x10120bba  pop     esi
0x10120bbb  push    esi; Ch
0x10120bbc  push    eax; Str
0x10120bbd  mov     [ebp+var_430], eax
0x10120bc3  call    ds:__imp__wcschr
0x10120bc9  mov     [ebp+var_428], eax
0x10120bcf  pop     ecx
0x10120bd0  pop     ecx
0x10120bd1  test    eax, eax
0x10120bd3  jz      loc_10120DDC
0x10120bd9  push    [ebp+arg_0]
0x10120bdc  mov     edx, [ebp+var_430]
0x10120be2  xor     ecx, ecx
0x10120be4  mov     [eax], cx
0x10120be7  mov     ecx, [ebp+lpBuffer]
0x10120bed  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120bf2  mov     eax, [ebp+var_428]
0x10120bf8  mov     [eax], si
0x10120bfb  xor     esi, esi
0x10120bfd  xor     eax, eax
0x10120bff  inc     esi
0x10120c00  mov     [ebp+var_424], esi
0x10120c06  jmp     loc_10120DB6
0x10120c0b  mov     ecx, esi
0x10120c0d  call    _IsDrivePath@4; IsDrivePath(x)
0x10120c12  test    eax, eax
0x10120c14  jz      loc_10120DDC
0x10120c1a  mov     ax, [esi]
0x10120c1d  mov     [ebp+WideCharStr], ax
0x10120c21  mov     ax, [esi+2]
0x10120c25  mov     [ebp+var_A], ax
0x10120c29  xor     eax, eax
0x10120c2b  mov     [ebp+var_8], ax
0x10120c2f  call    _EnsureMPRLoaded@0; EnsureMPRLoaded()
0x10120c34  test    eax, eax
0x10120c36  jz      loc_10120DDC
0x10120c3c  push    3
0x10120c3e  lea     edx, [ebp+MultiByteStr]
0x10120c44  lea     ecx, [ebp+WideCharStr]
0x10120c47  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x10120c4c  test    eax, eax
0x10120c4e  jnz     loc_10120E11
0x10120c54  push    208h
0x10120c59  lea     edx, [ebp+var_420]
0x10120c5f  lea     ecx, [ebp+var_218]
0x10120c65  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x10120c6a  test    eax, eax
0x10120c6c  jnz     loc_10120E11
0x10120c72  mov     esi, _g_fnMPRWNetGetConnection
0x10120c78  lea     eax, [ebp+var_43C]
0x10120c7e  push    eax
0x10120c7f  lea     eax, [ebp+var_420]
0x10120c85  mov     ecx, esi
0x10120c87  push    eax; unsigned int
0x10120c88  lea     eax, [ebp+MultiByteStr]
0x10120c8e  push    eax; void *
0x10120c8f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10120c95  call    esi ; _g_fnMPRWNetGetConnection
0x10120c97  push    3; int
0x10120c99  lea     edx, [ebp+WideCharStr]; lpWideCharStr
0x10120c9c  mov     esi, eax
0x10120c9e  lea     ecx, [ebp+MultiByteStr]; lpMultiByteStr
0x10120ca4  call    _FMultiByteToWideN@12; FMultiByteToWideN(x,x,x)
0x10120ca9  test    eax, eax
0x10120cab  jz      loc_10120E11
0x10120cb1  push    104h; int
0x10120cb6  lea     edx, [ebp+var_218]; lpWideCharStr
0x10120cbc  lea     ecx, [ebp+var_420]; lpMultiByteStr
0x10120cc2  call    _FMultiByteToWideN@12; FMultiByteToWideN(x,x,x)
0x10120cc7  test    eax, eax
0x10120cc9  jz      loc_10120E11
0x10120ccf  test    esi, esi
0x10120cd1  jnz     loc_10120D5C
0x10120cd7  push    5Ch ; '\'
0x10120cd9  pop     esi
0x10120cda  lea     eax, [ebp+Str]
0x10120ce0  push    esi; Ch
0x10120ce1  push    eax; Str
0x10120ce2  call    ds:__imp__wcschr
0x10120ce8  mov     [ebp+var_428], eax
0x10120cee  pop     ecx
0x10120cef  pop     ecx
0x10120cf0  test    eax, eax
0x10120cf2  jz      short loc_10120D52
0x10120cf4  push    [ebp+arg_0]
0x10120cf7  xor     ecx, ecx
0x10120cf9  lea     edx, [ebp+Str]
0x10120cff  mov     [eax], cx
0x10120d02  mov     ecx, [ebp+lpBuffer]
0x10120d08  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120d0d  mov     eax, [ebp+var_428]
0x10120d13  mov     [eax], si
0x10120d16  mov     eax, [ebp+var_430]
0x10120d1c  mov     esi, [ebp+cchDest]
0x10120d22  add     eax, 4
0x10120d25  push    eax
0x10120d26  lea     eax, [ebp+var_218]
0x10120d2c  push    eax
0x10120d2d  push    offset aSS_0; "%s%s"
0x10120d32  push    esi; cchDest
0x10120d33  push    edi; pszDest
0x10120d34  call    _StringCchPrintfW
0x10120d39  add     esp, 14h
0x10120d3c  test    esi, esi
0x10120d3e  jz      short loc_10120D47
0x10120d40  xor     eax, eax
0x10120d42  mov     [edi+esi*2-2], ax
0x10120d47  xor     esi, esi
0x10120d49  inc     esi
0x10120d4a  mov     [ebp+var_424], esi
0x10120d50  jmp     short loc_10120D58
0x10120d52  mov     esi, [ebp+var_424]
0x10120d58  xor     eax, eax
0x10120d5a  jmp     short loc_10120DB2
0x10120d5c  sub     esi, 1E7h
0x10120d62  jz      short loc_10120D79
0x10120d64  sub     esi, 2CCh
0x10120d6a  jz      short loc_10120D79
0x10120d6c  sub     esi, 13h
0x10120d6f  jz      short loc_10120D79
0x10120d71  sub     esi, 404h
0x10120d77  jnz     short loc_10120DDC
0x10120d79  lea     eax, [ebp+nSize]
0x10120d7f  push    eax; nSize
0x10120d80  push    [ebp+lpBuffer]; lpBuffer
0x10120d86  call    _JetGetComputerNameW@8; JetGetComputerNameW(x,x)
0x10120d8b  test    eax, eax
0x10120d8d  jz      short loc_10120DA4
0x10120d8f  push    [ebp+arg_8]
0x10120d92  mov     edx, [ebp+var_430]
0x10120d98  mov     ecx, ebx
0x10120d9a  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10120d9f  xor     eax, eax
0x10120da1  inc     eax
0x10120da2  jmp     short loc_10120DAA
0x10120da4  mov     eax, [ebp+var_428]
0x10120daa  mov     esi, eax
0x10120dac  mov     [ebp+var_424], esi
0x10120db2  test    esi, esi
0x10120db4  jz      short loc_10120DDC
0x10120db6  mov     ecx, [ebp+var_444]
0x10120dbc  test    ecx, ecx
0x10120dbe  jz      short loc_10120DC2
0x10120dc0  mov     [ecx], eax
0x10120dc2  test    eax, eax
0x10120dc4  jz      short loc_10120DF3
0x10120dc6  push    [ebp+cchDest]
0x10120dcc  mov     edx, edi
0x10120dce  mov     ecx, ebx
0x10120dd0  call    _ResolveLocalPathToRemoteName@12; ResolveLocalPathToRemoteName(x,x,x)
0x10120dd5  test    eax, eax
0x10120dd7  jnz     short loc_10120DDC
0x10120dd9  mov     [edi], ax
0x10120ddc  mov     eax, [ebp+var_424]
0x10120de2  mov     ecx, [ebp+var_4]
0x10120de5  pop     edi
0x10120de6  pop     esi
0x10120de7  xor     ecx, ebp; StackCookie
0x10120de9  pop     ebx
0x10120dea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10120def  leave
0x10120df0  retn    18h
0x10120df3  push    [ebp+arg_8]
0x10120df6  mov     edx, ebx
0x10120df8  mov     ecx, edi
0x10120dfa  call    _ResolveRemotePathToLocalName@12; ResolveRemotePathToLocalName(x,x,x)
0x10120dff  test    eax, eax
0x10120e01  jnz     short loc_10120DDC
0x10120e03  test    ebx, ebx
0x10120e05  jz      short loc_10120DDC
0x10120e07  cmp     [ebp+arg_8], eax
0x10120e0a  jz      short loc_10120DDC
0x10120e0c  mov     [ebx], ax
0x10120e0f  jmp     short loc_10120DDC
0x10120e11  xor     eax, eax
0x10120e13  jmp     short loc_10120DE2
```
