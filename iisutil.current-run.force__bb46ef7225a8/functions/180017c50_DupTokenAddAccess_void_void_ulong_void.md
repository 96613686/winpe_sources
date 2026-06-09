# DupTokenAddAccess(void *,void * *,ulong,void * *)

- ea: `0x180017c50`
- end: `0x1800180ba`
- name: `?DupTokenAddAccess@@YAKPEAXPEAPEAXK1@Z`
- size: `1130`
- prototype: `unsigned int __fastcall(HANDLE hExistingToken, void **, unsigned int, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180002470`
- `0x180002b60`
- `0x180017c50`
- `0x1800180c0`
- `0x1800183f8`
- `0x180018438`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017fe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001806e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001806e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180017f67`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180017f67`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180017f1e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180017f1e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017fd8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017fd8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017cea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017dcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017cea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017dcb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017ea9`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180017ea9`

## string_xrefs

- `0x180017d8a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017ef1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180018059`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017d71`: `DupTokenAddAccess`
- `0x180017ee3`: `DupTokenAddAccess`
- `0x180018052`: `DupTokenAddAccess`
- `0x180017d1e`: `Failed to get size of default token\n`
- `0x180017df6`: `Failed to get the default token\n`
- `0x180017d78`: `Failed to resize the buffer for default dacl to %d\n`
- `0x180017ed1`: `Failed to set entries in token\n`
- `0x180017f92`: `Failed to set DACL in SD\n`
- `0x180017fff`: `Unable to duplicate the cached anonymous token\n`

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
0x180017c50  mov     [rsp-8+arg_8], rbx
0x180017c55  push    rbp
0x180017c56  push    rsi
0x180017c57  push    rdi
0x180017c58  push    r12
0x180017c5a  push    r13
0x180017c5c  push    r14
0x180017c5e  push    r15
0x180017c60  lea     rbp, [rsp-27h]
0x180017c65  sub     rsp, 0D0h
0x180017c6c  mov     rax, cs:__security_cookie
0x180017c73  xor     rax, rsp
0x180017c76  mov     [rbp+57h+var_38], rax
0x180017c7a  xor     eax, eax
0x180017c7c  mov     esi, r8d
0x180017c7f  xor     r15d, r15d
0x180017c82  mov     [rbp+57h+var_70], rax
0x180017c86  xorps   xmm0, xmm0
0x180017c89  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rax
0x180017c8d  lea     rax, [rbp+57h+var_68]
0x180017c91  mov     [rbp+57h+TokenInformationLength], r15d
0x180017c95  mov     [rbp+57h+TokenInformation], rax
0x180017c99  mov     r12, r9
0x180017c9c  lea     rax, [rcx-1]
0x180017ca0  mov     [rbp+57h+var_B0], r15
0x180017ca4  mov     [rbp+57h+NewAcl], r15
0x180017ca8  mov     r13, rdx
0x180017cab  mov     [rbp+57h+var_68], r15
0x180017caf  mov     r14, rcx
0x180017cb2  mov     [rbp+57h+var_40], 20h ; ' '
0x180017cb9  mov     [rbp+57h+var_3C], 100h
0x180017cbf  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180017cc3  movups  [rbp+57h+var_80], xmm0
0x180017cc7  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x180017ccb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017ccf  ja      loc_180018085
0x180017cd5  lea     rax, [rbp+57h+TokenInformationLength]
0x180017cd9  xor     r9d, r9d; TokenInformationLength
0x180017cdc  lea     edi, [r15+6]
0x180017ce0  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180017ce5  mov     edx, edi; TokenInformationClass
0x180017ce7  xor     r8d, r8d; TokenInformation
0x180017cea  call    cs:__imp_GetTokenInformation
0x180017cf0  test    eax, eax
0x180017cf2  jnz     loc_180018023
0x180017cf8  call    cs:__imp_GetLastError
0x180017cfe  mov     ebx, eax
0x180017d00  cmp     eax, 7Ah ; 'z'
0x180017d03  jz      short loc_180017D39
0x180017d05  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017d0c  jz      loc_180018065
0x180017d12  test    eax, eax
0x180017d14  jle     short loc_180017D1E
0x180017d16  movzx   eax, ax
0x180017d19  or      eax, 80070000h
0x180017d1e  lea     rcx, aFailedToGetSiz; "Failed to get size of default token\n"
0x180017d25  mov     r8d, 62Ah
0x180017d2b  mov     [rsp+100h+phNewToken], rcx
0x180017d30  mov     dword ptr [rsp+100h+ReturnLength], eax
0x180017d34  jmp     loc_18001804B
0x180017d39  mov     edx, [rbp+57h+TokenInformationLength]; unsigned int
0x180017d3c  lea     rcx, [rbp+57h+var_68]; this
0x180017d40  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180017d45  test    al, al
0x180017d47  jnz     short loc_180017DA6
0x180017d49  call    cs:__imp_GetLastError
0x180017d4f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017d56  mov     ebx, eax
0x180017d58  jz      loc_180018065
0x180017d5e  mov     ecx, [rbp+57h+TokenInformationLength]
0x180017d61  test    eax, eax
0x180017d63  jle     short loc_180017D6D
0x180017d65  movzx   eax, ax
0x180017d68  or      eax, 80070000h
0x180017d6d  mov     dword ptr [rsp+100h+var_D0], ecx; char
0x180017d71  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180017d78  lea     rcx, aFailedToResize_0; "Failed to resize the buffer for default"...
0x180017d7f  mov     r8d, 648h; unsigned int
0x180017d85  mov     [rsp+100h+phNewToken], rcx; char *
0x180017d8a  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017d91  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017d98  mov     dword ptr [rsp+100h+ReturnLength], eax; dwMessageId
0x180017d9c  call    PuDbgPrintError
0x180017da1  jmp     loc_180018065
0x180017da6  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x180017daa  xor     edx, edx; Val
0x180017dac  mov     rcx, [rbp+57h+TokenInformation]; void *
0x180017db0  call    memset_0
0x180017db5  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180017db9  lea     rax, [rbp+57h+TokenInformationLength]
0x180017dbd  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180017dc1  mov     edx, edi; TokenInformationClass
0x180017dc3  mov     rcx, r14; TokenHandle
0x180017dc6  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180017dcb  call    cs:__imp_GetTokenInformation
0x180017dd1  test    eax, eax
0x180017dd3  jnz     short loc_180017E11
0x180017dd5  call    cs:__imp_GetLastError
0x180017ddb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017de2  mov     ebx, eax
0x180017de4  jz      loc_180018065
0x180017dea  test    eax, eax
0x180017dec  jle     short loc_180017DF6
0x180017dee  movzx   eax, ax
0x180017df1  or      eax, 80070000h
0x180017df6  lea     rcx, aFailedToGetThe; "Failed to get the default token\n"
0x180017dfd  mov     r8d, 661h
0x180017e03  mov     [rsp+100h+phNewToken], rcx
0x180017e08  mov     dword ptr [rsp+100h+ReturnLength], eax
0x180017e0c  jmp     loc_18001804B
0x180017e11  mov     rax, [rbp+57h+TokenInformation]
0x180017e15  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180017e1c  mov     r15, [rax]
0x180017e1f  mov     eax, 30h ; '0'
0x180017e24  mul     rsi
0x180017e27  cmovb   rax, rcx
0x180017e2b  mov     rcx, rax; Size
0x180017e2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e33  mov     rdi, rax
0x180017e36  test    rax, rax
0x180017e39  jnz     short loc_180017E46
0x180017e3b  lea     ebx, [rax+0Eh]
0x180017e3e  xor     r15d, r15d
0x180017e41  jmp     loc_180018065
0x180017e46  lea     r8, [rsi+rsi*2]
0x180017e4a  xor     edx, edx; Val
0x180017e4c  shl     r8, 4; Size
0x180017e50  mov     rcx, rdi; void *
0x180017e53  call    memset_0
0x180017e58  xor     r9d, r9d
0x180017e5b  test    esi, esi
0x180017e5d  jz      short loc_180017E9D
0x180017e5f  xor     edx, edx
0x180017e61  mov     rcx, [r13+rdx*8+0]
0x180017e66  lea     rax, [rdx+rdx*2]
0x180017e6a  add     rax, rax
0x180017e6d  inc     r9d
0x180017e70  inc     rdx
0x180017e73  mov     qword ptr [rdi+rax*8+4], 1
0x180017e7c  mov     dword ptr [rdi+rax*8+1Ch], 0
0x180017e84  mov     dword ptr [rdi+rax*8+20h], 1
0x180017e8c  mov     dword ptr [rdi+rax*8], 10000000h
0x180017e93  mov     [rdi+rax*8+28h], rcx
0x180017e98  cmp     r9d, esi
0x180017e9b  jb      short loc_180017E61
0x180017e9d  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180017ea1  mov     r8, r15; OldAcl
0x180017ea4  mov     rdx, rdi; pListOfExplicitEntries
0x180017ea7  mov     ecx, esi; cCountOfExplicitEntries
0x180017ea9  call    cs:__imp_SetEntriesInAclW
0x180017eaf  xor     r15d, r15d
0x180017eb2  mov     ebx, eax
0x180017eb4  test    eax, eax
0x180017eb6  jz      short loc_180017F06
0x180017eb8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017ebf  jz      loc_180018019
0x180017ec5  test    eax, eax
0x180017ec7  jle     short loc_180017ED1
0x180017ec9  movzx   eax, ax
0x180017ecc  or      eax, 80070000h
0x180017ed1  lea     rcx, aFailedToSetEnt; "Failed to set entries in token\n"
0x180017ed8  mov     r8d, 691h; unsigned int
0x180017ede  mov     [rsp+100h+phNewToken], rcx; char *
0x180017ee3  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180017eea  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017ef1  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017ef8  mov     dword ptr [rsp+100h+ReturnLength], eax; dwMessageId
0x180017efc  call    PuDbgPrintError
0x180017f01  jmp     loc_180018019
0x180017f06  xor     eax, eax
0x180017f08  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180017f0c  xorps   xmm0, xmm0
0x180017f0f  mov     [rbp+57h+var_70], rax
0x180017f13  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180017f17  lea     edx, [rax+1]; dwRevision
0x180017f1a  movups  [rbp+57h+var_80], xmm0
0x180017f1e  call    cs:__imp_InitializeSecurityDescriptor
0x180017f24  test    eax, eax
0x180017f26  jnz     short loc_180017F58
0x180017f28  call    cs:__imp_GetLastError
0x180017f2e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017f35  mov     ebx, eax
0x180017f37  jz      loc_180018019
0x180017f3d  test    eax, eax
0x180017f3f  jle     short loc_180017F49
0x180017f41  movzx   eax, ax
0x180017f44  or      eax, 80070000h
0x180017f49  lea     rcx, aErrorInitializ; "Error initializing SD\n"
0x180017f50  mov     r8d, 6A3h
0x180017f56  jmp     short loc_180017EDE
0x180017f58  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180017f5c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180017f60  xor     r9d, r9d; bDaclDefaulted
0x180017f63  lea     edx, [r9+1]; bDaclPresent
0x180017f67  call    cs:__imp_SetSecurityDescriptorDacl
0x180017f6d  test    eax, eax
0x180017f6f  jnz     short loc_180017FA4
0x180017f71  call    cs:__imp_GetLastError
0x180017f77  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017f7e  mov     ebx, eax
0x180017f80  jz      loc_180018019
0x180017f86  test    eax, eax
0x180017f88  jle     short loc_180017F92
0x180017f8a  movzx   eax, ax
0x180017f8d  or      eax, 80070000h
0x180017f92  lea     rcx, aFailedToSetDac; "Failed to set DACL in SD\n"
0x180017f99  mov     r8d, 6B1h
0x180017f9f  jmp     loc_180017EDE
0x180017fa4  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180017fa8  mov     qword ptr [rbp+57h+TokenAttributes.nLength], 18h
0x180017fb0  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], rax
0x180017fb4  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180017fb8  lea     rax, [rbp+57h+var_B0]
0x180017fbc  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], r15
0x180017fc0  mov     r9d, 2; ImpersonationLevel
0x180017fc6  mov     [rsp+100h+phNewToken], rax; phNewToken
0x180017fcb  mov     edx, 2000000h; dwDesiredAccess
0x180017fd0  mov     dword ptr [rsp+100h+ReturnLength], r9d; TokenType
0x180017fd5  mov     rcx, r14; hExistingToken
0x180017fd8  call    cs:__imp_DuplicateTokenEx
0x180017fde  test    eax, eax
0x180017fe0  jnz     short loc_180018011
0x180017fe2  call    cs:__imp_GetLastError
0x180017fe8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017fef  mov     ebx, eax
0x180017ff1  jz      short loc_180018019
0x180017ff3  test    eax, eax
0x180017ff5  jle     short loc_180017FFF
0x180017ff7  movzx   eax, ax
0x180017ffa  or      eax, 80070000h
0x180017fff  lea     rcx, aUnableToDuplic; "Unable to duplicate the cached anonymou"...
0x180018006  mov     r8d, 6CFh
0x18001800c  jmp     loc_180017EDE
0x180018011  mov     rax, [rbp+57h+var_B0]
0x180018015  mov     [r12], rax
0x180018019  mov     rcx, rdi; Block
0x18001801c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018021  jmp     short loc_180018065
0x180018023  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18001802a  mov     ebx, 6Eh ; 'n'
0x18001802f  jz      short loc_180018065
0x180018031  lea     rax, aDidNotGetAnErr; "Did not get an error when we expected t"...
0x180018038  mov     r8d, 639h; unsigned int
0x18001803e  mov     [rsp+100h+phNewToken], rax; char *
0x180018043  mov     dword ptr [rsp+100h+ReturnLength], 8007006Eh; dwMessageId
0x18001804b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180018052  lea     r9, aDuptokenaddacc_0; "DupTokenAddAccess"
0x180018059  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018060  call    PuDbgPrintError
0x180018065  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180018069  test    rcx, rcx
0x18001806c  jz      short loc_180018078
0x18001806e  call    cs:__imp_LocalFree
0x180018074  mov     [rbp+57h+NewAcl], r15
0x180018078  lea     rcx, [rbp+57h+var_68]; this
0x18001807c  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018081  mov     eax, ebx
0x180018083  jmp     short loc_180018093
0x180018085  lea     rcx, [rbp+57h+var_68]; this
0x180018089  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001808e  mov     eax, 57h ; 'W'
0x180018093  mov     rcx, [rbp+57h+var_38]
0x180018097  xor     rcx, rsp; StackCookie
0x18001809a  call    __security_check_cookie
0x18001809f  mov     rbx, [rsp+100h+arg_8]
0x1800180a7  add     rsp, 0D0h
0x1800180ae  pop     r15
0x1800180b0  pop     r14
0x1800180b2  pop     r13
0x1800180b4  pop     r12
0x1800180b6  pop     rdi
0x1800180b7  pop     rsi
0x1800180b8  pop     rbp
0x1800180b9  retn
```
