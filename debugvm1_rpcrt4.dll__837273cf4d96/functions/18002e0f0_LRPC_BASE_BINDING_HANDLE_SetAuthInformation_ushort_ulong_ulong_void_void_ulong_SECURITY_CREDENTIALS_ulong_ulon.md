# LRPC_BASE_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)

- ea: `0x18002e0f0`
- end: `0x18002e96d`
- name: `?SetAuthInformation@LRPC_BASE_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z`
- size: `2173`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, PSID pSourceSid, int, int, PSECURITY_DESCRIPTOR CreatorDescriptor)`
- caller_count: `6`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d760`
- `0x18002da30`
- `0x18002dc2c`
- `0x18002fa70`
- `0x180067778`
- `0x18008b050`

## callees

- `0x180022870`
- `0x1800283bc`
- `0x18002d420`
- `0x18002e0f0`
- `0x18002f460`
- `0x18002ff38`
- `0x180030754`
- `0x18004980c`
- `0x18004f938`
- `0x180083f1c`
- `0x18008fcc8`
- `0x1800b66a0`
- `0x1800b7670`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18002e484`
- `ntdll!NtOpenThreadToken` at `0x18002e484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e88a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e88a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e325`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e46a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e46a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e778`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e778`
- `SspiCli!SspiValidateAuthIdentity` at `0x18002e714`
- `SspiCli!SspiValidateAuthIdentity` at `0x18002e714`
- `SspiCli!LogonUserExExW` at `0x18002e87c`
- `SspiCli!LogonUserExExW` at `0x18002e87c`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_BINDING_HANDLE::SetAuthInformation(
        LRPC_BASE_BINDING_HANDLE *this,
        unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData,
        void *a6,
        unsigned int a7,
        struct SECURITY_CREDENTIALS *a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        void *a14,
        PSID pSourceSid,
        int a16,
        int a17,
        PSECURITY_DESCRIPTOR CreatorDescriptor)
{
  PSID v18; // r15
  int v20; // esi
  DWORD LowPart; // ebx
  int v22; // r14d
  void *v23; // rcx
  unsigned int v24; // eax
  void *v25; // r13
  int v26; // ecx
  unsigned __int16 *v27; // r12
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  int v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  char *v36; // rcx
  unsigned __int16 *v37; // rsi
  unsigned int v38; // r12d
  HANDLE CurrentThread; // rax
  NTSTATUS v41; // eax
  __int64 v42; // rax
  unsigned int v43; // eax
  SID_CACHE *v44; // rcx
  __int64 v45; // rax
  __int64 (__fastcall *v46)(LRPC_BASE_BINDING_HANDLE *); // rax
  int v47; // eax
  unsigned __int16 v48; // r8
  DWORD v49; // eax
  DWORD LastError; // eax
  unsigned __int16 *v51; // [rsp+60h] [rbp-A0h]
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+70h] [rbp-90h]
  void *v54; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *Src; // [rsp+80h] [rbp-80h]
  struct _LUID v56; // [rsp+88h] [rbp-78h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR ppszUserName; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR ppszPackedCredentialsString; // [rsp+A0h] [rbp-60h] BYREF
  PCWSTR ppszDomainName; // [rsp+A8h] [rbp-58h] BYREF
  int v61; // [rsp+B0h] [rbp-50h] BYREF
  DWORD v62; // [rsp+B8h] [rbp-48h]
  void *v63; // [rsp+C8h] [rbp-38h]
  _OWORD TokenInformation[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct _LUID v65; // [rsp+100h] [rbp+0h]

  v18 = pSourceSid;
  Src = a2;
  v20 = a3;
  v63 = AuthData;
  LowPart = 0;
  v54 = 0;
  TokenHandle = 0;
  v56 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v65 = 0;
  ReturnLength = 0;
  ppszUserName = 0;
  ppszPackedCredentialsString = 0;
  ppszDomainName = 0;
  if ( a13 || a14 )
  {
    RpcpErrorAddRecord(2u, 1764, 0x35Cu, 0, 0);
    return 1764;
  }
  if ( a3 <= 6 )
  {
    if ( a3 != 1 )
      v20 = 6;
    v22 = 10;
    if ( a4 != 20 )
      v22 = a4;
    if ( v22 != 10 && v22 )
    {
      RpcpErrorAddRecord(2u, 1747, 0x35Du, 0, 0);
      return 1747;
    }
    if ( !AuthData )
    {
LABEL_10:
      v23 = (void *)*((_QWORD *)this + 51);
      if ( v23 )
      {
        FreeWrapper(v23);
        *((_QWORD *)this + 51) = 0;
      }
      if ( CreatorDescriptor
        && (unsigned int)RpcpNormalizeSecurityDescriptor(CreatorDescriptor, 0x18u, (void **)this + 51) )
      {
        return 14;
      }
      v24 = a11;
      v25 = 0;
      v53 = 0;
      v26 = 0;
      v51 = 0;
      v27 = 0;
      if ( (a11 & 1) == 0 )
        goto LABEL_14;
      if ( pSourceSid )
      {
LABEL_55:
        a11 = v24 | 0x10;
LABEL_14:
        if ( v18 )
        {
          if ( !v26 )
          {
            v18 = DuplicateSID(v18);
            if ( !v18 )
            {
              v38 = 14;
              v37 = 0;
              goto LABEL_40;
            }
            v53 = 1;
          }
          v25 = DuplicateSID(v18);
          if ( !v25 )
          {
            v38 = 14;
LABEL_61:
            v37 = v51;
LABEL_40:
            if ( ppszUserName )
              WipeAndFreeEncodedString(ppszUserName);
            if ( ppszPackedCredentialsString )
              WipeAndFreeEncodedString(ppszPackedCredentialsString);
            if ( ppszDomainName )
              WipeAndFreeEncodedString(ppszDomainName);
            if ( TokenHandle )
              CloseCapturedToken(TokenHandle);
            if ( v18 && v53 )
              FreeWrapper(v18);
            if ( v25 )
              FreeWrapper(v25);
            if ( v37 )
              FreeWrapper(v37);
            return v38;
          }
        }
        if ( Src )
        {
          if ( *Src )
          {
            v51 = DuplicateString(Src);
            v27 = v51;
            if ( !v51 )
            {
              v38 = 14;
              v37 = 0;
              goto LABEL_40;
            }
          }
        }
        v28 = a10;
        if ( a10 )
        {
LABEL_17:
          *((_DWORD *)this + 21) = 10;
          *((_QWORD *)this + 14) = 0;
          *((_QWORD *)this + 15) = a6;
          if ( v22 )
          {
            *((_DWORD *)this + 104) = v28;
            *((_DWORD *)this + 33) = v28;
            v29 = 1;
            if ( v20 != 1 )
              v29 = a9;
            *((_DWORD *)this + 32) = a7;
            v30 = v29;
            *((_DWORD *)this + 20) = v20;
            if ( !v29 )
              v30 = 3;
            *((_DWORD *)this + 34) = v29;
            *((_DWORD *)this + 105) = v30;
            if ( a17 )
              v31 = (*(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *, __int64))(*(_QWORD *)this + 424LL))(this, 3);
            else
              v31 = a16;
            v32 = a11;
          }
          else
          {
            v45 = *(_QWORD *)this;
            *((_DWORD *)this + 20) = 6;
            *((_DWORD *)this + 32) = 0;
            *((_DWORD *)this + 105) = 3;
            v46 = *(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(v45 + 416);
            *((_DWORD *)this + 34) = 3;
            v47 = v46(this);
            *((_DWORD *)this + 104) = v47;
            v32 = 0;
            *((_DWORD *)this + 33) = v47;
            v31 = (*(__int64 (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(*(_QWORD *)this + 424LL))(this);
          }
          if ( v31 )
            *((_DWORD *)this + 124) |= 2u;
          else
            *((_DWORD *)this + 124) &= ~2u;
          v33 = (void *)*((_QWORD *)this + 13);
          *((_DWORD *)this + 35) = v32;
          if ( v33 )
            FreeWrapper(v33);
          *((_QWORD *)this + 13) = v18;
          v18 = 0;
          v34 = (void *)*((_QWORD *)this + 50);
          if ( v34 )
            FreeWrapper(v34);
          *((_QWORD *)this + 50) = v25;
          v25 = 0;
          v35 = (void *)*((_QWORD *)this + 12);
          if ( v35 )
            FreeWrapper(v35);
          v36 = (char *)*((_QWORD *)this + 63);
          v37 = 0;
          *((_QWORD *)this + 12) = v27;
          if ( v36 )
          {
            if ( (unsigned __int64)(v36 - 0xFFFFFFFDLL) > 1 )
              CloseHandle(v36);
            *((_QWORD *)this + 63) = 0;
            *((_QWORD *)this + 64) = 0;
          }
          if ( !*((_DWORD *)this + 104) )
          {
            *((_QWORD *)this + 63) = TokenHandle;
            *((_DWORD *)this + 129) = v56.HighPart;
            TokenHandle = 0;
            *((_DWORD *)this + 128) = LowPart;
          }
          v38 = 0;
          goto LABEL_40;
        }
        if ( v63 )
        {
          if ( !(unsigned int)EncodeAuthIdentityAsStrings(
                                v63,
                                &ppszUserName,
                                &ppszDomainName,
                                &ppszPackedCredentialsString) )
          {
            if ( !(unsigned int)LogonUserExExW(
                                  ppszUserName,
                                  ppszDomainName,
                                  ppszPackedCredentialsString,
                                  3,
                                  3,
                                  0,
                                  &TokenHandle,
                                  0,
                                  0,
                                  0,
                                  0) )
            {
              LastError = GetLastError();
              if ( LastError == 5 || LastError != 14 && (LastError == 1314 || LastError == 1326 || LastError == 1385) )
                v38 = 5;
              else
                v38 = 14;
              v62 = LastError;
              v61 = 3;
              RpcpErrorAddRecord(2u, v38, 0x363u, 1, (struct tagParam *)&v61);
              v37 = v51;
              TokenHandle = 0;
              goto LABEL_40;
            }
            if ( !GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
            {
              v49 = GetLastError();
              v38 = v49;
              if ( v49 )
              {
                RpcpErrorAddRecord(2u, v49, 0x364u, 0, 0);
                v37 = v51;
                goto LABEL_40;
              }
              v27 = v51;
            }
            LowPart = v65.LowPart;
            v56 = v65;
LABEL_69:
            v28 = 0;
            goto LABEL_17;
          }
          v38 = 87;
          RpcpErrorAddRecord(2u, 87, 0x365u, 0, 0);
        }
        else
        {
          CurrentThread = GetCurrentThread();
          v38 = 14;
          v41 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, &TokenHandle);
          switch ( v41 )
          {
            case -1073741700:
              v42 = 4294967293LL;
LABEL_66:
              TokenHandle = (void *)v42;
LABEL_67:
              v38 = CaptureModifiedIdEx(&v56);
              if ( v38 )
                goto LABEL_61;
              LowPart = v56.LowPart;
              v27 = v51;
              goto LABEL_69;
            case -1073741790:
              v38 = 5;
              break;
            case -1073741658:
              v42 = 4294967294LL;
              goto LABEL_66;
            case 0:
              goto LABEL_67;
          }
          v62 = v41;
          TokenHandle = 0;
          v61 = 3;
          RpcpErrorAddRecord(2u, v38, 0x460u, 1, (struct tagParam *)&v61);
        }
        v37 = v51;
        goto LABEL_40;
      }
      if ( *(_QWORD *)&SIDCache.Revision )
      {
        v38 = SID_CACHE::Query(0, Src, &v54);
        if ( !v38 )
        {
          v18 = v54;
          if ( v54 )
            goto LABEL_76;
          v43 = RpcpLookupAccountNameDirect(Src, &v54);
          v18 = v54;
          v38 = v43;
          if ( v43 == 1789 )
          {
            v38 = 5;
          }
          else if ( !v43 && *(_QWORD *)&SIDCache.Revision )
          {
            SID_CACHE::Add(v44, Src, v54, 0);
          }
          if ( !v38 )
          {
LABEL_76:
            v24 = a11;
            v26 = 1;
            v53 = 1;
            v27 = 0;
            goto LABEL_55;
          }
        }
      }
      else
      {
        v38 = 14;
      }
      RpcpErrorAddRecord(2u, v38, 0x35Eu, 0, 0);
      v18 = 0;
      v37 = 0;
      goto LABEL_40;
    }
    if ( SspiValidateAuthIdentity(AuthData) >= 0 )
    {
      if ( !a10 )
        goto LABEL_10;
      v48 = 866;
    }
    else
    {
      v48 = 865;
    }
    v38 = 87;
    RpcpErrorAddRecord(2u, 87, v48, 0, 0);
    return v38;
  }
  v62 = a3;
  v61 = 3;
  RpcpErrorAddRecord(2u, 1748, 0x360u, 1, (struct tagParam *)&v61);
  return 1748;
}

```

## disassembly

```asm
0x18002e0f0  push    rbp
0x18002e0f2  push    rbx
0x18002e0f3  push    rsi
0x18002e0f4  push    rdi
0x18002e0f5  push    r13
0x18002e0f7  push    r15
0x18002e0f9  lea     rbp, [rsp-18h]
0x18002e0fe  sub     rsp, 118h
0x18002e105  mov     rax, cs:__security_cookie
0x18002e10c  xor     rax, rsp
0x18002e10f  mov     [rbp+40h+var_38], rax
0x18002e113  mov     r15, [rbp+40h+pSourceSid]
0x18002e11a  xorps   xmm0, xmm0
0x18002e11d  mov     r13, [rbp+40h+CreatorDescriptor]
0x18002e124  xor     eax, eax
0x18002e126  mov     [rbp+40h+Src], rdx
0x18002e12a  mov     rdi, rcx
0x18002e12d  mov     rcx, [rbp+40h+AuthData]; AuthData
0x18002e131  xor     edx, edx
0x18002e133  mov     esi, r8d
0x18002e136  mov     [rbp+40h+var_78], rcx
0x18002e13a  mov     ebx, edx
0x18002e13c  mov     [rsp+140h+var_C8], rdx
0x18002e141  mov     [rsp+140h+TokenHandle], rdx
0x18002e146  mov     qword ptr [rbp+40h+var_B8.LowPart], rdx
0x18002e14a  movups  [rbp+40h+TokenInformation], xmm0
0x18002e14e  mov     [rbp+40h+var_40], rax
0x18002e152  movups  [rbp+40h+var_60], xmm0
0x18002e156  mov     [rbp+40h+var_B0], edx
0x18002e159  movups  [rbp+40h+var_50], xmm0
0x18002e15d  mov     [rbp+40h+ppszUserName], rdx
0x18002e161  mov     [rbp+40h+ppszPackedCredentialsString], rdx
0x18002e165  mov     [rbp+40h+ppszDomainName], rdx
0x18002e169  cmp     [rbp+40h+arg_60], eax
0x18002e16f  jnz     loc_18002E566
0x18002e175  cmp     [rbp+40h+arg_68], rax
0x18002e17c  jnz     loc_18002E566
0x18002e182  cmp     r8d, 6
0x18002e186  ja      loc_18002E6CD
0x18002e18c  mov     [rsp+140h+var_30], r14
0x18002e194  cmp     r8d, 1
0x18002e198  jz      short loc_18002E19F
0x18002e19a  mov     esi, 6
0x18002e19f  cmp     r9d, 14h
0x18002e1a3  mov     r14d, 0Ah
0x18002e1a9  cmovnz  r14d, r9d
0x18002e1ad  cmp     r14d, 0Ah
0x18002e1b1  jnz     loc_18002E67A
0x18002e1b7  mov     [rsp+140h+arg_10], r12
0x18002e1bf  test    rcx, rcx
0x18002e1c2  jnz     loc_18002E714
0x18002e1c8  mov     rcx, [rdi+198h]; lpMem
0x18002e1cf  test    rcx, rcx
0x18002e1d2  jnz     loc_18002E4C8
0x18002e1d8  test    r13, r13
0x18002e1db  jnz     loc_18002E58D
0x18002e1e1  mov     eax, [rbp+40h+arg_50]
0x18002e1e7  mov     r13, rdx
0x18002e1ea  mov     [rsp+140h+var_D0], edx
0x18002e1ee  mov     ecx, edx; this
0x18002e1f0  mov     [rsp+140h+var_E0], rdx
0x18002e1f5  mov     r12, rdx
0x18002e1f8  test    al, 1
0x18002e1fa  jnz     loc_18002E3F7
0x18002e200  test    r15, r15
0x18002e203  jnz     loc_18002E40E
0x18002e209  mov     rax, [rbp+40h+Src]
0x18002e20d  test    rax, rax
0x18002e210  jnz     loc_18002E4DB
0x18002e216  mov     ecx, [rbp+40h+arg_48]
0x18002e21c  mov     edx, 3
0x18002e221  test    ecx, ecx
0x18002e223  jz      loc_18002E45D
0x18002e229  mov     rax, [rbp+40h+arg_28]
0x18002e22d  mov     dword ptr [rdi+54h], 0Ah
0x18002e234  mov     qword ptr [rdi+70h], 0
0x18002e23c  mov     [rdi+78h], rax
0x18002e240  test    r14d, r14d
0x18002e243  jz      loc_18002E626
0x18002e249  mov     eax, [rbp+40h+arg_30]
0x18002e24f  cmp     esi, 1
0x18002e252  mov     [rdi+1A0h], ecx
0x18002e258  mov     [rdi+84h], ecx
0x18002e25e  mov     ecx, 1
0x18002e263  cmovnz  ecx, [rbp+40h+arg_40]
0x18002e26a  test    ecx, ecx
0x18002e26c  mov     [rdi+80h], eax
0x18002e272  mov     eax, ecx
0x18002e274  mov     [rdi+50h], esi
0x18002e277  cmovz   eax, edx
0x18002e27a  mov     [rdi+88h], ecx
0x18002e280  cmp     [rbp+40h+arg_80], 0
0x18002e287  mov     [rdi+1A4h], eax
0x18002e28d  jz      loc_18002E452
0x18002e293  mov     rax, [rdi]
0x18002e296  mov     rcx, rdi
0x18002e299  mov     rax, [rax+1A8h]
0x18002e2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2a5  mov     esi, [rbp+40h+arg_50]
0x18002e2ab  test    eax, eax
0x18002e2ad  jnz     loc_18002E552
0x18002e2b3  mov     eax, 0FFFFFFFDh
0x18002e2b8  and     [rdi+1F0h], eax
0x18002e2be  mov     rcx, [rdi+68h]; lpMem
0x18002e2c2  mov     [rdi+8Ch], esi
0x18002e2c8  test    rcx, rcx
0x18002e2cb  jnz     loc_18002E3E3
0x18002e2d1  mov     [rdi+68h], r15
0x18002e2d5  xor     r15d, r15d
0x18002e2d8  mov     rcx, [rdi+190h]; lpMem
0x18002e2df  test    rcx, rcx
0x18002e2e2  jz      short loc_18002E2E9
0x18002e2e4  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002e2e9  mov     [rdi+190h], r13
0x18002e2f0  xor     r13d, r13d
0x18002e2f3  mov     rcx, [rdi+60h]; lpMem
0x18002e2f7  test    rcx, rcx
0x18002e2fa  jnz     loc_18002E3ED
0x18002e300  mov     rcx, [rdi+1F8h]; hObject
0x18002e307  xor     esi, esi
0x18002e309  mov     [rdi+60h], r12
0x18002e30d  test    rcx, rcx
0x18002e310  jz      short loc_18002E339
0x18002e312  mov     rax, 0FFFFFFFF00000003h
0x18002e31c  add     rax, rcx
0x18002e31f  cmp     rax, 1
0x18002e323  jbe     short loc_18002E32B
0x18002e325  call    cs:__imp_CloseHandle
0x18002e32b  mov     [rdi+1F8h], rsi
0x18002e332  mov     [rdi+200h], rsi
0x18002e339  cmp     [rdi+1A0h], esi
0x18002e33f  jnz     short loc_18002E361
0x18002e341  mov     rax, [rsp+140h+TokenHandle]
0x18002e346  mov     [rdi+1F8h], rax
0x18002e34d  mov     eax, [rbp+40h+var_B8.HighPart]
0x18002e350  mov     [rdi+204h], eax
0x18002e356  mov     [rsp+140h+TokenHandle], rsi
0x18002e35b  mov     [rdi+200h], ebx
0x18002e361  xor     r12d, r12d
0x18002e364  mov     rcx, [rbp+40h+ppszUserName]; unsigned __int16 *
0x18002e368  test    rcx, rcx
0x18002e36b  jnz     loc_18002E913
0x18002e371  mov     rcx, [rbp+40h+ppszPackedCredentialsString]; unsigned __int16 *
0x18002e375  test    rcx, rcx
0x18002e378  jnz     loc_18002E91D
0x18002e37e  mov     rcx, [rbp+40h+ppszDomainName]; unsigned __int16 *
0x18002e382  test    rcx, rcx
0x18002e385  jnz     loc_18002E927
0x18002e38b  mov     rcx, [rsp+140h+TokenHandle]; void *
0x18002e390  test    rcx, rcx
0x18002e393  jnz     loc_18002E931
0x18002e399  test    r15, r15
0x18002e39c  jnz     loc_18002E93B
0x18002e3a2  test    r13, r13
0x18002e3a5  jnz     loc_18002E953
0x18002e3ab  test    rsi, rsi
0x18002e3ae  jnz     loc_18002E960
0x18002e3b4  mov     eax, r12d
0x18002e3b7  mov     r12, [rsp+140h+arg_10]
0x18002e3bf  mov     r14, [rsp+140h+var_30]
0x18002e3c7  mov     rcx, [rbp+40h+var_38]
0x18002e3cb  xor     rcx, rsp; StackCookie
0x18002e3ce  call    __security_check_cookie
0x18002e3d3  add     rsp, 118h
0x18002e3da  pop     r15
0x18002e3dc  pop     r13
0x18002e3de  pop     rdi
0x18002e3df  pop     rsi
0x18002e3e0  pop     rbx
0x18002e3e1  pop     rbp
0x18002e3e2  retn
0x18002e3e3  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002e3e8  jmp     loc_18002E2D1
0x18002e3ed  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002e3f2  jmp     loc_18002E300
0x18002e3f7  test    r15, r15
0x18002e3fa  jz      loc_18002E50B
0x18002e400  or      eax, 10h
0x18002e403  mov     [rbp+40h+arg_50], eax
0x18002e409  jmp     loc_18002E200
0x18002e40e  test    ecx, ecx
0x18002e410  jnz     short loc_18002E42E
0x18002e412  mov     rcx, r15; pSourceSid
0x18002e415  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18002e41a  mov     r15, rax
0x18002e41d  test    rax, rax
0x18002e420  jz      loc_18002E706
0x18002e426  mov     [rsp+140h+var_D0], 1
0x18002e42e  mov     rcx, r15; pSourceSid
0x18002e431  call    ?DuplicateSID@@YAPEAXQEAX@Z; DuplicateSID(void * const)
0x18002e436  mov     r13, rax
0x18002e439  test    rax, rax
0x18002e43c  jnz     loc_18002E209
0x18002e442  mov     r12d, 0Eh
0x18002e448  mov     rsi, [rsp+140h+var_E0]
0x18002e44d  jmp     loc_18002E364
0x18002e452  mov     eax, [rbp+40h+arg_78]
0x18002e458  jmp     loc_18002E2A5
0x18002e45d  mov     rcx, [rbp+40h+var_78]; void *
0x18002e461  test    rcx, rcx
0x18002e464  jnz     loc_18002E7D1
0x18002e46a  call    cs:__imp_GetCurrentThread
0x18002e470  mov     r12d, 0Eh
0x18002e476  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x18002e47b  mov     edx, r12d; DesiredAccess
0x18002e47e  mov     rcx, rax; ThreadHandle
0x18002e481  mov     r8b, 1; OpenAsSelf
0x18002e484  call    cs:__imp_NtOpenThreadToken
0x18002e48a  cmp     eax, 0C000007Ch
0x18002e48f  jnz     loc_18002E6AA
0x18002e495  mov     eax, 0FFFFFFFDh
0x18002e49a  mov     [rsp+140h+TokenHandle], rax
0x18002e49f  lea     rcx, [rbp+40h+var_B8]; struct _LUID *
0x18002e4a3  call    ?CaptureModifiedIdEx@@YAJPEAU_LUID@@@Z; CaptureModifiedIdEx(_LUID *)
0x18002e4a8  mov     r12d, eax
0x18002e4ab  test    eax, eax
0x18002e4ad  jnz     short loc_18002E448
0x18002e4af  mov     rbx, qword ptr [rbp+40h+var_B8.LowPart]
0x18002e4b3  mov     r12, [rsp+140h+var_E0]
0x18002e4b8  mov     ecx, [rbp+40h+arg_48]
0x18002e4be  mov     edx, 3
0x18002e4c3  jmp     loc_18002E229
0x18002e4c8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18002e4cd  xor     edx, edx
0x18002e4cf  mov     [rdi+198h], rdx
0x18002e4d6  jmp     loc_18002E1D8
0x18002e4db  cmp     [rax], bx
0x18002e4de  jz      loc_18002E216
0x18002e4e4  mov     rcx, rax; Src
0x18002e4e7  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18002e4ec  mov     [rsp+140h+var_E0], rax
0x18002e4f1  mov     r12, rax
0x18002e4f4  test    rax, rax
0x18002e4f7  jnz     loc_18002E216
0x18002e4fd  mov     r12d, 0Eh
0x18002e503  mov     rsi, rax
0x18002e506  jmp     loc_18002E364
0x18002e50b  cmp     qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision, rbx; SID_CACHE * SIDCache ...
0x18002e512  jz      loc_18002E7BB
0x18002e518  mov     rdx, [rbp+40h+Src]; unsigned __int16 *
0x18002e51c  lea     r8, [rsp+140h+var_C8]; void **
0x18002e521  call    ?Query@SID_CACHE@@QEAAJPEBGPEAPEAX@Z; SID_CACHE::Query(ushort const *,void * *)
0x18002e526  mov     r12d, eax
0x18002e529  test    eax, eax
0x18002e52b  jnz     short loc_18002E5AC
0x18002e52d  mov     r15, [rsp+140h+var_C8]
0x18002e532  test    r15, r15
0x18002e535  jz      loc_18002E5D4
0x18002e53b  mov     eax, [rbp+40h+arg_50]
0x18002e541  mov     ecx, 1
0x18002e546  mov     [rsp+140h+var_D0], ecx
0x18002e54a  mov     r12, r13
0x18002e54d  jmp     loc_18002E400
0x18002e552  mov     eax, [rdi+1F0h]
0x18002e558  or      eax, 2
0x18002e55b  mov     [rdi+1F0h], eax
0x18002e561  jmp     loc_18002E2BE
0x18002e566  mov     [rsp+140h+ReturnLength], rdx; struct tagParam *
0x18002e56b  mov     r8d, 35Ch; unsigned __int16
0x18002e571  mov     edx, 6E4h; int
0x18002e576  xor     r9d, r9d; int
0x18002e579  mov     ecx, 2; unsigned int
0x18002e57e  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002e583  mov     eax, 6E4h
0x18002e588  jmp     loc_18002E3C7
0x18002e58d  lea     r8, [rdi+198h]; void **
0x18002e594  mov     edx, 18h; AutoInheritFlags
0x18002e599  mov     rcx, r13; CreatorDescriptor
0x18002e59c  call    ?RpcpNormalizeSecurityDescriptor@@YAJPEAXKPEAPEAX@Z; RpcpNormalizeSecurityDescriptor(void *,ulong,void * *)
0x18002e5a1  test    eax, eax
0x18002e5a3  jnz     short loc_18002E61C
0x18002e5a5  xor     edx, edx
0x18002e5a7  jmp     loc_18002E1E1
0x18002e5ac  xor     edx, edx
0x18002e5ae  mov     [rsp+140h+ReturnLength], rdx; struct tagParam *
0x18002e5b3  mov     r8d, 35Eh; unsigned __int16
0x18002e5b9  mov     edx, r12d; int
0x18002e5bc  xor     r9d, r9d; int
0x18002e5bf  mov     ecx, 2; unsigned int
0x18002e5c4  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002e5c9  xor     r15d, r15d
0x18002e5cc  mov     rsi, r13
0x18002e5cf  jmp     loc_18002E364
0x18002e5d4  mov     rcx, [rbp+40h+Src]; lpAccountName
0x18002e5d8  lea     rdx, [rsp+140h+var_C8]; void **
0x18002e5dd  call    ?RpcpLookupAccountNameDirect@@YAJPEBGPEAPEAX@Z; RpcpLookupAccountNameDirect(ushort const *,void * *)
0x18002e5e2  mov     r15, [rsp+140h+var_C8]
0x18002e5e7  mov     r12d, eax
0x18002e5ea  cmp     eax, 6FDh
0x18002e5ef  jz      loc_18002E7C6
0x18002e5f5  test    eax, eax
0x18002e5f7  jnz     short loc_18002E611
0x18002e5f9  cmp     qword ptr cs:?SIDCache@@3PEAVSID_CACHE@@EA.Revision, rbx; SID_CACHE * SIDCache ...
0x18002e600  jz      short loc_18002E611
0x18002e602  mov     rdx, [rbp+40h+Src]; unsigned __int16 *
0x18002e606  xor     r9d, r9d; int
0x18002e609  mov     r8, r15; void *
0x18002e60c  call    ?Add@SID_CACHE@@QEAAJPEBGPEAXH@Z; SID_CACHE::Add(ushort const *,void *,int)
0x18002e611  test    r12d, r12d
0x18002e614  jz      loc_18002E53B
  ... truncated ...
```
