# DnsCreateDohUrl

- ea: `0x1800634a8`
- end: `0x18006376b`
- name: `DnsCreateDohUrl`
- size: `707`
- prototype: `__int64 __fastcall(STRSAFE_PCNZCH psz, STRSAFE_PCNZCH)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18006b4a4`

## callees

- `0x180008870`
- `0x180008b00`
- `0x18000b130`
- `0x18000c640`
- `0x180046ec0`
- `0x180047818`
- `0x1800634a8`
- `0x180072ae8`
- `0x180072b48`
- `0x180083658`
- `0x180085fb8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006358b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006358b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800636fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800636fd`
- `WINHTTP!WinHttpCreateUrl` at `0x18006368b`
- `WINHTTP!WinHttpCreateUrl` at `0x1800636f3`
- `WINHTTP!WinHttpCreateUrl` at `0x18006368b`
- `WINHTTP!WinHttpCreateUrl` at `0x1800636f3`

## pseudocode

```c
__int64 __fastcall DnsCreateDohUrl(STRSAFE_PCNZCH psz, STRSAFE_PCNZCH a2, INTERNET_PORT a3, WCHAR **a4)
{
  WCHAR *v7; // rdi
  CHAR *v8; // r14
  size_t v9; // rdx
  CHAR *v10; // r15
  DWORD LastError; // ebx
  HRESULT v12; // eax
  DWORD v13; // esi
  const wchar_t *v14; // rax
  wchar_t *v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // eax
  size_t v18; // rdx
  HRESULT v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rax
  __int64 v22; // rdx
  unsigned int v23; // eax
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  WCHAR *v27; // rax
  size_t v30; // [rsp+38h] [rbp-91h] BYREF
  WCHAR **v31; // [rsp+40h] [rbp-89h]
  DWORD v32; // [rsp+48h] [rbp-81h] BYREF
  DWORD pdwUrlLength; // [rsp+4Ch] [rbp-7Dh] BYREF
  size_t pcchLength[2]; // [rsp+50h] [rbp-79h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+60h] [rbp-69h] BYREF

  v31 = a4;
  v7 = 0;
  v8 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  pdwUrlLength = 0;
  v10 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && psz )
  {
    HIDWORD(v30) = 0;
    v32 = 0;
    pcchLength[0] = 0;
    v12 = StringCchLengthA(a2, v9, pcchLength);
    if ( v12 >= 0 )
    {
      v13 = pcchLength[0];
      v32 = pcchLength[0];
    }
    else
    {
      v13 = v32;
      HIDWORD(v30) = 54;
    }
    LastError = WX_WIN32_FROM_HR((unsigned int)v12);
    if ( !LastError )
    {
      v14 = (const wchar_t *)Dns_StringCopyAllocate(a2, v13, 3);
      v8 = (CHAR *)v14;
      if ( !v14 )
      {
LABEL_11:
        LastError = 14;
        goto LABEL_33;
      }
      v15 = wcschr(v14, 0x7Bu);
      if ( v15 )
        *v15 = 0;
      v17 = WxStringCchLengthDWordW(v8, v16, &v32);
      LastError = WX_WIN32_FROM_HR(v17);
      if ( !LastError )
      {
        v30 = 0;
        LODWORD(pcchLength[0]) = 0;
        v19 = StringCchLengthA(psz, v18, &v30);
        if ( v19 >= 0 )
        {
          v20 = v30;
          LODWORD(pcchLength[0]) = v30;
        }
        else
        {
          v20 = pcchLength[0];
          HIDWORD(v30) = 54;
        }
        LastError = WX_WIN32_FROM_HR((unsigned int)v19);
        if ( !LastError )
        {
          v21 = Dns_StringCopyAllocate(psz, v20, 3);
          v10 = (CHAR *)v21;
          if ( !v21 )
            goto LABEL_11;
          v23 = WxStringCchLengthDWordW(v21, v22, pcchLength);
          LastError = WX_WIN32_FROM_HR(v23);
          if ( !LastError )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_sSS(v25, v24, v26, (_DWORD)a2, (__int64)v8, (__int64)v10);
            UrlComponents.nPort = a3;
            UrlComponents.dwHostNameLength = pcchLength[0];
            UrlComponents.dwUrlPathLength = v32;
            UrlComponents.dwStructSize = 104;
            UrlComponents.nScheme = INTERNET_SCHEME_GOPHER;
            UrlComponents.lpszHostName = v10;
            UrlComponents.lpszUrlPath = v8;
            if ( WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength) || (LastError = GetLastError(), LastError == 122) )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_d(1035, 39, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, pdwUrlLength);
              v27 = (WCHAR *)Dns_Allocate(2LL * (pdwUrlLength + 1));
              v7 = v27;
              if ( !v27 )
                goto LABEL_11;
              if ( WinHttpCreateUrl(&UrlComponents, 0, v27, &pdwUrlLength) )
              {
                LastError = 0;
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_S(1035, 40, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, v7);
                *v31 = v7;
                v7 = 0;
              }
              else
              {
                LastError = GetLastError();
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_33:
  MIDL_user_free(v8);
  MIDL_user_free(v7);
  MIDL_user_free(v10);
  return LastError;
}

```

## disassembly

```asm
0x1800634a8  push    rbp
0x1800634aa  push    rbx
0x1800634ab  push    rsi
0x1800634ac  push    rdi
0x1800634ad  push    r12
0x1800634af  push    r13
0x1800634b1  push    r14
0x1800634b3  push    r15
0x1800634b5  lea     rbp, [rsp-1Fh]
0x1800634ba  sub     rsp, 0E8h
0x1800634c1  mov     rax, cs:__security_cookie
0x1800634c8  xor     rax, rsp
0x1800634cb  mov     [rbp+57h+var_50], rax
0x1800634cf  xor     esi, esi
0x1800634d1  mov     [rsp+120h+var_F0], r8w
0x1800634d7  mov     rbx, r9
0x1800634da  mov     r12, rdx
0x1800634dd  mov     r13, rcx
0x1800634e0  mov     [rsp+120h+var_E0], rbx
0x1800634e5  xor     edx, edx; Val
0x1800634e7  lea     rcx, [rbp+57h+UrlComponents]; void *
0x1800634eb  lea     r8d, [rsi+68h]; Size
0x1800634ef  mov     edi, esi
0x1800634f1  mov     r14d, esi
0x1800634f4  call    memset_0
0x1800634f9  mov     [rbp+57h+pdwUrlLength], esi
0x1800634fc  mov     r15d, esi
0x1800634ff  test    rbx, rbx
0x180063502  jz      short loc_180063507
0x180063504  mov     [rbx], rsi
0x180063507  test    r12, r12
0x18006350a  jnz     short loc_180063516
0x18006350c  mov     ebx, 57h ; 'W'
0x180063511  jmp     loc_180063731
0x180063516  test    r13, r13
0x180063519  jz      short loc_18006350C
0x18006351b  mov     dword ptr [rsp+120h+var_E8+4], esi
0x18006351f  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x180063523  mov     rcx, r12; psz
0x180063526  mov     [rsp+120h+var_D8], esi
0x18006352a  mov     [rbp+57h+pcchLength], rsi
0x18006352e  call    StringCchLengthA
0x180063533  test    eax, eax
0x180063535  jns     short loc_180063545
0x180063537  mov     esi, [rsp+120h+var_D8]
0x18006353b  mov     dword ptr [rsp+120h+var_E8+4], 36h ; '6'
0x180063543  jmp     short loc_18006354C
0x180063545  mov     esi, dword ptr [rbp+57h+pcchLength]
0x180063548  mov     [rsp+120h+var_D8], esi
0x18006354c  mov     ecx, eax
0x18006354e  call    WX_WIN32_FROM_HR
0x180063553  mov     ebx, eax
0x180063555  test    eax, eax
0x180063557  jnz     loc_180063731
0x18006355d  lea     r9d, [rax+1]
0x180063561  mov     edx, esi
0x180063563  lea     r8d, [rax+3]
0x180063567  mov     rcx, r12
0x18006356a  call    Dns_StringCopyAllocate
0x18006356f  xor     esi, esi
0x180063571  mov     r14, rax
0x180063574  test    rax, rax
0x180063577  jnz     short loc_180063583
0x180063579  mov     ebx, 0Eh
0x18006357e  jmp     loc_180063731
0x180063583  mov     edx, 7Bh ; '{'; Ch
0x180063588  mov     rcx, r14; Str
0x18006358b  call    cs:__imp_wcschr
0x180063591  test    rax, rax
0x180063594  jz      short loc_180063599
0x180063596  mov     [rax], si
0x180063599  lea     r8, [rsp+120h+var_D8]
0x18006359e  mov     rcx, r14
0x1800635a1  call    WxStringCchLengthDWordW
0x1800635a6  mov     ecx, eax
0x1800635a8  call    WX_WIN32_FROM_HR
0x1800635ad  mov     ebx, eax
0x1800635af  test    eax, eax
0x1800635b1  jnz     loc_180063731
0x1800635b7  mov     dword ptr [rsp+120h+var_E8+4], esi
0x1800635bb  lea     r8, [rsp+120h+var_E8]; pcchLength
0x1800635c0  mov     rcx, r13; psz
0x1800635c3  mov     [rsp+120h+var_E8], rsi
0x1800635c8  mov     dword ptr [rbp+57h+pcchLength], esi
0x1800635cb  call    StringCchLengthA
0x1800635d0  test    eax, eax
0x1800635d2  jns     short loc_1800635E1
0x1800635d4  mov     esi, dword ptr [rbp+57h+pcchLength]
0x1800635d7  mov     dword ptr [rsp+120h+var_E8+4], 36h ; '6'
0x1800635df  jmp     short loc_1800635E8
0x1800635e1  mov     esi, dword ptr [rsp+120h+var_E8]
0x1800635e5  mov     dword ptr [rbp+57h+pcchLength], esi
0x1800635e8  mov     ecx, eax
0x1800635ea  call    WX_WIN32_FROM_HR
0x1800635ef  mov     ebx, eax
0x1800635f1  test    eax, eax
0x1800635f3  jnz     loc_180063731
0x1800635f9  lea     r9d, [rax+1]
0x1800635fd  mov     edx, esi
0x1800635ff  lea     r8d, [rax+3]
0x180063603  mov     rcx, r13
0x180063606  call    Dns_StringCopyAllocate
0x18006360b  mov     r15, rax
0x18006360e  test    rax, rax
0x180063611  jz      loc_180063579
0x180063617  lea     r8, [rbp+57h+pcchLength]
0x18006361b  mov     rcx, rax
0x18006361e  call    WxStringCchLengthDWordW
0x180063623  mov     ecx, eax
0x180063625  call    WX_WIN32_FROM_HR
0x18006362a  mov     ebx, eax
0x18006362c  test    eax, eax
0x18006362e  jnz     loc_180063731
0x180063634  mov     sil, 8
0x180063637  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x18006363e  jz      short loc_180063652
0x180063640  mov     [rsp+120h+var_F8], r15
0x180063645  mov     r9, r12
0x180063648  mov     [rsp+120h+var_100], r14
0x18006364d  call    WPP_SF_sSS
0x180063652  movzx   eax, [rsp+120h+var_F0]
0x180063657  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x18006365b  mov     [rbp+57h+UrlComponents.nPort], ax
0x18006365f  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x180063663  mov     eax, dword ptr [rbp+57h+pcchLength]
0x180063666  xor     r8d, r8d; pwszUrl
0x180063669  mov     [rbp+57h+UrlComponents.dwHostNameLength], eax
0x18006366c  xor     edx, edx; dwFlags
0x18006366e  mov     eax, [rsp+120h+var_D8]
0x180063672  mov     [rbp+57h+UrlComponents.dwUrlPathLength], eax
0x180063675  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x18006367c  mov     [rbp+57h+UrlComponents.nScheme], 2
0x180063683  mov     [rbp+57h+UrlComponents.lpszHostName], r15
0x180063687  mov     [rbp+57h+UrlComponents.lpszUrlPath], r14
0x18006368b  call    cs:__imp_WinHttpCreateUrl
0x180063691  test    eax, eax
0x180063693  jnz     short loc_1800636A6
0x180063695  call    cs:__imp_GetLastError
0x18006369b  mov     ebx, eax
0x18006369d  cmp     eax, 7Ah ; 'z'
0x1800636a0  jnz     loc_180063731
0x1800636a6  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x1800636ad  mov     r12d, 40Bh
0x1800636b3  jz      short loc_1800636CD
0x1800636b5  mov     r9d, [rbp+57h+pdwUrlLength]
0x1800636b9  lea     r8, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x1800636c0  mov     edx, 27h ; '''
0x1800636c5  mov     ecx, r12d
0x1800636c8  call    WPP_SF_d
0x1800636cd  mov     ecx, [rbp+57h+pdwUrlLength]
0x1800636d0  inc     ecx
0x1800636d2  add     rcx, rcx
0x1800636d5  call    Dns_Allocate
0x1800636da  mov     rdi, rax
0x1800636dd  test    rax, rax
0x1800636e0  jz      loc_180063579
0x1800636e6  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x1800636ea  mov     r8, rax; pwszUrl
0x1800636ed  xor     edx, edx; dwFlags
0x1800636ef  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800636f3  call    cs:__imp_WinHttpCreateUrl
0x1800636f9  test    eax, eax
0x1800636fb  jnz     short loc_180063707
0x1800636fd  call    cs:__imp_GetLastError
0x180063703  mov     ebx, eax
0x180063705  jmp     short loc_180063731
0x180063707  xor     ebx, ebx
0x180063709  test    byte ptr cs:xmmword_1800AB5A0+1, sil
0x180063710  jz      short loc_180063727
0x180063712  lea     edx, [rbx+28h]
0x180063715  mov     ecx, r12d
0x180063718  mov     r9, rdi
0x18006371b  lea     r8, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x180063722  call    WPP_SF_S
0x180063727  mov     rax, [rsp+120h+var_E0]
0x18006372c  mov     [rax], rdi
0x18006372f  xor     edi, edi
0x180063731  mov     rcx, r14; void *
0x180063734  call    MIDL_user_free
0x180063739  mov     rcx, rdi; void *
0x18006373c  call    MIDL_user_free
0x180063741  mov     rcx, r15; void *
0x180063744  call    MIDL_user_free
0x180063749  mov     eax, ebx
0x18006374b  mov     rcx, [rbp+57h+var_50]
0x18006374f  xor     rcx, rsp; StackCookie
0x180063752  call    __security_check_cookie
0x180063757  add     rsp, 0E8h
0x18006375e  pop     r15
0x180063760  pop     r14
0x180063762  pop     r13
0x180063764  pop     r12
0x180063766  pop     rdi
0x180063767  pop     rsi
0x180063768  pop     rbx
0x180063769  pop     rbp
0x18006376a  retn
```
