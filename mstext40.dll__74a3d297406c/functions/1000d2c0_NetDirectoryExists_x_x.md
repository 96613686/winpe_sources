# NetDirectoryExists(x,x)

- ea: `0x1000d2c0`
- end: `0x1000d712`
- name: `_NetDirectoryExists@8`
- size: `1106`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1000b860`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000c970`
- `0x1000ca60`
- `0x1000d2c0`
- `0x1000ddd0`
- `0x1000e900`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1000d482`
- `KERNEL32!WideCharToMultiByte` at `0x1000d4c4`
- `KERNEL32!WideCharToMultiByte` at `0x1000d500`
- `KERNEL32!WideCharToMultiByte` at `0x1000d555`
- `KERNEL32!WideCharToMultiByte` at `0x1000d591`
- `KERNEL32!WideCharToMultiByte` at `0x1000d5f5`
- `KERNEL32!WideCharToMultiByte` at `0x1000d67d`
- `KERNEL32!WideCharToMultiByte` at `0x1000d6be`
- `KERNEL32!WideCharToMultiByte` at `0x1000d46b`
- `KERNEL32!WideCharToMultiByte` at `0x1000d4ba`
- `KERNEL32!WideCharToMultiByte` at `0x1000d4d0`
- `KERNEL32!WideCharToMultiByte` at `0x1000d53d`
- `KERNEL32!WideCharToMultiByte` at `0x1000d591`
- `KERNEL32!WideCharToMultiByte` at `0x1000d5f5`
- `KERNEL32!WideCharToMultiByte` at `0x1000d67d`
- `KERNEL32!WideCharToMultiByte` at `0x1000d6be`

## pseudocode

```c
int __stdcall NetDirectoryExists(const unsigned __int16 *a1, int *a2)
{
  CHAR *v2; // ebp
  int result; // eax
  int v4; // esi
  WCHAR *v5; // ecx
  int v6; // edx
  WCHAR v7; // ax
  int v8; // edx
  WCHAR v9; // ax
  WCHAR *v10; // eax
  WCHAR v11; // cx
  WCHAR *v12; // esi
  const WCHAR *v13; // ebx
  LPCWCH v14; // edi
  _WORD *v15; // ecx
  LPCWCH v16; // edx
  int (__stdcall *v18)(UINT, DWORD, LPCWCH, int, LPSTR, int, LPCCH, LPBOOL); // edi
  CHAR *v19; // edi
  CHAR *v20; // ebx
  LPCWCH v21; // ecx
  WCHAR *v23; // ebp
  int InternetError; // ebx
  CHAR *v25; // edi
  const WCHAR *v26; // [esp-Ch] [ebp-248h]
  LPCWCH lpWideCharStr; // [esp+1Ch] [ebp-220h] BYREF
  LPCWCH v28; // [esp+20h] [ebp-21Ch] BYREF
  LPCWCH v29; // [esp+24h] [ebp-218h] BYREF
  int *v30; // [esp+28h] [ebp-214h]
  WCHAR WideCharStr[262]; // [esp+2Ch] [ebp-210h] BYREF

  v2 = 0;
  v30 = a2;
  *a2 = 0;
  if ( ProtocolPrefix(a1) != 1 && ProtocolPrefix(a1) )
    return -1305;
  if ( !dword_10040FB8 && !NetInitializeInternetServices() )
    return -20163;
  v4 = wcslen(a1);
  if ( ProtocolPrefix(a1) == 1 )
  {
    if ( v4 > 6 )
    {
      v5 = WideCharStr;
      v6 = 261;
      while ( v6 != -2147483385 )
      {
        v7 = *(WCHAR *)((char *)v5 + (char *)(a1 + 6) - (char *)WideCharStr);
        if ( !v7 )
          break;
        *v5++ = v7;
        if ( !--v6 )
          goto LABEL_22;
      }
      goto LABEL_23;
    }
    return -1305;
  }
  if ( v4 <= 7 )
    return -1305;
  v5 = WideCharStr;
  v8 = 261;
  while ( v8 != -2147483385 )
  {
    v9 = *(WCHAR *)((char *)v5 + (char *)(a1 + 7) - (char *)WideCharStr);
    if ( !v9 )
      break;
    *v5++ = v9;
    if ( !--v8 )
    {
LABEL_22:
      --v5;
      break;
    }
  }
LABEL_23:
  *v5 = 0;
  v10 = WideCharStr;
  v11 = WideCharStr[0];
  if ( WideCharStr[0] )
  {
    do
    {
      if ( *v10 == 47 )
        *v10 = 92;
      ++v10;
    }
    while ( *v10 );
    v11 = WideCharStr[0];
  }
  lpWideCharStr = WideCharStr;
  v12 = WideCharStr;
  if ( v11 )
  {
    while ( *v12 != 92 )
    {
      if ( !*++v12 )
        goto LABEL_33;
    }
    *v12++ = 0;
  }
LABEL_33:
  FindUserNamePassword(&lpWideCharStr, &v29, &v28);
  v13 = v29;
  if ( v29 && !*v29 )
  {
    result = -20159;
    *v30 = -20159;
    return result;
  }
  v14 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    v2 = (CHAR *)MemAllocate((size_t)lpWideCharStr + 1);
    if ( !v2 )
      return -1011;
    v15 = v14;
    v16 = v14 + 1;
    while ( *v15++ )
      ;
    v26 = v14;
    v18 = WideCharToMultiByte;
    WideCharToMultiByte(0, 0, v26, v15 - v16, v2, (int)lpWideCharStr, 0, 0);
    v2[(_DWORD)lpWideCharStr] = 0;
  }
  else
  {
    v18 = WideCharToMultiByte;
  }
  if ( v13 )
  {
    lpWideCharStr = (LPCWCH)v18(0, 0, v13, wcslen(v13), 0, 0, 0, 0);
    v19 = (CHAR *)MemAllocate((size_t)lpWideCharStr + 1);
    if ( !v19 )
    {
      if ( v2 )
      {
        MemFree(v2);
        return -1011;
      }
      return -1011;
    }
    WideCharToMultiByte(0, 0, v13, wcslen(v13), v19, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v19) = 0;
  }
  else
  {
    v19 = 0;
  }
  if ( v28 )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, v28, wcslen(v28), 0, 0, 0, 0);
    v20 = (CHAR *)MemAllocate((size_t)lpWideCharStr + 1);
    if ( !v20 )
    {
      if ( v2 )
        MemFree(v2);
      if ( v19 )
        MemFree(v19);
      return -1011;
    }
    v21 = v28;
    v29 = v28 + 1;
    while ( *v21++ )
      ;
    WideCharToMultiByte(0, 0, v28, v21 - v29, v20, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v20) = 0;
  }
  else
  {
    v20 = 0;
  }
  v29 = (LPCWCH)InternetConnectA((HINTERNET)dword_10040FB8, v2, 0, v19, v20, 1u, 0, 0);
  if ( v2 )
    MemFree(v2);
  if ( v19 )
    MemFree(v19);
  if ( v20 )
    MemFree(v20);
  v23 = (WCHAR *)v29;
  if ( !v29 )
  {
    result = GetInternetError();
    *v30 = result;
    return result;
  }
  InternetError = 0;
  v28 = (LPCWCH)WideCharToMultiByte(0, 0, v12, wcslen(v12), 0, 0, 0, 0);
  v25 = (CHAR *)MemAllocate((size_t)v28 + 1);
  if ( !v25 )
    return -1011;
  WideCharToMultiByte(0, 0, v12, wcslen(v12), v25, (int)v28, 0, 0);
  *((_BYTE *)v28 + (_DWORD)v25) = 0;
  if ( *v25 && !FtpSetCurrentDirectoryA(v23, v25) )
  {
    InternetError = GetInternetError();
    *v30 = InternetError;
  }
  MemFree(v25);
  InternetCloseHandle(v23);
  return InternetError;
}

```

## disassembly

```asm
0x1000d2c0  sub     esp, 220h
0x1000d2c6  mov     eax, ___security_cookie
0x1000d2cb  xor     eax, esp
0x1000d2cd  mov     [esp+220h+var_4], eax
0x1000d2d4  mov     eax, [esp+220h+arg_4]
0x1000d2db  push    ebp
0x1000d2dc  push    edi
0x1000d2dd  mov     edi, [esp+228h+arg_0]
0x1000d2e4  xor     ebp, ebp
0x1000d2e6  push    edi
0x1000d2e7  mov     [esp+22Ch+var_214], eax
0x1000d2eb  mov     [eax], ebp
0x1000d2ed  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1000d2f2  cmp     eax, 1
0x1000d2f5  jz      short loc_1000D30B
0x1000d2f7  push    edi
0x1000d2f8  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1000d2fd  test    eax, eax
0x1000d2ff  jz      short loc_1000D30B
0x1000d301  mov     eax, 0FFFFFAE7h
0x1000d306  jmp     loc_1000D6F9
0x1000d30b  cmp     dword_10040FB8, ebp
0x1000d311  jnz     short loc_1000D326
0x1000d313  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1000d318  test    eax, eax
0x1000d31a  jnz     short loc_1000D326
0x1000d31c  mov     eax, 0FFFFB13Dh
0x1000d321  jmp     loc_1000D6F9
0x1000d326  push    esi
0x1000d327  mov     esi, edi
0x1000d329  lea     ecx, [esi+2]
0x1000d32c  lea     esp, [esp+0]
0x1000d330  mov     ax, [esi]
0x1000d333  add     esi, 2
0x1000d336  test    ax, ax
0x1000d339  jnz     short loc_1000D330
0x1000d33b  sub     esi, ecx
0x1000d33d  push    edi
0x1000d33e  sar     esi, 1
0x1000d340  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x1000d345  cmp     eax, 1
0x1000d348  jnz     short loc_1000D37E
0x1000d34a  cmp     esi, 6
0x1000d34d  jle     short loc_1000D383
0x1000d34f  lea     ecx, [esp+22Ch+WideCharStr]
0x1000d353  add     edi, 0Ch
0x1000d356  mov     eax, ecx
0x1000d358  mov     edx, 105h
0x1000d35d  sub     edi, eax
0x1000d35f  nop
0x1000d360  lea     eax, [edx+7FFFFEF9h]
0x1000d366  test    eax, eax
0x1000d368  jz      short loc_1000D3BE
0x1000d36a  movzx   eax, word ptr [edi+ecx]
0x1000d36e  test    ax, ax
0x1000d371  jz      short loc_1000D3BE
0x1000d373  mov     [ecx], ax
0x1000d376  add     ecx, 2
0x1000d379  dec     edx
0x1000d37a  jnz     short loc_1000D360
0x1000d37c  jmp     short loc_1000D3C2
0x1000d37e  cmp     esi, 7
0x1000d381  jg      short loc_1000D38D
0x1000d383  mov     eax, 0FFFFFAE7h
0x1000d388  jmp     loc_1000D6F8
0x1000d38d  lea     ecx, [esp+22Ch+WideCharStr]
0x1000d391  add     edi, 0Eh
0x1000d394  mov     eax, ecx
0x1000d396  mov     edx, 105h
0x1000d39b  sub     edi, eax
0x1000d39d  lea     ecx, [ecx+0]
0x1000d3a0  lea     eax, [edx+7FFFFEF9h]
0x1000d3a6  test    eax, eax
0x1000d3a8  jz      short loc_1000D3BE
0x1000d3aa  movzx   eax, word ptr [edi+ecx]
0x1000d3ae  test    ax, ax
0x1000d3b1  jz      short loc_1000D3BE
0x1000d3b3  mov     [ecx], ax
0x1000d3b6  add     ecx, 2
0x1000d3b9  dec     edx
0x1000d3ba  jnz     short loc_1000D3A0
0x1000d3bc  jmp     short loc_1000D3C2
0x1000d3be  test    edx, edx
0x1000d3c0  jnz     short loc_1000D3C5
0x1000d3c2  sub     ecx, 2
0x1000d3c5  xor     eax, eax
0x1000d3c7  mov     [ecx], ax
0x1000d3ca  lea     eax, [esp+22Ch+WideCharStr]
0x1000d3ce  mov     cx, [esp+22Ch+WideCharStr]
0x1000d3d3  test    cx, cx
0x1000d3d6  jz      short loc_1000D3F6
0x1000d3d8  mov     ecx, 5Ch ; '\'
0x1000d3dd  lea     ecx, [ecx+0]
0x1000d3e0  cmp     word ptr [eax], 2Fh ; '/'
0x1000d3e4  jnz     short loc_1000D3E9
0x1000d3e6  mov     [eax], cx
0x1000d3e9  add     eax, 2
0x1000d3ec  cmp     [eax], bp
0x1000d3ef  jnz     short loc_1000D3E0
0x1000d3f1  mov     cx, [esp+22Ch+WideCharStr]
0x1000d3f6  lea     eax, [esp+22Ch+WideCharStr]
0x1000d3fa  mov     [esp+22Ch+lpWideCharStr], eax
0x1000d3fe  mov     esi, eax
0x1000d400  test    cx, cx
0x1000d403  jz      short loc_1000D41D
0x1000d405  cmp     word ptr [esi], 5Ch ; '\'
0x1000d409  jz      short loc_1000D415
0x1000d40b  add     esi, 2
0x1000d40e  cmp     [esi], bp
0x1000d411  jnz     short loc_1000D405
0x1000d413  jmp     short loc_1000D41D
0x1000d415  xor     eax, eax
0x1000d417  mov     [esi], ax
0x1000d41a  add     esi, 2
0x1000d41d  push    ebx
0x1000d41e  lea     eax, [esp+230h+var_21C]
0x1000d422  push    eax
0x1000d423  lea     eax, [esp+234h+var_218]
0x1000d427  push    eax
0x1000d428  lea     eax, [esp+238h+lpWideCharStr]
0x1000d42c  push    eax
0x1000d42d  call    FindUserNamePassword
0x1000d432  mov     ebx, [esp+230h+var_218]
0x1000d436  test    ebx, ebx
0x1000d438  jz      short loc_1000D453
0x1000d43a  cmp     [ebx], bp
0x1000d43d  jnz     short loc_1000D453
0x1000d43f  mov     ecx, [esp+230h+var_214]
0x1000d443  mov     eax, 0FFFFB141h
0x1000d448  mov     dword ptr [ecx], 0FFFFB141h
0x1000d44e  jmp     loc_1000D6F7
0x1000d453  mov     edi, [esp+230h+lpWideCharStr]
0x1000d457  test    edi, edi
0x1000d459  jz      short loc_1000D4D0
0x1000d45b  mov     ecx, edi
0x1000d45d  lea     edx, [ecx+2]
0x1000d460  mov     ax, [ecx]
0x1000d463  add     ecx, 2
0x1000d466  test    ax, ax
0x1000d469  jnz     short loc_1000D460
0x1000d46b  mov     eax, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d470  sub     ecx, edx
0x1000d472  push    0; lpUsedDefaultChar
0x1000d474  push    0; lpDefaultChar
0x1000d476  push    0; cbMultiByte
0x1000d478  push    0; lpMultiByteStr
0x1000d47a  sar     ecx, 1
0x1000d47c  push    ecx; cchWideChar
0x1000d47d  push    edi; lpWideCharStr
0x1000d47e  push    0; dwFlags
0x1000d480  push    0; CodePage
0x1000d482  call    eax ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d484  mov     [esp+230h+lpWideCharStr], eax
0x1000d488  inc     eax
0x1000d489  push    eax; Size
0x1000d48a  call    _MemAllocate@4; MemAllocate(x)
0x1000d48f  mov     ebp, eax
0x1000d491  test    ebp, ebp
0x1000d493  jz      loc_1000D5BE
0x1000d499  mov     ecx, edi
0x1000d49b  lea     edx, [ecx+2]
0x1000d49e  mov     edi, edi
0x1000d4a0  mov     ax, [ecx]
0x1000d4a3  add     ecx, 2
0x1000d4a6  test    ax, ax
0x1000d4a9  jnz     short loc_1000D4A0
0x1000d4ab  push    0; lpUsedDefaultChar
0x1000d4ad  push    0; lpDefaultChar
0x1000d4af  push    [esp+238h+lpWideCharStr]; cbMultiByte
0x1000d4b3  sub     ecx, edx
0x1000d4b5  push    ebp; lpMultiByteStr
0x1000d4b6  sar     ecx, 1
0x1000d4b8  push    ecx; cchWideChar
0x1000d4b9  push    edi; lpWideCharStr
0x1000d4ba  mov     edi, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d4c0  push    0; dwFlags
0x1000d4c2  push    0; CodePage
0x1000d4c4  call    edi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d4c6  mov     eax, [esp+230h+lpWideCharStr]
0x1000d4ca  mov     byte ptr [eax+ebp], 0
0x1000d4ce  jmp     short loc_1000D4D6
0x1000d4d0  mov     edi, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d4d6  test    ebx, ebx
0x1000d4d8  jz      loc_1000D561
0x1000d4de  mov     ecx, ebx
0x1000d4e0  lea     edx, [ecx+2]
0x1000d4e3  mov     ax, [ecx]
0x1000d4e6  add     ecx, 2
0x1000d4e9  test    ax, ax
0x1000d4ec  jnz     short loc_1000D4E3
0x1000d4ee  push    0; lpUsedDefaultChar
0x1000d4f0  push    0; lpDefaultChar
0x1000d4f2  push    0; cbMultiByte
0x1000d4f4  push    0; lpMultiByteStr
0x1000d4f6  sub     ecx, edx
0x1000d4f8  sar     ecx, 1
0x1000d4fa  push    ecx; cchWideChar
0x1000d4fb  push    ebx; lpWideCharStr
0x1000d4fc  push    0; dwFlags
0x1000d4fe  push    0; CodePage
0x1000d500  call    edi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d502  mov     [esp+230h+lpWideCharStr], eax
0x1000d506  lea     ecx, [eax+1]
0x1000d509  push    ecx; Size
0x1000d50a  call    _MemAllocate@4; MemAllocate(x)
0x1000d50f  mov     edi, eax
0x1000d511  test    edi, edi
0x1000d513  jnz     short loc_1000D52D
0x1000d515  test    ebp, ebp
0x1000d517  jz      loc_1000D5BE
0x1000d51d  push    ebp
0x1000d51e  call    _MemFree@4; MemFree(x)
0x1000d523  mov     eax, 0FFFFFC0Dh
0x1000d528  jmp     loc_1000D6F7
0x1000d52d  mov     ecx, ebx
0x1000d52f  lea     edx, [ecx+2]
0x1000d532  mov     ax, [ecx]
0x1000d535  add     ecx, 2
0x1000d538  test    ax, ax
0x1000d53b  jnz     short loc_1000D532
0x1000d53d  mov     eax, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d542  sub     ecx, edx
0x1000d544  push    0; lpUsedDefaultChar
0x1000d546  push    0; lpDefaultChar
0x1000d548  push    [esp+238h+lpWideCharStr]; cbMultiByte
0x1000d54c  sar     ecx, 1
0x1000d54e  push    edi; lpMultiByteStr
0x1000d54f  push    ecx; cchWideChar
0x1000d550  push    ebx; lpWideCharStr
0x1000d551  push    0; dwFlags
0x1000d553  push    0; CodePage
0x1000d555  call    eax ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d557  mov     eax, [esp+230h+lpWideCharStr]
0x1000d55b  mov     byte ptr [edi+eax], 0
0x1000d55f  jmp     short loc_1000D563
0x1000d561  xor     edi, edi
0x1000d563  mov     edx, [esp+230h+var_21C]
0x1000d567  test    edx, edx
0x1000d569  jz      loc_1000D605
0x1000d56f  mov     ecx, edx
0x1000d571  lea     ebx, [ecx+2]
0x1000d574  mov     ax, [ecx]
0x1000d577  add     ecx, 2
0x1000d57a  test    ax, ax
0x1000d57d  jnz     short loc_1000D574
0x1000d57f  push    0; lpUsedDefaultChar
0x1000d581  push    0; lpDefaultChar
0x1000d583  push    0; cbMultiByte
0x1000d585  push    0; lpMultiByteStr
0x1000d587  sub     ecx, ebx
0x1000d589  sar     ecx, 1
0x1000d58b  push    ecx; cchWideChar
0x1000d58c  push    edx; lpWideCharStr
0x1000d58d  push    0; dwFlags
0x1000d58f  push    0; CodePage
0x1000d591  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d597  mov     [esp+230h+lpWideCharStr], eax
0x1000d59b  lea     ecx, [eax+1]
0x1000d59e  push    ecx; Size
0x1000d59f  call    _MemAllocate@4; MemAllocate(x)
0x1000d5a4  mov     ebx, eax
0x1000d5a6  test    ebx, ebx
0x1000d5a8  jnz     short loc_1000D5C8
0x1000d5aa  test    ebp, ebp
0x1000d5ac  jz      short loc_1000D5B4
0x1000d5ae  push    ebp
0x1000d5af  call    _MemFree@4; MemFree(x)
0x1000d5b4  test    edi, edi
0x1000d5b6  jz      short loc_1000D5BE
0x1000d5b8  push    edi
0x1000d5b9  call    _MemFree@4; MemFree(x)
0x1000d5be  mov     eax, 0FFFFFC0Dh
0x1000d5c3  jmp     loc_1000D6F7
0x1000d5c8  mov     edx, [esp+230h+var_21C]
0x1000d5cc  mov     ecx, edx
0x1000d5ce  lea     eax, [ecx+2]
0x1000d5d1  mov     [esp+230h+var_218], eax
0x1000d5d5  mov     ax, [ecx]
0x1000d5d8  add     ecx, 2
0x1000d5db  test    ax, ax
0x1000d5de  jnz     short loc_1000D5D5
0x1000d5e0  sub     ecx, [esp+230h+var_218]
0x1000d5e4  push    0; lpUsedDefaultChar
0x1000d5e6  push    0; lpDefaultChar
0x1000d5e8  push    [esp+238h+lpWideCharStr]; cbMultiByte
0x1000d5ec  sar     ecx, 1
0x1000d5ee  push    ebx; lpMultiByteStr
0x1000d5ef  push    ecx; cchWideChar
0x1000d5f0  push    edx; lpWideCharStr
0x1000d5f1  push    0; dwFlags
0x1000d5f3  push    0; CodePage
0x1000d5f5  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d5fb  mov     eax, [esp+230h+lpWideCharStr]
0x1000d5ff  mov     byte ptr [ebx+eax], 0
0x1000d603  jmp     short loc_1000D607
0x1000d605  xor     ebx, ebx
0x1000d607  push    0
0x1000d609  push    0
0x1000d60b  push    1
0x1000d60d  push    ebx
  ... truncated ...
```
