# DavCredUIPromptForCredentials

- ea: `0x18000bda0`
- end: `0x18000c169`
- name: `DavCredUIPromptForCredentials`
- size: `969`
- prototype: `__int64 __fastcall(__int64 *pUiInfo, LPCWSTR UncPath, __int64 pszTargetName, PCWSTR, unsigned int, PWSTR *, PWSTR *, PWSTR *, PWSTR *, PBOOL pfSave, int, DWORD dwFlags, unsigned int, _QWORD *, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007ad0`

## callees

- `0x18000b494`
- `0x18000bcc0`
- `0x18000bda0`
- `0x18000da5c`
- `0x180010c28`
- `0x180010d00`
- `0x180010e68`
- `0x180013010`

## import_xrefs

- `credui!SspiPromptForCredentialsW` at `0x18000c0cb`
- `credui!SspiPromptForCredentialsW` at `0x18000c0cb`
- `credui!CredUICmdLinePromptForCredentialsW` at `0x18000bfc2`
- `credui!CredUICmdLinePromptForCredentialsW` at `0x18000bfc2`

## pseudocode

```c
__int64 __fastcall DavCredUIPromptForCredentials(
        __int64 *pUiInfo,
        LPCWSTR UncPath,
        __int64 pszTargetName,
        PCWSTR a4,
        unsigned int a5,
        PWSTR *a6,
        PWSTR *a7,
        PWSTR *a8,
        PWSTR *a9,
        PBOOL pfSave,
        int a11,
        DWORD dwFlags,
        unsigned int a13,
        _QWORD *a14,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *a15)
{
  const WCHAR *v15; // r15
  const WCHAR *v16; // rdi
  __int64 *v18; // r14
  __int64 v19; // rdx
  PWSTR v20; // rcx
  void (__fastcall *v21)(PWSTR, __int64, _QWORD); // rdi
  int v22; // eax
  PWSTR *v23; // rsi
  DWORD v24; // edi
  PWSTR v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  PWSTR v28; // rcx
  const WCHAR *v29; // r9
  int v30; // r8d
  _QWORD *v31; // rcx
  __int64 v33; // [rsp+68h] [rbp-49h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity[2]; // [rsp+70h] [rbp-41h] BYREF
  __int128 pInputAuthIdentity; // [rsp+80h] [rbp-31h] BYREF
  __int128 v36; // [rsp+90h] [rbp-21h]
  __int128 v37; // [rsp+A0h] [rbp-11h]

  v15 = a4;
  pInputAuthIdentity = 0;
  v16 = (const WCHAR *)pszTargetName;
  v36 = 0;
  v18 = pUiInfo;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      321,
      (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
      (_DWORD)UncPath,
      pszTargetName);
  if ( !(unsigned int)CallBackRegistered() )
  {
    v23 = a6;
    goto LABEL_24;
  }
  ppAuthIdentity[1] = 0;
  LODWORD(ppAuthIdentity[0]) = 0;
  v20 = *a8;
  v21 = (void (__fastcall *)(PWSTR, __int64, _QWORD))*a14;
  LODWORD(v33) = 1;
  if ( v20 && v21 )
  {
    v21(v20, v19, 0);
    *a8 = 0;
  }
  if ( *a9 && v21 )
  {
    v21(*a9, v19, 0);
    *a9 = 0;
  }
  if ( *a14 )
    *a14 = 0;
  v22 = DavConvertHttpAuthDAVAuth(a13, a5, 0);
  v23 = a6;
  v24 = DavPromptForCredentialsUsingCallback(
          UncPath,
          (__int64)a7,
          (__int64)pfSave,
          a11,
          v22,
          (__int64)&v33,
          (__int64)ppAuthIdentity,
          (__int64)a14);
  if ( !v24 )
  {
    *a8 = *a6;
    *a9 = *a7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, *a8);
    if ( (_DWORD)v33 == 1 )
      return 13;
    if ( LODWORD(ppAuthIdentity[0]) == 1 )
      return v24;
    if ( LODWORD(ppAuthIdentity[0]) == 2 )
      return 1223;
    v16 = (const WCHAR *)pszTargetName;
    v18 = pUiInfo;
    v15 = a4;
LABEL_24:
    if ( (a11 & 0x800) != 0 )
    {
      v24 = CredUICmdLinePromptForCredentialsW(v16, 0, 0, *v23, 0x201u, *a7, 0x100u, pfSave, dwFlags);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 323, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, UncPath);
      return v24;
    }
    v25 = *v23;
    v26 = -1;
    ppAuthIdentity[0] = 0;
    *(_QWORD *)&pInputAuthIdentity = v25;
    if ( v25 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v25[v27] );
      DWORD2(pInputAuthIdentity) = v27;
    }
    else
    {
      DWORD2(pInputAuthIdentity) = 0;
    }
    v28 = *a7;
    *(_QWORD *)&v36 = 0;
    DWORD2(v36) = 0;
    *(_QWORD *)&v37 = v28;
    if ( v28 )
    {
      do
        ++v26;
      while ( v28[v26] );
      DWORD2(v37) = v26;
    }
    else
    {
      DWORD2(v37) = 0;
    }
    HIDWORD(v37) = 2;
    if ( a13 != 1 )
    {
      if ( a13 == 2 )
      {
        v29 = L"NTLM";
        goto LABEL_46;
      }
      if ( a13 != 4 )
      {
        if ( a13 == 8 )
        {
          v29 = L"WDigest";
          goto LABEL_46;
        }
        if ( a13 == 16 )
        {
          v29 = L"Negotiate";
          goto LABEL_46;
        }
      }
    }
    v29 = L"Basic";
LABEL_46:
    v24 = SspiPromptForCredentialsW(v15, v18, 0, v29, &pInputAuthIdentity, ppAuthIdentity, pfSave, 0);
    *a15 = ppAuthIdentity[0];
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v15);
        v31 = WPP_GLOBAL_Control;
      }
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 2) != 0 )
        WPP_SF_SSSS(v31[2], 325, v30, v18[3], v18[2], (__int64)v15, (__int64)*v23);
    }
  }
  return v24;
}

```

## disassembly

```asm
0x18000bda0  mov     rax, rsp
0x18000bda3  mov     [rax+10h], rbx
0x18000bda7  mov     [rax+20h], r9
0x18000bdab  mov     [rax+18h], r8
0x18000bdaf  mov     [rax+8], rcx
0x18000bdb3  push    rbp
0x18000bdb4  push    rsi
0x18000bdb5  push    rdi
0x18000bdb6  push    r12
0x18000bdb8  push    r13
0x18000bdba  push    r14
0x18000bdbc  push    r15
0x18000bdbe  lea     rbp, [rax-3Fh]
0x18000bdc2  sub     rsp, 0B0h
0x18000bdc9  xorps   xmm0, xmm0
0x18000bdcc  mov     r15, r9
0x18000bdcf  movups  [rbp+37h+pInputAuthIdentity], xmm0
0x18000bdd3  mov     rdi, r8
0x18000bdd6  mov     r12, rdx
0x18000bdd9  movups  [rbp+37h+var_58], xmm0
0x18000bddd  mov     r14, rcx
0x18000bde0  movups  [rbp+37h+var_48], xmm0
0x18000bde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdeb  lea     rax, WPP_GLOBAL_Control
0x18000bdf2  cmp     rcx, rax
0x18000bdf5  jz      short loc_18000BE1A
0x18000bdf7  test    byte ptr [rcx+1Ch], 2
0x18000bdfb  jz      short loc_18000BE1A
0x18000bdfd  mov     rcx, [rcx+10h]
0x18000be01  mov     edx, 141h
0x18000be06  mov     qword ptr [rsp+0E0h+ulUserBufferSize], r8
0x18000be0b  mov     r9, r12
0x18000be0e  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000be15  call    WPP_SF_SS
0x18000be1a  call    CallBackRegistered
0x18000be1f  mov     ebx, [rbp+37h+arg_60]
0x18000be25  xor     r8d, r8d
0x18000be28  mov     r13, [rbp+37h+arg_30]
0x18000be2c  test    eax, eax
0x18000be2e  jz      loc_18000BF66
0x18000be34  mov     r14, [rbp+37h+arg_38]
0x18000be38  mov     rsi, [rbp+37h+arg_68]
0x18000be3f  mov     [rbp+37h+var_70], r8
0x18000be43  mov     dword ptr [rbp+37h+ppAuthIdentity], r8d
0x18000be47  mov     rcx, [r14]
0x18000be4a  mov     rdi, [rsi]
0x18000be4d  mov     dword ptr [rbp+37h+var_80], 1
0x18000be54  test    rcx, rcx
0x18000be57  jz      short loc_18000BE6C
0x18000be59  test    rdi, rdi
0x18000be5c  jz      short loc_18000BE6C
0x18000be5e  mov     rax, rdi
0x18000be61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be66  xor     r8d, r8d
0x18000be69  mov     [r14], r8
0x18000be6c  mov     r15, [rbp+37h+arg_40]
0x18000be73  mov     rcx, [r15]
0x18000be76  test    rcx, rcx
0x18000be79  jz      short loc_18000BE8E
0x18000be7b  test    rdi, rdi
0x18000be7e  jz      short loc_18000BE8E
0x18000be80  mov     rax, rdi
0x18000be83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be88  xor     r8d, r8d
0x18000be8b  mov     [r15], r8
0x18000be8e  cmp     [rsi], r8
0x18000be91  jz      short loc_18000BE96
0x18000be93  mov     [rsi], r8
0x18000be96  mov     edx, [rbp+37h+arg_20]
0x18000be99  mov     ecx, ebx
0x18000be9b  call    DavConvertHttpAuthDAVAuth
0x18000bea0  mov     rdx, [rbp+37h+arg_10]
0x18000bea4  lea     rcx, [rbp+37h+ppAuthIdentity]
0x18000bea8  mov     [rsp+50h], rsi; __int64
0x18000bead  lea     r8, [rbp+37h+var_70]
0x18000beb1  mov     rsi, [rbp+37h+arg_28]
0x18000beb5  mov     [rsp+0E0h+var_98], rcx; __int64
0x18000beba  mov     r9, rsi
0x18000bebd  lea     rcx, [rbp+37h+var_80]
0x18000bec1  mov     qword ptr [rsp+0E0h+dwFlags], rcx; __int64
0x18000bec6  mov     rcx, r12; UncPath
0x18000bec9  mov     dword ptr [rsp+0E0h+pfSave], eax; int
0x18000becd  mov     eax, [rbp+37h+arg_50]
0x18000bed3  mov     [rsp+0E0h+ulPasswordBufferSize], eax; int
0x18000bed7  mov     rax, [rbp+37h+arg_48]
0x18000bede  mov     [rsp+0E0h+pszPassword], rax; __int64
0x18000bee3  mov     qword ptr [rsp+0E0h+ulUserBufferSize], r13; __int64
0x18000bee8  call    DavPromptForCredentialsUsingCallback
0x18000beed  xor     r8d, r8d
0x18000bef0  mov     edi, eax
0x18000bef2  test    eax, eax
0x18000bef4  jnz     loc_18000C14C
0x18000befa  mov     rcx, [rsi]
0x18000befd  mov     [r14], rcx
0x18000bf00  mov     rcx, [r13+0]
0x18000bf04  mov     [r15], rcx
0x18000bf07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf0e  lea     rax, WPP_GLOBAL_Control
0x18000bf15  cmp     rcx, rax
0x18000bf18  jz      short loc_18000BF3B
0x18000bf1a  test    byte ptr [rcx+1Ch], 2
0x18000bf1e  jz      short loc_18000BF3B
0x18000bf20  mov     r9, [r14]
0x18000bf23  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bf2a  mov     rcx, [rcx+10h]
0x18000bf2e  mov     edx, 142h
0x18000bf33  call    WPP_SF_S
0x18000bf38  xor     r8d, r8d
0x18000bf3b  cmp     dword ptr [rbp+37h+var_80], 1
0x18000bf3f  jnz     short loc_18000BF4B
0x18000bf41  mov     edi, 0Dh
0x18000bf46  jmp     loc_18000C14C
0x18000bf4b  mov     ecx, dword ptr [rbp+37h+ppAuthIdentity]
0x18000bf4e  sub     ecx, 1
0x18000bf51  jz      loc_18000C14C
0x18000bf57  cmp     ecx, 1
0x18000bf5a  jnz     short loc_18000BF6C
0x18000bf5c  mov     edi, 4C7h
0x18000bf61  jmp     loc_18000C14C
0x18000bf66  mov     rsi, [rbp+37h+arg_28]
0x18000bf6a  jmp     short loc_18000BF78
0x18000bf6c  mov     rdi, [rbp+37h+arg_10]
0x18000bf70  mov     r14, [rbp+37h+arg_0]
0x18000bf74  mov     r15, [rbp+37h+arg_18]
0x18000bf78  test    [rbp+37h+arg_50], 800h
0x18000bf82  jz      loc_18000C008
0x18000bf88  mov     eax, [rbp+37h+arg_58]
0x18000bf8e  xor     r8d, r8d; dwAuthError
0x18000bf91  mov     r9, [rsi]; UserName
0x18000bf94  xor     edx, edx; pContext
0x18000bf96  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x18000bf9a  mov     rcx, rdi; pszTargetName
0x18000bf9d  mov     rax, [rbp+37h+arg_48]
0x18000bfa4  mov     [rsp+0E0h+pfSave], rax; pfSave
0x18000bfa9  mov     rax, [r13+0]
0x18000bfad  mov     [rsp+0E0h+ulPasswordBufferSize], 100h; ulPasswordBufferSize
0x18000bfb5  mov     [rsp+0E0h+pszPassword], rax; pszPassword
0x18000bfba  mov     [rsp+0E0h+ulUserBufferSize], 201h; ulUserBufferSize
0x18000bfc2  call    cs:__imp_CredUICmdLinePromptForCredentialsW
0x18000bfc8  mov     edi, eax
0x18000bfca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfd1  lea     rax, WPP_GLOBAL_Control
0x18000bfd8  cmp     rcx, rax
0x18000bfdb  jz      loc_18000C14C
0x18000bfe1  test    byte ptr [rcx+1Ch], 2
0x18000bfe5  jz      loc_18000C14C
0x18000bfeb  mov     rcx, [rcx+10h]
0x18000bfef  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000bff6  mov     edx, 143h
0x18000bffb  mov     r9, r12
0x18000bffe  call    WPP_SF_S
0x18000c003  jmp     loc_18000C14C
0x18000c008  mov     rdx, [rsi]
0x18000c00b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c00f  mov     [rbp+37h+ppAuthIdentity], r8
0x18000c013  mov     qword ptr [rbp+37h+pInputAuthIdentity], rdx
0x18000c017  test    rdx, rdx
0x18000c01a  jz      short loc_18000C02E
0x18000c01c  mov     rcx, rax
0x18000c01f  inc     rcx
0x18000c022  cmp     [rdx+rcx*2], r8w
0x18000c027  jnz     short loc_18000C01F
0x18000c029  mov     dword ptr [rbp+37h+pInputAuthIdentity+8], ecx
0x18000c02c  jmp     short loc_18000C032
0x18000c02e  mov     dword ptr [rbp+37h+pInputAuthIdentity+8], r8d
0x18000c032  mov     rcx, [r13+0]
0x18000c036  mov     qword ptr [rbp+37h+var_58], r8
0x18000c03a  mov     dword ptr [rbp+37h+var_58+8], r8d
0x18000c03e  mov     qword ptr [rbp+37h+var_48], rcx
0x18000c042  test    rcx, rcx
0x18000c045  jz      short loc_18000C056
0x18000c047  inc     rax
0x18000c04a  cmp     [rcx+rax*2], r8w
0x18000c04f  jnz     short loc_18000C047
0x18000c051  mov     dword ptr [rbp+37h+var_48+8], eax
0x18000c054  jmp     short loc_18000C05A
0x18000c056  mov     dword ptr [rbp+37h+var_48+8], r8d
0x18000c05a  mov     r12d, 2
0x18000c060  mov     dword ptr [rbp+37h+var_48+0Ch], r12d
0x18000c064  sub     ebx, 1
0x18000c067  jz      short loc_18000C098
0x18000c069  sub     ebx, 1
0x18000c06c  jz      short loc_18000C08F
0x18000c06e  sub     ebx, r12d
0x18000c071  jz      short loc_18000C098
0x18000c073  sub     ebx, 4
0x18000c076  jz      short loc_18000C086
0x18000c078  cmp     ebx, 8
0x18000c07b  jnz     short loc_18000C098
0x18000c07d  lea     r9, aNegotiate; "Negotiate"
0x18000c084  jmp     short loc_18000C09F
0x18000c086  lea     r9, aWdigest; "WDigest"
0x18000c08d  jmp     short loc_18000C09F
0x18000c08f  lea     r9, aNtlm; "NTLM"
0x18000c096  jmp     short loc_18000C09F
0x18000c098  lea     r9, pszPackage; "Basic"
0x18000c09f  mov     rax, [rbp+37h+arg_48]
0x18000c0a6  mov     rdx, r14; pUiInfo
0x18000c0a9  mov     dword ptr [rsp+0E0h+pfSave], r8d; dwFlags
0x18000c0ae  mov     rcx, r15; pszTargetName
0x18000c0b1  mov     qword ptr [rsp+0E0h+ulPasswordBufferSize], rax; pfSave
0x18000c0b6  xor     r8d, r8d; dwAuthError
0x18000c0b9  lea     rax, [rbp+37h+ppAuthIdentity]
0x18000c0bd  mov     [rsp+0E0h+pszPassword], rax; ppAuthIdentity
0x18000c0c2  lea     rax, [rbp+37h+pInputAuthIdentity]
0x18000c0c6  mov     qword ptr [rsp+0E0h+ulUserBufferSize], rax; pInputAuthIdentity
0x18000c0cb  call    cs:__imp_SspiPromptForCredentialsW
0x18000c0d1  mov     rcx, [rbp+37h+arg_70]
0x18000c0d8  mov     edi, eax
0x18000c0da  mov     rax, [rbp+37h+ppAuthIdentity]
0x18000c0de  mov     [rcx], rax
0x18000c0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0e8  lea     rbx, WPP_GLOBAL_Control
0x18000c0ef  cmp     rcx, rbx
0x18000c0f2  jz      short loc_18000C14C
0x18000c0f4  test    [rcx+1Ch], r12b
0x18000c0f8  jz      short loc_18000C119
0x18000c0fa  mov     rcx, [rcx+10h]
0x18000c0fe  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000c105  mov     edx, 144h
0x18000c10a  mov     r9, r15
0x18000c10d  call    WPP_SF_S
0x18000c112  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c119  cmp     rcx, rbx
0x18000c11c  jz      short loc_18000C14C
0x18000c11e  test    [rcx+1Ch], r12b
0x18000c122  jz      short loc_18000C14C
0x18000c124  mov     rax, [rsi]
0x18000c127  mov     edx, 145h
0x18000c12c  mov     r9, [r14+18h]
0x18000c130  mov     rcx, [rcx+10h]
0x18000c134  mov     qword ptr [rsp+0E0h+ulPasswordBufferSize], rax
0x18000c139  mov     rax, [r14+10h]
0x18000c13d  mov     [rsp+0E0h+pszPassword], r15
0x18000c142  mov     qword ptr [rsp+0E0h+ulUserBufferSize], rax
0x18000c147  call    WPP_SF_SSSS
0x18000c14c  mov     rbx, [rsp+0E0h+arg_8]
0x18000c154  mov     eax, edi
0x18000c156  add     rsp, 0B0h
0x18000c15d  pop     r15
0x18000c15f  pop     r14
0x18000c161  pop     r13
0x18000c163  pop     r12
0x18000c165  pop     rdi
0x18000c166  pop     rsi
0x18000c167  pop     rbp
0x18000c168  retn
```
