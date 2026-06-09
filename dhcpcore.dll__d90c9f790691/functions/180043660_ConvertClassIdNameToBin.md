# ConvertClassIdNameToBin

- ea: `0x180043660`
- end: `0x1800438a7`
- name: `ConvertClassIdNameToBin`
- size: `583`
- prototype: `__int64 __fastcall(WCHAR *ReservedMustBeZero, char *lpWideCharStr, int, CHAR **, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800056d4`

## callees

- `0x180005670`
- `0x1800057f0`
- `0x180006440`
- `0x180018fbc`
- `0x18003eed0`
- `0x180043660`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043847`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004383d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004383d`

## pseudocode

```c
__int64 __fastcall ConvertClassIdNameToBin(
        WCHAR *ReservedMustBeZero,
        char *lpWideCharStr,
        int a3,
        CHAR **a4,
        _DWORD *a5)
{
  _DWORD *v5; // r13
  unsigned int v6; // esi
  const void *v7; // r15
  DWORD v10; // edi
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rbx
  DWORD v14; // eax
  DWORD v15; // edi
  __int64 result; // rax
  __int64 v17; // rdx
  char *v18; // rax
  char *v19; // r10
  int v20; // r9d
  int v21; // ecx
  CHAR *v22; // rax
  unsigned int v23; // eax
  int v24; // edi
  CHAR *v25; // rax
  CHAR *v26; // rbx
  DWORD LastError; // ebx
  LPDHCP_CLASS_INFO_ARRAY *lpMultiByteStr; // [rsp+20h] [rbp-20h]
  LPDHCP_CLASS_INFO_ARRAY *lpMultiByteStra; // [rsp+20h] [rbp-20h]
  DWORD *cbMultiByte; // [rsp+28h] [rbp-18h]
  DWORD *cbMultiBytea; // [rsp+28h] [rbp-18h]
  DWORD *lpDefaultChar; // [rsp+30h] [rbp-10h]
  DWORD *lpDefaultChara; // [rsp+30h] [rbp-10h]
  DHCP_RESUME_HANDLE ResumeHandle; // [rsp+90h] [rbp+50h] BYREF
  int cchWideChar; // [rsp+98h] [rbp+58h] BYREF

  v5 = a5;
  v6 = 0;
  v7 = 0;
  ResumeHandle = 0;
  cchWideChar = 0;
  *a4 = 0;
  *v5 = 0;
  v10 = (unsigned int)ReservedMustBeZero;
  if ( !a3
    && DhcpEnumClasses(
         ReservedMustBeZero,
         (DWORD)ReservedMustBeZero,
         &ResumeHandle,
         0,
         lpMultiByteStr,
         cbMultiByte,
         lpDefaultChar) == 234 )
  {
    v11 = DhcpAlloc(ResumeHandle);
    a5 = (_DWORD *)v11;
    v13 = v11;
    if ( !v11 )
      return 8;
    v14 = DhcpEnumClasses(v12, v10, &ResumeHandle, v11, lpMultiByteStra, cbMultiBytea, lpDefaultChara);
    v15 = v14;
    if ( v14 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 11, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v14);
      DhcpPunycodeFree(&a5);
      return v15;
    }
    v17 = 0;
    if ( !ResumeHandle )
      goto LABEL_16;
    do
    {
      v18 = *(char **)(v13 + 40 * v17 + 8);
      v19 = (char *)(lpWideCharStr - v18);
      do
      {
        v20 = *(unsigned __int16 *)&v19[(_QWORD)v18];
        v21 = *(unsigned __int16 *)v18 - v20;
        if ( v21 )
          break;
        v18 += 2;
      }
      while ( v20 );
      if ( !v21 )
        break;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (_DWORD)v17 != ResumeHandle );
    if ( (_DWORD)v17 == ResumeHandle )
    {
LABEL_16:
      DhcpPunycodeFree(&a5);
      v13 = (__int64)a5;
    }
    else
    {
      v6 = *(_DWORD *)(v13 + 40 * v17 + 32);
      v7 = *(const void **)(v13 + 40 * v17 + 24);
      cchWideChar = v6;
    }
    if ( v7 )
    {
      v22 = (CHAR *)DhcpAlloc(v6);
      *a4 = v22;
      if ( v22 )
      {
        memcpy_0(v22, v7, v6);
        *v5 = v6;
        if ( v13 )
          DhcpPunycodeFree(&a5);
        return 0;
      }
      return 8;
    }
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_S(1025, 12, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, lpWideCharStr);
  v23 = WxStringCchLengthDWordW(lpWideCharStr, 0x7FFFFFFF, &cchWideChar);
  result = WX_WIN32_FROM_HR(v23);
  if ( !(_DWORD)result )
  {
    v24 = cchWideChar;
    v25 = (CHAR *)DhcpAlloc((unsigned int)cchWideChar);
    a5 = v25;
    v26 = v25;
    if ( !v25 )
      return 8;
    if ( WideCharToMultiByte(0, 0x400u, (LPCWCH)lpWideCharStr, v24, v25, v24, 0, 0) )
    {
      *a4 = v26;
      *v5 = v24;
      return 0;
    }
    LastError = GetLastError();
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_S(1025, 13, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, lpWideCharStr);
    DhcpPunycodeFree(&a5);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180043660  mov     [rsp-38h+arg_0], rbx
0x180043665  push    rbp
0x180043666  push    rsi
0x180043667  push    rdi
0x180043668  push    r12
0x18004366a  push    r13
0x18004366c  push    r14
0x18004366e  push    r15
0x180043670  mov     rbp, rsp
0x180043673  sub     rsp, 40h
0x180043677  mov     r13, [rbp+arg_20]
0x18004367b  xor     esi, esi
0x18004367d  xor     r15d, r15d
0x180043680  mov     [rbp+ResumeHandle], 0
0x180043687  mov     [rbp+cchWideChar], esi
0x18004368a  mov     r12, r9
0x18004368d  mov     [r9], rsi
0x180043690  mov     r14, rdx
0x180043693  mov     [r13+0], esi
0x180043697  mov     rdi, rcx
0x18004369a  test    r8d, r8d
0x18004369d  jnz     loc_1800437BD
0x1800436a3  xor     r9d, r9d; PreferredMaximum
0x1800436a6  lea     r8, [rbp+ResumeHandle]; ResumeHandle
0x1800436aa  mov     rdx, rcx; ReservedMustBeZero
0x1800436ad  call    DhcpEnumClasses
0x1800436b2  cmp     eax, 0EAh
0x1800436b7  jnz     loc_1800437BD
0x1800436bd  mov     ecx, [rbp+ResumeHandle]
0x1800436c0  call    DhcpAlloc
0x1800436c5  mov     [rbp+arg_20], rax
0x1800436c9  mov     rbx, rax
0x1800436cc  test    rax, rax
0x1800436cf  jz      loc_18004388A
0x1800436d5  mov     r9, rax; PreferredMaximum
0x1800436d8  lea     r8, [rbp+ResumeHandle]; ResumeHandle
0x1800436dc  mov     rdx, rdi; ReservedMustBeZero
0x1800436df  call    DhcpEnumClasses
0x1800436e4  mov     edi, eax
0x1800436e6  test    eax, eax
0x1800436e8  jz      short loc_18004371A
0x1800436ea  test    byte ptr cs:xmmword_1800616A0, 2
0x1800436f1  jz      short loc_18004370A
0x1800436f3  lea     edx, [rsi+0Bh]
0x1800436f6  mov     ecx, 401h
0x1800436fb  mov     r9d, eax
0x1800436fe  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x180043705  call    WPP_SF_D
0x18004370a  lea     rcx, [rbp+arg_20]
0x18004370e  call    DhcpPunycodeFree
0x180043713  mov     eax, edi
0x180043715  jmp     loc_18004388F
0x18004371a  mov     r8d, [rbp+ResumeHandle]
0x18004371e  xor     edx, edx
0x180043720  test    r8d, r8d
0x180043723  jz      short loc_18004376C
0x180043725  lea     rcx, [rdx+rdx*4]
0x180043729  mov     r10, r14
0x18004372c  mov     rax, [rbx+rcx*8+8]
0x180043731  sub     r10, rax
0x180043734  movzx   ecx, word ptr [rax]
0x180043737  movzx   r9d, word ptr [rax+r10]
0x18004373c  sub     ecx, r9d
0x18004373f  jnz     short loc_18004374A
0x180043741  add     rax, 2
0x180043745  test    r9d, r9d
0x180043748  jnz     short loc_180043734
0x18004374a  test    ecx, ecx
0x18004374c  jz      short loc_180043755
0x18004374e  inc     edx
0x180043750  cmp     edx, r8d
0x180043753  jnz     short loc_180043725
0x180043755  cmp     edx, r8d
0x180043758  jz      short loc_18004376C
0x18004375a  lea     rcx, [rdx+rdx*4]
0x18004375e  mov     esi, [rbx+rcx*8+20h]
0x180043762  mov     r15, [rbx+rcx*8+18h]
0x180043767  mov     [rbp+cchWideChar], esi
0x18004376a  jmp     short loc_180043779
0x18004376c  lea     rcx, [rbp+arg_20]
0x180043770  call    DhcpPunycodeFree
0x180043775  mov     rbx, [rbp+arg_20]
0x180043779  test    r15, r15
0x18004377c  jz      short loc_1800437BD
0x18004377e  mov     ecx, esi
0x180043780  mov     edi, esi
0x180043782  call    DhcpAlloc
0x180043787  mov     [r12], rax
0x18004378b  test    rax, rax
0x18004378e  jz      loc_18004388A
0x180043794  mov     r8d, edi; Size
0x180043797  mov     rdx, r15; Src
0x18004379a  mov     rcx, rax; void *
0x18004379d  call    memcpy_0
0x1800437a2  mov     [r13+0], esi
0x1800437a6  test    rbx, rbx
0x1800437a9  jz      loc_180043886
0x1800437af  lea     rcx, [rbp+arg_20]
0x1800437b3  call    DhcpPunycodeFree
0x1800437b8  jmp     loc_180043886
0x1800437bd  test    byte ptr cs:xmmword_1800616A0, 2
0x1800437c4  jz      short loc_1800437DF
0x1800437c6  mov     edx, 0Ch
0x1800437cb  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x1800437d2  mov     ecx, 401h
0x1800437d7  mov     r9, r14
0x1800437da  call    WPP_SF_S
0x1800437df  lea     r8, [rbp+cchWideChar]
0x1800437e3  mov     edx, 7FFFFFFFh
0x1800437e8  mov     rcx, r14
0x1800437eb  call    WxStringCchLengthDWordW
0x1800437f0  mov     ecx, eax
0x1800437f2  call    WX_WIN32_FROM_HR
0x1800437f7  test    eax, eax
0x1800437f9  jnz     loc_18004388F
0x1800437ff  mov     edi, [rbp+cchWideChar]
0x180043802  mov     ecx, edi
0x180043804  call    DhcpAlloc
0x180043809  mov     [rbp+arg_20], rax
0x18004380d  mov     rbx, rax
0x180043810  test    rax, rax
0x180043813  jz      short loc_18004388A
0x180043815  mov     [rsp+40h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18004381e  mov     r9d, edi; cchWideChar
0x180043821  mov     [rsp+40h+lpDefaultChar], 0; lpDefaultChar
0x18004382a  mov     r8, r14; lpWideCharStr
0x18004382d  mov     dword ptr [rsp+40h+cbMultiByte], edi; cbMultiByte
0x180043831  mov     edx, 400h; dwFlags
0x180043836  xor     ecx, ecx; CodePage
0x180043838  mov     [rsp+40h+lpMultiByteStr], rax; lpMultiByteStr
0x18004383d  call    cs:__imp_WideCharToMultiByte
0x180043843  test    eax, eax
0x180043845  jnz     short loc_18004387E
0x180043847  call    cs:__imp_GetLastError
0x18004384d  mov     ebx, eax
0x18004384f  test    byte ptr cs:xmmword_1800616A0, 2
0x180043856  jz      short loc_180043871
0x180043858  mov     edx, 0Dh
0x18004385d  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x180043864  mov     ecx, 401h
0x180043869  mov     r9, r14
0x18004386c  call    WPP_SF_S
0x180043871  lea     rcx, [rbp+arg_20]
0x180043875  call    DhcpPunycodeFree
0x18004387a  mov     eax, ebx
0x18004387c  jmp     short loc_18004388F
0x18004387e  mov     [r12], rbx
0x180043882  mov     [r13+0], edi
0x180043886  xor     eax, eax
0x180043888  jmp     short loc_18004388F
0x18004388a  mov     eax, 8
0x18004388f  mov     rbx, [rsp+40h+arg_0]
0x180043897  add     rsp, 40h
0x18004389b  pop     r15
0x18004389d  pop     r14
0x18004389f  pop     r13
0x1800438a1  pop     r12
0x1800438a3  pop     rdi
0x1800438a4  pop     rsi
0x1800438a5  pop     rbp
0x1800438a6  retn
```
