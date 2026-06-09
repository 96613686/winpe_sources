# DOSUniquePathname(x,x,x,x,x)

- ea: `0x1000bab0`
- end: `0x1000bd7d`
- name: `_DOSUniquePathname@20`
- size: `717`
- prototype: `int __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR, int, STRSAFE_LPCWSTR)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000d130`
- `0x10011d90`

## callees

- `0x1000ad60`
- `0x1000ae20`
- `0x1000bab0`
- `0x1000bdb0`
- `0x1000d7a0`
- `0x1000e350`
- `0x1002ad40`
- `0x1002b81a`
- `0x1002ba60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000bd25`
- `KERNEL32!GetLastError` at `0x1000bd25`

## pseudocode

```c
int __stdcall DOSUniquePathname(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        STRSAFE_LPCWSTR a3,
        void *a4,
        STRSAFE_LPCWSTR a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // esi
  int v8; // ecx
  unsigned int v9; // edx
  wchar_t *v10; // esi
  unsigned int v11; // ecx
  wchar_t *v12; // esi
  wchar_t v13; // ax
  int v14; // edx
  wchar_t *v15; // eax
  wchar_t v16; // cx
  void *v17; // esi
  wchar_t *v18; // eax
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  wchar_t *v22; // eax
  int v23; // edx
  int result; // eax
  __int16 v25; // [esp+10h] [ebp-44h]
  void *Src; // [esp+18h] [ebp-3Ch]
  wchar_t pszSrc[16]; // [esp+1Ch] [ebp-38h] BYREF
  wchar_t v28[8]; // [esp+3Ch] [ebp-18h] BYREF
  _BYTE v29[4]; // [esp+4Ch] [ebp-8h] BYREF

  Src = a4;
  v25 = 0;
  if ( a3 )
  {
    if ( *a3 )
    {
      v5 = a3[wcslen(a3) - 1];
      if ( v5 != 92 && v5 != 58 )
        v25 = 92;
    }
  }
  v6 = 0;
  v7 = (char *)L"00000000" - (char *)v28;
  while ( 1 )
  {
    v8 = 0;
    v9 = v6;
    if ( v6 )
    {
      do
      {
        ++v8;
        v9 /= 0xAu;
      }
      while ( v9 );
      if ( v8 < 16 )
      {
        v10 = &pszSrc[v8];
        v11 = v6;
        *v10 = 0;
        v12 = v10 - 1;
        do
        {
          --v12;
          v13 = byte_10001130[v11 % 0xA];
          v11 /= 0xAu;
          v12[1] = v13;
        }
        while ( v11 );
        v7 = (char *)L"00000000" - (char *)v28;
      }
    }
    else
    {
      wcscpy(pszSrc, L"0");
    }
    v14 = 9;
    v15 = v28;
    while ( v14 != -2147483637 )
    {
      v16 = *(wchar_t *)((char *)v15 + v7);
      if ( !v16 )
        break;
      *v15++ = v16;
      if ( !--v14 )
      {
        --v15;
        break;
      }
    }
    v17 = Src;
    *v15 = 0;
    memcpy(v28, v17, 2 * wcslen((const unsigned __int16 *)v17));
    v18 = pszSrc;
    v19 = 16;
    while ( *v18 )
    {
      ++v18;
      if ( !--v19 )
      {
        v20 = 0;
        goto LABEL_23;
      }
    }
    v20 = 16 - v19;
LABEL_23:
    if ( (unsigned int)(8 - v20) < 9 )
    {
      v21 = 16;
      v22 = pszSrc;
      while ( *v22 )
      {
        ++v22;
        if ( !--v21 )
        {
          v23 = 0;
          goto LABEL_28;
        }
      }
      v23 = 16 - v21;
LABEL_28:
      StringCchCopyW((STRSAFE_LPWSTR)&v29[-2 * wcslen(pszSrc)], v23 + 1, pszSrc);
    }
    *pszDest = 0;
    if ( a3 )
    {
      if ( *a3 )
      {
        StringCchCopyW(pszDest, cchDest, a3);
        if ( v25 )
          StringCchCatW(pszDest, cchDest, L"\\");
      }
    }
    StringCchCatW(pszDest, cchDest, v28);
    StringCchCatW(pszDest, cchDest, a5);
    if ( NetProtocolType(pszDest) )
    {
      result = NetFileExists(pszDest);
      goto LABEL_40;
    }
    if ( JetGetFileAttributesW(pszDest) == -1 )
      break;
    result = 0;
LABEL_41:
    v7 = (char *)L"00000000" - (char *)v28;
    if ( ++v6 >= 0xFFFF )
      return result;
  }
  result = -(unsigned __int16)GetLastError();
LABEL_40:
  if ( !result )
    goto LABEL_41;
  if ( result == -2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1000bab0  sub     esp, 44h
0x1000bab3  mov     eax, ___security_cookie
0x1000bab8  xor     eax, esp
0x1000baba  mov     [esp+44h+var_4], eax
0x1000babe  mov     eax, [esp+44h+arg_C]
0x1000bac2  push    ebx
0x1000bac3  push    ebp
0x1000bac4  mov     ebp, [esp+4Ch+arg_8]
0x1000bac8  mov     [esp+4Ch+Src], eax
0x1000bacc  mov     [esp+4Ch+var_44], 0
0x1000bad4  push    esi
0x1000bad5  push    edi
0x1000bad6  mov     edi, [esp+54h+pszDest]
0x1000bada  test    ebp, ebp
0x1000badc  jz      short loc_1000BB18
0x1000bade  cmp     word ptr [ebp+0], 0
0x1000bae3  jz      short loc_1000BB18
0x1000bae5  mov     ecx, ebp
0x1000bae7  lea     edx, [ecx+2]
0x1000baea  lea     ebx, [ebx+0]
0x1000baf0  mov     ax, [ecx]
0x1000baf3  add     ecx, 2
0x1000baf6  test    ax, ax
0x1000baf9  jnz     short loc_1000BAF0
0x1000bafb  sub     ecx, edx
0x1000bafd  sar     ecx, 1
0x1000baff  movzx   eax, word ptr [ebp+ecx*2-2]
0x1000bb04  cmp     eax, 5Ch ; '\'
0x1000bb07  jz      short loc_1000BB18
0x1000bb09  cmp     eax, 3Ah ; ':'
0x1000bb0c  jz      short loc_1000BB18
0x1000bb0e  mov     eax, 5Ch ; '\'
0x1000bb13  mov     word ptr [esp+54h+var_44], ax
0x1000bb18  xor     ebx, ebx
0x1000bb1a  lea     eax, [esp+54h+var_18]
0x1000bb1e  mov     esi, offset a00000000; "00000000"
0x1000bb23  sub     esi, eax
0x1000bb25  mov     [esp+54h+var_40], esi
0x1000bb29  lea     ecx, [ebx+2Dh]
0x1000bb2c  lea     esp, [esp+0]
0x1000bb30  test    ebx, ebx
0x1000bb32  jns     short loc_1000BB4E
0x1000bb34  push    0Ah
0x1000bb36  mov     eax, ebx
0x1000bb38  mov     [esp+58h+pszSrc], cx
0x1000bb3d  neg     eax
0x1000bb3f  push    eax
0x1000bb40  push    0Fh
0x1000bb42  lea     eax, [esp+60h+pszSrc+2]
0x1000bb46  push    eax
0x1000bb47  call    _DecodeUintW@16; DecodeUintW(x,x,x,x)
0x1000bb4c  jmp     short loc_1000BBAF
0x1000bb4e  xor     ecx, ecx
0x1000bb50  mov     edx, ebx
0x1000bb52  test    ebx, ebx
0x1000bb54  jnz     short loc_1000BB60
0x1000bb56  mov     dword ptr [esp+54h+pszSrc], 30h ; '0'
0x1000bb5e  jmp     short loc_1000BBAF
0x1000bb60  mov     eax, 0CCCCCCCDh
0x1000bb65  inc     ecx
0x1000bb66  mul     edx
0x1000bb68  shr     edx, 3
0x1000bb6b  test    edx, edx
0x1000bb6d  jnz     short loc_1000BB60
0x1000bb6f  cmp     ecx, 10h
0x1000bb72  jge     short loc_1000BBAF
0x1000bb74  lea     esi, [esp+54h+pszSrc]
0x1000bb78  xor     eax, eax
0x1000bb7a  lea     esi, [esi+ecx*2]
0x1000bb7d  mov     ecx, ebx
0x1000bb7f  mov     [esi], ax
0x1000bb82  sub     esi, 2
0x1000bb85  mov     eax, 0CCCCCCCDh
0x1000bb8a  lea     esi, [esi-2]
0x1000bb8d  mul     ecx
0x1000bb8f  shr     edx, 3
0x1000bb92  lea     eax, [edx+edx*4]
0x1000bb95  add     eax, eax
0x1000bb97  sub     ecx, eax
0x1000bb99  movsx   ax, ds:byte_10001130[ecx]
0x1000bba1  mov     ecx, edx
0x1000bba3  mov     [esi+2], ax
0x1000bba7  test    ecx, ecx
0x1000bba9  jnz     short loc_1000BB85
0x1000bbab  mov     esi, [esp+54h+var_40]
0x1000bbaf  mov     edx, 9
0x1000bbb4  lea     eax, [esp+54h+var_18]
0x1000bbb8  jmp     short loc_1000BBC0
0x1000bbc0  lea     ecx, [edx+7FFFFFF5h]
0x1000bbc6  test    ecx, ecx
0x1000bbc8  jz      short loc_1000BBDE
0x1000bbca  movzx   ecx, word ptr [esi+eax]
0x1000bbce  test    cx, cx
0x1000bbd1  jz      short loc_1000BBDE
0x1000bbd3  mov     [eax], cx
0x1000bbd6  add     eax, 2
0x1000bbd9  dec     edx
0x1000bbda  jnz     short loc_1000BBC0
0x1000bbdc  jmp     short loc_1000BBE2
0x1000bbde  test    edx, edx
0x1000bbe0  jnz     short loc_1000BBE5
0x1000bbe2  sub     eax, 2
0x1000bbe5  mov     esi, [esp+54h+Src]
0x1000bbe9  xor     ecx, ecx
0x1000bbeb  mov     [eax], cx
0x1000bbee  mov     ecx, esi
0x1000bbf0  lea     edx, [ecx+2]
0x1000bbf3  mov     ax, [ecx]
0x1000bbf6  add     ecx, 2
0x1000bbf9  test    ax, ax
0x1000bbfc  jnz     short loc_1000BBF3
0x1000bbfe  sub     ecx, edx
0x1000bc00  sar     ecx, 1
0x1000bc02  lea     eax, [ecx+ecx]
0x1000bc05  push    eax; Size
0x1000bc06  lea     eax, [esp+58h+var_18]
0x1000bc0a  push    esi; Src
0x1000bc0b  push    eax; void *
0x1000bc0c  call    _memcpy
0x1000bc11  add     esp, 0Ch
0x1000bc14  lea     eax, [esp+54h+pszSrc]
0x1000bc18  mov     ecx, 10h
0x1000bc1d  lea     ecx, [ecx+0]
0x1000bc20  cmp     word ptr [eax], 0
0x1000bc24  jz      loc_1000BCEF
0x1000bc2a  add     eax, 2
0x1000bc2d  dec     ecx
0x1000bc2e  jnz     short loc_1000BC20
0x1000bc30  xor     edx, edx
0x1000bc32  mov     eax, 8
0x1000bc37  sub     eax, edx
0x1000bc39  cmp     eax, 9
0x1000bc3c  jnb     short loc_1000BC97
0x1000bc3e  mov     ecx, 10h
0x1000bc43  lea     eax, [esp+54h+pszSrc]
0x1000bc47  jmp     short loc_1000BC50
0x1000bc50  cmp     word ptr [eax], 0
0x1000bc54  jz      loc_1000BD03
0x1000bc5a  add     eax, 2
0x1000bc5d  dec     ecx
0x1000bc5e  jnz     short loc_1000BC50
0x1000bc60  xor     edx, edx
0x1000bc62  lea     ecx, [esp+54h+pszSrc]
0x1000bc66  lea     esi, [ecx+2]
0x1000bc69  lea     esp, [esp+0]
0x1000bc70  mov     ax, [ecx]
0x1000bc73  add     ecx, 2
0x1000bc76  test    ax, ax
0x1000bc79  jnz     short loc_1000BC70
0x1000bc7b  sub     ecx, esi
0x1000bc7d  lea     eax, [esp+54h+pszSrc]
0x1000bc81  sar     ecx, 1
0x1000bc83  push    eax; pszSrc
0x1000bc84  lea     eax, [edx+1]
0x1000bc87  push    eax; cchDest
0x1000bc88  lea     eax, [ecx+ecx]
0x1000bc8b  lea     ecx, [esp+5Ch+var_8]
0x1000bc8f  sub     ecx, eax
0x1000bc91  push    ecx; pszDest
0x1000bc92  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000bc97  mov     esi, [esp+54h+cchDest]
0x1000bc9b  xor     eax, eax
0x1000bc9d  mov     [edi], ax
0x1000bca0  test    ebp, ebp
0x1000bca2  jz      short loc_1000BCC6
0x1000bca4  cmp     [ebp+0], ax
0x1000bca8  jz      short loc_1000BCC6
0x1000bcaa  push    ebp; pszSrc
0x1000bcab  push    esi; cchDest
0x1000bcac  push    edi; pszDest
0x1000bcad  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000bcb2  cmp     word ptr [esp+54h+var_44], 0
0x1000bcb8  jz      short loc_1000BCC6
0x1000bcba  push    offset asc_10001120; "\\"
0x1000bcbf  push    esi; cchDest
0x1000bcc0  push    edi; pszDest
0x1000bcc1  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000bcc6  lea     eax, [esp+54h+var_18]
0x1000bcca  push    eax; pszSrc
0x1000bccb  push    esi; cchDest
0x1000bccc  push    edi; pszDest
0x1000bccd  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000bcd2  push    [esp+54h+arg_10]; pszSrc
0x1000bcd6  push    esi; cchDest
0x1000bcd7  push    edi; pszDest
0x1000bcd8  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000bcdd  push    edi
0x1000bcde  call    _NetProtocolType@4; NetProtocolType(x)
0x1000bce3  push    edi; lpFileName
0x1000bce4  test    eax, eax
0x1000bce6  jz      short loc_1000BD17
0x1000bce8  call    _NetFileExists@4; NetFileExists(x)
0x1000bced  jmp     short loc_1000BD32
0x1000bcef  test    ecx, ecx
0x1000bcf1  jz      loc_1000BC30
0x1000bcf7  mov     edx, 10h
0x1000bcfc  sub     edx, ecx
0x1000bcfe  jmp     loc_1000BC32
0x1000bd03  test    ecx, ecx
0x1000bd05  jz      loc_1000BC60
0x1000bd0b  mov     edx, 10h
0x1000bd10  sub     edx, ecx
0x1000bd12  jmp     loc_1000BC62
0x1000bd17  call    _JetGetFileAttributesW@4; JetGetFileAttributesW(x)
0x1000bd1c  cmp     eax, 0FFFFFFFFh
0x1000bd1f  jz      short loc_1000BD25
0x1000bd21  xor     eax, eax
0x1000bd23  jmp     short loc_1000BD36
0x1000bd25  call    ds:__imp__GetLastError@0; GetLastError()
0x1000bd2b  and     eax, 0FFFFh
0x1000bd30  neg     eax
0x1000bd32  test    eax, eax
0x1000bd34  jnz     short loc_1000BD61
0x1000bd36  mov     esi, [esp+54h+var_40]
0x1000bd3a  inc     ebx
0x1000bd3b  mov     ecx, 2Dh ; '-'
0x1000bd40  cmp     ebx, 0FFFFh
0x1000bd46  jb      loc_1000BB30
0x1000bd4c  pop     edi
0x1000bd4d  pop     esi
0x1000bd4e  pop     ebp
0x1000bd4f  pop     ebx
0x1000bd50  mov     ecx, [esp+44h+var_4]
0x1000bd54  xor     ecx, esp; StackCookie
0x1000bd56  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000bd5b  add     esp, 44h
0x1000bd5e  retn    14h
0x1000bd61  cmp     eax, 0FFFFFFFEh
0x1000bd64  jnz     short loc_1000BD68
0x1000bd66  xor     eax, eax
0x1000bd68  mov     ecx, [esp+54h+var_4]
0x1000bd6c  pop     edi
0x1000bd6d  pop     esi
0x1000bd6e  pop     ebp
0x1000bd6f  pop     ebx
0x1000bd70  xor     ecx, esp; StackCookie
0x1000bd72  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000bd77  add     esp, 44h
0x1000bd7a  retn    14h
```
