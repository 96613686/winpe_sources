# DupTokenAddAccess(void *,void * *,ulong,void * *)

- ea: `0x1800189f0`
- end: `0x180018eac`
- name: `?DupTokenAddAccess@@YAKPEAXPEAPEAXK1@Z`
- size: `1212`
- prototype: `__int64 __fastcall(char *hExistingToken, void **, unsigned int, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x1800189f0`
- `0x180018ec0`
- `0x180019230`
- `0x180019270`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018dc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e59`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018d3a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180018d3a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018ce2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180018ce2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018db7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180018db7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018a8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018b7d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018a8a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018b7d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018c67`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180018c67`

## string_xrefs

- `0x180018b3c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018cb5`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018e44`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018b23`: `DupTokenAddAccess`
- `0x180018ca7`: `DupTokenAddAccess`
- `0x180018e3d`: `DupTokenAddAccess`
- `0x180018aca`: `Failed to get size of default token\n`
- `0x180018bb4`: `Failed to get the default token\n`
- `0x180018b2a`: `Failed to resize the buffer for default dacl to %d\n`
- `0x180018c95`: `Failed to set entries in token\n`
- `0x180018d71`: `Failed to set DACL in SD\n`
- `0x180018dea`: `Unable to duplicate the cached anonymous token\n`

## pseudocode

```c
__int64 __fastcall DupTokenAddAccess(char *hExistingToken, void **a2, unsigned int a3, void **a4)
{
  unsigned __int64 v4; // rsi
  int LastError; // eax
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  struct _ACL *v12; // r15
  struct _EXPLICIT_ACCESS_W *v13; // rax
  struct _EXPLICIT_ACCESS_W *v14; // rdi
  unsigned int v15; // r9d
  __int64 v16; // rdx
  WCHAR *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  char *v20; // rcx
  unsigned int v21; // r8d
  char v23; // [rsp+30h] [rbp-79h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-69h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-61h] BYREF
  void *phNewToken; // [rsp+50h] [rbp-59h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+58h] [rbp-51h] BYREF
  __int128 pSecurityDescriptor; // [rsp+70h] [rbp-39h] BYREF
  __int128 v29; // [rsp+80h] [rbp-29h]
  __int64 v30; // [rsp+90h] [rbp-19h]
  _QWORD v31[4]; // [rsp+98h] [rbp-11h] BYREF
  void *TokenInformation; // [rsp+B8h] [rbp+Fh]
  int v33; // [rsp+C0h] [rbp+17h]
  __int16 v34; // [rsp+C4h] [rbp+1Bh]

  v4 = a3;
  v30 = 0;
  TokenInformationLength = 0;
  TokenInformation = v31;
  phNewToken = 0;
  NewAcl = 0;
  v31[0] = 0;
  v33 = 32;
  v34 = 256;
  pSecurityDescriptor = 0;
  v29 = 0;
  memset(&TokenAttributes, 0, sizeof(TokenAttributes));
  if ( (unsigned __int64)(hExistingToken - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    BUFFER::~BUFFER((BUFFER *)v31);
    return 87;
  }
  if ( GetTokenInformation(hExistingToken, TokenDefaultDacl, 0, 0, &TokenInformationLength) )
  {
    v9 = 110;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        0x639u,
        "DupTokenAddAccess",
        0x8007006E,
        "Did not get an error when we expected to ( changed the error to this hr ) \n",
        v23);
    goto LABEL_48;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError != 122 )
  {
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        0x62Au,
        "DupTokenAddAccess",
        LastError,
        "Failed to get size of default token\n",
        v23);
    }
    goto LABEL_48;
  }
  if ( !BUFFER::Resize((BUFFER *)v31, TokenInformationLength) )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        0x648u,
        "DupTokenAddAccess",
        v10,
        "Failed to resize the buffer for default dacl to %d\n",
        TokenInformationLength);
    }
    goto LABEL_48;
  }
  memset_0(TokenInformation, 0, TokenInformationLength);
  if ( !GetTokenInformation(
          hExistingToken,
          TokenDefaultDacl,
          TokenInformation,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    v11 = GetLastError();
    v9 = v11;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        0x661u,
        "DupTokenAddAccess",
        v11,
        "Failed to get the default token\n",
        v23);
    }
    goto LABEL_48;
  }
  v12 = *(struct _ACL **)TokenInformation;
  v13 = (struct _EXPLICIT_ACCESS_W *)operator new(saturated_mul(v4, 0x30u));
  v14 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 48 * v4);
    v15 = 0;
    if ( (_DWORD)v4 )
    {
      v16 = 0;
      do
      {
        v17 = (WCHAR *)a2[v16];
        v18 = v16;
        ++v15;
        ++v16;
        *(_QWORD *)&v14[v18].grfAccessMode = 1;
        v14[v18].Trustee.TrusteeForm = TRUSTEE_IS_SID;
        v14[v18].Trustee.TrusteeType = TRUSTEE_IS_USER;
        v14[v18].grfAccessPermissions = 0x10000000;
        v14[v18].Trustee.ptstrName = v17;
      }
      while ( v15 < (unsigned int)v4 );
    }
    v19 = SetEntriesInAclW(v4, v14, v12, &NewAcl);
    v9 = v19;
    if ( v19 )
    {
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = "Failed to set entries in token\n";
        v21 = 1681;
LABEL_28:
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          v21,
          "DupTokenAddAccess",
          v19,
          v20,
          v23);
      }
    }
    else
    {
      v30 = 0;
      pSecurityDescriptor = 0;
      v29 = 0;
      if ( !InitializeSecurityDescriptor(&pSecurityDescriptor, 1u) )
      {
        v19 = GetLastError();
        v9 = v19;
        if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
          goto LABEL_45;
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = "Error initializing SD\n";
        v21 = 1699;
        goto LABEL_28;
      }
      if ( !SetSecurityDescriptorDacl(&pSecurityDescriptor, 1, NewAcl, 0) )
      {
        v19 = GetLastError();
        v9 = v19;
        if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
          goto LABEL_45;
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = "Failed to set DACL in SD\n";
        v21 = 1713;
        goto LABEL_28;
      }
      *(_QWORD *)&TokenAttributes.nLength = 24;
      TokenAttributes.lpSecurityDescriptor = &pSecurityDescriptor;
      *(_QWORD *)&TokenAttributes.bInheritHandle = 0;
      if ( DuplicateTokenEx(
             hExistingToken,
             0x2000000u,
             &TokenAttributes,
             SecurityImpersonation,
             TokenImpersonation,
             &phNewToken) )
      {
        *a4 = phNewToken;
        goto LABEL_45;
      }
      v19 = GetLastError();
      v9 = v19;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
        v20 = "Unable to duplicate the cached anonymous token\n";
        v21 = 1743;
        goto LABEL_28;
      }
    }
LABEL_45:
    operator delete(v14);
    goto LABEL_48;
  }
  v9 = 14;
LABEL_48:
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v31);
  return v9;
}

```

## disassembly

```asm
0x1800189f0  mov     [rsp-8+arg_8], rbx
0x1800189f5  push    rbp
0x1800189f6  push    rsi
0x1800189f7  push    rdi
0x1800189f8  push    r12
0x1800189fa  push    r13
0x1800189fc  push    r14
0x1800189fe  push    r15
0x180018a00  lea     rbp, [rsp-27h]
0x180018a05  sub     rsp, 0D0h
0x180018a0c  mov     rax, cs:__security_cookie
0x180018a13  xor     rax, rsp
0x180018a16  mov     [rbp+57h+var_38], rax
0x180018a1a  xor     eax, eax
0x180018a1c  mov     esi, r8d
0x180018a1f  xor     r15d, r15d
0x180018a22  mov     [rbp+57h+var_70], rax
0x180018a26  xorps   xmm0, xmm0
0x180018a29  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x180018a2d  lea     rax, [rbp+57h+var_68]
0x180018a31  mov     [rbp+57h+TokenInformationLength], r15d
0x180018a35  mov     [rbp+57h+TokenInformation], rax
0x180018a39  mov     r12, r9
0x180018a3c  lea     rax, [rcx-1]
0x180018a40  mov     [rbp+57h+var_B0], r15
0x180018a44  mov     [rbp+57h+NewAcl], r15
0x180018a48  mov     r13, rdx
0x180018a4b  mov     [rbp+57h+var_68], r15
0x180018a4f  mov     r14, rcx
0x180018a52  mov     [rbp+57h+var_40], 20h ; ' '
0x180018a59  mov     [rbp+57h+var_3C], 100h
0x180018a5f  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180018a63  movups  [rbp+57h+var_80], xmm0
0x180018a67  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x180018a6b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018a6f  ja      loc_180018E76
0x180018a75  lea     rax, [rbp+57h+TokenInformationLength]
0x180018a79  xor     r9d, r9d; TokenInformationLength
0x180018a7c  lea     edi, [r15+6]
0x180018a80  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180018a85  mov     edx, edi; TokenInformationClass
0x180018a87  xor     r8d, r8d; TokenInformation
0x180018a8a  call    cs:__imp_GetTokenInformation
0x180018a91  nop     dword ptr [rax+rax+00h]
0x180018a96  test    eax, eax
0x180018a98  jnz     loc_180018E0E
0x180018a9e  call    cs:__imp_GetLastError
0x180018aa5  nop     dword ptr [rax+rax+00h]
0x180018aaa  mov     ebx, eax
0x180018aac  cmp     eax, 7Ah ; 'z'
0x180018aaf  jz      short loc_180018AE5
0x180018ab1  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018ab8  jz      loc_180018E50
0x180018abe  test    eax, eax
0x180018ac0  jle     short loc_180018ACA
0x180018ac2  movzx   eax, ax
0x180018ac5  or      eax, 80070000h
0x180018aca  lea     rcx, aFailedToGetSiz; "Failed to get size of default token\n"
0x180018ad1  mov     r8d, 62Ah
0x180018ad7  mov     [rsp+100h+phNewToken], rcx
0x180018adc  mov     dword ptr [rsp+100h+ReturnLength], eax
0x180018ae0  jmp     loc_180018E36
0x180018ae5  mov     edx, [rbp+57h+TokenInformationLength]; unsigned int
0x180018ae8  lea     rcx, [rbp+57h+var_68]; this
0x180018aec  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180018af1  test    al, al
0x180018af3  jnz     short loc_180018B58
0x180018af5  call    cs:__imp_GetLastError
0x180018afc  nop     dword ptr [rax+rax+00h]
0x180018b01  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018b08  mov     ebx, eax
0x180018b0a  jz      loc_180018E50
0x180018b10  mov     ecx, [rbp+57h+TokenInformationLength]
0x180018b13  test    eax, eax
0x180018b15  jle     short loc_180018B1F
0x180018b17  movzx   eax, ax
0x180018b1a  or      eax, 80070000h
0x180018b1f  mov     dword ptr [rsp+100h+var_D0], ecx; char
0x180018b23  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180018b2a  lea     rcx, aFailedToResize_0; "Failed to resize the buffer for default"...
0x180018b31  mov     r8d, 648h; unsigned int
0x180018b37  mov     [rsp+100h+phNewToken], rcx; char *
0x180018b3c  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018b43  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018b4a  mov     dword ptr [rsp+100h+ReturnLength], eax; dwMessageId
0x180018b4e  call    PuDbgPrintError
0x180018b53  jmp     loc_180018E50
0x180018b58  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x180018b5c  xor     edx, edx; Val
0x180018b5e  mov     rcx, [rbp+57h+TokenInformation]; void *
0x180018b62  call    memset_0
0x180018b67  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180018b6b  lea     rax, [rbp+57h+TokenInformationLength]
0x180018b6f  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180018b73  mov     edx, edi; TokenInformationClass
0x180018b75  mov     rcx, r14; TokenHandle
0x180018b78  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180018b7d  call    cs:__imp_GetTokenInformation
0x180018b84  nop     dword ptr [rax+rax+00h]
0x180018b89  test    eax, eax
0x180018b8b  jnz     short loc_180018BCF
0x180018b8d  call    cs:__imp_GetLastError
0x180018b94  nop     dword ptr [rax+rax+00h]
0x180018b99  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018ba0  mov     ebx, eax
0x180018ba2  jz      loc_180018E50
0x180018ba8  test    eax, eax
0x180018baa  jle     short loc_180018BB4
0x180018bac  movzx   eax, ax
0x180018baf  or      eax, 80070000h
0x180018bb4  lea     rcx, aFailedToGetThe; "Failed to get the default token\n"
0x180018bbb  mov     r8d, 661h
0x180018bc1  mov     [rsp+100h+phNewToken], rcx
0x180018bc6  mov     dword ptr [rsp+100h+ReturnLength], eax
0x180018bca  jmp     loc_180018E36
0x180018bcf  mov     rax, [rbp+57h+TokenInformation]
0x180018bd3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018bda  mov     r15, [rax]
0x180018bdd  mov     eax, 30h ; '0'
0x180018be2  mul     rsi
0x180018be5  cmovb   rax, rcx
0x180018be9  mov     rcx, rax; Size
0x180018bec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018bf1  mov     rdi, rax
0x180018bf4  test    rax, rax
0x180018bf7  jnz     short loc_180018C04
0x180018bf9  lea     ebx, [rax+0Eh]
0x180018bfc  xor     r15d, r15d
0x180018bff  jmp     loc_180018E50
0x180018c04  lea     r8, [rsi+rsi*2]
0x180018c08  xor     edx, edx; Val
0x180018c0a  shl     r8, 4; Size
0x180018c0e  mov     rcx, rdi; void *
0x180018c11  call    memset_0
0x180018c16  xor     r9d, r9d
0x180018c19  test    esi, esi
0x180018c1b  jz      short loc_180018C5B
0x180018c1d  xor     edx, edx
0x180018c1f  mov     rcx, [r13+rdx*8+0]
0x180018c24  lea     rax, [rdx+rdx*2]
0x180018c28  add     rax, rax
0x180018c2b  inc     r9d
0x180018c2e  inc     rdx
0x180018c31  mov     qword ptr [rdi+rax*8+4], 1
0x180018c3a  mov     dword ptr [rdi+rax*8+1Ch], 0
0x180018c42  mov     dword ptr [rdi+rax*8+20h], 1
0x180018c4a  mov     dword ptr [rdi+rax*8], 10000000h
0x180018c51  mov     [rdi+rax*8+28h], rcx
0x180018c56  cmp     r9d, esi
0x180018c59  jb      short loc_180018C1F
0x180018c5b  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180018c5f  mov     r8, r15; OldAcl
0x180018c62  mov     rdx, rdi; pListOfExplicitEntries
0x180018c65  mov     ecx, esi; cCountOfExplicitEntries
0x180018c67  call    cs:__imp_SetEntriesInAclW
0x180018c6e  nop     dword ptr [rax+rax+00h]
0x180018c73  xor     r15d, r15d
0x180018c76  mov     ebx, eax
0x180018c78  test    eax, eax
0x180018c7a  jz      short loc_180018CCA
0x180018c7c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018c83  jz      loc_180018E04
0x180018c89  test    eax, eax
0x180018c8b  jle     short loc_180018C95
0x180018c8d  movzx   eax, ax
0x180018c90  or      eax, 80070000h
0x180018c95  lea     rcx, aFailedToSetEnt; "Failed to set entries in token\n"
0x180018c9c  mov     r8d, 691h; unsigned int
0x180018ca2  mov     [rsp+100h+phNewToken], rcx; char *
0x180018ca7  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180018cae  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018cb5  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018cbc  mov     dword ptr [rsp+100h+ReturnLength], eax; dwMessageId
0x180018cc0  call    PuDbgPrintError
0x180018cc5  jmp     loc_180018E04
0x180018cca  xor     eax, eax
0x180018ccc  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180018cd0  xorps   xmm0, xmm0
0x180018cd3  mov     [rbp+57h+var_70], rax
0x180018cd7  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180018cdb  lea     edx, [rax+1]; dwRevision
0x180018cde  movups  [rbp+57h+var_80], xmm0
0x180018ce2  call    cs:__imp_InitializeSecurityDescriptor
0x180018ce9  nop     dword ptr [rax+rax+00h]
0x180018cee  test    eax, eax
0x180018cf0  jnz     short loc_180018D2B
0x180018cf2  call    cs:__imp_GetLastError
0x180018cf9  nop     dword ptr [rax+rax+00h]
0x180018cfe  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018d05  mov     ebx, eax
0x180018d07  jz      loc_180018E04
0x180018d0d  test    eax, eax
0x180018d0f  jle     short loc_180018D19
0x180018d11  movzx   eax, ax
0x180018d14  or      eax, 80070000h
0x180018d19  lea     rcx, aErrorInitializ; "Error initializing SD\n"
0x180018d20  mov     r8d, 6A3h
0x180018d26  jmp     loc_180018CA2
0x180018d2b  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180018d2f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180018d33  xor     r9d, r9d; bDaclDefaulted
0x180018d36  lea     edx, [r9+1]; bDaclPresent
0x180018d3a  call    cs:__imp_SetSecurityDescriptorDacl
0x180018d41  nop     dword ptr [rax+rax+00h]
0x180018d46  test    eax, eax
0x180018d48  jnz     short loc_180018D83
0x180018d4a  call    cs:__imp_GetLastError
0x180018d51  nop     dword ptr [rax+rax+00h]
0x180018d56  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018d5d  mov     ebx, eax
0x180018d5f  jz      loc_180018E04
0x180018d65  test    eax, eax
0x180018d67  jle     short loc_180018D71
0x180018d69  movzx   eax, ax
0x180018d6c  or      eax, 80070000h
0x180018d71  lea     rcx, aFailedToSetDac; "Failed to set DACL in SD\n"
0x180018d78  mov     r8d, 6B1h
0x180018d7e  jmp     loc_180018CA2
0x180018d83  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180018d87  mov     qword ptr [rbp+57h+TokenAttributes.nLength], 18h
0x180018d8f  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], rax
0x180018d93  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180018d97  lea     rax, [rbp+57h+var_B0]
0x180018d9b  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], r15
0x180018d9f  mov     r9d, 2; ImpersonationLevel
0x180018da5  mov     [rsp+100h+phNewToken], rax; phNewToken
0x180018daa  mov     edx, 2000000h; dwDesiredAccess
0x180018daf  mov     dword ptr [rsp+100h+ReturnLength], r9d; TokenType
0x180018db4  mov     rcx, r14; hExistingToken
0x180018db7  call    cs:__imp_DuplicateTokenEx
0x180018dbe  nop     dword ptr [rax+rax+00h]
0x180018dc3  test    eax, eax
0x180018dc5  jnz     short loc_180018DFC
0x180018dc7  call    cs:__imp_GetLastError
0x180018dce  nop     dword ptr [rax+rax+00h]
0x180018dd3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018dda  mov     ebx, eax
0x180018ddc  jz      short loc_180018E04
0x180018dde  test    eax, eax
0x180018de0  jle     short loc_180018DEA
0x180018de2  movzx   eax, ax
0x180018de5  or      eax, 80070000h
0x180018dea  lea     rcx, aUnableToDuplic; "Unable to duplicate the cached anonymou"...
0x180018df1  mov     r8d, 6CFh
0x180018df7  jmp     loc_180018CA2
0x180018dfc  mov     rax, [rbp+57h+var_B0]
0x180018e00  mov     [r12], rax
0x180018e04  mov     rcx, rdi; Block
0x180018e07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018e0c  jmp     short loc_180018E50
0x180018e0e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018e15  mov     ebx, 6Eh ; 'n'
0x180018e1a  jz      short loc_180018E50
0x180018e1c  lea     rax, aDidNotGetAnErr; "Did not get an error when we expected t"...
0x180018e23  mov     r8d, 639h; unsigned int
0x180018e29  mov     [rsp+100h+phNewToken], rax; char *
0x180018e2e  mov     dword ptr [rsp+100h+ReturnLength], 8007006Eh; dwMessageId
0x180018e36  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018e3d  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180018e44  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018e4b  call    PuDbgPrintError
0x180018e50  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180018e54  test    rcx, rcx
0x180018e57  jz      short loc_180018E69
0x180018e59  call    cs:__imp_LocalFree
0x180018e60  nop     dword ptr [rax+rax+00h]
0x180018e65  mov     [rbp+57h+NewAcl], r15
0x180018e69  lea     rcx, [rbp+57h+var_68]; this
0x180018e6d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018e72  mov     eax, ebx
0x180018e74  jmp     short loc_180018E84
0x180018e76  lea     rcx, [rbp+57h+var_68]; this
0x180018e7a  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018e7f  mov     eax, 57h ; 'W'
0x180018e84  mov     rcx, [rbp+57h+var_38]
0x180018e88  xor     rcx, rsp; StackCookie
0x180018e8b  call    __security_check_cookie
0x180018e90  mov     rbx, [rsp+100h+arg_8]
0x180018e98  add     rsp, 0D0h
0x180018e9f  pop     r15
0x180018ea1  pop     r14
0x180018ea3  pop     r13
0x180018ea5  pop     r12
0x180018ea7  pop     rdi
0x180018ea8  pop     rsi
0x180018ea9  pop     rbp
0x180018eaa  retn
```
