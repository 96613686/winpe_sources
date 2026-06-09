# s_SSRecoverPassword

- ea: `0x180038d40`
- end: `0x18003917e`
- name: `s_SSRecoverPassword`
- size: `1086`
- prototype: `__int64 __fastcall(void *, PCWSTR, unsigned int, unsigned __int8 *, unsigned int, WCHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800063c0`
- `0x180007f10`
- `0x1800097f0`
- `0x18000db40`
- `0x18001ab70`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180036ac8`
- `0x180037e98`
- `0x180038d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039116`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039116`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038f3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038f3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180038eb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180038eb2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180038f08`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180038fbc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180038f08`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180038fbc`

## string_xrefs

- `0x180038f5b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180039023`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180039081`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x1800390b5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x1800390d2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall s_SSRecoverPassword(
        void *a1,
        PCWSTR a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        WCHAR *a6,
        unsigned int a7)
{
  WCHAR *v7; // rdi
  unsigned __int64 v8; // rbx
  _WORD *v11; // rsi
  __int64 result; // rax
  void *v14; // rcx
  __int64 v15; // r12
  void *v16; // r14
  __int64 v17; // rax
  __int64 v18; // r9
  DWORD LastError; // eax
  unsigned int v20; // ebx
  __int64 v21; // rcx
  HLOCAL v22; // rax
  __int64 v23; // r9
  DWORD v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  _BYTE *v27; // rdx
  __int64 i; // rax
  __int64 v29; // rax
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v34; // [rsp+58h] [rbp-A8h]
  _BYTE v35[52]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v37[142]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[16]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v7 = a6;
  v8 = a3;
  hMem = 0;
  v34 = a4;
  v11 = 0;
  memset_0(v35, 0, 0x270u);
  cbSid = 0;
  nSize = 0;
  peUse = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  result = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v35, a1, 0, 0);
  if ( !(_DWORD)result )
  {
    GetDefaultAlgInfo(v14, &v36, 0, v37, 0);
    v15 = -1;
    if ( a2 && (unsigned int)v8 >= 2 && a4 )
    {
      LOBYTE(v16) = 0;
      if ( a5 && a6 && a7 >= 2 )
      {
        if ( a2[(v8 >> 1) - 1] || a6[((unsigned __int64)a7 >> 1) - 1] )
        {
          v18 = 1872;
          goto LABEL_42;
        }
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        if ( !(_DWORD)v17 )
        {
          v18 = 1880;
LABEL_42:
          v21 = 87;
          v20 = 87;
          goto LABEL_43;
        }
        nSize = 16;
        if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
        {
          LastError = GetLastError();
          v20 = LastError;
          v18 = 1892;
LABEL_19:
          v21 = LastError;
LABEL_43:
          DebugTraceError(v21, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v18);
LABEL_53:
          v29 = a7;
          do
          {
            *(_BYTE *)v7 = (_BYTE)v16;
            v7 = (WCHAR *)((char *)v7 + 1);
            --v29;
          }
          while ( v29 );
LABEL_55:
          CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v35);
          return v20;
        }
        if ( !LookupAccountNameW(Buffer, a2, 0, &cbSid, 0, &nSize, &peUse) )
        {
          LastError = GetLastError();
          v20 = LastError;
          if ( LastError != 122 )
          {
            v18 = 1908;
            goto LABEL_19;
          }
        }
        v22 = LocalAlloc(0x40u, cbSid);
        v16 = v22;
        if ( !v22 )
        {
          v20 = 8;
          DebugTraceError(8, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1917);
          goto LABEL_53;
        }
        if ( nSize > 0x10 )
        {
          v20 = 8;
          v23 = 1924;
LABEL_38:
          v25 = v20;
          goto LABEL_39;
        }
        if ( !LookupAccountNameW(Buffer, a2, v22, &cbSid, Buffer, &nSize, &peUse) )
        {
          v24 = GetLastError();
          v20 = v24;
          v23 = 1937;
LABEL_29:
          v25 = v24;
LABEL_39:
          DebugTraceError(v25, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v23);
          goto LABEL_40;
        }
        if ( a5 < 8 || *(_DWORD *)v34 != 1112691533 || *((_DWORD *)v34 + 1) != 1 )
        {
          v20 = 13;
          v23 = 1955;
          goto LABEL_38;
        }
        v26 = DecryptRecoveryPassword(v16, v34, a5, (unsigned __int8 **)&hMem);
        v20 = v26;
        if ( v26 )
        {
          DebugTraceError(v26, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1971);
          CPSImpersonateClient(v35);
          v11 = hMem;
        }
        else
        {
          v11 = hMem;
          v24 = ResetLocalUserPassword(Buffer, a2, (PCWSTR)hMem, a6);
          v20 = v24;
          if ( v24 )
          {
            v23 = 1987;
            goto LABEL_29;
          }
        }
LABEL_40:
        LocalFree(v16);
        LOBYTE(v16) = 0;
        goto LABEL_46;
      }
    }
    else
    {
      LOBYTE(v16) = 0;
    }
    v20 = 87;
    DebugTraceError(87, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1863);
LABEL_46:
    if ( v11 )
    {
      do
        ++v15;
      while ( v11[v15] );
      v27 = v11;
      for ( i = 2LL * (int)v15; i; --i )
        *v27++ = 0;
      LocalFree(v11);
    }
    if ( !a6 || !a7 )
      goto LABEL_55;
    goto LABEL_53;
  }
  return result;
}

```

## disassembly

```asm
0x180038d40  mov     [rsp-8+arg_10], rbx
0x180038d45  push    rbp
0x180038d46  push    rsi
0x180038d47  push    rdi
0x180038d48  push    r12
0x180038d4a  push    r13
0x180038d4c  push    r14
0x180038d4e  push    r15
0x180038d50  lea     rbp, [rsp-200h]
0x180038d58  sub     rsp, 300h
0x180038d5f  mov     rax, cs:__security_cookie
0x180038d66  xor     rax, rsp
0x180038d69  mov     [rbp+230h+var_40], rax
0x180038d70  mov     rdi, [rbp+230h+arg_28]
0x180038d77  xor     r13d, r13d
0x180038d7a  mov     ebx, r8d
0x180038d7d  mov     r15, rdx
0x180038d80  mov     r12, rcx
0x180038d83  mov     [rsp+330h+hMem], r13
0x180038d88  xor     edx, edx; Val
0x180038d8a  mov     [rsp+330h+var_2D8], r9
0x180038d8f  mov     r8d, 270h; Size
0x180038d95  lea     rcx, [rsp+330h+var_2D0]; void *
0x180038d9a  mov     esi, r13d
0x180038d9d  mov     r14, r9
0x180038da0  call    memset_0
0x180038da5  mov     [rsp+330h+cbSid], r13d
0x180038daa  mov     [rsp+330h+nSize], r13d
0x180038daf  mov     [rsp+330h+var_2E8], r13d
0x180038db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dbb  lea     rax, WPP_GLOBAL_Control
0x180038dc2  cmp     rcx, rax
0x180038dc5  jz      short loc_180038DE1
0x180038dc7  test    byte ptr [rcx+1Ch], 4
0x180038dcb  jz      short loc_180038DE1
0x180038dcd  mov     rcx, [rcx+10h]
0x180038dd1  lea     edx, [r13+1Bh]
0x180038dd5  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180038ddc  call    WPP_SF_
0x180038de1  xor     r9d, r9d; unsigned int *
0x180038de4  lea     rcx, [rsp+330h+var_2D0]; struct CRYPT_SERVER_CONTEXT *
0x180038de9  xor     r8d, r8d; unsigned __int16 **
0x180038dec  mov     rdx, r12; void *
0x180038def  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x180038df4  test    eax, eax
0x180038df6  jnz     loc_180039153
0x180038dfc  lea     r9, [rbp+230h+var_298]; unsigned int *
0x180038e00  mov     [rsp+330h+ReferencedDomainName], r13; unsigned int *
0x180038e05  xor     r8d, r8d; unsigned int *
0x180038e08  lea     rdx, [rbp+230h+var_29C]; unsigned int *
0x180038e0c  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x180038e11  or      r12, 0FFFFFFFFFFFFFFFFh
0x180038e15  test    r15, r15
0x180038e18  jz      loc_1800390CA
0x180038e1e  cmp     ebx, 2
0x180038e21  jb      loc_1800390CA
0x180038e27  test    r14, r14
0x180038e2a  jz      loc_1800390CA
0x180038e30  mov     r13d, [rbp+230h+arg_20]
0x180038e37  xor     r14d, r14d
0x180038e3a  test    r13d, r13d
0x180038e3d  jz      loc_1800390CD
0x180038e43  test    rdi, rdi
0x180038e46  jz      loc_1800390CD
0x180038e4c  cmp     [rbp+230h+arg_30], 2
0x180038e53  jb      loc_1800390CD
0x180038e59  mov     rax, rbx
0x180038e5c  shr     rax, 1
0x180038e5f  cmp     [r15+rax*2-2], r14w
0x180038e65  jnz     loc_1800390A8
0x180038e6b  mov     eax, [rbp+230h+arg_30]
0x180038e71  shr     rax, 1
0x180038e74  cmp     [rdi+rax*2-2], r14w
0x180038e7a  jnz     loc_1800390A8
0x180038e80  mov     rax, r12
0x180038e83  inc     rax
0x180038e86  cmp     [r15+rax*2], r14w
0x180038e8b  jnz     short loc_180038E83
0x180038e8d  test    eax, eax
0x180038e8f  jnz     short loc_180038E9C
0x180038e91  mov     r9d, 758h
0x180038e97  jmp     loc_1800390AE
0x180038e9c  lea     r8, [rsp+330h+nSize]; nSize
0x180038ea1  mov     [rsp+330h+nSize], 10h
0x180038ea9  lea     rdx, [rbp+230h+Buffer]; lpBuffer
0x180038eb0  xor     ecx, ecx; NameType
0x180038eb2  call    cs:__imp_GetComputerNameExW
0x180038eb9  nop     dword ptr [rax+rax+00h]
0x180038ebe  test    eax, eax
0x180038ec0  jnz     short loc_180038EDD
0x180038ec2  call    cs:__imp_GetLastError
0x180038ec9  nop     dword ptr [rax+rax+00h]
0x180038ece  mov     ebx, eax
0x180038ed0  mov     r9d, 764h
0x180038ed6  mov     ecx, eax
0x180038ed8  jmp     loc_1800390B5
0x180038edd  lea     rax, [rsp+330h+var_2E8]
0x180038ee2  xor     r8d, r8d; Sid
0x180038ee5  mov     [rsp+330h+peUse], rax; peUse
0x180038eea  lea     r9, [rsp+330h+cbSid]; cbSid
0x180038eef  lea     rax, [rsp+330h+nSize]
0x180038ef4  mov     rdx, r15; lpAccountName
0x180038ef7  mov     [rsp+330h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180038efc  lea     rcx, [rbp+230h+Buffer]; lpSystemName
0x180038f03  mov     [rsp+330h+ReferencedDomainName], r14; ReferencedDomainName
0x180038f08  call    cs:__imp_LookupAccountNameW
0x180038f0f  nop     dword ptr [rax+rax+00h]
0x180038f14  test    eax, eax
0x180038f16  jnz     short loc_180038F33
0x180038f18  call    cs:__imp_GetLastError
0x180038f1f  nop     dword ptr [rax+rax+00h]
0x180038f24  mov     ebx, eax
0x180038f26  cmp     eax, 7Ah ; 'z'
0x180038f29  jz      short loc_180038F33
0x180038f2b  mov     r9d, 774h
0x180038f31  jmp     short loc_180038ED6
0x180038f33  mov     edx, [rsp+330h+cbSid]; uBytes
0x180038f37  mov     ecx, 40h ; '@'; uFlags
0x180038f3c  call    cs:__imp_LocalAlloc
0x180038f43  nop     dword ptr [rax+rax+00h]
0x180038f48  mov     r14, rax
0x180038f4b  test    rax, rax
0x180038f4e  jnz     short loc_180038F73
0x180038f50  lea     ebx, [rax+8]
0x180038f53  mov     r9d, 77Dh
0x180038f59  mov     ecx, ebx
0x180038f5b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038f62  lea     rdx, aDwerror; "dwError"
0x180038f69  call    DebugTraceError
0x180038f6e  jmp     loc_180039130
0x180038f73  cmp     [rsp+330h+nSize], 10h
0x180038f78  jbe     short loc_180038F8A
0x180038f7a  mov     ebx, 8
0x180038f7f  mov     r9d, 784h
0x180038f85  jmp     loc_18003907F
0x180038f8a  lea     rax, [rsp+330h+var_2E8]
0x180038f8f  mov     r8, r14; Sid
0x180038f92  mov     [rsp+330h+peUse], rax; peUse
0x180038f97  lea     r9, [rsp+330h+cbSid]; cbSid
0x180038f9c  lea     rax, [rsp+330h+nSize]
0x180038fa1  mov     rdx, r15; lpAccountName
0x180038fa4  mov     [rsp+330h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180038fa9  lea     rcx, [rbp+230h+Buffer]; lpSystemName
0x180038fb0  lea     rax, [rbp+230h+Buffer]
0x180038fb7  mov     [rsp+330h+ReferencedDomainName], rax; ReferencedDomainName
0x180038fbc  call    cs:__imp_LookupAccountNameW
0x180038fc3  nop     dword ptr [rax+rax+00h]
0x180038fc8  test    eax, eax
0x180038fca  jnz     short loc_180038FE7
0x180038fcc  call    cs:__imp_GetLastError
0x180038fd3  nop     dword ptr [rax+rax+00h]
0x180038fd8  mov     ebx, eax
0x180038fda  mov     r9d, 791h
0x180038fe0  mov     ecx, eax
0x180038fe2  jmp     loc_180039081
0x180038fe7  cmp     r13d, 8
0x180038feb  jb      loc_180039074
0x180038ff1  mov     rax, [rsp+330h+var_2D8]
0x180038ff6  cmp     dword ptr [rax], 4252534Dh
0x180038ffc  jnz     short loc_180039074
0x180038ffe  cmp     dword ptr [rax+4], 1
0x180039002  jnz     short loc_180039074
0x180039004  lea     r9, [rsp+330h+hMem]; unsigned __int16 **
0x180039009  mov     r8d, r13d; unsigned int
0x18003900c  mov     rdx, rax; unsigned __int8 *
0x18003900f  mov     rcx, r14; void *
0x180039012  call    ?DecryptRecoveryPassword@@YAKPEAXPEAEKPEAPEAG@Z; DecryptRecoveryPassword(void *,uchar *,ulong,ushort * *)
0x180039017  mov     ebx, eax
0x180039019  test    eax, eax
0x18003901b  jz      short loc_180039049
0x18003901d  mov     r9d, 7B3h
0x180039023  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003902a  lea     rdx, aDwerror; "dwError"
0x180039031  mov     ecx, eax
0x180039033  call    DebugTraceError
0x180039038  lea     rcx, [rsp+330h+var_2D0]; void *
0x18003903d  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180039042  mov     rsi, [rsp+330h+hMem]
0x180039047  jmp     short loc_180039094
0x180039049  mov     rsi, [rsp+330h+hMem]
0x18003904e  lea     rcx, [rbp+230h+Buffer]; SourceString
0x180039055  mov     r8, rsi; PCWSTR
0x180039058  mov     r9, rdi; PCWSTR
0x18003905b  mov     rdx, r15; PCWSTR
0x18003905e  call    ?ResetLocalUserPassword@@YAKPEAG000@Z; ResetLocalUserPassword(ushort *,ushort *,ushort *,ushort *)
0x180039063  mov     ebx, eax
0x180039065  test    eax, eax
0x180039067  jz      short loc_180039094
0x180039069  mov     r9d, 7C3h
0x18003906f  jmp     loc_180038FE0
0x180039074  mov     ebx, 0Dh
0x180039079  mov     r9d, 7A3h
0x18003907f  mov     ecx, ebx
0x180039081  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180039088  lea     rdx, aDwerror; "dwError"
0x18003908f  call    DebugTraceError
0x180039094  mov     rcx, r14; hMem
0x180039097  call    cs:__imp_LocalFree
0x18003909e  nop     dword ptr [rax+rax+00h]
0x1800390a3  xor     r14d, r14d
0x1800390a6  jmp     short loc_1800390ED
0x1800390a8  mov     r9d, 750h
0x1800390ae  mov     ecx, 57h ; 'W'
0x1800390b3  mov     ebx, ecx
0x1800390b5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800390bc  lea     rdx, aDwerror; "dwError"
0x1800390c3  call    DebugTraceError
0x1800390c8  jmp     short loc_180039130
0x1800390ca  xor     r14d, r14d
0x1800390cd  mov     ecx, 57h ; 'W'
0x1800390d2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800390d9  mov     r9d, 747h
0x1800390df  lea     rdx, aDwerror; "dwError"
0x1800390e6  mov     ebx, ecx
0x1800390e8  call    DebugTraceError
0x1800390ed  test    rsi, rsi
0x1800390f0  jz      short loc_180039122
0x1800390f2  inc     r12
0x1800390f5  cmp     [rsi+r12*2], r14w
0x1800390fa  jnz     short loc_1800390F2
0x1800390fc  movsxd  rax, r12d
0x1800390ff  mov     rdx, rsi
0x180039102  add     rax, rax
0x180039105  jz      short loc_180039113
0x180039107  mov     [rdx], r14b
0x18003910a  inc     rdx
0x18003910d  sub     rax, 1
0x180039111  jnz     short loc_180039107
0x180039113  mov     rcx, rsi; hMem
0x180039116  call    cs:__imp_LocalFree
0x18003911d  nop     dword ptr [rax+rax+00h]
0x180039122  test    rdi, rdi
0x180039125  jz      short loc_180039147
0x180039127  cmp     [rbp+230h+arg_30], r14d
0x18003912e  jz      short loc_180039147
0x180039130  mov     eax, [rbp+230h+arg_30]
0x180039136  test    rax, rax
0x180039139  jz      short loc_180039147
0x18003913b  mov     [rdi], r14b
0x18003913e  inc     rdi
0x180039141  sub     rax, 1
0x180039145  jnz     short loc_18003913B
0x180039147  lea     rcx, [rsp+330h+var_2D0]; struct CRYPT_SERVER_CONTEXT *
0x18003914c  call    ?CPSDeleteServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@@Z; CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *)
0x180039151  mov     eax, ebx
0x180039153  mov     rcx, [rbp+230h+var_40]
0x18003915a  xor     rcx, rsp; StackCookie
0x18003915d  call    __security_check_cookie
0x180039162  mov     rbx, [rsp+330h+arg_10]
0x18003916a  add     rsp, 300h
0x180039171  pop     r15
0x180039173  pop     r14
0x180039175  pop     r13
0x180039177  pop     r12
0x180039179  pop     rdi
0x18003917a  pop     rsi
0x18003917b  pop     rbp
0x18003917c  retn
```
