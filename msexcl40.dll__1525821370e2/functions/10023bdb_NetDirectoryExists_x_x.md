# NetDirectoryExists(x,x)

- ea: `0x10023bdb`
- end: `0x1002403c`
- name: `_NetDirectoryExists@8`
- size: `1121`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x10026676`

## callees

- `0x10006400`
- `0x100224b6`
- `0x10022628`
- `0x10022838`
- `0x10022df6`
- `0x10023bdb`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023d68`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023dad`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023de6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023e36`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023e7b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023eea`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023f86`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023fd1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023d68`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023dad`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023de6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023e36`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023e7b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023eea`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023f86`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023fd1`

## pseudocode

```c
int __fastcall NetDirectoryExists(const unsigned __int16 *a1, int *a2)
{
  CHAR *v3; // ebx
  int result; // eax
  int v5; // esi
  WCHAR v6; // ax
  _WORD *v7; // ecx
  __int16 v8; // dx
  _WORD *v9; // edi
  WCHAR v10; // cx
  const WCHAR *v11; // eax
  const WCHAR *v12; // esi
  const WCHAR *v13; // edi
  const WCHAR *v14; // ecx
  __int16 v15; // ax
  CHAR *v16; // edi
  CHAR *v17; // ecx
  const WCHAR *v18; // ecx
  __int16 v19; // ax
  LPCWCH v20; // ecx
  __int16 v21; // ax
  WCHAR *v22; // esi
  LPCWCH v23; // ecx
  __int16 v24; // ax
  const WCHAR *v25; // esi
  int InternetError; // ebx
  CHAR *v27; // edi
  const WCHAR *v28; // ecx
  __int16 v29; // ax
  int v30; // [esp-4h] [ebp-238h]
  const WCHAR *v32; // [esp+10h] [ebp-224h]
  LPCWCH v33; // [esp+14h] [ebp-220h] BYREF
  int v34; // [esp+18h] [ebp-21Ch]
  LPCWCH v35; // [esp+1Ch] [ebp-218h]
  LPCWCH lpWideCharStr; // [esp+20h] [ebp-214h]
  _WORD v37[262]; // [esp+24h] [ebp-210h] BYREF

  v34 = 0;
  v3 = 0;
  *a2 = 0;
  if ( ProtocolPrefix(a1) != 1 && ProtocolPrefix(a1) )
    return -1305;
  if ( !dword_1003AE18 && !NetInitializeInternetServices() )
    return -20163;
  v5 = wcslen(a1);
  if ( ProtocolPrefix(a1) == 1 )
  {
    if ( v5 > 6 )
    {
      v30 = 6;
      goto LABEL_12;
    }
    return -1305;
  }
  if ( v5 <= 7 )
    return -1305;
  v30 = 7;
LABEL_12:
  WCSCPY2(v37, &a1[v30], 0x105u);
  v6 = v37[0];
  v7 = v37;
  v8 = v37[0];
  if ( v37[0] )
  {
    do
    {
      if ( v8 == 47 )
        *v7 = 92;
      v8 = *++v7;
    }
    while ( *v7 );
    v6 = v37[0];
  }
  lpWideCharStr = v37;
  v9 = v37;
  v32 = v37;
  if ( v6 )
  {
    v10 = v6;
    while ( 1 )
    {
      v11 = v9 + 1;
      if ( v10 == 92 )
        break;
      ++v9;
      v32 = v11;
      v10 = *v11;
      if ( !*v11 )
        goto LABEL_23;
    }
    v32 = v9 + 1;
    *v9 = 0;
  }
LABEL_23:
  FindUserNamePassword(&v33);
  v12 = v35;
  if ( v35 && !*v35 )
  {
    result = -20159;
LABEL_26:
    *a2 = result;
    return result;
  }
  v13 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    v3 = (CHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    if ( !v3 )
      return -1011;
    v14 = v13;
    do
      v15 = *v14++;
    while ( v15 != (_WORD)v34 );
    WideCharToMultiByte(0, 0, v13, v14 - (v13 + 1), v3, (int)lpWideCharStr, 0, 0);
    v3[(_DWORD)lpWideCharStr] = 0;
  }
  if ( v12 )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, v12, wcslen(v12), 0, 0, 0, 0);
    v16 = (CHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    if ( !v16 )
    {
      if ( v3 )
      {
        v17 = v3;
LABEL_48:
        MemFree(v17);
      }
      return -1011;
    }
    v18 = v12;
    do
      v19 = *v18++;
    while ( v19 != (_WORD)v34 );
    WideCharToMultiByte(0, 0, v12, v18 - (v12 + 1), v16, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v16) = 0;
  }
  else
  {
    v16 = 0;
  }
  if ( v33 )
  {
    v20 = v33;
    do
      v21 = *v20++;
    while ( v21 != (_WORD)v34 );
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, v33, v20 - (v33 + 1), 0, 0, 0, 0);
    v22 = (WCHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    v35 = v22;
    if ( !v22 )
    {
      if ( v3 )
        MemFree(v3);
      if ( !v16 )
        return -1011;
      v17 = v16;
      goto LABEL_48;
    }
    v23 = v33;
    do
      v24 = *v23++;
    while ( v24 != (_WORD)v34 );
    WideCharToMultiByte(0, 0, v33, v23 - (v33 + 1), (LPSTR)v22, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v22) = 0;
  }
  else
  {
    v22 = 0;
    v35 = 0;
  }
  v25 = (const WCHAR *)InternetConnectA((HINTERNET)dword_1003AE18, v3, 0, v16, (LPCSTR)v22, 1u, 0, 0);
  lpWideCharStr = v25;
  if ( v3 )
    MemFree(v3);
  if ( v16 )
    MemFree(v16);
  if ( v35 )
    MemFree(v35);
  if ( !v25 )
  {
    result = GetInternetError();
    goto LABEL_26;
  }
  InternetError = 0;
  v35 = (LPCWCH)WideCharToMultiByte(0, 0, v32, wcslen(v32), 0, 0, 0, 0);
  v27 = (CHAR *)MemAllocate((signed int)v35 + 1);
  if ( !v27 )
    return -1011;
  v28 = v32;
  do
    v29 = *v28++;
  while ( v29 != (_WORD)v34 );
  WideCharToMultiByte(0, 0, v32, v28 - (v32 + 1), v27, (int)v35, 0, 0);
  *((_BYTE *)v35 + (_DWORD)v27) = 0;
  if ( *v27 && !FtpSetCurrentDirectoryA((HINTERNET)lpWideCharStr, v27) )
  {
    InternetError = GetInternetError();
    *a2 = InternetError;
  }
  MemFree(v27);
  InternetCloseHandle((HINTERNET)lpWideCharStr);
  return InternetError;
}

```

## disassembly

```asm
0x10023bdb  mov     edi, edi
0x10023bdd  push    ebp
0x10023bde  mov     ebp, esp
0x10023be0  sub     esp, 228h
0x10023be6  mov     eax, ___security_cookie
0x10023beb  xor     eax, ebp
0x10023bed  mov     [ebp+var_4], eax
0x10023bf0  push    ebx
0x10023bf1  push    esi
0x10023bf2  mov     eax, edx
0x10023bf4  push    edi
0x10023bf5  mov     edi, ecx
0x10023bf7  mov     [ebp+var_228], eax
0x10023bfd  xor     ecx, ecx
0x10023bff  mov     [ebp+var_21C], ecx
0x10023c05  mov     ebx, ecx
0x10023c07  mov     [eax], ecx
0x10023c09  mov     ecx, edi
0x10023c0b  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10023c10  cmp     eax, 1
0x10023c13  jz      short loc_10023C20
0x10023c15  mov     ecx, edi
0x10023c17  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10023c1c  test    eax, eax
0x10023c1e  jnz     short loc_10023C6B
0x10023c20  cmp     dword_1003AE18, ebx
0x10023c26  jnz     short loc_10023C3B
0x10023c28  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x10023c2d  test    eax, eax
0x10023c2f  jnz     short loc_10023C3B
0x10023c31  mov     eax, 0FFFFB13Dh
0x10023c36  jmp     loc_1002402D
0x10023c3b  mov     esi, edi
0x10023c3d  xor     edx, edx
0x10023c3f  lea     ecx, [esi+2]
0x10023c42  mov     ax, [esi]
0x10023c45  add     esi, 2
0x10023c48  cmp     ax, dx
0x10023c4b  jnz     short loc_10023C42
0x10023c4d  sub     esi, ecx
0x10023c4f  mov     ecx, edi
0x10023c51  sar     esi, 1
0x10023c53  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10023c58  cmp     eax, 1
0x10023c5b  jnz     short loc_10023C66
0x10023c5d  cmp     esi, 6
0x10023c60  jle     short loc_10023C6B
0x10023c62  push    0Ch
0x10023c64  jmp     short loc_10023C77
0x10023c66  cmp     esi, 7
0x10023c69  jg      short loc_10023C75
0x10023c6b  mov     eax, 0FFFFFAE7h
0x10023c70  jmp     loc_1002402D
0x10023c75  push    0Eh
0x10023c77  pop     eax
0x10023c78  push    105h
0x10023c7d  lea     ecx, [ebp+var_210]
0x10023c83  lea     edx, [edi+eax]
0x10023c86  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10023c8b  mov     ax, [ebp+var_210]
0x10023c92  lea     ecx, [ebp+var_210]
0x10023c98  movzx   edx, ax
0x10023c9b  push    5Ch ; '\'
0x10023c9d  pop     esi
0x10023c9e  test    dx, dx
0x10023ca1  jz      short loc_10023CC0
0x10023ca3  cmp     dx, 2Fh ; '/'
0x10023ca7  jnz     short loc_10023CAC
0x10023ca9  mov     [ecx], si
0x10023cac  add     ecx, 2
0x10023caf  movzx   eax, word ptr [ecx]
0x10023cb2  mov     edx, eax
0x10023cb4  test    ax, ax
0x10023cb7  jnz     short loc_10023CA3
0x10023cb9  mov     ax, [ebp+var_210]
0x10023cc0  lea     ecx, [ebp+var_210]
0x10023cc6  movzx   eax, ax
0x10023cc9  mov     [ebp+lpWideCharStr], ecx
0x10023ccf  mov     edi, ecx
0x10023cd1  mov     [ebp+var_224], edi
0x10023cd7  test    ax, ax
0x10023cda  jz      short loc_10023D05
0x10023cdc  mov     ecx, eax
0x10023cde  lea     eax, [edi+2]
0x10023ce1  cmp     cx, si
0x10023ce4  jz      short loc_10023CFA
0x10023ce6  mov     edi, eax
0x10023ce8  mov     [ebp+var_224], edi
0x10023cee  movzx   eax, word ptr [edi]
0x10023cf1  mov     ecx, eax
0x10023cf3  test    ax, ax
0x10023cf6  jnz     short loc_10023CDE
0x10023cf8  jmp     short loc_10023D05
0x10023cfa  xor     ecx, ecx
0x10023cfc  mov     [ebp+var_224], eax
0x10023d02  mov     [edi], cx
0x10023d05  lea     eax, [ebp+var_220]
0x10023d0b  push    eax
0x10023d0c  lea     edx, [ebp+var_218]
0x10023d12  lea     ecx, [ebp+lpWideCharStr]
0x10023d18  call    FindUserNamePassword
0x10023d1d  mov     esi, [ebp+var_218]
0x10023d23  xor     ecx, ecx
0x10023d25  test    esi, esi
0x10023d27  jz      short loc_10023D40
0x10023d29  cmp     [esi], cx
0x10023d2c  jnz     short loc_10023D40
0x10023d2e  mov     eax, 0FFFFB141h
0x10023d33  mov     ecx, [ebp+var_228]
0x10023d39  mov     [ecx], eax
0x10023d3b  jmp     loc_1002402D
0x10023d40  mov     edi, [ebp+lpWideCharStr]
0x10023d46  test    edi, edi
0x10023d48  jz      short loc_10023DBE
0x10023d4a  mov     ecx, edi
0x10023d4c  xor     ebx, ebx
0x10023d4e  lea     edx, [ecx+2]
0x10023d51  mov     ax, [ecx]
0x10023d54  add     ecx, 2
0x10023d57  cmp     ax, bx
0x10023d5a  jnz     short loc_10023D51
0x10023d5c  push    ebx; lpUsedDefaultChar
0x10023d5d  push    ebx; lpDefaultChar
0x10023d5e  push    ebx; cbMultiByte
0x10023d5f  push    ebx; lpMultiByteStr
0x10023d60  sub     ecx, edx
0x10023d62  sar     ecx, 1
0x10023d64  push    ecx; cchWideChar
0x10023d65  push    edi; lpWideCharStr
0x10023d66  push    ebx; dwFlags
0x10023d67  push    ebx; CodePage
0x10023d68  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023d6e  mov     [ebp+lpWideCharStr], eax
0x10023d74  lea     ecx, [eax+1]
0x10023d77  call    _MemAllocate@4; MemAllocate(x)
0x10023d7c  mov     ebx, eax
0x10023d7e  test    ebx, ebx
0x10023d80  jz      loc_10023FA0
0x10023d86  mov     ecx, edi
0x10023d88  lea     edx, [ecx+2]
0x10023d8b  mov     ax, [ecx]
0x10023d8e  add     ecx, 2
0x10023d91  cmp     ax, word ptr [ebp+var_21C]
0x10023d98  jnz     short loc_10023D8B
0x10023d9a  xor     eax, eax
0x10023d9c  sub     ecx, edx
0x10023d9e  push    eax; lpUsedDefaultChar
0x10023d9f  push    eax; lpDefaultChar
0x10023da0  push    [ebp+lpWideCharStr]; cbMultiByte
0x10023da6  sar     ecx, 1
0x10023da8  push    ebx; lpMultiByteStr
0x10023da9  push    ecx; cchWideChar
0x10023daa  push    edi; lpWideCharStr
0x10023dab  push    eax; dwFlags
0x10023dac  push    eax; CodePage
0x10023dad  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023db3  mov     eax, [ebp+lpWideCharStr]
0x10023db9  xor     ecx, ecx
0x10023dbb  mov     [eax+ebx], cl
0x10023dbe  test    esi, esi
0x10023dc0  jz      loc_10023E49
0x10023dc6  mov     ecx, esi
0x10023dc8  xor     edi, edi
0x10023dca  lea     edx, [ecx+2]
0x10023dcd  mov     ax, [ecx]
0x10023dd0  add     ecx, 2
0x10023dd3  cmp     ax, di
0x10023dd6  jnz     short loc_10023DCD
0x10023dd8  xor     eax, eax
0x10023dda  sub     ecx, edx
0x10023ddc  push    eax; lpUsedDefaultChar
0x10023ddd  push    eax; lpDefaultChar
0x10023dde  push    eax; cbMultiByte
0x10023ddf  push    eax; lpMultiByteStr
0x10023de0  sar     ecx, 1
0x10023de2  push    ecx; cchWideChar
0x10023de3  push    esi; lpWideCharStr
0x10023de4  push    eax; dwFlags
0x10023de5  push    eax; CodePage
0x10023de6  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023dec  mov     [ebp+lpWideCharStr], eax
0x10023df2  lea     ecx, [eax+1]
0x10023df5  call    _MemAllocate@4; MemAllocate(x)
0x10023dfa  mov     edi, eax
0x10023dfc  test    edi, edi
0x10023dfe  jnz     short loc_10023E0F
0x10023e00  test    ebx, ebx
0x10023e02  jz      loc_10023FA0
0x10023e08  mov     ecx, ebx
0x10023e0a  jmp     loc_10023EB0
0x10023e0f  mov     ecx, esi
0x10023e11  lea     edx, [ecx+2]
0x10023e14  mov     ax, [ecx]
0x10023e17  add     ecx, 2
0x10023e1a  cmp     ax, word ptr [ebp+var_21C]
0x10023e21  jnz     short loc_10023E14
0x10023e23  xor     eax, eax
0x10023e25  sub     ecx, edx
0x10023e27  push    eax; lpUsedDefaultChar
0x10023e28  push    eax; lpDefaultChar
0x10023e29  push    [ebp+lpWideCharStr]; cbMultiByte
0x10023e2f  sar     ecx, 1
0x10023e31  push    edi; lpMultiByteStr
0x10023e32  push    ecx; cchWideChar
0x10023e33  push    esi; lpWideCharStr
0x10023e34  push    eax; dwFlags
0x10023e35  push    eax; CodePage
0x10023e36  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023e3c  mov     eax, [ebp+lpWideCharStr]
0x10023e42  xor     ecx, ecx
0x10023e44  mov     [edi+eax], cl
0x10023e47  jmp     short loc_10023E4B
0x10023e49  mov     edi, ecx
0x10023e4b  mov     edx, [ebp+var_220]
0x10023e51  test    edx, edx
0x10023e53  jz      loc_10023EFD
0x10023e59  mov     ecx, edx
0x10023e5b  lea     esi, [ecx+2]
0x10023e5e  mov     ax, [ecx]
0x10023e61  add     ecx, 2
0x10023e64  cmp     ax, word ptr [ebp+var_21C]
0x10023e6b  jnz     short loc_10023E5E
0x10023e6d  xor     eax, eax
0x10023e6f  sub     ecx, esi
0x10023e71  push    eax; lpUsedDefaultChar
0x10023e72  push    eax; lpDefaultChar
0x10023e73  push    eax; cbMultiByte
0x10023e74  push    eax; lpMultiByteStr
0x10023e75  sar     ecx, 1
0x10023e77  push    ecx; cchWideChar
0x10023e78  push    edx; lpWideCharStr
0x10023e79  push    eax; dwFlags
0x10023e7a  push    eax; CodePage
0x10023e7b  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023e81  mov     [ebp+lpWideCharStr], eax
0x10023e87  lea     ecx, [eax+1]
0x10023e8a  call    _MemAllocate@4; MemAllocate(x)
0x10023e8f  mov     esi, eax
0x10023e91  mov     [ebp+var_218], esi
0x10023e97  test    esi, esi
0x10023e99  jnz     short loc_10023EBA
0x10023e9b  test    ebx, ebx
0x10023e9d  jz      short loc_10023EA6
0x10023e9f  mov     ecx, ebx
0x10023ea1  call    _MemFree@4; MemFree(x)
0x10023ea6  test    edi, edi
0x10023ea8  jz      loc_10023FA0
0x10023eae  mov     ecx, edi
0x10023eb0  call    _MemFree@4; MemFree(x)
0x10023eb5  jmp     loc_10023FA0
0x10023eba  mov     ecx, [ebp+var_220]
0x10023ec0  lea     edx, [ecx+2]
0x10023ec3  mov     ax, [ecx]
0x10023ec6  add     ecx, 2
0x10023ec9  cmp     ax, word ptr [ebp+var_21C]
0x10023ed0  jnz     short loc_10023EC3
0x10023ed2  xor     eax, eax
0x10023ed4  sub     ecx, edx
0x10023ed6  push    eax; lpUsedDefaultChar
0x10023ed7  push    eax; lpDefaultChar
0x10023ed8  push    [ebp+lpWideCharStr]; cbMultiByte
0x10023ede  sar     ecx, 1
0x10023ee0  push    esi; lpMultiByteStr
0x10023ee1  push    ecx; cchWideChar
0x10023ee2  push    [ebp+var_220]; lpWideCharStr
0x10023ee8  push    eax; dwFlags
0x10023ee9  push    eax; CodePage
0x10023eea  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023ef0  mov     eax, [ebp+lpWideCharStr]
0x10023ef6  xor     ecx, ecx
0x10023ef8  mov     [esi+eax], cl
0x10023efb  jmp     short loc_10023F05
0x10023efd  mov     esi, ecx
0x10023eff  mov     [ebp+var_218], ecx
0x10023f05  push    ecx
0x10023f06  push    ecx
0x10023f07  push    1
0x10023f09  push    esi
0x10023f0a  mov     esi, InternetConnectA
0x10023f10  push    edi
0x10023f11  push    ecx
0x10023f12  push    ebx
0x10023f13  push    dword_1003AE18
0x10023f19  mov     ecx, esi
0x10023f1b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023f21  call    esi ; InternetConnectA
0x10023f23  mov     esi, eax
0x10023f25  mov     [ebp+lpWideCharStr], esi
0x10023f2b  test    ebx, ebx
0x10023f2d  jz      short loc_10023F36
0x10023f2f  mov     ecx, ebx
0x10023f31  call    _MemFree@4; MemFree(x)
0x10023f36  test    edi, edi
0x10023f38  jz      short loc_10023F41
0x10023f3a  mov     ecx, edi
0x10023f3c  call    _MemFree@4; MemFree(x)
0x10023f41  mov     ecx, [ebp+var_218]
0x10023f47  test    ecx, ecx
0x10023f49  jz      short loc_10023F50
0x10023f4b  call    _MemFree@4; MemFree(x)
  ... truncated ...
```
