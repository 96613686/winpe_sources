# DavMatchUserNameToCurrentName

- ea: `0x18000d5f0`
- end: `0x18000da55`
- name: `DavMatchUserNameToCurrentName`
- size: `1125`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, BOOL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007ad0`

## callees

- `0x18000d5f0`
- `0x180010be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d87b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d87b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d96c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9c0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d9f7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000d9f7`
- `KERNEL32!LocalAlloc` at `0x18000d6a6`
- `KERNEL32!LocalAlloc` at `0x18000d7b5`
- `KERNEL32!LocalAlloc` at `0x18000d814`
- `KERNEL32!LocalAlloc` at `0x18000d912`
- `KERNEL32!LocalAlloc` at `0x18000d95e`
- `KERNEL32!LocalAlloc` at `0x18000d6a6`
- `KERNEL32!LocalAlloc` at `0x18000d7b5`
- `KERNEL32!LocalAlloc` at `0x18000d814`
- `KERNEL32!LocalAlloc` at `0x18000d912`
- `KERNEL32!LocalAlloc` at `0x18000d95e`
- `KERNEL32!LocalFree` at `0x18000da04`
- `KERNEL32!LocalFree` at `0x18000da12`
- `KERNEL32!LocalFree` at `0x18000da20`
- `KERNEL32!LocalFree` at `0x18000da2e`
- `KERNEL32!LocalFree` at `0x18000da3c`
- `KERNEL32!LocalFree` at `0x18000da04`
- `KERNEL32!LocalFree` at `0x18000da12`
- `KERNEL32!LocalFree` at `0x18000da20`
- `KERNEL32!LocalFree` at `0x18000da2e`
- `KERNEL32!LocalFree` at `0x18000da3c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d778`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d871`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d8ca`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d9b6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d778`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d871`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d8ca`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000d9b6`
- `SspiCli!GetUserNameExW` at `0x18000d649`
- `SspiCli!GetUserNameExW` at `0x18000d70f`
- `SspiCli!GetUserNameExW` at `0x18000d649`
- `SspiCli!GetUserNameExW` at `0x18000d70f`

## pseudocode

```c
__int64 __fastcall DavMatchUserNameToCurrentName(LPCWSTR lpAccountName, BOOL *a2)
{
  WCHAR *v2; // r15
  DWORD v6; // eax
  unsigned int v7; // ebx
  WCHAR *v8; // rax
  WCHAR *v9; // r13
  DWORD LastError; // eax
  HLOCAL v11; // r14
  WCHAR *v12; // r12
  HLOCAL v13; // rsi
  DWORD v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  WCHAR *v20; // rax
  WCHAR *v21; // rax
  DWORD v22; // [rsp+30h] [rbp-18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-14h] BYREF
  enum _SID_NAME_USE v24[4]; // [rsp+38h] [rbp-10h] BYREF
  ULONG nSize; // [rsp+90h] [rbp+48h] BYREF
  DWORD cchReferencedDomainName; // [rsp+98h] [rbp+50h] BYREF
  DWORD cbSid; // [rsp+A0h] [rbp+58h] BYREF
  DWORD v28; // [rsp+A8h] [rbp+60h] BYREF

  v2 = 0;
  nSize = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  v22 = 0;
  peUse = SidTypeInvalid;
  v24[0] = SidTypeInvalid;
  v28 = 0;
  *a2 = 0;
  if ( !lpAccountName )
  {
    *a2 = 1;
    return 0;
  }
  if ( GetUserNameExW(NameSamCompatible, 0, &nSize) || (v6 = GetLastError(), v6 == 234) )
  {
    v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize);
    v9 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 264, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
      return v7;
    }
    v11 = 0;
    v12 = 0;
    v13 = 0;
    if ( !GetUserNameExW(NameSamCompatible, v8, &nSize) )
    {
      v14 = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v16 = 265;
LABEL_17:
      WPP_SF_d(v15[2], v16, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v14);
LABEL_18:
      v7 = 2202;
LABEL_55:
      LocalFree(v9);
      if ( v11 )
        LocalFree(v11);
      if ( v13 )
        LocalFree(v13);
      if ( v12 )
        LocalFree(v12);
      if ( v2 )
        LocalFree(v2);
      return v7;
    }
    if ( !LookupAccountNameLocalW(v9, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
    {
      v14 = GetLastError();
      if ( v14 != 122 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        v16 = 266;
        goto LABEL_17;
      }
    }
    v11 = LocalAlloc(0x40u, cbSid);
    if ( v11 )
    {
      v20 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
      v12 = v20;
      if ( v20 )
      {
        if ( !LookupAccountNameLocalW(v9, v11, &cbSid, v20, &cchReferencedDomainName, &peUse) )
        {
          v14 = GetLastError();
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_18;
          v16 = 269;
          goto LABEL_17;
        }
        if ( !LookupAccountNameLocalW(lpAccountName, 0, &v22, 0, &v28, v24) )
        {
          v14 = GetLastError();
          if ( v14 != 122 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_18;
            v16 = 270;
            goto LABEL_17;
          }
        }
        v13 = LocalAlloc(0x40u, v22);
        if ( v13 )
        {
          v21 = (WCHAR *)LocalAlloc(0x40u, 2LL * v28);
          v2 = v21;
          if ( v21 )
          {
            if ( LookupAccountNameLocalW(lpAccountName, v13, &v22, v21, &v28, v24) )
            {
              *a2 = EqualSid(v13, v11);
              v7 = 0;
              goto LABEL_55;
            }
            v14 = GetLastError();
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_18;
            v16 = 273;
            goto LABEL_17;
          }
          v17 = GetLastError();
          v7 = v17;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v19 = 272;
        }
        else
        {
          v17 = GetLastError();
          v7 = v17;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v19 = 271;
        }
      }
      else
      {
        v17 = GetLastError();
        v7 = v17;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_55;
        v19 = 268;
      }
    }
    else
    {
      v17 = GetLastError();
      v7 = v17;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v19 = 267;
    }
    WPP_SF_d(v18[2], v19, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v17);
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v6);
  return 2202;
}

```

## disassembly

```asm
0x18000d5f0  push    rbp
0x18000d5f2  push    rbx
0x18000d5f3  push    rsi
0x18000d5f4  push    rdi
0x18000d5f5  push    r12
0x18000d5f7  push    r13
0x18000d5f9  push    r14
0x18000d5fb  push    r15
0x18000d5fd  mov     rbp, rsp
0x18000d600  sub     rsp, 48h
0x18000d604  xor     r15d, r15d
0x18000d607  mov     rbx, rdx
0x18000d60a  mov     [rbp+nSize], r15d
0x18000d60e  mov     rdi, rcx
0x18000d611  mov     [rbp+cbSid], r15d
0x18000d615  mov     [rbp+arg_8], r15d
0x18000d619  mov     [rbp+var_18], r15d
0x18000d61d  lea     eax, [r15+7]
0x18000d621  mov     [rbp+var_14], eax
0x18000d624  mov     [rbp+var_10], eax
0x18000d627  mov     [rbp+arg_18], r15d
0x18000d62b  mov     [rdx], r15d
0x18000d62e  test    rcx, rcx
0x18000d631  jnz     short loc_18000D640
0x18000d633  mov     dword ptr [rdx], 1
0x18000d639  xor     eax, eax
0x18000d63b  jmp     loc_18000DA44
0x18000d640  xor     edx, edx; lpNameBuffer
0x18000d642  lea     r8, [rbp+nSize]; nSize
0x18000d646  lea     ecx, [rdx+2]; NameFormat
0x18000d649  call    cs:__imp_GetUserNameExW
0x18000d64f  test    al, al
0x18000d651  jnz     short loc_18000D69B
0x18000d653  call    cs:__imp_GetLastError
0x18000d659  cmp     eax, 0EAh
0x18000d65e  jz      short loc_18000D69B
0x18000d660  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d667  lea     rdx, WPP_GLOBAL_Control
0x18000d66e  cmp     rcx, rdx
0x18000d671  jz      short loc_18000D691
0x18000d673  test    byte ptr [rcx+1Ch], 1
0x18000d677  jz      short loc_18000D691
0x18000d679  mov     rcx, [rcx+10h]
0x18000d67d  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d684  mov     edx, 107h
0x18000d689  mov     r9d, eax
0x18000d68c  call    WPP_SF_d
0x18000d691  mov     ebx, 89Ah
0x18000d696  jmp     loc_18000DA42
0x18000d69b  mov     edx, [rbp+nSize]
0x18000d69e  mov     ecx, 40h ; '@'; uFlags
0x18000d6a3  add     rdx, rdx; uBytes
0x18000d6a6  call    cs:__imp_LocalAlloc
0x18000d6ac  mov     r13, rax
0x18000d6af  test    rax, rax
0x18000d6b2  jnz     short loc_18000D6FA
0x18000d6b4  call    cs:__imp_GetLastError
0x18000d6ba  mov     ebx, eax
0x18000d6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6c3  lea     rdx, WPP_GLOBAL_Control
0x18000d6ca  cmp     rcx, rdx
0x18000d6cd  jz      loc_18000DA42
0x18000d6d3  test    byte ptr [rcx+1Ch], 1
0x18000d6d7  jz      loc_18000DA42
0x18000d6dd  mov     rcx, [rcx+10h]
0x18000d6e1  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d6e8  mov     edx, 108h
0x18000d6ed  mov     r9d, eax
0x18000d6f0  call    WPP_SF_d
0x18000d6f5  jmp     loc_18000DA42
0x18000d6fa  lea     r8, [rbp+nSize]; nSize
0x18000d6fe  mov     rdx, r13; lpNameBuffer
0x18000d701  mov     ecx, 2; NameFormat
0x18000d706  mov     r14, r15
0x18000d709  mov     r12, r15
0x18000d70c  mov     rsi, r15
0x18000d70f  call    cs:__imp_GetUserNameExW
0x18000d715  test    al, al
0x18000d717  jnz     short loc_18000D75A
0x18000d719  call    cs:__imp_GetLastError
0x18000d71f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d726  lea     rdx, WPP_GLOBAL_Control
0x18000d72d  cmp     rcx, rdx
0x18000d730  jz      short loc_18000D750
0x18000d732  test    byte ptr [rcx+1Ch], 1
0x18000d736  jz      short loc_18000D750
0x18000d738  mov     edx, 109h
0x18000d73d  mov     rcx, [rcx+10h]
0x18000d741  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d748  mov     r9d, eax
0x18000d74b  call    WPP_SF_d
0x18000d750  mov     ebx, 89Ah
0x18000d755  jmp     loc_18000DA01
0x18000d75a  lea     rax, [rbp+var_14]
0x18000d75e  xor     r9d, r9d; ReferencedDomainName
0x18000d761  mov     [rsp+48h+peUse], rax; peUse
0x18000d766  lea     r8, [rbp+cbSid]; cbSid
0x18000d76a  lea     rax, [rbp+arg_8]
0x18000d76e  xor     edx, edx; Sid
0x18000d770  mov     rcx, r13; lpAccountName
0x18000d773  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d778  call    cs:__imp_LookupAccountNameLocalW
0x18000d77e  test    eax, eax
0x18000d780  jnz     short loc_18000D7AD
0x18000d782  call    cs:__imp_GetLastError
0x18000d788  cmp     eax, 7Ah ; 'z'
0x18000d78b  jz      short loc_18000D7AD
0x18000d78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d794  lea     rdx, WPP_GLOBAL_Control
0x18000d79b  cmp     rcx, rdx
0x18000d79e  jz      short loc_18000D750
0x18000d7a0  test    byte ptr [rcx+1Ch], 1
0x18000d7a4  jz      short loc_18000D750
0x18000d7a6  mov     edx, 10Ah
0x18000d7ab  jmp     short loc_18000D73D
0x18000d7ad  mov     edx, [rbp+cbSid]; uBytes
0x18000d7b0  mov     ecx, 40h ; '@'; uFlags
0x18000d7b5  call    cs:__imp_LocalAlloc
0x18000d7bb  mov     r14, rax
0x18000d7be  test    rax, rax
0x18000d7c1  jnz     short loc_18000D809
0x18000d7c3  call    cs:__imp_GetLastError
0x18000d7c9  mov     ebx, eax
0x18000d7cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7d2  lea     rdx, WPP_GLOBAL_Control
0x18000d7d9  cmp     rcx, rdx
0x18000d7dc  jz      loc_18000DA01
0x18000d7e2  test    byte ptr [rcx+1Ch], 1
0x18000d7e6  jz      loc_18000DA01
0x18000d7ec  mov     edx, 10Bh
0x18000d7f1  mov     rcx, [rcx+10h]
0x18000d7f5  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d7fc  mov     r9d, eax
0x18000d7ff  call    WPP_SF_d
0x18000d804  jmp     loc_18000DA01
0x18000d809  mov     edx, [rbp+arg_8]
0x18000d80c  mov     ecx, 40h ; '@'; uFlags
0x18000d811  add     rdx, rdx; uBytes
0x18000d814  call    cs:__imp_LocalAlloc
0x18000d81a  mov     r12, rax
0x18000d81d  test    rax, rax
0x18000d820  jnz     short loc_18000D852
0x18000d822  call    cs:__imp_GetLastError
0x18000d828  mov     ebx, eax
0x18000d82a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d831  lea     rdx, WPP_GLOBAL_Control
0x18000d838  cmp     rcx, rdx
0x18000d83b  jz      loc_18000DA01
0x18000d841  test    byte ptr [rcx+1Ch], 1
0x18000d845  jz      loc_18000DA01
0x18000d84b  mov     edx, 10Ch
0x18000d850  jmp     short loc_18000D7F1
0x18000d852  lea     rax, [rbp+var_14]
0x18000d856  mov     r9, r12; ReferencedDomainName
0x18000d859  mov     [rsp+48h+peUse], rax; peUse
0x18000d85e  lea     r8, [rbp+cbSid]; cbSid
0x18000d862  lea     rax, [rbp+arg_8]
0x18000d866  mov     rdx, r14; Sid
0x18000d869  mov     rcx, r13; lpAccountName
0x18000d86c  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d871  call    cs:__imp_LookupAccountNameLocalW
0x18000d877  test    eax, eax
0x18000d879  jnz     short loc_18000D8AC
0x18000d87b  call    cs:__imp_GetLastError
0x18000d881  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d888  lea     rdx, WPP_GLOBAL_Control
0x18000d88f  cmp     rcx, rdx
0x18000d892  jz      loc_18000D750
0x18000d898  test    byte ptr [rcx+1Ch], 1
0x18000d89c  jz      loc_18000D750
0x18000d8a2  mov     edx, 10Dh
0x18000d8a7  jmp     loc_18000D73D
0x18000d8ac  lea     rax, [rbp+var_10]
0x18000d8b0  xor     r9d, r9d; ReferencedDomainName
0x18000d8b3  mov     [rsp+48h+peUse], rax; peUse
0x18000d8b8  lea     r8, [rbp+var_18]; cbSid
0x18000d8bc  lea     rax, [rbp+arg_18]
0x18000d8c0  xor     edx, edx; Sid
0x18000d8c2  mov     rcx, rdi; lpAccountName
0x18000d8c5  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d8ca  call    cs:__imp_LookupAccountNameLocalW
0x18000d8d0  test    eax, eax
0x18000d8d2  jnz     short loc_18000D90A
0x18000d8d4  call    cs:__imp_GetLastError
0x18000d8da  cmp     eax, 7Ah ; 'z'
0x18000d8dd  jz      short loc_18000D90A
0x18000d8df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8e6  lea     rdx, WPP_GLOBAL_Control
0x18000d8ed  cmp     rcx, rdx
0x18000d8f0  jz      loc_18000D750
0x18000d8f6  test    byte ptr [rcx+1Ch], 1
0x18000d8fa  jz      loc_18000D750
0x18000d900  mov     edx, 10Eh
0x18000d905  jmp     loc_18000D73D
0x18000d90a  mov     edx, [rbp+var_18]; uBytes
0x18000d90d  mov     ecx, 40h ; '@'; uFlags
0x18000d912  call    cs:__imp_LocalAlloc
0x18000d918  mov     rsi, rax
0x18000d91b  test    rax, rax
0x18000d91e  jnz     short loc_18000D953
0x18000d920  call    cs:__imp_GetLastError
0x18000d926  mov     ebx, eax
0x18000d928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d92f  lea     rdx, WPP_GLOBAL_Control
0x18000d936  cmp     rcx, rdx
0x18000d939  jz      loc_18000DA01
0x18000d93f  test    byte ptr [rcx+1Ch], 1
0x18000d943  jz      loc_18000DA01
0x18000d949  mov     edx, 10Fh
0x18000d94e  jmp     loc_18000D7F1
0x18000d953  mov     edx, [rbp+arg_18]
0x18000d956  mov     ecx, 40h ; '@'; uFlags
0x18000d95b  add     rdx, rdx; uBytes
0x18000d95e  call    cs:__imp_LocalAlloc
0x18000d964  mov     r15, rax
0x18000d967  test    rax, rax
0x18000d96a  jnz     short loc_18000D997
0x18000d96c  call    cs:__imp_GetLastError
0x18000d972  mov     ebx, eax
0x18000d974  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d97b  lea     rdx, WPP_GLOBAL_Control
0x18000d982  cmp     rcx, rdx
0x18000d985  jz      short loc_18000DA01
0x18000d987  test    byte ptr [rcx+1Ch], 1
0x18000d98b  jz      short loc_18000DA01
0x18000d98d  mov     edx, 110h
0x18000d992  jmp     loc_18000D7F1
0x18000d997  lea     rax, [rbp+var_10]
0x18000d99b  mov     r9, r15; ReferencedDomainName
0x18000d99e  mov     [rsp+48h+peUse], rax; peUse
0x18000d9a3  lea     r8, [rbp+var_18]; cbSid
0x18000d9a7  lea     rax, [rbp+arg_18]
0x18000d9ab  mov     rdx, rsi; Sid
0x18000d9ae  mov     rcx, rdi; lpAccountName
0x18000d9b1  mov     [rsp+48h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000d9b6  call    cs:__imp_LookupAccountNameLocalW
0x18000d9bc  test    eax, eax
0x18000d9be  jnz     short loc_18000D9F1
0x18000d9c0  call    cs:__imp_GetLastError
0x18000d9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9cd  lea     rdx, WPP_GLOBAL_Control
0x18000d9d4  cmp     rcx, rdx
0x18000d9d7  jz      loc_18000D750
0x18000d9dd  test    byte ptr [rcx+1Ch], 1
0x18000d9e1  jz      loc_18000D750
0x18000d9e7  mov     edx, 111h
0x18000d9ec  jmp     loc_18000D73D
0x18000d9f1  mov     rdx, r14; pSid2
0x18000d9f4  mov     rcx, rsi; pSid1
0x18000d9f7  call    cs:__imp_EqualSid
0x18000d9fd  mov     [rbx], eax
0x18000d9ff  xor     ebx, ebx
0x18000da01  mov     rcx, r13; hMem
0x18000da04  call    cs:__imp_LocalFree
0x18000da0a  test    r14, r14
0x18000da0d  jz      short loc_18000DA18
0x18000da0f  mov     rcx, r14; hMem
0x18000da12  call    cs:__imp_LocalFree
0x18000da18  test    rsi, rsi
0x18000da1b  jz      short loc_18000DA26
0x18000da1d  mov     rcx, rsi; hMem
0x18000da20  call    cs:__imp_LocalFree
0x18000da26  test    r12, r12
0x18000da29  jz      short loc_18000DA34
0x18000da2b  mov     rcx, r12; hMem
0x18000da2e  call    cs:__imp_LocalFree
0x18000da34  test    r15, r15
0x18000da37  jz      short loc_18000DA42
0x18000da39  mov     rcx, r15; hMem
0x18000da3c  call    cs:__imp_LocalFree
0x18000da42  mov     eax, ebx
0x18000da44  add     rsp, 48h
0x18000da48  pop     r15
0x18000da4a  pop     r14
0x18000da4c  pop     r13
0x18000da4e  pop     r12
0x18000da50  pop     rdi
0x18000da51  pop     rsi
0x18000da52  pop     rbx
0x18000da53  pop     rbp
0x18000da54  retn
```
