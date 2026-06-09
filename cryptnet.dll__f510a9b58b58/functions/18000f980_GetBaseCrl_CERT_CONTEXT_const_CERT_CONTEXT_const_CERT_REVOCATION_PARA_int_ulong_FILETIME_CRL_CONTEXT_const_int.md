# GetBaseCrl(_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *,int *)

- ea: `0x18000f980`
- end: `0x18000fb5c`
- name: `?GetBaseCrl@@YAHPEBU_CERT_CONTEXT@@0PEAU_CERT_REVOCATION_PARA@@HKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH4@Z`
- size: `476`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *, struct _CERT_REVOCATION_PARA *, int, unsigned int, struct _FILETIME *, const struct _CRL_CONTEXT **, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f140`

## callees

- `0x18000f980`
- `0x18000fb70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fb31`
- `CRYPT32!I_CertDiagControl` at `0x18000fb26`
- `CRYPT32!I_CertDiagControl` at `0x18000fb26`
- `CRYPT32!CertFreeCRLContext` at `0x18000fb4e`
- `CRYPT32!CertFreeCRLContext` at `0x18000fb4e`

## string_xrefs

- `0x18000faef`: `IsCrlCriticalExtensionSupported`

## pseudocode

```c
__int64 __fastcall GetBaseCrl(
        struct _CERT_CONTEXT *a1,
        const struct _CERT_CONTEXT *a2,
        struct _CERT_REVOCATION_PARA *a3,
        int a4,
        unsigned int a5,
        struct _FILETIME *a6,
        const struct _CRL_CONTEXT **a7,
        int *a8,
        int *a9)
{
  PCRL_INFO pCrlInfo; // rax
  DWORD cExtension; // ebx
  PCERT_EXTENSION i; // r11
  const char * near **j; // r9
  unsigned __int8 *pszObjId; // rax
  int v18; // ecx
  int v19; // edx
  const struct _CRL_CONTEXT *v20; // rdx
  __int64 result; // rax
  PCCRL_CONTEXT pCrlContext; // [rsp+60h] [rbp-88h] BYREF
  _QWORD v23[3]; // [rsp+68h] [rbp-80h] BYREF
  __int128 v24; // [rsp+80h] [rbp-68h]
  __int64 v25; // [rsp+90h] [rbp-58h]

  pCrlContext = 0;
  *a9 = 0;
  if ( (unsigned int)GetTimeValidCrl((const char *)3, a1, a1, a2, a3, a4, a5, 0, a6, (LPVOID *)&pCrlContext, a9) )
  {
    *a8 = 1;
  }
  else
  {
    *a8 = 0;
    if ( !(unsigned int)GetTimeValidCrl((const char *)3, a1, a1, a2, a3, a4, a5, 1, a6, (LPVOID *)&pCrlContext, a9) )
      goto LABEL_15;
  }
  pCrlInfo = pCrlContext->pCrlInfo;
  cExtension = pCrlInfo->cExtension;
  for ( i = pCrlInfo->rgExtension; ; ++i )
  {
    if ( !cExtension )
    {
      result = 1;
      *a7 = pCrlContext;
      return result;
    }
    if ( i->fCritical )
      break;
LABEL_13:
    --cExtension;
  }
  for ( j = &rgpszSupportedCrlExtensionOID; *j; ++j )
  {
    pszObjId = (unsigned __int8 *)i->pszObjId;
    do
    {
      v18 = pszObjId[(char *)*j - i->pszObjId];
      v19 = *pszObjId - v18;
      if ( v19 )
        break;
      ++pszObjId;
    }
    while ( v18 );
    if ( !v19 )
      goto LABEL_13;
  }
  v23[0] = pCrlContext;
  v23[1] = L"IsCrlCriticalExtensionSupported";
  v23[2] = 0;
  v25 = 0;
  v24 = 0;
  I_CertDiagControl(5, v23, 0);
  SetLastError(0x80092012);
LABEL_15:
  v20 = pCrlContext;
  if ( pCrlContext )
  {
    CertFreeCRLContext(pCrlContext);
    v20 = 0;
  }
  result = 0;
  *a7 = v20;
  return result;
}

```

## disassembly

```asm
0x18000f980  push    rbx
0x18000f982  push    rbp
0x18000f983  push    rsi
0x18000f984  push    rdi
0x18000f985  push    r12
0x18000f987  push    r13
0x18000f989  push    r14
0x18000f98b  push    r15
0x18000f98d  sub     rsp, 0A8h
0x18000f994  mov     rdi, [rsp+0E8h+arg_40]
0x18000f99c  lea     rax, [rsp+0E8h+pCrlContext]
0x18000f9a1  mov     r15, [rsp+0E8h+arg_28]
0x18000f9a9  xor     r13d, r13d
0x18000f9ac  mov     r12d, [rsp+0E8h+arg_20]
0x18000f9b4  mov     esi, r9d
0x18000f9b7  mov     [rsp+0E8h+var_98], rdi; int *
0x18000f9bc  mov     rbp, r8
0x18000f9bf  mov     [rsp+0E8h+var_A0], rax; struct _CRL_CONTEXT **
0x18000f9c4  mov     r14, rdx
0x18000f9c7  mov     [rsp+0E8h+var_A8], r15; struct _FILETIME *
0x18000f9cc  mov     rbx, rcx
0x18000f9cf  mov     [rsp+0E8h+var_B0], r13d; unsigned int
0x18000f9d4  mov     [rsp+0E8h+var_B8], r12d; unsigned int
0x18000f9d9  mov     [rsp+0E8h+var_C0], r9d; int
0x18000f9de  mov     r9, rdx; struct _CERT_CONTEXT *
0x18000f9e1  mov     [rsp+0E8h+var_C8], r8; struct _CERT_REVOCATION_PARA *
0x18000f9e6  mov     rdx, rcx; void *
0x18000f9e9  mov     r8, rcx; struct _CERT_CONTEXT *
0x18000f9ec  mov     [rsp+0E8h+pCrlContext], r13
0x18000f9f1  mov     ecx, 3; char *
0x18000f9f6  mov     [rdi], r13d
0x18000f9f9  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x18000f9fe  test    eax, eax
0x18000fa00  mov     rax, [rsp+0E8h+arg_38]
0x18000fa08  jz      short loc_18000FA77
0x18000fa0a  mov     dword ptr [rax], 1
0x18000fa10  mov     rdi, [rsp+0E8h+pCrlContext]
0x18000fa15  lea     rsi, ?rgpszSupportedCrlExtensionOID@@3PAPEBDA; char const * near * rgpszSupportedCrlExtensionOID
0x18000fa1c  mov     rax, [rdi+18h]
0x18000fa20  mov     ebx, [rax+50h]
0x18000fa23  mov     r11, [rax+58h]
0x18000fa27  test    ebx, ebx
0x18000fa29  jz      loc_18000FB39
0x18000fa2f  cmp     [r11+8], r13d
0x18000fa33  jz      short loc_18000FA6F
0x18000fa35  mov     r10, [r11]
0x18000fa38  mov     r9, rsi
0x18000fa3b  nop     dword ptr [rax+rax+00h]
0x18000fa40  mov     r8, [r9]
0x18000fa43  test    r8, r8
0x18000fa46  jz      loc_18000FAEF
0x18000fa4c  mov     rax, r10
0x18000fa4f  sub     r8, r10
0x18000fa52  movzx   edx, byte ptr [rax]
0x18000fa55  movzx   ecx, byte ptr [rax+r8]
0x18000fa5a  sub     edx, ecx
0x18000fa5c  jnz     short loc_18000FA65
0x18000fa5e  inc     rax
0x18000fa61  test    ecx, ecx
0x18000fa63  jnz     short loc_18000FA52
0x18000fa65  test    edx, edx
0x18000fa67  jz      short loc_18000FA6F
0x18000fa69  add     r9, 8
0x18000fa6d  jmp     short loc_18000FA40
0x18000fa6f  dec     ebx
0x18000fa71  add     r11, 20h ; ' '
0x18000fa75  jmp     short loc_18000FA27
0x18000fa77  mov     [rsp+0E8h+var_98], rdi; int *
0x18000fa7c  mov     r9, r14; struct _CERT_CONTEXT *
0x18000fa7f  mov     [rax], r13d
0x18000fa82  mov     r8, rbx; struct _CERT_CONTEXT *
0x18000fa85  lea     rax, [rsp+0E8h+pCrlContext]
0x18000fa8a  mov     rdx, rbx; void *
0x18000fa8d  mov     [rsp+0E8h+var_A0], rax; struct _CRL_CONTEXT **
0x18000fa92  mov     ecx, 3; char *
0x18000fa97  mov     [rsp+0E8h+var_A8], r15; struct _FILETIME *
0x18000fa9c  mov     [rsp+0E8h+var_B0], 1; unsigned int
0x18000faa4  mov     [rsp+0E8h+var_B8], r12d; unsigned int
0x18000faa9  mov     [rsp+0E8h+var_C0], esi; int
0x18000faad  mov     [rsp+0E8h+var_C8], rbp; struct _CERT_REVOCATION_PARA *
0x18000fab2  call    ?GetTimeValidCrl@@YAHPEBDPEAXPEBU_CERT_CONTEXT@@2PEAU_CERT_REVOCATION_PARA@@HKKPEAU_FILETIME@@PEAPEBU_CRL_CONTEXT@@PEAH@Z; GetTimeValidCrl(char const *,void *,_CERT_CONTEXT const *,_CERT_CONTEXT const *,_CERT_REVOCATION_PARA *,int,ulong,ulong,_FILETIME *,_CRL_CONTEXT const * *,int *)
0x18000fab7  test    eax, eax
0x18000fab9  jnz     loc_18000FA10
0x18000fabf  mov     rdx, [rsp+0E8h+pCrlContext]
0x18000fac4  test    rdx, rdx
0x18000fac7  jnz     loc_18000FB4B
0x18000facd  mov     rcx, [rsp+0E8h+arg_30]
0x18000fad5  mov     eax, r13d
0x18000fad8  mov     [rcx], rdx
0x18000fadb  add     rsp, 0A8h
0x18000fae2  pop     r15
0x18000fae4  pop     r14
0x18000fae6  pop     r13
0x18000fae8  pop     r12
0x18000faea  pop     rdi
0x18000faeb  pop     rsi
0x18000faec  pop     rbp
0x18000faed  pop     rbx
0x18000faee  retn
0x18000faef  lea     rax, aIscrlcriticale; "IsCrlCriticalExtensionSupported"
0x18000faf6  mov     [rsp+0E8h+var_80], rdi
0x18000fafb  xorps   xmm0, xmm0
0x18000fafe  mov     [rsp+0E8h+var_78], rax
0x18000fb03  xor     r8d, r8d
0x18000fb06  mov     [rsp+0E8h+var_70], r13
0x18000fb0b  lea     rdx, [rsp+0E8h+var_80]
0x18000fb10  mov     [rsp+0E8h+var_58], r13
0x18000fb18  mov     ecx, 5
0x18000fb1d  movdqu  [rsp+0E8h+var_68], xmm0
0x18000fb26  call    cs:__imp_I_CertDiagControl
0x18000fb2c  mov     ecx, 80092012h; dwErrCode
0x18000fb31  call    cs:__imp_SetLastError
0x18000fb37  jmp     short loc_18000FABF
0x18000fb39  mov     rcx, [rsp+0E8h+arg_30]
0x18000fb41  mov     eax, 1
0x18000fb46  mov     [rcx], rdi
0x18000fb49  jmp     short loc_18000FADB
0x18000fb4b  mov     rcx, rdx; pCrlContext
0x18000fb4e  call    cs:__imp_CertFreeCRLContext
0x18000fb54  mov     rdx, r13
0x18000fb57  jmp     loc_18000FACD
```
