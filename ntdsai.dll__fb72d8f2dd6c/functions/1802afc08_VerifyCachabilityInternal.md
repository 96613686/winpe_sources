# VerifyCachabilityInternal

- ea: `0x1802afc08`
- end: `0x1802b0345`
- name: `VerifyCachabilityInternal`
- size: `1853`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180239828`
- `0x1802afb40`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x180022690`
- `0x180181c60`
- `0x18019e94c`
- `0x1801c4a34`
- `0x1802aee90`
- `0x1802aeff0`
- `0x1802af7f0`
- `0x1802afc08`
- `0x1802b0404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aff33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b0081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b01c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b029b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18046c5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802aff33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b0081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b01c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802b029b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18046c5c0`
- `AUTHZ!AuthzFreeContext` at `0x1802b0291`
- `AUTHZ!AuthzFreeContext` at `0x18046c5b6`
- `AUTHZ!AuthzFreeContext` at `0x1802b0291`
- `AUTHZ!AuthzFreeContext` at `0x18046c5b6`
- `AUTHZ!AuthzAccessCheck` at `0x1802b0077`
- `AUTHZ!AuthzAccessCheck` at `0x1802b01bb`
- `AUTHZ!AuthzAccessCheck` at `0x1802b0077`
- `AUTHZ!AuthzAccessCheck` at `0x1802b01bb`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1802aff29`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1802aff29`

## pseudocode

```c
__int64 __fastcall VerifyCachabilityInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  int v9; // edi
  _DWORD *v10; // r13
  _DWORD *v11; // r15
  unsigned int v12; // eax
  int v13; // r8d
  int v14; // r9d
  unsigned int IsUACBitSet; // ebx
  unsigned int v16; // eax
  __int64 v17; // r12
  unsigned int v18; // eax
  unsigned int DNKrbtgt; // eax
  unsigned int v20; // eax
  DWORD LastError; // eax
  unsigned int PolicySDs; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  int v27; // [rsp+58h] [rbp-C0h]
  __int64 v28; // [rsp+60h] [rbp-B8h] BYREF
  int v29; // [rsp+68h] [rbp-B0h] BYREF
  int v30; // [rsp+6Ch] [rbp-ACh] BYREF
  int v31; // [rsp+70h] [rbp-A8h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+78h] [rbp-A0h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+80h] [rbp-98h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+A8h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR v36; // [rsp+B0h] [rbp-68h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+B8h] [rbp-60h] BYREF

  v9 = 0;
  v28 = 0;
  v34 = 0;
  v30 = 1;
  pSecurityDescriptor = 0;
  v36 = 0;
  hAuthzClientContext = 0;
  v27 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  v29 = 0;
  v31 = 0;
  v10 = a5;
  *a5 = 0;
  v11 = a6;
  *a6 = 0;
  v12 = DBRefreshDSName(a2, a3, &v28);
  IsUACBitSet = v12;
  if ( v12 )
    DoLogUnhandledError(19137635, v12, 1);
  if ( !IsUACBitSet )
  {
    v16 = DBRefreshDSName(a2, a4, &v34);
    IsUACBitSet = v16;
    if ( v16 )
      DoLogUnhandledError(19137641, v16, 1);
    v17 = v34;
    if ( !IsUACBitSet )
    {
      IsUACBitSet = draIsUACBitSet(a2, v34, 0x4000000, &v29);
      if ( !IsUACBitSet && !v29 )
        IsUACBitSet = 87;
      if ( !IsUACBitSet )
      {
        v18 = DBFindDSName(a2, v17);
        IsUACBitSet = v18;
        if ( v18 )
          DoLogUnhandledError(19137657, v18, 1);
        if ( !IsUACBitSet )
        {
          IsUACBitSet = dword_18052B2C8 != *(_DWORD *)(a2 + 32) ? 0x57 : 0;
          if ( !IsUACBitSet )
          {
            a5 = 0;
            DNKrbtgt = GetDNKrbtgt(a1, a2, v17, &a5);
            IsUACBitSet = DNKrbtgt;
            if ( DNKrbtgt )
              DoLogUnhandledError(19137668, DNKrbtgt, 1);
            if ( !IsUACBitSet && (unsigned int)NameMatched(v28, a5) )
            {
              *v10 = 0;
              *v11 = 1;
              v9 = 1;
            }
            if ( a5 )
            {
              THFreeAux(a1, (_DWORD)a5, v13, v14, 19137678);
              a5 = 0;
            }
            if ( !IsUACBitSet )
            {
              if ( v9 )
              {
LABEL_29:
                if ( !v9 && (unsigned int)NameMatched(v28, v17) )
                {
                  *v10 = 0;
                  *v11 = 1;
                  v9 = 1;
                }
                if ( !v9 )
                {
                  IsUACBitSet = draIsUACBitSet(a2, v28, 2048, &v31);
                  if ( !IsUACBitSet )
                  {
                    if ( v31 )
                    {
                      *v10 = 1;
                      *v11 = 0;
                      v9 = 1;
                    }
                  }
                }
                if ( !IsUACBitSet )
                {
                  if ( !v9 )
                  {
                    if ( AuthzInitializeContextFromSid(
                           0,
                           (PSID)(v28 + 24),
                           ghAuthzRM,
                           0,
                           gLUID,
                           0,
                           &hAuthzClientContext) )
                    {
                      v27 = 1;
                    }
                    else
                    {
                      LastError = GetLastError();
                      IsUACBitSet = LastError;
                      if ( LastError )
                        DoLogUnhandledError(19137730, LastError, 1);
                    }
                  }
                  if ( !IsUACBitSet && !v9 )
                  {
                    PolicySDs = GetPolicySDs(a1, a2, v17, &pSecurityDescriptor, &v36);
                    IsUACBitSet = PolicySDs;
                    if ( PolicySDs )
                      DoLogUnhandledError(19137741, PolicySDs, 1);
                  }
                }
                goto LABEL_46;
              }
              v20 = IsKrbtgt(a1, a2, v28, &v30);
              IsUACBitSet = v20;
              if ( v20 )
                DoLogUnhandledError(19137686, v20, 1);
              if ( !IsUACBitSet )
              {
                if ( v30 )
                {
                  *v10 = 1;
                  *v11 = 0;
                  v9 = 1;
                }
                goto LABEL_29;
              }
            }
          }
        }
      }
    }
  }
LABEL_46:
  if ( !IsUACBitSet && !v9 )
  {
    pRequest.DesiredAccess = 0x20000;
    memset(&pRequest.PrincipalSelfSid, 0, 20);
    pReply.ResultListLength = 1;
    pReply.Error = (PDWORD)THAlloc_(a1, 1, 4, 1, 0, 19137754);
    pReply.GrantedAccessMask = (PACCESS_MASK)THAlloc_(a1, 1, 4, 1, 0, 19137755);
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
    {
      *v10 = *pReply.Error != 0;
    }
    else
    {
      v23 = GetLastError();
      IsUACBitSet = v23;
      if ( v23 )
        DoLogUnhandledError(19137768, v23, 1);
    }
    if ( pReply.Error )
    {
      THFreeAux(a1, pReply.Error, v13, v14, 19137781);
      pReply.Error = 0;
    }
    if ( pReply.GrantedAccessMask )
    {
      THFreeAux(a1, pReply.GrantedAccessMask, v13, v14, 19137786);
      pReply.GrantedAccessMask = 0;
    }
  }
  if ( IsUACBitSet )
    goto LABEL_72;
  if ( !v9 )
  {
    pReply.ResultListLength = 1;
    pReply.Error = (PDWORD)THAlloc_(a1, 1, 4, 1, 0, 19137794);
    pReply.GrantedAccessMask = (PACCESS_MASK)THAlloc_(a1, 1, 4, 1, 0, 19137795);
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, v36, 0, 0, &pReply, 0) )
    {
      v9 = 1;
      if ( *pReply.Error )
        *v11 = 0;
      else
        *v11 = 1;
    }
    else
    {
      v24 = GetLastError();
      IsUACBitSet = v24;
      if ( v24 )
        DoLogUnhandledError(19137808, v24, 1);
    }
    if ( pReply.Error )
    {
      THFreeAux(a1, pReply.Error, v13, v14, 19137826);
      pReply.Error = 0;
    }
    if ( pReply.GrantedAccessMask )
    {
      THFreeAux(a1, pReply.GrantedAccessMask, v13, v14, 19137831);
      pReply.GrantedAccessMask = 0;
    }
  }
  if ( IsUACBitSet )
  {
LABEL_72:
    *v10 = 0;
    *v11 = 0;
  }
  else if ( !v9 )
  {
    *v10 = 0;
    *v11 = 0;
  }
  if ( v27 )
  {
    if ( !AuthzFreeContext(hAuthzClientContext) )
    {
      v25 = GetLastError();
      IsUACBitSet = v25;
      if ( v25 )
        DoLogUnhandledError(19137929, v25, 1);
    }
  }
  if ( v28 )
    THFreeAux(a1, v28, v13, v14, 19137934);
  if ( v34 )
    THFreeAux(a1, v34, v13, v14, 19137937);
  if ( pSecurityDescriptor )
    THFreeAux(a1, (_DWORD)pSecurityDescriptor, v13, v14, 19137940);
  if ( v36 )
    THFreeAux(a1, (_DWORD)v36, v13, v14, 19137943);
  return IsUACBitSet;
}

```

## disassembly

```asm
0x1802afc08  mov     r11, rsp
0x1802afc0b  push    rbx
0x1802afc0c  push    rsi
0x1802afc0d  push    rdi
0x1802afc0e  push    r12
0x1802afc10  push    r13
0x1802afc12  push    r14
0x1802afc14  push    r15
0x1802afc16  sub     rsp, 0E0h
0x1802afc1d  mov     r12, r9
0x1802afc20  mov     rax, r8
0x1802afc23  mov     r14, rdx
0x1802afc26  mov     rsi, rcx
0x1802afc29  xor     edx, edx
0x1802afc2b  mov     edi, edx
0x1802afc2d  mov     [rsp+118h+var_B8], rdx
0x1802afc32  mov     [r11-78h], rdx
0x1802afc36  mov     [rsp+118h+var_AC], 1
0x1802afc3e  mov     [r11-70h], rdx
0x1802afc42  mov     [r11-68h], rdx
0x1802afc46  mov     [rsp+118h+hAuthzClientContext], rdx
0x1802afc4b  mov     [rsp+118h+var_C0], edx
0x1802afc4f  xorps   xmm0, xmm0
0x1802afc52  xor     ecx, ecx
0x1802afc54  movups  xmmword ptr [r11-60h], xmm0
0x1802afc59  movups  xmmword ptr [r11-50h], xmm0
0x1802afc5e  mov     [r11-40h], rcx
0x1802afc62  movups  xmmword ptr [rsp+118h+var_98.ResultListLength], xmm0
0x1802afc6a  movups  xmmword ptr [rsp+118h+var_98.SaclEvaluationResults], xmm0
0x1802afc72  mov     [rsp+118h+var_B0], edx
0x1802afc76  mov     [rsp+118h+var_A8], edx
0x1802afc7a  mov     r13, [rsp+118h+arg_20]
0x1802afc82  mov     [r13+0], edx
0x1802afc86  mov     r15, [rsp+118h+arg_28]
0x1802afc8e  mov     [r15], edx
0x1802afc91  lea     r8, [rsp+118h+var_B8]
0x1802afc96  mov     rdx, rax
0x1802afc99  mov     rcx, r14
0x1802afc9c  call    DBRefreshDSName
0x1802afca1  mov     ebx, eax
0x1802afca3  mov     [rsp+118h+var_C8], eax
0x1802afca7  test    eax, eax
0x1802afca9  jz      short loc_1802AFCBD
0x1802afcab  mov     r8d, 1
0x1802afcb1  mov     edx, eax
0x1802afcb3  mov     ecx, 1240463h
0x1802afcb8  call    DoLogUnhandledError
0x1802afcbd  test    ebx, ebx
0x1802afcbf  jnz     loc_1802AFFA7
0x1802afcc5  lea     r8, [rsp+118h+var_78]
0x1802afccd  mov     rdx, r12
0x1802afcd0  mov     rcx, r14
0x1802afcd3  call    DBRefreshDSName
0x1802afcd8  mov     ebx, eax
0x1802afcda  mov     [rsp+118h+var_C8], eax
0x1802afcde  test    eax, eax
0x1802afce0  jz      short loc_1802AFCF4
0x1802afce2  mov     r8d, 1
0x1802afce8  mov     edx, eax
0x1802afcea  mov     ecx, 1240469h
0x1802afcef  call    DoLogUnhandledError
0x1802afcf4  mov     r12, [rsp+118h+var_78]
0x1802afcfc  test    ebx, ebx
0x1802afcfe  jnz     loc_1802AFFA7
0x1802afd04  lea     r9, [rsp+118h+var_B0]
0x1802afd09  mov     r8d, 4000000h
0x1802afd0f  mov     rdx, r12
0x1802afd12  mov     rcx, r14
0x1802afd15  call    draIsUACBitSet
0x1802afd1a  mov     ebx, eax
0x1802afd1c  mov     [rsp+118h+var_C8], eax
0x1802afd20  test    eax, eax
0x1802afd22  jnz     short loc_1802AFD32
0x1802afd24  lea     eax, [rbx+57h]
0x1802afd27  cmp     [rsp+118h+var_B0], ebx
0x1802afd2b  cmovz   ebx, eax
0x1802afd2e  mov     [rsp+118h+var_C8], ebx
0x1802afd32  test    ebx, ebx
0x1802afd34  jnz     loc_1802AFFA7
0x1802afd3a  mov     rdx, r12
0x1802afd3d  mov     rcx, r14
0x1802afd40  call    DBFindDSName
0x1802afd45  mov     ebx, eax
0x1802afd47  mov     [rsp+118h+var_C8], eax
0x1802afd4b  test    eax, eax
0x1802afd4d  jz      short loc_1802AFD61
0x1802afd4f  mov     r8d, 1
0x1802afd55  mov     edx, eax
0x1802afd57  mov     ecx, 1240479h
0x1802afd5c  call    DoLogUnhandledError
0x1802afd61  test    ebx, ebx
0x1802afd63  jnz     loc_1802AFFA7
0x1802afd69  mov     eax, [r14+20h]
0x1802afd6d  sub     eax, cs:dword_18052B2C8
0x1802afd73  neg     eax
0x1802afd75  sbb     ebx, ebx
0x1802afd77  and     ebx, 57h
0x1802afd7a  mov     [rsp+118h+var_C8], ebx
0x1802afd7e  test    ebx, ebx
0x1802afd80  jnz     loc_1802AFFA7
0x1802afd86  mov     [rsp+118h+arg_20], 0
0x1802afd92  lea     r9, [rsp+118h+arg_20]
0x1802afd9a  mov     r8, r12
0x1802afd9d  mov     rdx, r14
0x1802afda0  mov     rcx, rsi
0x1802afda3  call    GetDNKrbtgt
0x1802afda8  mov     ebx, eax
0x1802afdaa  mov     [rsp+118h+var_C8], eax
0x1802afdae  test    eax, eax
0x1802afdb0  jz      short loc_1802AFDC4
0x1802afdb2  mov     r8d, 1
0x1802afdb8  mov     edx, eax
0x1802afdba  mov     ecx, 1240484h
0x1802afdbf  call    DoLogUnhandledError
0x1802afdc4  test    ebx, ebx
0x1802afdc6  jnz     short loc_1802AFDF0
0x1802afdc8  mov     rdx, [rsp+118h+arg_20]
0x1802afdd0  mov     rcx, [rsp+118h+var_B8]
0x1802afdd5  call    NameMatched
0x1802afdda  test    eax, eax
0x1802afddc  jz      short loc_1802AFDF0
0x1802afdde  mov     [r13+0], ebx
0x1802afde2  mov     dword ptr [r15], 1
0x1802afde9  lea     edi, [rbx+1]
0x1802afdec  mov     [rsp+118h+var_C4], edi
0x1802afdf0  mov     rdx, [rsp+118h+arg_20]
0x1802afdf8  test    rdx, rdx
0x1802afdfb  jz      short loc_1802AFE19
0x1802afdfd  mov     [rsp+118h+Identifier.LowPart], 124048Eh
0x1802afe05  mov     rcx, rsi
0x1802afe08  call    THFreeAux
0x1802afe0d  mov     [rsp+118h+arg_20], 0
0x1802afe19  test    ebx, ebx
0x1802afe1b  jnz     loc_1802AFFA7
0x1802afe21  test    edi, edi
0x1802afe23  jnz     short loc_1802AFE74
0x1802afe25  lea     r9, [rsp+118h+var_AC]
0x1802afe2a  mov     r8, [rsp+118h+var_B8]
0x1802afe2f  mov     rdx, r14
0x1802afe32  mov     rcx, rsi
0x1802afe35  call    IsKrbtgt
0x1802afe3a  mov     ebx, eax
0x1802afe3c  mov     [rsp+118h+var_C8], eax
0x1802afe40  test    eax, eax
0x1802afe42  jz      short loc_1802AFE54
0x1802afe44  lea     r8d, [rdi+1]
0x1802afe48  mov     edx, eax
0x1802afe4a  mov     ecx, 1240496h
0x1802afe4f  call    DoLogUnhandledError
0x1802afe54  test    ebx, ebx
0x1802afe56  jnz     loc_1802AFFA7
0x1802afe5c  cmp     [rsp+118h+var_AC], ebx
0x1802afe60  jz      short loc_1802AFE74
0x1802afe62  mov     dword ptr [r13+0], 1
0x1802afe6a  mov     [r15], ebx
0x1802afe6d  lea     edi, [rbx+1]
0x1802afe70  mov     [rsp+118h+var_C4], edi
0x1802afe74  test    ebx, ebx
0x1802afe76  jnz     loc_1802AFFA7
0x1802afe7c  test    edi, edi
0x1802afe7e  jnz     short loc_1802AFEA3
0x1802afe80  mov     rdx, r12
0x1802afe83  mov     rcx, [rsp+118h+var_B8]
0x1802afe88  call    NameMatched
0x1802afe8d  test    eax, eax
0x1802afe8f  jz      short loc_1802AFEA3
0x1802afe91  mov     [r13+0], edi
0x1802afe95  mov     dword ptr [r15], 1
0x1802afe9c  lea     edi, [rbx+1]
0x1802afe9f  mov     [rsp+118h+var_C4], edi
0x1802afea3  test    ebx, ebx
0x1802afea5  jnz     loc_1802AFFA7
0x1802afeab  test    edi, edi
0x1802afead  jnz     short loc_1802AFEE9
0x1802afeaf  lea     r9, [rsp+118h+var_A8]
0x1802afeb4  mov     r8d, 800h
0x1802afeba  mov     rdx, [rsp+118h+var_B8]
0x1802afebf  mov     rcx, r14
0x1802afec2  call    draIsUACBitSet
0x1802afec7  mov     ebx, eax
0x1802afec9  mov     [rsp+118h+var_C8], eax
0x1802afecd  test    eax, eax
0x1802afecf  jnz     short loc_1802AFEE9
0x1802afed1  cmp     [rsp+118h+var_A8], eax
0x1802afed5  jz      short loc_1802AFEE9
0x1802afed7  mov     dword ptr [r13+0], 1
0x1802afedf  mov     [r15], eax
0x1802afee2  lea     edi, [rax+1]
0x1802afee5  mov     [rsp+118h+var_C4], edi
0x1802afee9  test    ebx, ebx
0x1802afeeb  jnz     loc_1802AFFA7
0x1802afef1  test    edi, edi
0x1802afef3  jnz     short loc_1802AFF5D
0x1802afef5  mov     rdx, [rsp+118h+var_B8]
0x1802afefa  add     rdx, 18h; UserSid
0x1802afefe  lea     rax, [rsp+118h+hAuthzClientContext]
0x1802aff03  mov     [rsp+118h+phAuthzClientContext], rax; phAuthzClientContext
0x1802aff08  mov     [rsp+118h+DynamicGroupArgs], 0; DynamicGroupArgs
0x1802aff11  mov     rax, qword ptr cs:gLUID.LowPart
0x1802aff18  mov     qword ptr [rsp+118h+Identifier.LowPart], rax; Identifier
0x1802aff1d  xor     r9d, r9d; pExpirationTime
0x1802aff20  mov     r8, cs:ghAuthzRM; hAuthzResourceManager
0x1802aff27  xor     ecx, ecx; Flags
0x1802aff29  call    cs:__imp_AuthzInitializeContextFromSid
0x1802aff2f  test    eax, eax
0x1802aff31  jnz     short loc_1802AFF55
0x1802aff33  call    cs:__imp_GetLastError
0x1802aff39  mov     ebx, eax
0x1802aff3b  mov     [rsp+118h+var_C8], eax
0x1802aff3f  test    eax, eax
0x1802aff41  jz      short loc_1802AFF5D
0x1802aff43  lea     r8d, [rdi+1]
0x1802aff47  mov     edx, eax
0x1802aff49  mov     ecx, 12404C2h
0x1802aff4e  call    DoLogUnhandledError
0x1802aff53  jmp     short loc_1802AFF5D
0x1802aff55  mov     [rsp+118h+var_C0], 1
0x1802aff5d  test    ebx, ebx
0x1802aff5f  jnz     short loc_1802AFFA7
0x1802aff61  test    edi, edi
0x1802aff63  jnz     short loc_1802AFFA7
0x1802aff65  lea     rax, [rsp+118h+var_68]
0x1802aff6d  mov     qword ptr [rsp+118h+Identifier.LowPart], rax
0x1802aff72  lea     r9, [rsp+118h+pSecurityDescriptor]
0x1802aff7a  mov     r8, r12
0x1802aff7d  mov     rdx, r14
0x1802aff80  mov     rcx, rsi
0x1802aff83  call    GetPolicySDs
0x1802aff88  mov     ebx, eax
0x1802aff8a  mov     [rsp+118h+var_C8], eax
0x1802aff8e  xor     r12d, r12d
0x1802aff91  test    eax, eax
0x1802aff93  jz      short loc_1802AFFAA
0x1802aff95  lea     r8d, [rdi+1]
0x1802aff99  mov     edx, eax
0x1802aff9b  mov     ecx, 12404CDh
0x1802affa0  call    DoLogUnhandledError
0x1802affa5  jmp     short loc_1802AFFAA
0x1802affa7  xor     r12d, r12d
0x1802affaa  test    ebx, ebx
0x1802affac  jnz     loc_1802B0114
0x1802affb2  test    edi, edi
0x1802affb4  jnz     loc_1802B0114
0x1802affba  mov     [rsp+118h+pRequest.DesiredAccess], 20000h
0x1802affc5  xorps   xmm0, xmm0
0x1802affc8  movdqu  xmmword ptr [rsp+118h+pRequest.PrincipalSelfSid], xmm0
0x1802affd1  mov     [rsp+118h+pRequest.ObjectTypeListLength], r12d
0x1802affd9  mov     [rsp+118h+pRequest.PrincipalSelfSid], r12
0x1802affe1  lea     eax, [rbx+1]
0x1802affe4  mov     [rsp+118h+var_98.ResultListLength], eax
0x1802affeb  mov     dword ptr [rsp+118h+DynamicGroupArgs], 12404DAh
0x1802afff3  mov     [rsp+118h+Identifier.LowPart], r12d
0x1802afff8  mov     r9d, eax
0x1802afffb  lea     r14d, [rbx+4]
0x1802affff  mov     r8d, r14d
0x1802b0002  mov     edx, eax
0x1802b0004  mov     rcx, rsi
0x1802b0007  call    THAlloc_
0x1802b000c  mov     [rsp+118h+var_98.Error], rax
0x1802b0014  mov     dword ptr [rsp+118h+DynamicGroupArgs], 12404DBh
0x1802b001c  mov     [rsp+118h+Identifier.LowPart], r12d
0x1802b0021  lea     eax, [rbx+1]
0x1802b0024  mov     r9d, eax
0x1802b0027  mov     r8d, r14d
0x1802b002a  mov     edx, eax
0x1802b002c  mov     rcx, rsi
0x1802b002f  call    THAlloc_
0x1802b0034  mov     [rsp+118h+var_98.GrantedAccessMask], rax
0x1802b003c  mov     [rsp+118h+phAccessCheckResults], r12; phAccessCheckResults
0x1802b0041  lea     rax, [rsp+118h+var_98]
0x1802b0049  mov     [rsp+118h+pReply], rax; pReply
0x1802b004e  mov     dword ptr [rsp+118h+phAuthzClientContext], r12d; OptionalSecurityDescriptorCount
0x1802b0053  mov     [rsp+118h+DynamicGroupArgs], r12; OptionalSecurityDescriptorArray
0x1802b0058  mov     rax, [rsp+118h+pSecurityDescriptor]
0x1802b0060  mov     qword ptr [rsp+118h+Identifier.LowPart], rax; pSecurityDescriptor
0x1802b0065  xor     r9d, r9d; hAuditEvent
0x1802b0068  lea     r8, [rsp+118h+pRequest]; pRequest
0x1802b0070  mov     rdx, [rsp+118h+hAuthzClientContext]; hAuthzClientContext
0x1802b0075  xor     ecx, ecx; Flags
0x1802b0077  call    cs:__imp_AuthzAccessCheck
0x1802b007d  test    eax, eax
0x1802b007f  jnz     short loc_1802B00A3
0x1802b0081  call    cs:__imp_GetLastError
0x1802b0087  mov     ebx, eax
0x1802b0089  mov     [rsp+118h+var_C8], eax
0x1802b008d  test    eax, eax
0x1802b008f  jz      short loc_1802B00B8
0x1802b0091  lea     r8d, [rdi+1]
0x1802b0095  mov     edx, eax
0x1802b0097  mov     ecx, 12404E8h
0x1802b009c  call    DoLogUnhandledError
0x1802b00a1  jmp     short loc_1802B00B8
0x1802b00a3  mov     ecx, r12d
0x1802b00a6  mov     rax, [rsp+118h+var_98.Error]
0x1802b00ae  cmp     [rax], r12d
0x1802b00b1  setnz   cl
0x1802b00b4  mov     [r13+0], ecx
0x1802b00b8  mov     rdx, [rsp+118h+var_98.Error]
0x1802b00c0  test    rdx, rdx
0x1802b00c3  jz      short loc_1802B00E5
  ... truncated ...
```
