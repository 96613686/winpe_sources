# CPSGetUserName(void *,ushort * *,ulong *)

- ea: `0x1800065b0`
- end: `0x180006c52`
- name: `?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z`
- size: `1698`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int16 **, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011014`
- `0x18001866c`
- `0x180019f40`
- `0x18002e130`

## callees

- `0x1800065b0`
- `0x180007f10`
- `0x18001d810`
- `0x18001e1b4`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180006c0a`
- `RPCRT4!RpcRevertToSelfEx` at `0x180006c0a`
- `RPCRT4!RpcImpersonateClient` at `0x180006b7c`
- `RPCRT4!RpcImpersonateClient` at `0x180006b7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800067a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800069f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800067a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800069f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800067bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800067bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800066cc`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1800066cc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800067f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800067f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006950`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006740`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006ac0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006740`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006ac0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006674`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006674`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006aa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006816`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800068df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800069c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800067d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800069c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800068ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bd8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006855`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006855`

## string_xrefs

- `0x18000669a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800066ee`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180006b98`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180006bbe`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x180006c38`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSGetUserName(_DWORD *a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned int *v3; // r15
  unsigned __int16 **v4; // r12
  int v6; // eax
  void *v7; // rdx
  DWORD v8; // ebx
  HLOCAL v9; // r14
  unsigned int v10; // esi
  int v11; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v13; // rbx
  int v14; // esi
  void *v15; // rdi
  void *v16; // rcx
  PSID *v17; // r12
  DWORD LengthSid; // r15d
  HLOCAL v19; // rax
  int v20; // ebx
  BOOL v21; // eax
  LPWSTR v22; // r10
  __int64 v23; // rcx
  __int16 *p_Src; // r9
  LPWSTR v25; // rdx
  __int64 v26; // r8
  __int16 *v27; // rax
  __int64 v28; // rax
  unsigned int v30; // edi
  unsigned __int64 v32; // rax
  unsigned __int16 *v33; // rax
  HANDLE v34; // rax
  __int128 v35; // xmm0
  __int64 v36; // xmm1_8
  void *v37; // rcx
  unsigned int v38; // eax
  DWORD v39; // edi
  void *v40; // rcx
  DWORD LastError; // eax
  __int64 v42; // r9
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+34h] [rbp-CCh]
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 **v47; // [rsp+48h] [rbp-B8h]
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v49; // [rsp+58h] [rbp-A8h]
  __int16 Src; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v51; // [rsp+62h] [rbp-9Eh]
  __int64 v52; // [rsp+72h] [rbp-8Eh]
  _BYTE TokenInformation[256]; // [rsp+270h] [rbp+170h] BYREF

  v3 = a3;
  v49 = a3;
  v4 = a2;
  v47 = a2;
  memset_0(&Src, 0, 0x20Au);
  if ( !a1 )
  {
LABEL_19:
    v9 = 0;
    v10 = 260;
    v11 = 0;
    TokenHandle = 0;
    v44 = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_49;
    v13 = TokenHandle;
    v14 = 0;
    TokenInformationLength = 0;
    v15 = 0;
    hObject = 0;
    if ( TokenHandle )
    {
      v16 = TokenHandle;
      hObject = TokenHandle;
    }
    else
    {
      v34 = GetCurrentThread();
      if ( !OpenThreadToken(v34, 8u, 1, &hObject) )
      {
LABEL_29:
        if ( hObject && hObject != v13 )
          CloseHandle(hObject);
        if ( !v14 )
          goto LABEL_45;
        StringSid = 0;
        v20 = 0;
        v21 = ConvertSidToStringSidW(v15, &StringSid);
        v22 = StringSid;
        if ( v21 )
        {
          v23 = 2147483646;
          p_Src = &Src;
          v25 = StringSid;
          v26 = 261;
          do
          {
            if ( !v23 )
              break;
            if ( !*v25 )
              break;
            *p_Src++ = *v25++;
            --v23;
            --v26;
          }
          while ( v26 );
          v27 = p_Src - 1;
          if ( v26 )
            v27 = p_Src;
          *v27 = 0;
          if ( v26 )
            v20 = 1;
        }
        if ( v22 )
          LocalFree(v22);
        if ( v20 )
          v11 = 1;
        else
LABEL_45:
          v11 = v44;
        if ( v15 )
          LocalFree(v15);
        v3 = v49;
        v10 = 260;
LABEL_49:
        if ( TokenHandle )
          CloseHandle(TokenHandle);
        if ( v11 )
        {
          v28 = -1;
          while ( *(&Src + ++v28) != 0 )
            ;
          v10 = v28 + 1;
        }
        if ( a1 && *a1 == 624 )
        {
          if ( a1[4] || *((_QWORD *)a1 + 3) )
          {
            if ( RevertToSelf() )
              goto LABEL_60;
            LastError = GetLastError();
            v42 = 858;
            goto LABEL_96;
          }
          v40 = (void *)*((_QWORD *)a1 + 1);
          if ( v40 )
          {
            LastError = RpcRevertToSelfEx(v40);
            if ( LastError )
            {
              v42 = 872;
LABEL_96:
              DebugTraceError(
                LastError,
                "dwLastError",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
                v42);
            }
          }
        }
LABEL_60:
        v30 = 8;
        if ( !v11 )
          return v30;
LABEL_69:
        v32 = 2LL * v10;
        if ( v32 > 0xFFFFFFFF )
        {
          return 534;
        }
        else
        {
          v33 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)v32);
          *v4 = v33;
          if ( v33 )
          {
            memcpy_0(v33, &Src, 2 * v10);
            if ( v3 )
              *v3 = v10;
            return 0;
          }
        }
        return v30;
      }
      v16 = hObject;
    }
    TokenInformationLength = 256;
    v17 = (PSID *)TokenInformation;
    if ( !GetTokenInformation(v16, TokenUser, TokenInformation, 0x100u, &TokenInformationLength)
      && GetLastError() == 122 )
    {
      v9 = LocalAlloc(0x40u, TokenInformationLength);
      if ( !v9 )
        goto LABEL_28;
      if ( !GetTokenInformation(hObject, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_27;
      v17 = (PSID *)v9;
    }
    LengthSid = GetLengthSid(*v17);
    v19 = LocalAlloc(0x40u, LengthSid);
    v15 = v19;
    if ( v19 )
    {
      if ( CopySid(LengthSid, v19, *v17) )
      {
        v14 = 1;
        goto LABEL_26;
      }
      LocalFree(v15);
    }
    v15 = 0;
LABEL_26:
    if ( !v9 )
    {
LABEL_28:
      v4 = v47;
      goto LABEL_29;
    }
LABEL_27:
    LocalFree(v9);
    goto LABEL_28;
  }
  if ( *a1 != 624 )
    return 87;
  v6 = a1[12];
  if ( a1[4] || v6 == 18 )
  {
    v35 = xmmword_180041552;
    v10 = 9;
LABEL_84:
    TokenInformationLength = 8;
    v30 = 8;
    Src = 83;
    v51 = v35;
    goto LABEL_69;
  }
  switch ( v6 )
  {
    case 19:
      v10 = 9;
      Src = 83;
      v51 = xmmword_180041622;
      v30 = 8;
      goto LABEL_69;
    case 20:
      TokenInformationLength = 8;
      v30 = 8;
      v10 = 9;
      v51 = xmmword_1800428CA;
      Src = 83;
      goto LABEL_69;
    case 90:
      v35 = xmmword_180042932;
      v36 = 0x31002D0032LL;
LABEL_83:
      v52 = v36;
      v10 = 13;
      goto LABEL_84;
    case 91:
      v35 = xmmword_18004290A;
      v36 = 0x32002D0032LL;
      goto LABEL_83;
  }
  if ( !a1[4] && (!v6 || (unsigned int)(v6 - 90) <= 1 || v6 == 99) )
  {
    v7 = (void *)*((_QWORD *)a1 + 3);
    if ( v7 )
    {
      if ( SetThreadToken(0, v7) )
        goto LABEL_19;
      v8 = GetLastError();
      DebugTraceError(v8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 752);
      if ( !v8 )
        goto LABEL_19;
    }
    else
    {
      v37 = (void *)*((_QWORD *)a1 + 1);
      if ( v37 )
      {
        v38 = RpcImpersonateClient(v37);
        v39 = v38;
        if ( !v38 )
          goto LABEL_19;
        DebugTraceError(v38, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 768);
        v8 = v39;
        goto LABEL_90;
      }
      v8 = 87;
    }
    v39 = v8;
LABEL_90:
    DebugTraceError(v39, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 825);
    return v8;
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
    goto LABEL_19;
  v8 = GetLastError();
  DebugTraceError(v8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 816);
  if ( !v8 )
    goto LABEL_19;
  return v8;
}

```

## disassembly

```asm
0x1800065b0  mov     [rsp-8+arg_18], rbx
0x1800065b5  push    rbp
0x1800065b6  push    rsi
0x1800065b7  push    rdi
0x1800065b8  push    r12
0x1800065ba  push    r13
0x1800065bc  push    r14
0x1800065be  push    r15
0x1800065c0  lea     rbp, [rsp-280h]
0x1800065c8  sub     rsp, 380h
0x1800065cf  mov     rax, cs:__security_cookie
0x1800065d6  xor     rax, rsp
0x1800065d9  mov     [rbp+2B0h+var_40], rax
0x1800065e0  mov     r15, r8
0x1800065e3  mov     [rsp+3B0h+var_358], r8
0x1800065e8  mov     r12, rdx
0x1800065eb  mov     [rsp+3B0h+var_368], rdx
0x1800065f0  mov     r13, rcx
0x1800065f3  xor     edx, edx; Val
0x1800065f5  mov     r8d, 20Ah; Size
0x1800065fb  lea     rcx, [rsp+3B0h+Src]; void *
0x180006600  call    memset_0
0x180006605  test    r13, r13
0x180006608  jz      loc_18000670D
0x18000660e  cmp     dword ptr [r13+0], 270h
0x180006616  jnz     loc_18000699E
0x18000661c  cmp     dword ptr [r13+10h], 0
0x180006621  mov     eax, [r13+30h]
0x180006625  jnz     loc_180006AE8
0x18000662b  cmp     eax, 12h
0x18000662e  jz      loc_180006AE8
0x180006634  cmp     eax, 13h
0x180006637  jz      loc_180006A15
0x18000663d  cmp     eax, 14h
0x180006640  jz      loc_180006AF6
0x180006646  cmp     eax, 5Ah ; 'Z'
0x180006649  jz      loc_180006B25
0x18000664f  cmp     eax, 5Bh ; '['
0x180006652  jz      loc_180006B36
0x180006658  cmp     dword ptr [r13+10h], 0
0x18000665d  jnz     short loc_1800066C7
0x18000665f  mov     ecx, eax
0x180006661  test    eax, eax
0x180006663  jnz     short loc_1800066BA
0x180006665  mov     rdx, [r13+18h]; Token
0x180006669  test    rdx, rdx
0x18000666c  jz      loc_180006B73
0x180006672  xor     ecx, ecx; Thread
0x180006674  call    cs:__imp_SetThreadToken
0x18000667b  nop     dword ptr [rax+rax+00h]
0x180006680  test    eax, eax
0x180006682  jnz     loc_18000670D
0x180006688  call    cs:__imp_GetLastError
0x18000668f  nop     dword ptr [rax+rax+00h]
0x180006694  mov     r9d, 2F0h
0x18000669a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800066a1  mov     ecx, eax
0x1800066a3  lea     rdx, aDwlasterror; "dwLastError"
0x1800066aa  mov     ebx, eax
0x1800066ac  call    DebugTraceError
0x1800066b1  test    ebx, ebx
0x1800066b3  jz      short loc_18000670D
0x1800066b5  jmp     loc_180006BB6
0x1800066ba  add     eax, 0FFFFFFA6h
0x1800066bd  cmp     eax, 1
0x1800066c0  jbe     short loc_180006665
0x1800066c2  cmp     ecx, 63h ; 'c'
0x1800066c5  jz      short loc_180006665
0x1800066c7  mov     ecx, 2; ImpersonationLevel
0x1800066cc  call    cs:__imp_ImpersonateSelf
0x1800066d3  nop     dword ptr [rax+rax+00h]
0x1800066d8  test    eax, eax
0x1800066da  jnz     short loc_18000670D
0x1800066dc  call    cs:__imp_GetLastError
0x1800066e3  nop     dword ptr [rax+rax+00h]
0x1800066e8  mov     r9d, 330h
0x1800066ee  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800066f5  mov     ecx, eax
0x1800066f7  lea     rdx, aDwlasterror; "dwLastError"
0x1800066fe  mov     ebx, eax
0x180006700  call    DebugTraceError
0x180006705  test    ebx, ebx
0x180006707  jnz     loc_1800069A3
0x18000670d  xor     r14d, r14d
0x180006710  mov     esi, 104h
0x180006715  mov     ebx, r14d
0x180006718  mov     [rsp+3B0h+TokenHandle], r14
0x18000671d  mov     [rsp+3B0h+var_37C], ebx
0x180006721  call    cs:__imp_GetCurrentThread
0x180006728  nop     dword ptr [rax+rax+00h]
0x18000672d  lea     r9, [rsp+3B0h+TokenHandle]; TokenHandle
0x180006732  mov     edx, 8; DesiredAccess
0x180006737  mov     rcx, rax; ThreadHandle
0x18000673a  mov     r8d, 1; OpenAsSelf
0x180006740  call    cs:__imp_OpenThreadToken
0x180006747  nop     dword ptr [rax+rax+00h]
0x18000674c  test    eax, eax
0x18000674e  jz      loc_1800068F5
0x180006754  mov     rbx, [rsp+3B0h+TokenHandle]
0x180006759  mov     esi, r14d
0x18000675c  mov     [rsp+3B0h+TokenInformationLength], r14d
0x180006761  mov     edi, r14d
0x180006764  mov     [rsp+3B0h+hObject], r14
0x180006769  test    rbx, rbx
0x18000676c  jz      loc_180006AA1
0x180006772  mov     rcx, rbx; TokenHandle
0x180006775  mov     [rsp+3B0h+hObject], rbx
0x18000677a  lea     rax, [rsp+3B0h+TokenInformationLength]
0x18000677f  mov     [rsp+3B0h+TokenInformationLength], 100h
0x180006787  mov     r9d, 100h; TokenInformationLength
0x18000678d  mov     [rsp+3B0h+ReturnLength], rax; ReturnLength
0x180006792  lea     r8, [rbp+2B0h+TokenInformation]; TokenInformation
0x180006799  mov     edx, 1; TokenInformationClass
0x18000679e  lea     r12, [rbp+2B0h+TokenInformation]
0x1800067a5  call    cs:__imp_GetTokenInformation
0x1800067ac  nop     dword ptr [rax+rax+00h]
0x1800067b1  test    eax, eax
0x1800067b3  jz      loc_1800069A7
0x1800067b9  mov     rcx, [r12]; pSid
0x1800067bd  call    cs:__imp_GetLengthSid
0x1800067c4  nop     dword ptr [rax+rax+00h]
0x1800067c9  mov     edx, eax; uBytes
0x1800067cb  mov     ecx, 40h ; '@'; uFlags
0x1800067d0  mov     r15d, eax
0x1800067d3  call    cs:__imp_LocalAlloc
0x1800067da  nop     dword ptr [rax+rax+00h]
0x1800067df  mov     rdi, rax
0x1800067e2  test    rax, rax
0x1800067e5  jz      loc_180006A99
0x1800067eb  mov     r8, [r12]; pSourceSid
0x1800067ef  mov     rdx, rax; pDestinationSid
0x1800067f2  mov     ecx, r15d; nDestinationSidLength
0x1800067f5  call    cs:__imp_CopySid
0x1800067fc  nop     dword ptr [rax+rax+00h]
0x180006801  test    eax, eax
0x180006803  jz      loc_180006A8A
0x180006809  mov     esi, 1
0x18000680e  test    r14, r14
0x180006811  jz      short loc_180006822
0x180006813  mov     rcx, r14; hMem
0x180006816  call    cs:__imp_LocalFree
0x18000681d  nop     dword ptr [rax+rax+00h]
0x180006822  mov     r12, [rsp+3B0h+var_368]
0x180006827  xor     r14d, r14d
0x18000682a  mov     rcx, [rsp+3B0h+hObject]; hObject
0x18000682f  test    rcx, rcx
0x180006832  jz      short loc_18000683D
0x180006834  cmp     rcx, rbx
0x180006837  jnz     loc_180006BD8
0x18000683d  test    esi, esi
0x18000683f  jz      loc_1800068D3
0x180006845  lea     rdx, [rsp+3B0h+StringSid]; StringSid
0x18000684a  mov     [rsp+3B0h+StringSid], r14
0x18000684f  mov     rcx, rdi; Sid
0x180006852  mov     ebx, r14d
0x180006855  call    cs:__imp_ConvertSidToStringSidW
0x18000685c  nop     dword ptr [rax+rax+00h]
0x180006861  mov     r10, [rsp+3B0h+StringSid]
0x180006866  test    eax, eax
0x180006868  jz      short loc_1800068B7
0x18000686a  mov     ecx, 7FFFFFFEh
0x18000686f  lea     r9, [rsp+3B0h+Src]
0x180006874  mov     rdx, r10
0x180006877  mov     r8d, 105h
0x18000687d  nop     dword ptr [rax]
0x180006880  test    rcx, rcx
0x180006883  jz      short loc_1800068A2
0x180006885  movzx   eax, word ptr [rdx]
0x180006888  test    ax, ax
0x18000688b  jz      short loc_1800068A2
0x18000688d  mov     [r9], ax
0x180006891  add     rdx, 2
0x180006895  add     r9, 2
0x180006899  dec     rcx
0x18000689c  sub     r8, 1
0x1800068a0  jnz     short loc_180006880
0x1800068a2  test    r8, r8
0x1800068a5  lea     rax, [r9-2]
0x1800068a9  cmovnz  rax, r9
0x1800068ad  mov     [rax], r14w
0x1800068b1  jnz     loc_180006BE9
0x1800068b7  test    r10, r10
0x1800068ba  jz      short loc_1800068CB
0x1800068bc  mov     rcx, r10; hMem
0x1800068bf  call    cs:__imp_LocalFree
0x1800068c6  nop     dword ptr [rax+rax+00h]
0x1800068cb  test    ebx, ebx
0x1800068cd  jnz     loc_180006BF3
0x1800068d3  mov     ebx, [rsp+3B0h+var_37C]
0x1800068d7  test    rdi, rdi
0x1800068da  jz      short loc_1800068EB
0x1800068dc  mov     rcx, rdi; hMem
0x1800068df  call    cs:__imp_LocalFree
0x1800068e6  nop     dword ptr [rax+rax+00h]
0x1800068eb  mov     r15, [rsp+3B0h+var_358]
0x1800068f0  mov     esi, 104h
0x1800068f5  mov     rcx, [rsp+3B0h+TokenHandle]; hObject
0x1800068fa  test    rcx, rcx
0x1800068fd  jz      short loc_18000690B
0x1800068ff  call    cs:__imp_CloseHandle
0x180006906  nop     dword ptr [rax+rax+00h]
0x18000690b  test    ebx, ebx
0x18000690d  jz      short loc_18000692F
0x18000690f  lea     rcx, [rsp+3B0h+Src]
0x180006914  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000691b  nop     dword ptr [rax+rax+00h]
0x180006920  cmp     word ptr [rcx+rax*2+2], 0
0x180006926  lea     rax, [rax+1]
0x18000692a  jnz     short loc_180006920
0x18000692c  lea     esi, [rax+1]
0x18000692f  test    r13, r13
0x180006932  jz      short loc_180006964
0x180006934  cmp     dword ptr [r13+0], 270h
0x18000693c  jnz     short loc_180006964
0x18000693e  cmp     dword ptr [r13+10h], 0
0x180006943  jnz     short loc_180006950
0x180006945  cmp     qword ptr [r13+18h], 0
0x18000694a  jz      loc_180006BFD
0x180006950  call    cs:__imp_RevertToSelf
0x180006957  nop     dword ptr [rax+rax+00h]
0x18000695c  test    eax, eax
0x18000695e  jz      loc_180006C26
0x180006964  mov     edi, 8
0x180006969  test    ebx, ebx
0x18000696b  jnz     loc_180006A38
0x180006971  mov     eax, edi
0x180006973  mov     rcx, [rbp+2B0h+var_40]
0x18000697a  xor     rcx, rsp; StackCookie
0x18000697d  call    __security_check_cookie
0x180006982  mov     rbx, [rsp+3B0h+arg_18]
0x18000698a  add     rsp, 380h
0x180006991  pop     r15
0x180006993  pop     r14
0x180006995  pop     r13
0x180006997  pop     r12
0x180006999  pop     rdi
0x18000699a  pop     rsi
0x18000699b  pop     rbp
0x18000699c  retn
0x18000699e  mov     ebx, 57h ; 'W'
0x1800069a3  mov     eax, ebx
0x1800069a5  jmp     short loc_180006973
0x1800069a7  call    cs:__imp_GetLastError
0x1800069ae  nop     dword ptr [rax+rax+00h]
0x1800069b3  cmp     eax, 7Ah ; 'z'
0x1800069b6  jnz     loc_1800067B9
0x1800069bc  mov     edx, [rsp+3B0h+TokenInformationLength]; uBytes
0x1800069c0  mov     ecx, 40h ; '@'; uFlags
0x1800069c5  call    cs:__imp_LocalAlloc
0x1800069cc  nop     dword ptr [rax+rax+00h]
0x1800069d1  mov     r14, rax
0x1800069d4  test    rax, rax
0x1800069d7  jz      loc_180006822
0x1800069dd  mov     r9d, [rsp+3B0h+TokenInformationLength]; TokenInformationLength
0x1800069e2  lea     rax, [rsp+3B0h+TokenInformationLength]
0x1800069e7  mov     rcx, [rsp+3B0h+hObject]; TokenHandle
0x1800069ec  mov     r8, r14; TokenInformation
0x1800069ef  mov     edx, 1; TokenInformationClass
0x1800069f4  mov     [rsp+3B0h+ReturnLength], rax; ReturnLength
0x1800069f9  call    cs:__imp_GetTokenInformation
0x180006a00  nop     dword ptr [rax+rax+00h]
0x180006a05  test    eax, eax
0x180006a07  jz      loc_180006813
0x180006a0d  mov     r12, r14
0x180006a10  jmp     loc_1800067B9
0x180006a15  movups  xmm0, cs:xmmword_180041622
0x180006a1c  mov     eax, 53h ; 'S'
0x180006a21  mov     esi, 9
0x180006a26  mov     [rsp+3B0h+Src], ax
0x180006a2b  xor     r14d, r14d
0x180006a2e  movups  [rsp+3B0h+var_34E], xmm0
0x180006a33  mov     edi, 8
0x180006a38  mov     eax, esi
0x180006a3a  mov     ecx, 0FFFFFFFFh
0x180006a3f  add     rax, rax
0x180006a42  cmp     rax, rcx
0x180006a45  ja      loc_180006ADE
0x180006a4b  mov     edx, eax; uBytes
0x180006a4d  xor     ecx, ecx; uFlags
0x180006a4f  mov     ebx, eax
0x180006a51  call    cs:__imp_LocalAlloc
0x180006a58  nop     dword ptr [rax+rax+00h]
0x180006a5d  mov     [r12], rax
0x180006a61  test    rax, rax
0x180006a64  jz      loc_180006971
0x180006a6a  mov     r8d, ebx; Size
0x180006a6d  lea     rdx, [rsp+3B0h+Src]; Src
0x180006a72  mov     rcx, rax; void *
0x180006a75  call    memcpy_0
0x180006a7a  test    r15, r15
0x180006a7d  jz      short loc_180006A82
0x180006a7f  mov     [r15], esi
0x180006a82  mov     edi, r14d
0x180006a85  jmp     loc_180006971
0x180006a8a  mov     rcx, rdi; hMem
0x180006a8d  call    cs:__imp_LocalFree
0x180006a94  nop     dword ptr [rax+rax+00h]
0x180006a99  mov     rdi, rsi
0x180006a9c  jmp     loc_18000680E
0x180006aa1  call    cs:__imp_GetCurrentThread
  ... truncated ...
```
