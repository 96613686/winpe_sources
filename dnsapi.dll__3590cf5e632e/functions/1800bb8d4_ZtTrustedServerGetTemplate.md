# ZtTrustedServerGetTemplate

- ea: `0x1800bb8d4`
- end: `0x1800bba5a`
- name: `ZtTrustedServerGetTemplate`
- size: `390`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b2f9c`
- `0x1800b3274`

## callees

- `0x180029d80`
- `0x18002a160`
- `0x18002b050`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800bb8d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb9bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb9bb`
- `WINHTTP!WinHttpCrackUrl` at `0x1800bb959`
- `WINHTTP!WinHttpCrackUrl` at `0x1800bb959`
- `WINHTTP!WinHttpCreateUrl` at `0x1800bb9af`
- `WINHTTP!WinHttpCreateUrl` at `0x1800bb9f2`
- `WINHTTP!WinHttpCreateUrl` at `0x1800bb9af`
- `WINHTTP!WinHttpCreateUrl` at `0x1800bb9f2`

## pseudocode

```c
__int64 __fastcall ZtTrustedServerGetTemplate(__int64 a1, WCHAR **a2)
{
  WCHAR *StringCopy_W; // rdi
  DWORD LastError; // ebx
  const WCHAR *v6; // rcx
  __int16 v7; // ax
  DWORD v8; // eax
  WCHAR *v9; // rax
  DWORD pdwUrlLength[4]; // [rsp+20h] [rbp-49h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+30h] [rbp-39h] BYREF

  pdwUrlLength[0] = 0;
  StringCopy_W = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  if ( a2 )
    *a2 = 0;
  if ( a1 && (v6 = *(const WCHAR **)(a1 + 56)) != 0 && a2 )
  {
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwHostNameLength = -1;
    UrlComponents.dwUrlPathLength = -1;
    if ( !WinHttpCrackUrl(v6, 0, 0, &UrlComponents) )
    {
LABEL_8:
      LastError = GetLastError();
      goto LABEL_17;
    }
    v7 = *(_WORD *)(a1 + 44);
    if ( UrlComponents.nPort == v7 || UrlComponents.nPort == 443 && !v7 )
    {
      StringCopy_W = (WCHAR *)Dns_CreateStringCopy_W(*(void **)(a1 + 56));
      if ( StringCopy_W )
        goto LABEL_16;
      goto LABEL_19;
    }
    UrlComponents.nPort = *(_WORD *)(a1 + 44);
    WinHttpCreateUrl(&UrlComponents, 0, 0, pdwUrlLength);
    v8 = GetLastError();
    LastError = v8;
    if ( v8 == 122 || !v8 )
    {
      v9 = (WCHAR *)Dns_Allocate(2LL * pdwUrlLength[0]);
      StringCopy_W = v9;
      if ( v9 )
      {
        if ( !WinHttpCreateUrl(&UrlComponents, 0, v9, pdwUrlLength) )
          goto LABEL_8;
LABEL_16:
        *a2 = StringCopy_W;
        LastError = 0;
        StringCopy_W = 0;
        pdwUrlLength[0] = 0;
        goto LABEL_17;
      }
LABEL_19:
      LastError = 14;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_17:
  DnsApiFree(StringCopy_W);
  return LastError;
}

```

## disassembly

```asm
0x1800bb8d4  mov     [rsp-8+arg_10], rbx
0x1800bb8d9  mov     [rsp-8+arg_18], rsi
0x1800bb8de  push    rbp
0x1800bb8df  push    rdi
0x1800bb8e0  push    r14
0x1800bb8e2  lea     rbp, [rsp-47h]
0x1800bb8e7  sub     rsp, 0B0h
0x1800bb8ee  mov     rax, cs:__security_cookie
0x1800bb8f5  xor     rax, rsp
0x1800bb8f8  mov     [rbp+57h+var_20], rax
0x1800bb8fc  xor     r14d, r14d
0x1800bb8ff  mov     rsi, rdx
0x1800bb902  mov     rbx, rcx
0x1800bb905  mov     [rbp+57h+pdwUrlLength], r14d
0x1800bb909  xor     edx, edx; Val
0x1800bb90b  lea     rcx, [rbp+57h+UrlComponents]; void *
0x1800bb90f  mov     edi, r14d
0x1800bb912  lea     r8d, [r14+68h]; Size
0x1800bb916  call    memset_0
0x1800bb91b  test    rsi, rsi
0x1800bb91e  jz      short loc_1800BB923
0x1800bb920  mov     [rsi], r14
0x1800bb923  test    rbx, rbx
0x1800bb926  jnz     short loc_1800BB932
0x1800bb928  mov     ebx, 57h ; 'W'
0x1800bb92d  jmp     loc_1800BBA13
0x1800bb932  mov     rcx, [rbx+38h]; pwszUrl
0x1800bb936  test    rcx, rcx
0x1800bb939  jz      short loc_1800BB928
0x1800bb93b  test    rsi, rsi
0x1800bb93e  jz      short loc_1800BB928
0x1800bb940  or      eax, 0FFFFFFFFh
0x1800bb943  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800bb94a  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800bb94e  mov     [rbp+57h+UrlComponents.dwHostNameLength], eax
0x1800bb951  xor     r8d, r8d; dwFlags
0x1800bb954  mov     [rbp+57h+UrlComponents.dwUrlPathLength], eax
0x1800bb957  xor     edx, edx; dwUrlLength
0x1800bb959  call    cs:__imp_WinHttpCrackUrl
0x1800bb960  nop     dword ptr [rax+rax+00h]
0x1800bb965  test    eax, eax
0x1800bb967  jnz     short loc_1800BB97C
0x1800bb969  call    cs:__imp_GetLastError
0x1800bb970  nop     dword ptr [rax+rax+00h]
0x1800bb975  mov     ebx, eax
0x1800bb977  jmp     loc_1800BBA13
0x1800bb97c  movzx   eax, word ptr [rbx+2Ch]
0x1800bb980  cmp     [rbp+57h+UrlComponents.nPort], ax
0x1800bb984  jz      loc_1800BBA42
0x1800bb98a  mov     ecx, 1BBh
0x1800bb98f  cmp     [rbp+57h+UrlComponents.nPort], cx
0x1800bb993  jnz     short loc_1800BB99E
0x1800bb995  test    ax, ax
0x1800bb998  jz      loc_1800BBA42
0x1800bb99e  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x1800bb9a2  mov     [rbp+57h+UrlComponents.nPort], ax
0x1800bb9a6  xor     r8d, r8d; pwszUrl
0x1800bb9a9  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800bb9ad  xor     edx, edx; dwFlags
0x1800bb9af  call    cs:__imp_WinHttpCreateUrl
0x1800bb9b6  nop     dword ptr [rax+rax+00h]
0x1800bb9bb  call    cs:__imp_GetLastError
0x1800bb9c2  nop     dword ptr [rax+rax+00h]
0x1800bb9c7  mov     ebx, eax
0x1800bb9c9  cmp     eax, 7Ah ; 'z'
0x1800bb9cc  jz      short loc_1800BB9D2
0x1800bb9ce  test    eax, eax
0x1800bb9d0  jnz     short loc_1800BBA13
0x1800bb9d2  mov     ecx, [rbp+57h+pdwUrlLength]
0x1800bb9d5  add     rcx, rcx
0x1800bb9d8  call    Dns_Allocate
0x1800bb9dd  mov     rdi, rax
0x1800bb9e0  test    rax, rax
0x1800bb9e3  jz      short loc_1800BBA53
0x1800bb9e5  lea     r9, [rbp+57h+pdwUrlLength]; pdwUrlLength
0x1800bb9e9  mov     r8, rax; pwszUrl
0x1800bb9ec  xor     edx, edx; dwFlags
0x1800bb9ee  lea     rcx, [rbp+57h+UrlComponents]; lpUrlComponents
0x1800bb9f2  call    cs:__imp_WinHttpCreateUrl
0x1800bb9f9  nop     dword ptr [rax+rax+00h]
0x1800bb9fe  test    eax, eax
0x1800bba00  jz      loc_1800BB969
0x1800bba06  mov     [rsi], rdi
0x1800bba09  mov     ebx, r14d
0x1800bba0c  mov     rdi, r14
0x1800bba0f  mov     [rbp+57h+pdwUrlLength], r14d
0x1800bba13  mov     rcx, rdi; lpMem
0x1800bba16  call    DnsApiFree
0x1800bba1b  mov     eax, ebx
0x1800bba1d  mov     rcx, [rbp+57h+var_20]
0x1800bba21  xor     rcx, rsp; StackCookie
0x1800bba24  call    __security_check_cookie
0x1800bba29  lea     r11, [rsp+0C0h+var_10]
0x1800bba31  mov     rbx, [r11+30h]
0x1800bba35  mov     rsi, [r11+38h]
0x1800bba39  mov     rsp, r11
0x1800bba3c  pop     r14
0x1800bba3e  pop     rdi
0x1800bba3f  pop     rbp
0x1800bba40  retn
0x1800bba42  mov     rcx, [rbx+38h]; Src
0x1800bba46  call    Dns_CreateStringCopy_W
0x1800bba4b  mov     rdi, rax
0x1800bba4e  test    rax, rax
0x1800bba51  jnz     short loc_1800BBA06
0x1800bba53  mov     ebx, 0Eh
0x1800bba58  jmp     short loc_1800BBA13
```
