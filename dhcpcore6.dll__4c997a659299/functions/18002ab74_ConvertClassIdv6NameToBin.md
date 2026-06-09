# ConvertClassIdv6NameToBin

- ea: `0x18002ab74`
- end: `0x18002ad12`
- name: `ConvertClassIdv6NameToBin`
- size: `414`
- prototype: `DWORD __fastcall(__int64, const wchar_t *, __int64, CHAR **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002ad18`

## callees

- `0x180007564`
- `0x1800077e0`
- `0x18000c740`
- `0x18002ab74`
- `0x1800304d4`
- `0x1800337d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002acba`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ac3a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002aca6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002ac3a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002aca6`

## pseudocode

```c
DWORD __fastcall ConvertClassIdv6NameToBin(__int64 a1, const wchar_t *a2, __int64 a3, CHAR **a4, int *a5)
{
  int *v5; // r15
  HRESULT v8; // eax
  int v9; // ebx
  DWORD result; // eax
  unsigned int v11; // eax
  int cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rax
  CHAR *v14; // rsi
  DWORD LastError; // ebx
  size_t pcchLength; // [rsp+70h] [rbp+8h] BYREF
  int cchWideChar; // [rsp+80h] [rbp+18h]

  v5 = a5;
  *a4 = 0;
  pcchLength = 0;
  *v5 = 0;
  cchWideChar = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    HIDWORD(pcchLength) = 77;
LABEL_3:
    v9 = cchWideChar;
    goto LABEL_7;
  }
  v8 = StringCchLengthW(a2, (size_t)a2, &pcchLength);
  if ( v8 < 0 )
  {
    HIDWORD(pcchLength) = 81;
    goto LABEL_3;
  }
  v9 = pcchLength;
LABEL_7:
  result = WX_WIN32_FROM_HR((unsigned int)v8);
  if ( !result )
  {
    v11 = WideCharToMultiByte(0xFDE9u, 0, a2, v9, 0, 0, 0, 0);
    cbMultiByte = v11;
    if ( v11 || !v9 )
    {
      lpMultiByteStr = (CHAR *)DhcpAlloc(v11);
      pcchLength = (size_t)lpMultiByteStr;
      v14 = lpMultiByteStr;
      if ( lpMultiByteStr )
      {
        if ( WideCharToMultiByte(0xFDE9u, 0, a2, v9, lpMultiByteStr, cbMultiByte, 0, 0) || !v9 )
        {
          *a4 = v14;
          result = 0;
          *v5 = cbMultiByte;
        }
        else
        {
          LastError = GetLastError();
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_S(1025, 14, WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids, a2);
          DhcpFree((LPVOID *)&pcchLength);
          return LastError;
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ab74  mov     rax, rsp
0x18002ab77  mov     [rax+10h], rbx
0x18002ab7b  mov     [rax+18h], r8d
0x18002ab7f  mov     [rax+8], rcx
0x18002ab83  push    rbp
0x18002ab84  push    rsi
0x18002ab85  push    rdi
0x18002ab86  push    r14
0x18002ab88  push    r15
0x18002ab8a  sub     rsp, 40h
0x18002ab8e  mov     r15, [rsp+68h+arg_20]
0x18002ab96  mov     r14, r9
0x18002ab99  mov     dword ptr [rsp+68h+pcchLength+4], 0
0x18002aba1  mov     rdi, rdx
0x18002aba4  mov     qword ptr [r9], 0
0x18002abab  mov     qword ptr [rax+8], 0
0x18002abb3  mov     dword ptr [r15], 0
0x18002abba  mov     [rsp+68h+cchWideChar], 0
0x18002abc5  test    rdx, rdx
0x18002abc8  jnz     short loc_18002ABE0
0x18002abca  mov     eax, 80070057h
0x18002abcf  mov     dword ptr [rsp+68h+pcchLength+4], 4Dh ; 'M'
0x18002abd7  mov     ebx, [rsp+68h+cchWideChar]
0x18002abde  jmp     short loc_18002ABFF
0x18002abe0  lea     r8, [rsp+68h+pcchLength]; pcchLength
0x18002abe5  mov     rcx, rdi; psz
0x18002abe8  call    StringCchLengthW
0x18002abed  test    eax, eax
0x18002abef  jns     short loc_18002ABFB
0x18002abf1  mov     dword ptr [rsp+68h+pcchLength+4], 51h ; 'Q'
0x18002abf9  jmp     short loc_18002ABD7
0x18002abfb  mov     ebx, dword ptr [rsp+68h+pcchLength]
0x18002abff  mov     ecx, eax
0x18002ac01  call    WX_WIN32_FROM_HR
0x18002ac06  test    eax, eax
0x18002ac08  jnz     loc_18002AD00
0x18002ac0e  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18002ac17  mov     r9d, ebx; cchWideChar
0x18002ac1a  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18002ac23  mov     r8, rdi; lpWideCharStr
0x18002ac26  mov     [rsp+68h+cbMultiByte], eax; cbMultiByte
0x18002ac2a  xor     edx, edx; dwFlags
0x18002ac2c  mov     ecx, 0FDE9h; CodePage
0x18002ac31  mov     [rsp+68h+lpMultiByteStr], 0; lpMultiByteStr
0x18002ac3a  call    cs:__imp_WideCharToMultiByte
0x18002ac41  nop     dword ptr [rax+rax+00h]
0x18002ac46  mov     ebp, eax
0x18002ac48  test    eax, eax
0x18002ac4a  jnz     short loc_18002AC61
0x18002ac4c  test    ebx, ebx
0x18002ac4e  jz      short loc_18002AC61
0x18002ac50  call    cs:__imp_GetLastError
0x18002ac57  nop     dword ptr [rax+rax+00h]
0x18002ac5c  jmp     loc_18002AD00
0x18002ac61  mov     rcx, rbp
0x18002ac64  call    DhcpAlloc
0x18002ac69  mov     [rsp+68h+pcchLength], rax
0x18002ac6e  mov     rsi, rax
0x18002ac71  test    rax, rax
0x18002ac74  jnz     short loc_18002AC7E
0x18002ac76  lea     eax, [rsi+8]
0x18002ac79  jmp     loc_18002AD00
0x18002ac7e  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18002ac87  mov     r9d, ebx; cchWideChar
0x18002ac8a  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18002ac93  mov     r8, rdi; lpWideCharStr
0x18002ac96  mov     [rsp+68h+cbMultiByte], ebp; cbMultiByte
0x18002ac9a  xor     edx, edx; dwFlags
0x18002ac9c  mov     ecx, 0FDE9h; CodePage
0x18002aca1  mov     [rsp+68h+lpMultiByteStr], rsi; lpMultiByteStr
0x18002aca6  call    cs:__imp_WideCharToMultiByte
0x18002acad  nop     dword ptr [rax+rax+00h]
0x18002acb2  test    eax, eax
0x18002acb4  jnz     short loc_18002ACF8
0x18002acb6  test    ebx, ebx
0x18002acb8  jz      short loc_18002ACF8
0x18002acba  call    cs:__imp_GetLastError
0x18002acc1  nop     dword ptr [rax+rax+00h]
0x18002acc6  mov     ebx, eax
0x18002acc8  test    byte ptr cs:xmmword_1800423E0, 2
0x18002accf  jz      short loc_18002ACEA
0x18002acd1  mov     edx, 0Eh
0x18002acd6  lea     r8, WPP_96fa1a2bf2273733f8a7cb3146f56f72_Traceguids
0x18002acdd  mov     ecx, 401h
0x18002ace2  mov     r9, rdi
0x18002ace5  call    WPP_SF_S
0x18002acea  lea     rcx, [rsp+68h+pcchLength]
0x18002acef  call    DhcpFree
0x18002acf4  mov     eax, ebx
0x18002acf6  jmp     short loc_18002AD00
0x18002acf8  mov     [r14], rsi
0x18002acfb  xor     eax, eax
0x18002acfd  mov     [r15], ebp
0x18002ad00  mov     rbx, [rsp+68h+arg_8]
0x18002ad05  add     rsp, 40h
0x18002ad09  pop     r15
0x18002ad0b  pop     r14
0x18002ad0d  pop     rdi
0x18002ad0e  pop     rsi
0x18002ad0f  pop     rbp
0x18002ad10  retn
```
