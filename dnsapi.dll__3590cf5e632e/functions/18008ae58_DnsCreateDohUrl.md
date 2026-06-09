# DnsCreateDohUrl

- ea: `0x18008ae58`
- end: `0x18008b18c`
- name: `DnsCreateDohUrl`
- size: `820`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18008adb0`
- `0x1800bf2fc`

## callees

- `0x180011d40`
- `0x180029d80`
- `0x18002b050`
- `0x18003de30`
- `0x1800639a8`
- `0x18008ae58`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800ca8ec`
- `0x1800d9d20`
- `0x1800dbfe0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18008af3f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18008af3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b119`
- `WINHTTP!WinHttpCreateUrl` at `0x18008b097`
- `WINHTTP!WinHttpCreateUrl` at `0x18008b109`
- `WINHTTP!WinHttpCreateUrl` at `0x18008b097`
- `WINHTTP!WinHttpCreateUrl` at `0x18008b109`

## pseudocode

```c
__int64 __fastcall DnsCreateDohUrl(const char *a1, const char *a2, INTERNET_PORT a3, WCHAR **a4)
{
  WCHAR *v7; // rdi
  wchar_t *v8; // r14
  size_t v9; // rdx
  CHAR *v10; // r12
  DWORD LastError; // ebx
  HRESULT v12; // eax
  unsigned int v13; // esi
  const wchar_t *v14; // rax
  wchar_t *v15; // rax
  HRESULT v16; // eax
  DWORD v17; // r13d
  size_t v18; // rdx
  HRESULT v19; // eax
  unsigned int v20; // esi
  const wchar_t *v21; // rax
  HRESULT v22; // eax
  DWORD v23; // esi
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  WCHAR *v27; // rax
  size_t pcchLength; // [rsp+38h] [rbp-91h] BYREF
  INTERNET_PORT v30; // [rsp+40h] [rbp-89h]
  STRSAFE_PCNZCH psz; // [rsp+48h] [rbp-81h] BYREF
  WCHAR **v32; // [rsp+50h] [rbp-79h]
  DWORD pdwUrlLength; // [rsp+58h] [rbp-71h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+60h] [rbp-69h] BYREF

  v30 = a3;
  psz = a1;
  v32 = a4;
  v7 = 0;
  v8 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  pdwUrlLength = 0;
  v10 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && a1 )
  {
    pcchLength = 0;
    v12 = StringCchLengthA(a2, v9, &pcchLength);
    if ( v12 >= 0 )
    {
      v13 = pcchLength;
    }
    else
    {
      HIDWORD(pcchLength) = 54;
      v13 = 0;
    }
    LastError = WX_WIN32_FROM_HR((unsigned int)v12);
    if ( !LastError )
    {
      v14 = (const wchar_t *)Dns_StringCopyAllocate(a2, v13, 3, 1);
      v8 = (wchar_t *)v14;
      if ( !v14 )
      {
LABEL_11:
        LastError = 14;
        goto LABEL_39;
      }
      v15 = wcschr(v14, 0x7Bu);
      if ( v15 )
        *v15 = 0;
      pcchLength = 0;
      v16 = StringCchLengthW(v8, 0x7FFFFFFFu, &pcchLength);
      if ( v16 >= 0 )
      {
        v17 = pcchLength;
      }
      else
      {
        HIDWORD(pcchLength) = 81;
        v17 = 0;
      }
      LastError = WX_WIN32_FROM_HR((unsigned int)v16);
      if ( !LastError )
      {
        pcchLength = 0;
        v19 = StringCchLengthA(psz, v18, &pcchLength);
        if ( v19 >= 0 )
        {
          v20 = pcchLength;
        }
        else
        {
          HIDWORD(pcchLength) = 54;
          v20 = 0;
        }
        LastError = WX_WIN32_FROM_HR((unsigned int)v19);
        if ( !LastError )
        {
          v21 = (const wchar_t *)Dns_StringCopyAllocate(psz, v20, 3, 1);
          v10 = (CHAR *)v21;
          if ( !v21 )
            goto LABEL_11;
          psz = 0;
          v22 = StringCchLengthW(v21, 0x7FFFFFFFu, (size_t *)&psz);
          if ( v22 >= 0 )
          {
            v23 = (unsigned int)psz;
          }
          else
          {
            HIDWORD(psz) = 81;
            v23 = 0;
          }
          LastError = WX_WIN32_FROM_HR((unsigned int)v22);
          if ( !LastError )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_sSS(v25, v24, v26, (_DWORD)a2, (__int64)v8, (__int64)v10);
            UrlComponents.nPort = v30;
            UrlComponents.dwStructSize = 104;
            UrlComponents.nScheme = INTERNET_SCHEME_GOPHER;
            UrlComponents.lpszHostName = v10;
            UrlComponents.dwHostNameLength = v23;
            UrlComponents.lpszUrlPath = (LPSTR)v8;
            UrlComponents.dwUrlPathLength = v17;
            if ( WinHttpCreateUrl(&UrlComponents, 0, 0, &pdwUrlLength) || (LastError = GetLastError(), LastError == 122) )
            {
              if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                WPP_SF_d(1035, 39, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, pdwUrlLength);
              v27 = (WCHAR *)Dns_Allocate(2LL * (pdwUrlLength + 1));
              v7 = v27;
              if ( !v27 )
                goto LABEL_11;
              if ( WinHttpCreateUrl(&UrlComponents, 0, v27, &pdwUrlLength) )
              {
                LastError = 0;
                if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
                  WPP_SF_S(1035, 40, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, v7);
                *v32 = v7;
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
LABEL_39:
  DnsApiFree(v8);
  DnsApiFree(v7);
  DnsApiFree(v10);
  return LastError;
}

```

## disassembly

```asm
0x18008ae58  push    rbp
0x18008ae5a  push    rbx
0x18008ae5b  push    rsi
0x18008ae5c  push    rdi
0x18008ae5d  push    r12
0x18008ae5f  push    r13
0x18008ae61  push    r14
0x18008ae63  push    r15
0x18008ae65  lea     rbp, [rsp-1Fh]
0x18008ae6a  sub     rsp, 0E8h
0x18008ae71  mov     rax, cs:__security_cookie
0x18008ae78  xor     rax, rsp
0x18008ae7b  mov     [rbp+57h+var_50], rax
0x18008ae7f  xor     r13d, r13d
0x18008ae82  mov     [rsp+120h+var_E0], r8w
0x18008ae88  mov     r15, rdx
0x18008ae8b  mov     [rsp+120h+psz], rcx
0x18008ae90  mov     rbx, rcx
0x18008ae93  mov     [rbp+57h+var_D0], r9
0x18008ae97  xor     edx, edx; Val
0x18008ae99  lea     rcx, [rbp+57h+UrlComponents]; void *
0x18008ae9d  lea     r8d, [r13+68h]; Size
0x18008aea1  mov     rsi, r9
0x18008aea4  mov     edi, r13d
0x18008aea7  mov     r14d, r13d
0x18008aeaa  call    memset_0
0x18008aeaf  mov     [rbp+57h+pdwUrlLength], r13d
0x18008aeb3  mov     r12d, r13d
0x18008aeb6  test    rsi, rsi
0x18008aeb9  jz      short loc_18008AEBE
0x18008aebb  mov     [rsi], r13
0x18008aebe  test    r15, r15
0x18008aec1  jnz     short loc_18008AECD
0x18008aec3  mov     ebx, 57h ; 'W'
0x18008aec8  jmp     loc_18008B151
0x18008aecd  test    rbx, rbx
0x18008aed0  jz      short loc_18008AEC3
0x18008aed2  mov     dword ptr [rsp+120h+pcchLength+4], r13d
0x18008aed7  lea     r8, [rsp+120h+pcchLength]; pcchLength
0x18008aedc  mov     rcx, r15; psz
0x18008aedf  mov     [rsp+120h+pcchLength], r13
0x18008aee4  mov     [rsp+120h+var_F0], r13d
0x18008aee9  call    StringCchLengthA
0x18008aeee  test    eax, eax
0x18008aef0  jns     short loc_18008AEFE
0x18008aef2  mov     dword ptr [rsp+120h+pcchLength+4], 36h ; '6'
0x18008aefa  mov     esi, edi
0x18008aefc  jmp     short loc_18008AF02
0x18008aefe  mov     esi, dword ptr [rsp+120h+pcchLength]
0x18008af02  mov     ecx, eax
0x18008af04  call    WX_WIN32_FROM_HR
0x18008af09  mov     ebx, eax
0x18008af0b  test    eax, eax
0x18008af0d  jnz     loc_18008B151
0x18008af13  lea     r9d, [rax+1]
0x18008af17  mov     edx, esi
0x18008af19  lea     r8d, [rax+3]
0x18008af1d  mov     rcx, r15
0x18008af20  call    Dns_StringCopyAllocate
0x18008af25  mov     r14, rax
0x18008af28  test    rax, rax
0x18008af2b  jnz     short loc_18008AF37
0x18008af2d  mov     ebx, 0Eh
0x18008af32  jmp     loc_18008B151
0x18008af37  mov     edx, 7Bh ; '{'; Ch
0x18008af3c  mov     rcx, r14; Str
0x18008af3f  call    cs:__imp_wcschr
0x18008af46  nop     dword ptr [rax+rax+00h]
0x18008af4b  test    rax, rax
0x18008af4e  jz      short loc_18008AF54
0x18008af50  mov     [rax], r13w
0x18008af54  mov     dword ptr [rsp+120h+pcchLength+4], r13d
0x18008af59  lea     r8, [rsp+120h+pcchLength]; pcchLength
0x18008af5e  mov     edx, 7FFFFFFFh; cchMax
0x18008af63  mov     [rsp+120h+pcchLength], r13
0x18008af68  mov     rcx, r14; psz
0x18008af6b  mov     [rsp+120h+var_F0], r13d
0x18008af70  call    StringCchLengthW
0x18008af75  test    eax, eax
0x18008af77  jns     short loc_18008AF86
0x18008af79  mov     dword ptr [rsp+120h+pcchLength+4], 51h ; 'Q'
0x18008af81  mov     r13d, edi
0x18008af84  jmp     short loc_18008AF8B
0x18008af86  mov     r13d, dword ptr [rsp+120h+pcchLength]
0x18008af8b  mov     ecx, eax
0x18008af8d  call    WX_WIN32_FROM_HR
0x18008af92  xor     r11d, r11d
0x18008af95  mov     ebx, eax
0x18008af97  test    eax, eax
0x18008af99  jnz     loc_18008B151
0x18008af9f  mov     rcx, [rsp+120h+psz]; psz
0x18008afa4  lea     r8, [rsp+120h+pcchLength]; pcchLength
0x18008afa9  mov     dword ptr [rsp+120h+pcchLength+4], r11d
0x18008afae  mov     [rsp+120h+pcchLength], r11
0x18008afb3  mov     [rsp+120h+var_F0], r11d
0x18008afb8  call    StringCchLengthA
0x18008afbd  test    eax, eax
0x18008afbf  jns     short loc_18008AFCD
0x18008afc1  mov     dword ptr [rsp+120h+pcchLength+4], 36h ; '6'
0x18008afc9  mov     esi, edi
0x18008afcb  jmp     short loc_18008AFD1
0x18008afcd  mov     esi, dword ptr [rsp+120h+pcchLength]
0x18008afd1  mov     ecx, eax
0x18008afd3  call    WX_WIN32_FROM_HR
0x18008afd8  mov     ebx, eax
0x18008afda  test    eax, eax
0x18008afdc  jnz     loc_18008B151
0x18008afe2  mov     rcx, [rsp+120h+psz]
0x18008afe7  lea     r9d, [rax+1]
0x18008afeb  lea     r8d, [rax+3]
0x18008afef  mov     edx, esi
0x18008aff1  call    Dns_StringCopyAllocate
0x18008aff6  xor     r11d, r11d
0x18008aff9  mov     r12, rax
0x18008affc  test    rax, rax
0x18008afff  jz      loc_18008AF2D
0x18008b005  mov     dword ptr [rbp+57h+psz+4], r11d
0x18008b009  lea     r8, [rsp+120h+psz]; pcchLength
0x18008b00e  mov     edx, 7FFFFFFFh; cchMax
0x18008b013  mov     [rsp+120h+psz], r11
0x18008b018  mov     rcx, rax; psz
0x18008b01b  mov     [rsp+120h+var_F0], r11d
0x18008b020  call    StringCchLengthW
0x18008b025  test    eax, eax
0x18008b027  jns     short loc_18008B034
0x18008b029  mov     dword ptr [rbp+57h+psz+4], 51h ; 'Q'
0x18008b030  mov     esi, edi
0x18008b032  jmp     short loc_18008B038
0x18008b034  mov     esi, dword ptr [rsp+120h+psz]
0x18008b038  mov     ecx, eax
0x18008b03a  call    WX_WIN32_FROM_HR
0x18008b03f  mov     ebx, eax
0x18008b041  test    eax, eax
0x18008b043  jnz     loc_18008B151
0x18008b049  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008b050  jz      short loc_18008B064
0x18008b052  mov     [rsp+120h+var_F8], r12
0x18008b057  mov     r9, r15
0x18008b05a  mov     [rsp+120h+var_100], r14
0x18008b05f  call    WPP_SF_sSS
0x18008b064  movzx   eax, [rsp+120h+var_E0]
0x18008b069  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x18008b06d  xor     r8d, r8d; pwszUrl
0x18008b070  mov     [rbp+57h+UrlComponents.nPort], ax
0x18008b074  xor     edx, edx; dwFlags
0x18008b076  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x18008b07d  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x18008b081  mov     [rbp+57h+UrlComponents.nScheme], 2
0x18008b088  mov     [rbp+57h+UrlComponents.lpszHostName], r12
0x18008b08c  mov     [rbp+57h+UrlComponents.dwHostNameLength], esi
0x18008b08f  mov     [rbp+57h+UrlComponents.lpszUrlPath], r14
0x18008b093  mov     [rbp+57h+UrlComponents.dwUrlPathLength], r13d
0x18008b097  call    cs:__imp_WinHttpCreateUrl
0x18008b09e  nop     dword ptr [rax+rax+00h]
0x18008b0a3  test    eax, eax
0x18008b0a5  jnz     short loc_18008B0BE
0x18008b0a7  call    cs:__imp_GetLastError
0x18008b0ae  nop     dword ptr [rax+rax+00h]
0x18008b0b3  mov     ebx, eax
0x18008b0b5  cmp     eax, 7Ah ; 'z'
0x18008b0b8  jnz     loc_18008B151
0x18008b0be  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008b0c5  mov     esi, 40Bh
0x18008b0ca  jz      short loc_18008B0E3
0x18008b0cc  mov     r9d, [rbp+57h+pdwUrlLength]
0x18008b0d0  lea     r8, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x18008b0d7  mov     edx, 27h ; '''
0x18008b0dc  mov     ecx, esi
0x18008b0de  call    WPP_SF_d
0x18008b0e3  mov     ecx, [rbp+57h+pdwUrlLength]
0x18008b0e6  inc     ecx
0x18008b0e8  add     rcx, rcx
0x18008b0eb  call    Dns_Allocate
0x18008b0f0  mov     rdi, rax
0x18008b0f3  test    rax, rax
0x18008b0f6  jz      loc_18008AF2D
0x18008b0fc  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x18008b100  mov     r8, rax; pwszUrl
0x18008b103  xor     edx, edx; dwFlags
0x18008b105  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x18008b109  call    cs:__imp_WinHttpCreateUrl
0x18008b110  nop     dword ptr [rax+rax+00h]
0x18008b115  test    eax, eax
0x18008b117  jnz     short loc_18008B129
0x18008b119  call    cs:__imp_GetLastError
0x18008b120  nop     dword ptr [rax+rax+00h]
0x18008b125  mov     ebx, eax
0x18008b127  jmp     short loc_18008B151
0x18008b129  xor     ebx, ebx
0x18008b12b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18008b132  jz      short loc_18008B148
0x18008b134  lea     edx, [rbx+28h]
0x18008b137  mov     ecx, esi
0x18008b139  mov     r9, rdi
0x18008b13c  lea     r8, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x18008b143  call    WPP_SF_S
0x18008b148  mov     rax, [rbp+57h+var_D0]
0x18008b14c  mov     [rax], rdi
0x18008b14f  xor     edi, edi
0x18008b151  mov     rcx, r14; lpMem
0x18008b154  call    DnsApiFree
0x18008b159  mov     rcx, rdi; lpMem
0x18008b15c  call    DnsApiFree
0x18008b161  mov     rcx, r12; lpMem
0x18008b164  call    DnsApiFree
0x18008b169  mov     eax, ebx
0x18008b16b  mov     rcx, [rbp+57h+var_50]
0x18008b16f  xor     rcx, rsp; StackCookie
0x18008b172  call    __security_check_cookie
0x18008b177  add     rsp, 0E8h
0x18008b17e  pop     r15
0x18008b180  pop     r14
0x18008b182  pop     r13
0x18008b184  pop     r12
0x18008b186  pop     rdi
0x18008b187  pop     rsi
0x18008b188  pop     rbx
0x18008b189  pop     rbp
0x18008b18a  retn
```
