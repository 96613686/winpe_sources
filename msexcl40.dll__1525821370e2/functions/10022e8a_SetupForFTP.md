# SetupForFTP

- ea: `0x10022e8a`
- end: `0x100232c3`
- name: `SetupForFTP`
- size: `1081`
- prototype: `int __fastcall(int, _DWORD *)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100232c9`
- `0x10023563`
- `0x10023815`
- `0x10024042`

## callees

- `0x10006400`
- `0x100224b6`
- `0x10022838`
- `0x10022df6`
- `0x10022e8a`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100231cc`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100231cc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022fae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022ff5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002302a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002307a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100230bf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002312e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002320d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023268`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022fae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022ff5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002302a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002307a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100230bf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002312e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002320d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023268`

## pseudocode

```c
int __fastcall SetupForFTP(int a1, HINTERNET *a2)
{
  __int16 v4; // ax
  _WORD *v5; // ecx
  __int16 v6; // dx
  _WORD *v7; // ebx
  __int16 v8; // cx
  _WORD *v9; // eax
  const WCHAR *v10; // esi
  LPCWCH v11; // ebx
  CHAR *v12; // edi
  __int16 *v13; // ecx
  LPCWCH v14; // edx
  __int16 v15; // ax
  CHAR *v16; // ebx
  CHAR *v17; // ecx
  const WCHAR *v18; // ecx
  __int16 v19; // ax
  LPCWCH v20; // ecx
  __int16 v21; // ax
  WCHAR *v22; // esi
  LPCWCH v23; // ecx
  __int16 v24; // ax
  int v25; // esi
  CHAR *v26; // edi
  wchar_t *p_Dir; // ecx
  __int16 v28; // ax
  int InternetError; // edi
  const WCHAR *v30; // [esp-20h] [ebp-44Ch]
  _WORD *v32; // [esp+8h] [ebp-424h]
  LPCWCH v33; // [esp+Ch] [ebp-420h] BYREF
  LPCWCH v34; // [esp+10h] [ebp-41Ch]
  int v35; // [esp+14h] [ebp-418h]
  LPCWCH lpWideCharStr; // [esp+18h] [ebp-414h]
  _WORD v37[262]; // [esp+1Ch] [ebp-410h] BYREF
  wchar_t Dir; // [esp+228h] [ebp-204h] BYREF
  __int16 v39; // [esp+22Ah] [ebp-202h] BYREF

  if ( ProtocolPrefix(a1) != 1 )
    return -1305;
  WCSCPY2(v37, (_WORD *)(a1 + 12), 0x105u);
  v4 = v37[0];
  v5 = v37;
  v6 = v37[0];
  if ( v37[0] )
  {
    do
    {
      if ( v6 == 47 )
        *v5 = 92;
      v6 = *++v5;
    }
    while ( *v5 );
    v4 = v37[0];
  }
  lpWideCharStr = v37;
  v7 = v37;
  v32 = v37;
  if ( v4 )
  {
    v8 = v4;
    while ( 1 )
    {
      v9 = v7 + 1;
      if ( v8 == 92 )
        break;
      ++v7;
      v32 = v9;
      v8 = *v9;
      if ( !*v9 )
        goto LABEL_14;
    }
    v32 = v7 + 1;
    *v7 = 0;
  }
LABEL_14:
  FindUserNamePassword(&v33);
  v10 = v34;
  v35 = 0;
  if ( v34 && !*v34 )
    return -20159;
  v11 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    v12 = (CHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    if ( !v12 )
      return -1011;
    v13 = (__int16 *)v11;
    v14 = v11 + 1;
    do
      v15 = *v13++;
    while ( v15 != (_WORD)v35 );
    v30 = v11;
    v16 = 0;
    WideCharToMultiByte(0, 0, v30, ((char *)v13 - (char *)v14) >> 1, v12, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v12) = 0;
  }
  else
  {
    v16 = 0;
    v12 = 0;
  }
  if ( v10 )
  {
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, v10, wcslen(v10), 0, 0, 0, 0);
    v16 = (CHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    if ( !v16 )
    {
      if ( v12 )
      {
        v17 = v12;
LABEL_38:
        MemFree(v17);
      }
      return -1011;
    }
    v18 = v10;
    do
      v19 = *v18++;
    while ( v19 != (_WORD)v35 );
    WideCharToMultiByte(0, 0, v10, v18 - (v10 + 1), v16, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v16) = 0;
  }
  if ( v33 )
  {
    v20 = v33;
    do
      v21 = *v20++;
    while ( v21 != (_WORD)v35 );
    lpWideCharStr = (LPCWCH)WideCharToMultiByte(0, 0, v33, v20 - (v33 + 1), 0, 0, 0, 0);
    v22 = (WCHAR *)MemAllocate((signed int)lpWideCharStr + 1);
    v34 = v22;
    if ( !v22 )
    {
      if ( v12 )
        MemFree(v12);
      if ( !v16 )
        return -1011;
      v17 = v16;
      goto LABEL_38;
    }
    v23 = v33;
    do
      v24 = *v23++;
    while ( v24 != (_WORD)v35 );
    WideCharToMultiByte(0, 0, v33, v23 - (v33 + 1), (LPSTR)v22, (int)lpWideCharStr, 0, 0);
    *((_BYTE *)lpWideCharStr + (_DWORD)v22) = 0;
  }
  else
  {
    v22 = 0;
    v34 = 0;
  }
  *a2 = InternetConnectA((HINTERNET)dword_1003AE18, v12, 0, v16, (LPCSTR)v22, 1u, 0, 0);
  if ( v12 )
    MemFree(v12);
  if ( v16 )
    MemFree(v16);
  if ( v34 )
    MemFree(v34);
  if ( !*a2 )
    return GetInternetError();
  *(v32 - 1) = 92;
  __wsplitpath_s(v32 - 1, 0, 0, &Dir, 0xFFu, 0, 0, 0, 0);
  if ( Dir )
  {
    v25 = WideCharToMultiByte(0, 0, &Dir, wcslen(&Dir), 0, 0, 0, 0);
    v26 = (CHAR *)MemAllocate(v25 + 1);
    if ( !v26 )
    {
      InternetCloseHandle(*a2);
      return -1011;
    }
    p_Dir = &Dir;
    do
      v28 = *p_Dir++;
    while ( v28 != (_WORD)v35 );
    WideCharToMultiByte(0, 0, &Dir, ((char *)p_Dir - (char *)&v39) >> 1, v26, v25, 0, 0);
    v26[v25] = 0;
    if ( !FtpSetCurrentDirectoryA(*a2, v26) )
    {
      MemFree(v26);
      InternetError = GetInternetError();
      InternetCloseHandle(*a2);
      return InternetError;
    }
    MemFree(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x10022e8a  mov     edi, edi
0x10022e8c  push    ebp
0x10022e8d  mov     ebp, esp
0x10022e8f  sub     esp, 428h
0x10022e95  mov     eax, ___security_cookie
0x10022e9a  xor     eax, ebp
0x10022e9c  mov     [ebp+var_4], eax
0x10022e9f  push    esi
0x10022ea0  mov     [ebp+var_428], edx
0x10022ea6  mov     esi, ecx
0x10022ea8  call    _ProtocolPrefix@4; ProtocolPrefix(x)
0x10022ead  cmp     eax, 1
0x10022eb0  jz      short loc_10022EBC
0x10022eb2  mov     eax, 0FFFFFAE7h
0x10022eb7  jmp     loc_100232B6
0x10022ebc  push    105h
0x10022ec1  lea     edx, [esi+0Ch]
0x10022ec4  lea     ecx, [ebp+var_410]
0x10022eca  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10022ecf  mov     ax, [ebp+var_410]
0x10022ed6  lea     ecx, [ebp+var_410]
0x10022edc  movzx   edx, ax
0x10022edf  push    5Ch ; '\'
0x10022ee1  pop     esi
0x10022ee2  test    dx, dx
0x10022ee5  jz      short loc_10022F04
0x10022ee7  cmp     dx, 2Fh ; '/'
0x10022eeb  jnz     short loc_10022EF0
0x10022eed  mov     [ecx], si
0x10022ef0  add     ecx, 2
0x10022ef3  movzx   eax, word ptr [ecx]
0x10022ef6  mov     edx, eax
0x10022ef8  test    ax, ax
0x10022efb  jnz     short loc_10022EE7
0x10022efd  mov     ax, [ebp+var_410]
0x10022f04  lea     ecx, [ebp+var_410]
0x10022f0a  movzx   eax, ax
0x10022f0d  mov     [ebp+lpWideCharStr], ecx
0x10022f13  push    ebx
0x10022f14  mov     ebx, ecx
0x10022f16  mov     [ebp+var_424], ebx
0x10022f1c  test    ax, ax
0x10022f1f  jz      short loc_10022F4A
0x10022f21  mov     ecx, eax
0x10022f23  lea     eax, [ebx+2]
0x10022f26  cmp     cx, si
0x10022f29  jz      short loc_10022F3F
0x10022f2b  mov     ebx, eax
0x10022f2d  mov     [ebp+var_424], ebx
0x10022f33  movzx   eax, word ptr [ebx]
0x10022f36  mov     ecx, eax
0x10022f38  test    ax, ax
0x10022f3b  jnz     short loc_10022F23
0x10022f3d  jmp     short loc_10022F4A
0x10022f3f  xor     ecx, ecx
0x10022f41  mov     [ebp+var_424], eax
0x10022f47  mov     [ebx], cx
0x10022f4a  lea     eax, [ebp+var_420]
0x10022f50  push    eax
0x10022f51  lea     edx, [ebp+var_41C]
0x10022f57  lea     ecx, [ebp+lpWideCharStr]
0x10022f5d  call    FindUserNamePassword
0x10022f62  mov     esi, [ebp+var_41C]
0x10022f68  xor     eax, eax
0x10022f6a  mov     [ebp+var_418], eax
0x10022f70  test    esi, esi
0x10022f72  jz      short loc_10022F83
0x10022f74  cmp     [esi], ax
0x10022f77  jnz     short loc_10022F83
0x10022f79  mov     eax, 0FFFFB141h
0x10022f7e  jmp     loc_100232B5
0x10022f83  mov     ebx, [ebp+lpWideCharStr]
0x10022f89  push    edi
0x10022f8a  test    ebx, ebx
0x10022f8c  jz      short loc_10023006
0x10022f8e  mov     ecx, ebx
0x10022f90  xor     edi, edi
0x10022f92  lea     edx, [ecx+2]
0x10022f95  mov     ax, [ecx]
0x10022f98  add     ecx, 2
0x10022f9b  cmp     ax, di
0x10022f9e  jnz     short loc_10022F95
0x10022fa0  xor     eax, eax
0x10022fa2  sub     ecx, edx
0x10022fa4  push    eax; lpUsedDefaultChar
0x10022fa5  push    eax; lpDefaultChar
0x10022fa6  push    eax; cbMultiByte
0x10022fa7  push    eax; lpMultiByteStr
0x10022fa8  sar     ecx, 1
0x10022faa  push    ecx; cchWideChar
0x10022fab  push    ebx; lpWideCharStr
0x10022fac  push    eax; dwFlags
0x10022fad  push    eax; CodePage
0x10022fae  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022fb4  mov     [ebp+lpWideCharStr], eax
0x10022fba  lea     ecx, [eax+1]
0x10022fbd  call    _MemAllocate@4; MemAllocate(x)
0x10022fc2  mov     edi, eax
0x10022fc4  test    edi, edi
0x10022fc6  jz      loc_10023235
0x10022fcc  mov     ecx, ebx
0x10022fce  lea     edx, [ecx+2]
0x10022fd1  mov     ax, [ecx]
0x10022fd4  add     ecx, 2
0x10022fd7  cmp     ax, word ptr [ebp+var_418]
0x10022fde  jnz     short loc_10022FD1
0x10022fe0  xor     eax, eax
0x10022fe2  sub     ecx, edx
0x10022fe4  push    eax; lpUsedDefaultChar
0x10022fe5  push    eax; lpDefaultChar
0x10022fe6  push    [ebp+lpWideCharStr]; cbMultiByte
0x10022fec  sar     ecx, 1
0x10022fee  push    edi; lpMultiByteStr
0x10022fef  push    ecx; cchWideChar
0x10022ff0  push    ebx; lpWideCharStr
0x10022ff1  xor     ebx, ebx
0x10022ff3  push    ebx; dwFlags
0x10022ff4  push    ebx; CodePage
0x10022ff5  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022ffb  mov     eax, [ebp+lpWideCharStr]
0x10023001  mov     [edi+eax], bl
0x10023004  jmp     short loc_1002300A
0x10023006  xor     ebx, ebx
0x10023008  mov     edi, ebx
0x1002300a  test    esi, esi
0x1002300c  jz      short loc_1002308D
0x1002300e  mov     ecx, esi
0x10023010  lea     edx, [ecx+2]
0x10023013  mov     ax, [ecx]
0x10023016  add     ecx, 2
0x10023019  cmp     ax, bx
0x1002301c  jnz     short loc_10023013
0x1002301e  push    ebx; lpUsedDefaultChar
0x1002301f  push    ebx; lpDefaultChar
0x10023020  push    ebx; cbMultiByte
0x10023021  push    ebx; lpMultiByteStr
0x10023022  sub     ecx, edx
0x10023024  sar     ecx, 1
0x10023026  push    ecx; cchWideChar
0x10023027  push    esi; lpWideCharStr
0x10023028  push    ebx; dwFlags
0x10023029  push    ebx; CodePage
0x1002302a  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023030  mov     [ebp+lpWideCharStr], eax
0x10023036  lea     ecx, [eax+1]
0x10023039  call    _MemAllocate@4; MemAllocate(x)
0x1002303e  mov     ebx, eax
0x10023040  test    ebx, ebx
0x10023042  jnz     short loc_10023053
0x10023044  test    edi, edi
0x10023046  jz      loc_10023235
0x1002304c  mov     ecx, edi
0x1002304e  jmp     loc_100230F4
0x10023053  mov     ecx, esi
0x10023055  lea     edx, [ecx+2]
0x10023058  mov     ax, [ecx]
0x1002305b  add     ecx, 2
0x1002305e  cmp     ax, word ptr [ebp+var_418]
0x10023065  jnz     short loc_10023058
0x10023067  xor     eax, eax
0x10023069  sub     ecx, edx
0x1002306b  push    eax; lpUsedDefaultChar
0x1002306c  push    eax; lpDefaultChar
0x1002306d  push    [ebp+lpWideCharStr]; cbMultiByte
0x10023073  sar     ecx, 1
0x10023075  push    ebx; lpMultiByteStr
0x10023076  push    ecx; cchWideChar
0x10023077  push    esi; lpWideCharStr
0x10023078  push    eax; dwFlags
0x10023079  push    eax; CodePage
0x1002307a  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023080  mov     eax, [ebp+lpWideCharStr]
0x10023086  xor     ecx, ecx
0x10023088  mov     [ebx+eax], cl
0x1002308b  jmp     short loc_1002308F
0x1002308d  xor     ecx, ecx
0x1002308f  mov     edx, [ebp+var_420]
0x10023095  test    edx, edx
0x10023097  jz      loc_10023141
0x1002309d  mov     ecx, edx
0x1002309f  lea     esi, [ecx+2]
0x100230a2  mov     ax, [ecx]
0x100230a5  add     ecx, 2
0x100230a8  cmp     ax, word ptr [ebp+var_418]
0x100230af  jnz     short loc_100230A2
0x100230b1  xor     eax, eax
0x100230b3  sub     ecx, esi
0x100230b5  push    eax; lpUsedDefaultChar
0x100230b6  push    eax; lpDefaultChar
0x100230b7  push    eax; cbMultiByte
0x100230b8  push    eax; lpMultiByteStr
0x100230b9  sar     ecx, 1
0x100230bb  push    ecx; cchWideChar
0x100230bc  push    edx; lpWideCharStr
0x100230bd  push    eax; dwFlags
0x100230be  push    eax; CodePage
0x100230bf  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100230c5  mov     [ebp+lpWideCharStr], eax
0x100230cb  lea     ecx, [eax+1]
0x100230ce  call    _MemAllocate@4; MemAllocate(x)
0x100230d3  mov     esi, eax
0x100230d5  mov     [ebp+var_41C], esi
0x100230db  test    esi, esi
0x100230dd  jnz     short loc_100230FE
0x100230df  test    edi, edi
0x100230e1  jz      short loc_100230EA
0x100230e3  mov     ecx, edi
0x100230e5  call    _MemFree@4; MemFree(x)
0x100230ea  test    ebx, ebx
0x100230ec  jz      loc_10023235
0x100230f2  mov     ecx, ebx
0x100230f4  call    _MemFree@4; MemFree(x)
0x100230f9  jmp     loc_10023235
0x100230fe  mov     ecx, [ebp+var_420]
0x10023104  lea     edx, [ecx+2]
0x10023107  mov     ax, [ecx]
0x1002310a  add     ecx, 2
0x1002310d  cmp     ax, word ptr [ebp+var_418]
0x10023114  jnz     short loc_10023107
0x10023116  xor     eax, eax
0x10023118  sub     ecx, edx
0x1002311a  push    eax; lpUsedDefaultChar
0x1002311b  push    eax; lpDefaultChar
0x1002311c  push    [ebp+lpWideCharStr]; cbMultiByte
0x10023122  sar     ecx, 1
0x10023124  push    esi; lpMultiByteStr
0x10023125  push    ecx; cchWideChar
0x10023126  push    [ebp+var_420]; lpWideCharStr
0x1002312c  push    eax; dwFlags
0x1002312d  push    eax; CodePage
0x1002312e  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023134  mov     eax, [ebp+lpWideCharStr]
0x1002313a  xor     ecx, ecx
0x1002313c  mov     [esi+eax], cl
0x1002313f  jmp     short loc_10023149
0x10023141  mov     esi, ecx
0x10023143  mov     [ebp+var_41C], ecx
0x10023149  push    ecx
0x1002314a  push    ecx
0x1002314b  push    1
0x1002314d  push    esi
0x1002314e  mov     esi, InternetConnectA
0x10023154  push    ebx
0x10023155  push    ecx
0x10023156  push    edi
0x10023157  push    dword_1003AE18
0x1002315d  mov     ecx, esi
0x1002315f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023165  call    esi ; InternetConnectA
0x10023167  mov     ecx, [ebp+var_428]
0x1002316d  mov     [ecx], eax
0x1002316f  test    edi, edi
0x10023171  jz      short loc_1002317A
0x10023173  mov     ecx, edi
0x10023175  call    _MemFree@4; MemFree(x)
0x1002317a  test    ebx, ebx
0x1002317c  jz      short loc_10023185
0x1002317e  mov     ecx, ebx
0x10023180  call    _MemFree@4; MemFree(x)
0x10023185  mov     ecx, [ebp+var_41C]
0x1002318b  test    ecx, ecx
0x1002318d  jz      short loc_10023194
0x1002318f  call    _MemFree@4; MemFree(x)
0x10023194  mov     ebx, [ebp+var_428]
0x1002319a  xor     edx, edx
0x1002319c  cmp     [ebx], edx
0x1002319e  jnz     short loc_100231AA
0x100231a0  call    GetInternetError
0x100231a5  jmp     loc_100232B4
0x100231aa  mov     eax, [ebp+var_424]
0x100231b0  push    5Ch ; '\'
0x100231b2  pop     ecx
0x100231b3  push    edx; ExtCount
0x100231b4  push    edx; Ext
0x100231b5  push    edx; FilenameCount
0x100231b6  add     eax, 0FFFFFFFEh
0x100231b9  push    edx; Filename
0x100231ba  push    0FFh; DirCount
0x100231bf  mov     [eax], cx
0x100231c2  lea     ecx, [ebp+Dir]
0x100231c8  push    ecx; Dir
0x100231c9  push    edx; DriveCount
0x100231ca  push    edx; Drive
0x100231cb  push    eax; FullPath
0x100231cc  call    ds:__imp___wsplitpath_s
0x100231d2  add     esp, 24h
0x100231d5  cmp     [ebp+Dir], 0
0x100231dd  jz      loc_100232B2
0x100231e3  lea     ecx, [ebp+Dir]
0x100231e9  xor     esi, esi
0x100231eb  lea     edx, [ecx+2]
0x100231ee  mov     ax, [ecx]
0x100231f1  add     ecx, 2
0x100231f4  cmp     ax, si
0x100231f7  jnz     short loc_100231EE
0x100231f9  sub     ecx, edx
0x100231fb  lea     eax, [ebp+Dir]
0x10023201  xor     edx, edx
0x10023203  sar     ecx, 1
0x10023205  push    edx; lpUsedDefaultChar
  ... truncated ...
```
