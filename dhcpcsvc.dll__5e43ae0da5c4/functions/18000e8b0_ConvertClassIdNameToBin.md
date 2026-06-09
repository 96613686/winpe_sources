# ConvertClassIdNameToBin

- ea: `0x18000e8b0`
- end: `0x18000eb27`
- name: `ConvertClassIdNameToBin`
- size: `631`
- prototype: `__int64 __usercall@<rax>(DWORD ReservedMustBeZero@<ecx>, LPCWCH lpWideCharStr@<rdx>, int cchWideChar)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18000eb30`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180003210`
- `0x18000d4a4`
- `0x18000d660`
- `0x18000e8b0`
- `0x180010aac`
- `0x1800127f0`
- `0x180012a00`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000eac9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000eac9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000eabf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000eabf`

## pseudocode

```c
__int64 __fastcall ConvertClassIdNameToBin(
        DWORD ReservedMustBeZero,
        char *lpWideCharStr,
        __int64 a3,
        CHAR **a4,
        unsigned int *cchWideChar)
{
  unsigned int *v5; // r12
  const void *v6; // r14
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rbx
  DWORD v14; // eax
  DWORD v15; // edi
  __int64 result; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  char *v19; // rax
  char *v20; // r10
  int v21; // r9d
  int v22; // ecx
  unsigned int v23; // edi
  CHAR *v24; // rax
  HRESULT v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // r8
  CHAR *v29; // rax
  CHAR *v30; // rdi
  DWORD LastError; // ebx
  LPDHCP_CLASS_INFO_ARRAY *lpMultiByteStr; // [rsp+20h] [rbp-20h]
  LPDHCP_CLASS_INFO_ARRAY *lpMultiByteStra; // [rsp+20h] [rbp-20h]
  DWORD *cbMultiByte; // [rsp+28h] [rbp-18h]
  DWORD *cbMultiBytea; // [rsp+28h] [rbp-18h]
  DWORD *lpDefaultChar; // [rsp+30h] [rbp-10h]
  DWORD *lpDefaultChara; // [rsp+30h] [rbp-10h]
  DHCP_RESUME_HANDLE ResumeHandle; // [rsp+80h] [rbp+40h] BYREF
  size_t pcchLength; // [rsp+88h] [rbp+48h] BYREF

  v5 = cchWideChar;
  v6 = 0;
  *a4 = 0;
  ResumeHandle = 0;
  *v5 = 0;
  if ( DhcpEnumClasses(0, ReservedMustBeZero, &ResumeHandle, 0, lpMultiByteStr, cbMultiByte, lpDefaultChar) == 234 )
  {
    v12 = DhcpAlloc(ResumeHandle, v10, v11);
    cchWideChar = (unsigned int *)v12;
    v13 = v12;
    if ( !v12 )
      return 8;
    v14 = DhcpEnumClasses(0, ReservedMustBeZero, &ResumeHandle, v12, lpMultiByteStra, cbMultiBytea, lpDefaultChara);
    v15 = v14;
    if ( v14 )
    {
      if ( (xmmword_18001E1E0 & 2) != 0 )
        WPP_SF_d(1025, 11, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v14);
      DhcpFree(&cchWideChar);
      return v15;
    }
    v17 = ResumeHandle;
    v18 = 0;
    if ( !ResumeHandle )
      goto LABEL_15;
    do
    {
      v19 = *(char **)(v13 + 40 * v18 + 8);
      v20 = (char *)(lpWideCharStr - v19);
      do
      {
        v21 = *(unsigned __int16 *)&v20[(_QWORD)v19];
        v22 = *(unsigned __int16 *)v19 - v21;
        if ( v22 )
          break;
        v19 += 2;
      }
      while ( v21 );
      if ( !v22 )
        break;
      v18 = (unsigned int)(v18 + 1);
    }
    while ( (_DWORD)v18 != ResumeHandle );
    if ( (_DWORD)v18 == ResumeHandle )
    {
LABEL_15:
      v23 = 0;
      DhcpFree(&cchWideChar);
      v13 = (__int64)cchWideChar;
    }
    else
    {
      v6 = *(const void **)(v13 + 40 * v18 + 24);
      v23 = *(_DWORD *)(v13 + 40 * v18 + 32);
    }
    if ( v6 )
    {
      v24 = (CHAR *)DhcpAlloc(v23, v18, v17);
      *a4 = v24;
      if ( v24 )
      {
        memcpy_0(v24, v6, v23);
        *v5 = v23;
        if ( v13 )
          DhcpFree(&cchWideChar);
        return 0;
      }
      return 8;
    }
  }
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_S(1025, 12, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, lpWideCharStr);
  pcchLength = 0;
  LODWORD(cchWideChar) = 0;
  if ( !lpWideCharStr )
  {
    v25 = -2147024809;
    HIDWORD(pcchLength) = 77;
LABEL_24:
    v26 = (unsigned int)cchWideChar;
    goto LABEL_28;
  }
  v25 = StringCchLengthW((STRSAFE_PCNZWCH)lpWideCharStr, 0x7FFFFFFFu, &pcchLength);
  if ( v25 < 0 )
  {
    HIDWORD(pcchLength) = 81;
    goto LABEL_24;
  }
  v26 = pcchLength;
LABEL_28:
  result = WX_WIN32_FROM_HR((unsigned int)v25);
  if ( (_DWORD)result )
    return result;
  v29 = (CHAR *)DhcpAlloc(v26, v27, v28);
  cchWideChar = (unsigned int *)v29;
  v30 = v29;
  if ( !v29 )
    return 8;
  if ( WideCharToMultiByte(0, 0x400u, (LPCWCH)lpWideCharStr, v26, v29, v26, 0, 0) )
  {
    *a4 = v30;
    *v5 = v26;
    return 0;
  }
  LastError = GetLastError();
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_S(1025, 13, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, lpWideCharStr);
  DhcpFree(&cchWideChar);
  return LastError;
}

```

## disassembly

```asm
0x18000e8b0  mov     [rsp-28h+arg_0], rbx
0x18000e8b5  mov     [rsp-28h+arg_8], rsi
0x18000e8ba  mov     [rsp-28h+ResumeHandle], r8d
0x18000e8bf  push    rbp
0x18000e8c0  push    rdi
0x18000e8c1  push    r12
0x18000e8c3  push    r14
0x18000e8c5  push    r15
0x18000e8c7  mov     rbp, rsp
0x18000e8ca  sub     rsp, 40h
0x18000e8ce  mov     r12, [rbp+cchWideChar]
0x18000e8d2  lea     r8, [rbp+ResumeHandle]; ResumeHandle
0x18000e8d6  xor     r14d, r14d
0x18000e8d9  mov     rsi, rdx
0x18000e8dc  mov     r15, r9
0x18000e8df  mov     [r9], r14
0x18000e8e2  mov     rdi, rcx
0x18000e8e5  mov     [rbp+ResumeHandle], r14d
0x18000e8e9  mov     rdx, rcx; ReservedMustBeZero
0x18000e8ec  mov     [r12], r14d
0x18000e8f0  xor     r9d, r9d; PreferredMaximum
0x18000e8f3  xor     ecx, ecx; ServerIpAddress
0x18000e8f5  call    DhcpEnumClasses
0x18000e8fa  cmp     eax, 0EAh
0x18000e8ff  jnz     loc_18000EA06
0x18000e905  mov     ecx, [rbp+ResumeHandle]
0x18000e908  call    DhcpAlloc
0x18000e90d  mov     [rbp+cchWideChar], rax
0x18000e911  mov     rbx, rax
0x18000e914  test    rax, rax
0x18000e917  jz      loc_18000EB0B
0x18000e91d  mov     r9, rax; PreferredMaximum
0x18000e920  lea     r8, [rbp+ResumeHandle]; ResumeHandle
0x18000e924  mov     rdx, rdi; ReservedMustBeZero
0x18000e927  xor     ecx, ecx; ServerIpAddress
0x18000e929  call    DhcpEnumClasses
0x18000e92e  mov     edi, eax
0x18000e930  test    eax, eax
0x18000e932  jz      short loc_18000E965
0x18000e934  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000e93b  jz      short loc_18000E955
0x18000e93d  lea     edx, [r14+0Bh]
0x18000e941  mov     ecx, 401h
0x18000e946  mov     r9d, eax
0x18000e949  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000e950  call    WPP_SF_d
0x18000e955  lea     rcx, [rbp+cchWideChar]
0x18000e959  call    DhcpFree
0x18000e95e  mov     eax, edi
0x18000e960  jmp     loc_18000EB10
0x18000e965  mov     r8d, [rbp+ResumeHandle]
0x18000e969  xor     edx, edx
0x18000e96b  test    r8d, r8d
0x18000e96e  jz      short loc_18000E9B4
0x18000e970  lea     rcx, [rdx+rdx*4]
0x18000e974  mov     r10, rsi
0x18000e977  mov     rax, [rbx+rcx*8+8]
0x18000e97c  sub     r10, rax
0x18000e97f  movzx   ecx, word ptr [rax]
0x18000e982  movzx   r9d, word ptr [rax+r10]
0x18000e987  sub     ecx, r9d
0x18000e98a  jnz     short loc_18000E995
0x18000e98c  add     rax, 2
0x18000e990  test    r9d, r9d
0x18000e993  jnz     short loc_18000E97F
0x18000e995  test    ecx, ecx
0x18000e997  jz      short loc_18000E9A0
0x18000e999  inc     edx
0x18000e99b  cmp     edx, r8d
0x18000e99e  jnz     short loc_18000E970
0x18000e9a0  cmp     edx, r8d
0x18000e9a3  jz      short loc_18000E9B4
0x18000e9a5  lea     rcx, [rdx+rdx*4]
0x18000e9a9  mov     r14, [rbx+rcx*8+18h]
0x18000e9ae  mov     edi, [rbx+rcx*8+20h]
0x18000e9b2  jmp     short loc_18000E9C3
0x18000e9b4  xor     edi, edi
0x18000e9b6  lea     rcx, [rbp+cchWideChar]
0x18000e9ba  call    DhcpFree
0x18000e9bf  mov     rbx, [rbp+cchWideChar]
0x18000e9c3  test    r14, r14
0x18000e9c6  jz      short loc_18000EA06
0x18000e9c8  mov     ecx, edi
0x18000e9ca  mov     esi, edi
0x18000e9cc  call    DhcpAlloc
0x18000e9d1  mov     [r15], rax
0x18000e9d4  test    rax, rax
0x18000e9d7  jz      loc_18000EB0B
0x18000e9dd  mov     r8d, esi; Size
0x18000e9e0  mov     rdx, r14; Src
0x18000e9e3  mov     rcx, rax; void *
0x18000e9e6  call    memcpy_0
0x18000e9eb  mov     [r12], edi
0x18000e9ef  test    rbx, rbx
0x18000e9f2  jz      loc_18000EB07
0x18000e9f8  lea     rcx, [rbp+cchWideChar]
0x18000e9fc  call    DhcpFree
0x18000ea01  jmp     loc_18000EB07
0x18000ea06  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000ea0d  jz      short loc_18000EA28
0x18000ea0f  mov     edx, 0Ch
0x18000ea14  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000ea1b  mov     ecx, 401h
0x18000ea20  mov     r9, rsi
0x18000ea23  call    WPP_SF_S
0x18000ea28  mov     dword ptr [rbp+pcchLength+4], 0
0x18000ea2f  mov     qword ptr [rbp+48h], 0
0x18000ea37  mov     dword ptr [rbp+cchWideChar], 0
0x18000ea3e  test    rsi, rsi
0x18000ea41  jnz     short loc_18000EA54
0x18000ea43  mov     eax, 80070057h
0x18000ea48  mov     dword ptr [rbp+pcchLength+4], 4Dh ; 'M'
0x18000ea4f  mov     ebx, dword ptr [rbp+cchWideChar]
0x18000ea52  jmp     short loc_18000EA75
0x18000ea54  lea     r8, [rbp+pcchLength]; pcchLength
0x18000ea58  mov     edx, 7FFFFFFFh; cchMax
0x18000ea5d  mov     rcx, rsi; psz
0x18000ea60  call    StringCchLengthW
0x18000ea65  test    eax, eax
0x18000ea67  jns     short loc_18000EA72
0x18000ea69  mov     dword ptr [rbp+pcchLength+4], 51h ; 'Q'
0x18000ea70  jmp     short loc_18000EA4F
0x18000ea72  mov     ebx, dword ptr [rbp+pcchLength]
0x18000ea75  mov     ecx, eax
0x18000ea77  call    WX_WIN32_FROM_HR
0x18000ea7c  test    eax, eax
0x18000ea7e  jnz     loc_18000EB10
0x18000ea84  mov     ecx, ebx
0x18000ea86  call    DhcpAlloc
0x18000ea8b  mov     [rbp+cchWideChar], rax
0x18000ea8f  mov     rdi, rax
0x18000ea92  test    rax, rax
0x18000ea95  jz      short loc_18000EB0B
0x18000ea97  mov     [rsp+40h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000eaa0  mov     r9d, ebx; cchWideChar
0x18000eaa3  mov     [rsp+40h+lpDefaultChar], 0; lpDefaultChar
0x18000eaac  mov     r8, rsi; lpWideCharStr
0x18000eaaf  mov     dword ptr [rsp+40h+cbMultiByte], ebx; cbMultiByte
0x18000eab3  mov     edx, 400h; dwFlags
0x18000eab8  xor     ecx, ecx; CodePage
0x18000eaba  mov     [rsp+40h+lpMultiByteStr], rax; lpMultiByteStr
0x18000eabf  call    cs:__imp_WideCharToMultiByte
0x18000eac5  test    eax, eax
0x18000eac7  jnz     short loc_18000EB00
0x18000eac9  call    cs:__imp_GetLastError
0x18000eacf  mov     ebx, eax
0x18000ead1  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000ead8  jz      short loc_18000EAF3
0x18000eada  mov     edx, 0Dh
0x18000eadf  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000eae6  mov     ecx, 401h
0x18000eaeb  mov     r9, rsi
0x18000eaee  call    WPP_SF_S
0x18000eaf3  lea     rcx, [rbp+cchWideChar]
0x18000eaf7  call    DhcpFree
0x18000eafc  mov     eax, ebx
0x18000eafe  jmp     short loc_18000EB10
0x18000eb00  mov     [r15], rdi
0x18000eb03  mov     [r12], ebx
0x18000eb07  xor     eax, eax
0x18000eb09  jmp     short loc_18000EB10
0x18000eb0b  mov     eax, 8
0x18000eb10  mov     rbx, [rsp+40h+arg_0]
0x18000eb15  mov     rsi, [rsp+40h+arg_8]
0x18000eb1a  add     rsp, 40h
0x18000eb1e  pop     r15
0x18000eb20  pop     r14
0x18000eb22  pop     r12
0x18000eb24  pop     rdi
0x18000eb25  pop     rbp
0x18000eb26  retn
```
