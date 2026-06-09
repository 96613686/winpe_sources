# ZtCertUpdateAclIfNeeded

- ea: `0x18005a1c4`
- end: `0x18005a389`
- name: `ZtCertUpdateAclIfNeeded`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800564c8`
- `0x180056b70`
- `0x180059eb0`
- `0x18005a41c`

## callees

- `0x180046ec0`
- `0x18005a1c4`
- `0x180066b8c`
- `0x18006a6ec`
- `0x18006a7ac`
- `0x18006aad4`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18005a34b`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18005a34b`
- `DNSAPI!DnsZtHelperProcessClientCerts` at `0x18005a28a`
- `DNSAPI!DnsZtHelperProcessClientCerts` at `0x18005a28a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005a362`
- `CRYPT32!CertFreeCertificateContext` at `0x18005a362`

## pseudocode

```c
__int64 __fastcall ZtCertUpdateAclIfNeeded(unsigned int a1, int *a2)
{
  bool v2; // zf
  __int64 v4; // r14
  unsigned int ClientCertConfigLocked; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int ClientCertContextRef; // eax
  __int128 *v9; // rdx
  __int64 v10; // rcx
  int v11; // edi
  void *v13; // [rsp+20h] [rbp-20h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+28h] [rbp-18h] BYREF
  int v15; // [rsp+30h] [rbp-10h] BYREF

  v2 = g_fVelocityZtdnsProbing == 0;
  *a2 = 0;
  v4 = (int)a1;
  v13 = 0;
  pCertContext = 0;
  v15 = 0;
  if ( v2 )
  {
    ClientCertConfigLocked = ZtGetClientCertConfigLocked(0, &v13);
    v6 = ClientCertConfigLocked;
    if ( ClientCertConfigLocked )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_31;
      v7 = 12;
      goto LABEL_30;
    }
  }
  else
  {
    ClientCertConfigLocked = ZtGetClientCertConfigLocked(a1, &v13);
    v6 = ClientCertConfigLocked;
    if ( ClientCertConfigLocked )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_31;
      v7 = 11;
LABEL_30:
      WPP_SF_d(1035, v7, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, ClientCertConfigLocked);
      goto LABEL_31;
    }
  }
  ClientCertContextRef = ZtGetClientCertContextRef(v13, &pCertContext, &v15);
  if ( !v15 )
  {
    if ( !ClientCertContextRef )
    {
LABEL_14:
      v11 = 1;
      goto LABEL_17;
    }
LABEL_16:
    v11 = 0;
LABEL_17:
    if ( g_fVelocityZtdnsProbing )
    {
      ClientCertConfigLocked = ZtUpdateClientCertsGlobal((unsigned int)v4, v13, 0, 0);
      v6 = ClientCertConfigLocked;
      if ( ClientCertConfigLocked )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_31;
        v7 = 13;
        goto LABEL_30;
      }
      if ( (_DWORD)v4 != 1 )
        v11 = 0;
    }
    else
    {
      ClientCertConfigLocked = ZtUpdateClientCertsGlobal(0, v13, 0, 0);
      v6 = ClientCertConfigLocked;
      if ( ClientCertConfigLocked )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
          goto LABEL_31;
        v7 = 14;
        goto LABEL_30;
      }
    }
    *a2 = v11;
    goto LABEL_31;
  }
  if ( ClientCertContextRef == 1168 )
    goto LABEL_16;
  v9 = &g_rgZtHelperSettingsState;
  if ( g_fVelocityZtdnsProbing )
  {
    v9 = (__int128 *)((char *)&g_rgZtHelperSettingsState + 20 * v4);
    v10 = (unsigned int)v4;
  }
  else
  {
    v10 = 0;
  }
  v6 = DnsZtHelperProcessClientCerts(v10, v9);
  if ( v6 == 5023 )
  {
    v6 = 0;
    goto LABEL_31;
  }
  if ( !v6 )
    goto LABEL_14;
LABEL_31:
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeClientCertConfig(v13);
  }
  else
  {
    if ( !v13 )
      goto LABEL_36;
    DnsFreeZtClientCertConfig(v13);
  }
  v13 = 0;
LABEL_36:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  return v6;
}

```

## disassembly

```asm
0x18005a1c4  mov     [rsp-18h+arg_10], rbx
0x18005a1c9  mov     [rsp-18h+arg_18], rsi
0x18005a1ce  push    rbp
0x18005a1cf  push    rdi
0x18005a1d0  push    r14
0x18005a1d2  mov     rbp, rsp
0x18005a1d5  sub     rsp, 40h
0x18005a1d9  mov     rax, cs:__security_cookie
0x18005a1e0  xor     rax, rsp
0x18005a1e3  mov     [rbp+var_8], rax
0x18005a1e7  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18005a1ee  mov     rsi, rdx
0x18005a1f1  mov     dword ptr [rdx], 0
0x18005a1f7  lea     rdx, [rbp+var_20]
0x18005a1fb  movsxd  r14, ecx
0x18005a1fe  mov     [rbp+var_20], 0
0x18005a206  mov     [rbp+pCertContext], 0
0x18005a20e  mov     [rbp+var_10], 0
0x18005a215  jz      short loc_18005A23C
0x18005a217  mov     ecx, r14d
0x18005a21a  call    ZtGetClientCertConfigLocked
0x18005a21f  mov     ebx, eax
0x18005a221  test    eax, eax
0x18005a223  jz      short loc_18005A24D
0x18005a225  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a22c  jz      loc_18005A332
0x18005a232  mov     edx, 0Bh
0x18005a237  jmp     loc_18005A31E
0x18005a23c  xor     ecx, ecx
0x18005a23e  call    ZtGetClientCertConfigLocked
0x18005a243  mov     ebx, eax
0x18005a245  test    eax, eax
0x18005a247  jnz     loc_18005A310
0x18005a24d  mov     rcx, [rbp+var_20]
0x18005a251  lea     r8, [rbp+var_10]
0x18005a255  lea     rdx, [rbp+pCertContext]
0x18005a259  call    ZtGetClientCertContextRef
0x18005a25e  cmp     [rbp+var_10], 0
0x18005a262  jz      short loc_18005A2AF
0x18005a264  cmp     eax, 490h
0x18005a269  jz      short loc_18005A2B3
0x18005a26b  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18005a272  lea     rdx, g_rgZtHelperSettingsState
0x18005a279  jz      short loc_18005A288
0x18005a27b  lea     rcx, [r14+r14*4]
0x18005a27f  lea     rdx, [rdx+rcx*4]
0x18005a283  mov     ecx, r14d
0x18005a286  jmp     short loc_18005A28A
0x18005a288  xor     ecx, ecx
0x18005a28a  call    cs:__imp_DnsZtHelperProcessClientCerts
0x18005a290  mov     ebx, eax
0x18005a292  cmp     eax, 139Fh
0x18005a297  jnz     short loc_18005A2A0
0x18005a299  xor     ebx, ebx
0x18005a29b  jmp     loc_18005A332
0x18005a2a0  test    ebx, ebx
0x18005a2a2  jnz     loc_18005A332
0x18005a2a8  mov     edi, 1
0x18005a2ad  jmp     short loc_18005A2B5
0x18005a2af  test    eax, eax
0x18005a2b1  jz      short loc_18005A2A8
0x18005a2b3  xor     edi, edi
0x18005a2b5  mov     rdx, [rbp+var_20]
0x18005a2b9  xor     r9d, r9d
0x18005a2bc  xor     r8d, r8d
0x18005a2bf  cmp     cs:g_fVelocityZtdnsProbing, r8d
0x18005a2c6  jz      short loc_18005A2EF
0x18005a2c8  mov     ecx, r14d
0x18005a2cb  call    ZtUpdateClientCertsGlobal
0x18005a2d0  mov     ebx, eax
0x18005a2d2  test    eax, eax
0x18005a2d4  jnz     short loc_18005A2DF
0x18005a2d6  cmp     r14d, 1
0x18005a2da  cmovnz  edi, eax
0x18005a2dd  jmp     short loc_18005A2FC
0x18005a2df  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a2e6  jz      short loc_18005A332
0x18005a2e8  mov     edx, 0Dh
0x18005a2ed  jmp     short loc_18005A31E
0x18005a2ef  xor     ecx, ecx
0x18005a2f1  call    ZtUpdateClientCertsGlobal
0x18005a2f6  mov     ebx, eax
0x18005a2f8  test    eax, eax
0x18005a2fa  jnz     short loc_18005A300
0x18005a2fc  mov     [rsi], edi
0x18005a2fe  jmp     short loc_18005A332
0x18005a300  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a307  jz      short loc_18005A332
0x18005a309  mov     edx, 0Eh
0x18005a30e  jmp     short loc_18005A31E
0x18005a310  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a317  jz      short loc_18005A332
0x18005a319  mov     edx, 0Ch
0x18005a31e  mov     r9d, eax
0x18005a321  lea     r8, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids
0x18005a328  mov     ecx, 40Bh
0x18005a32d  call    WPP_SF_d
0x18005a332  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x18005a339  mov     rcx, [rbp+var_20]; void *
0x18005a33d  jz      short loc_18005A346
0x18005a33f  call    ZtFreeClientCertConfig
0x18005a344  jmp     short loc_18005A351
0x18005a346  test    rcx, rcx
0x18005a349  jz      short loc_18005A359
0x18005a34b  call    cs:__imp_DnsFreeZtClientCertConfig
0x18005a351  mov     [rbp+var_20], 0
0x18005a359  mov     rcx, [rbp+pCertContext]; pCertContext
0x18005a35d  test    rcx, rcx
0x18005a360  jz      short loc_18005A368
0x18005a362  call    cs:__imp_CertFreeCertificateContext
0x18005a368  mov     eax, ebx
0x18005a36a  mov     rcx, [rbp+var_8]
0x18005a36e  xor     rcx, rsp; StackCookie
0x18005a371  call    __security_check_cookie
0x18005a376  mov     rbx, [rsp+40h+arg_10]
0x18005a37b  mov     rsi, [rsp+40h+arg_18]
0x18005a380  add     rsp, 40h
0x18005a384  pop     r14
0x18005a386  pop     rdi
0x18005a387  pop     rbp
0x18005a388  retn
```
