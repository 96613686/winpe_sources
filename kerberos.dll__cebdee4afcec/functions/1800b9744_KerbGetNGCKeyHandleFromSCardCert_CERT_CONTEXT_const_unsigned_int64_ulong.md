# KerbGetNGCKeyHandleFromSCardCert(_CERT_CONTEXT const *,unsigned __int64 *,ulong *)

- ea: `0x1800b9744`
- end: `0x1800b9971`
- name: `?KerbGetNGCKeyHandleFromSCardCert@@YAJPEBU_CERT_CONTEXT@@PEA_KPEAK@Z`
- size: `557`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800603d8`

## callees

- `0x180070680`
- `0x18008b70c`
- `0x1800b9744`
- `0x1800d8354`
- `0x1800f1a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b97e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b97e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b97df`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b98ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b97df`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b98ee`
- `ntdll!NtClose` at `0x1800b993b`
- `ntdll!NtClose` at `0x1800b993b`
- `ntdll!NtOpenThreadToken` at `0x1800b979b`
- `ntdll!NtOpenThreadToken` at `0x1800b979b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800b9877`
- `CRYPT32!CertSetCertificateContextProperty` at `0x1800b9877`
- `ncrypt!NCryptFreeObject` at `0x1800b98d8`
- `ncrypt!NCryptFreeObject` at `0x1800b98d8`

## string_xrefs

- `0x1800b97b2`: `NtOpenThreadToken failed - %#x\n`
- `0x1800b9806`: `SetThreadToken failed - %#x\n`
- `0x1800b98fe`: `SetThreadToken(Revert) failed - last error %#x\n`

## pseudocode

```c
__int64 __fastcall KerbGetNGCKeyHandleFromSCardCert(
        PCCERT_CONTEXT pCertContext,
        unsigned __int64 *a2,
        unsigned int *a3)
{
  signed int v3; // edi
  int v7; // r15d
  NTSTATUS v8; // eax
  __int64 v9; // rdx
  signed int v10; // ebx
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  NCRYPT_HANDLE hObject; // [rsp+30h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  __int128 pvData; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]

  *a2 = 0;
  v3 = 0;
  *a3 = 0;
  v18 = 0;
  TokenHandle = 0;
  hObject = 0;
  v7 = 0;
  pvData = 0;
  v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -1073741700 )
    {
      KerbTracerT::Log(1, "KerbGetNGCKeyHandleFromSCardCert", 2394, "NtOpenThreadToken failed - %#x\n", v8);
      goto LABEL_20;
    }
    TokenHandle = 0;
    goto LABEL_12;
  }
  if ( SetThreadToken(0, 0) )
  {
    v7 = 1;
LABEL_12:
    v12 = SCardCertToNgc(pCertContext, v9, &hObject);
    v10 = v12;
    if ( v12 )
    {
      KerbTracerT::Log(1, "KerbGetNGCKeyHandleFromSCardCert", 2431, "SCardCertToNgc failed - %#x\n", v12);
      v3 = v10;
    }
    else
    {
      LODWORD(pvData) = 24;
      LODWORD(v18) = -1;
      *((_QWORD *)&pvData + 1) = hObject;
      if ( CertSetCertificateContextProperty(pCertContext, 5u, 0, &pvData) )
      {
        v10 = 0;
        *a2 = hObject;
        hObject = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0xC0070000;
        else
          v10 = LastError;
        KerbTracerT::Log(
          1,
          "KerbGetNGCKeyHandleFromSCardCert",
          2452,
          "CertSetCertificateContextProperty failed - %#x, last error %#x\n",
          v10,
          LastError);
      }
    }
    goto LABEL_20;
  }
  v11 = GetLastError();
  v3 = v11;
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0xC0070000;
  else
    v10 = v11;
  KerbTracerT::Log(1, "KerbGetNGCKeyHandleFromSCardCert", 2417, "SetThreadToken failed - %#x\n", v10);
LABEL_20:
  if ( hObject )
    NCryptFreeObject(hObject);
  if ( TokenHandle )
  {
    if ( v7 )
    {
      if ( !SetThreadToken(0, TokenHandle) )
      {
        v3 = GetLastError();
        KerbTracerT::Log(
          1,
          "KerbGetNGCKeyHandleFromSCardCert",
          2477,
          "SetThreadToken(Revert) failed - last error %#x\n",
          v3);
        if ( v10 >= 0 )
        {
          if ( v3 > 0 )
            v10 = (unsigned __int16)v3 | 0xC0070000;
          else
            v10 = v3;
        }
      }
    }
    NtClose(TokenHandle);
  }
  if ( v10 < 0 )
  {
    *a3 = v3;
    return (unsigned int)ScNtStatusTranslation((unsigned int)v10, (unsigned int)v3);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b9744  push    rbp
0x1800b9746  push    rbx
0x1800b9747  push    rsi
0x1800b9748  push    rdi
0x1800b9749  push    r12
0x1800b974b  push    r14
0x1800b974d  push    r15
0x1800b974f  mov     rbp, rsp
0x1800b9752  sub     rsp, 60h
0x1800b9756  mov     rax, cs:__security_cookie
0x1800b975d  xor     rax, rsp
0x1800b9760  mov     [rbp+var_8], rax
0x1800b9764  xor     eax, eax
0x1800b9766  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800b976a  mov     [rdx], rax
0x1800b976d  xor     edi, edi
0x1800b976f  mov     r12, r8
0x1800b9772  mov     [r8], eax
0x1800b9775  mov     r14, rdx
0x1800b9778  mov     [rbp+var_10], rax
0x1800b977c  mov     rsi, rcx
0x1800b977f  mov     [rbp+TokenHandle], rax
0x1800b9783  xorps   xmm0, xmm0
0x1800b9786  mov     [rbp+hObject], rax
0x1800b978a  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800b978d  mov     r8b, 1; OpenAsSelf
0x1800b9790  lea     rcx, [rdi-2]; ThreadHandle
0x1800b9794  xor     r15d, r15d
0x1800b9797  movups  [rbp+pvData], xmm0
0x1800b979b  call    cs:__imp_NtOpenThreadToken
0x1800b97a1  mov     ebx, eax
0x1800b97a3  test    eax, eax
0x1800b97a5  jns     short loc_1800B97DB
0x1800b97a7  cmp     eax, 0C000007Ch
0x1800b97ac  jz      short loc_1800B97D5
0x1800b97ae  mov     [rsp+60h+var_40], eax
0x1800b97b2  lea     r9, aNtopenthreadto_0; "NtOpenThreadToken failed - %#x\n"
0x1800b97b9  mov     r8d, 95Ah
0x1800b97bf  lea     rdx, aKerbgetngckeyh; "KerbGetNGCKeyHandleFromSCardCert"
0x1800b97c6  mov     ecx, 1
0x1800b97cb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b97d0  jmp     loc_1800B98CF
0x1800b97d5  mov     [rbp+TokenHandle], rdi
0x1800b97d9  jmp     short loc_1800B981B
0x1800b97db  xor     edx, edx; Token
0x1800b97dd  xor     ecx, ecx; Thread
0x1800b97df  call    cs:__imp_SetThreadToken
0x1800b97e5  test    eax, eax
0x1800b97e7  jnz     short loc_1800B9815
0x1800b97e9  call    cs:__imp_GetLastError
0x1800b97ef  mov     edi, eax
0x1800b97f1  test    eax, eax
0x1800b97f3  jg      short loc_1800B97F9
0x1800b97f5  mov     ebx, eax
0x1800b97f7  jmp     short loc_1800B9802
0x1800b97f9  movzx   ebx, ax
0x1800b97fc  or      ebx, 0C0070000h
0x1800b9802  mov     [rsp+60h+var_40], ebx
0x1800b9806  lea     r9, aSetthreadtoken_0; "SetThreadToken failed - %#x\n"
0x1800b980d  mov     r8d, 971h
0x1800b9813  jmp     short loc_1800B97BF
0x1800b9815  mov     r15d, 1
0x1800b981b  lea     r8, [rbp+hObject]
0x1800b981f  mov     rcx, rsi
0x1800b9822  call    SCardCertToNgc
0x1800b9827  mov     ebx, eax
0x1800b9829  test    eax, eax
0x1800b982b  jz      short loc_1800B9853
0x1800b982d  lea     r9, aScardcerttongc; "SCardCertToNgc failed - %#x\n"
0x1800b9834  mov     [rsp+60h+var_40], eax
0x1800b9838  mov     r8d, 97Fh
0x1800b983e  lea     rdx, aKerbgetngckeyh; "KerbGetNGCKeyHandleFromSCardCert"
0x1800b9845  mov     ecx, 1
0x1800b984a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b984f  mov     edi, ebx
0x1800b9851  jmp     short loc_1800B98CF
0x1800b9853  mov     rax, [rbp+hObject]
0x1800b9857  lea     r9, [rbp+pvData]; pvData
0x1800b985b  xor     r8d, r8d; dwFlags
0x1800b985e  mov     dword ptr [rbp+pvData], 18h
0x1800b9865  mov     rcx, rsi; pCertContext
0x1800b9868  mov     dword ptr [rbp+var_10], 0FFFFFFFFh
0x1800b986f  mov     qword ptr [rbp+pvData+8], rax
0x1800b9873  lea     edx, [r8+5]; dwPropId
0x1800b9877  call    cs:__imp_CertSetCertificateContextProperty
0x1800b987d  test    eax, eax
0x1800b987f  jnz     short loc_1800B98C2
0x1800b9881  call    cs:__imp_GetLastError
0x1800b9887  mov     edi, eax
0x1800b9889  test    eax, eax
0x1800b988b  jg      short loc_1800B9891
0x1800b988d  mov     ebx, eax
0x1800b988f  jmp     short loc_1800B989A
0x1800b9891  movzx   ebx, ax
0x1800b9894  or      ebx, 0C0070000h
0x1800b989a  mov     [rsp+60h+var_38], eax
0x1800b989e  lea     r9, aCertsetcertifi_0; "CertSetCertificateContextProperty faile"...
0x1800b98a5  mov     r8d, 994h
0x1800b98ab  mov     [rsp+60h+var_40], ebx
0x1800b98af  lea     rdx, aKerbgetngckeyh; "KerbGetNGCKeyHandleFromSCardCert"
0x1800b98b6  mov     ecx, 1
0x1800b98bb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b98c0  jmp     short loc_1800B98CF
0x1800b98c2  mov     rax, [rbp+hObject]
0x1800b98c6  xor     ebx, ebx
0x1800b98c8  mov     [r14], rax
0x1800b98cb  mov     [rbp+hObject], rdi
0x1800b98cf  mov     rcx, [rbp+hObject]; hObject
0x1800b98d3  test    rcx, rcx
0x1800b98d6  jz      short loc_1800B98DE
0x1800b98d8  call    cs:__imp_NCryptFreeObject
0x1800b98de  mov     rdx, [rbp+TokenHandle]; Token
0x1800b98e2  test    rdx, rdx
0x1800b98e5  jz      short loc_1800B9941
0x1800b98e7  test    r15d, r15d
0x1800b98ea  jz      short loc_1800B9937
0x1800b98ec  xor     ecx, ecx; Thread
0x1800b98ee  call    cs:__imp_SetThreadToken
0x1800b98f4  test    eax, eax
0x1800b98f6  jnz     short loc_1800B9937
0x1800b98f8  call    cs:__imp_GetLastError
0x1800b98fe  lea     r9, aSetthreadtoken; "SetThreadToken(Revert) failed - last er"...
0x1800b9905  mov     r8d, 9ADh
0x1800b990b  lea     rdx, aKerbgetngckeyh; "KerbGetNGCKeyHandleFromSCardCert"
0x1800b9912  mov     [rsp+60h+var_40], eax
0x1800b9916  mov     ecx, 1
0x1800b991b  mov     edi, eax
0x1800b991d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b9922  test    ebx, ebx
0x1800b9924  js      short loc_1800B9937
0x1800b9926  test    edi, edi
0x1800b9928  jg      short loc_1800B992E
0x1800b992a  mov     ebx, edi
0x1800b992c  jmp     short loc_1800B9937
0x1800b992e  movzx   ebx, di
0x1800b9931  or      ebx, 0C0070000h
0x1800b9937  mov     rcx, [rbp+TokenHandle]; Handle
0x1800b993b  call    cs:__imp_NtClose
0x1800b9941  test    ebx, ebx
0x1800b9943  jns     short loc_1800B9954
0x1800b9945  mov     edx, edi
0x1800b9947  mov     [r12], edi
0x1800b994b  mov     ecx, ebx
0x1800b994d  call    ScNtStatusTranslation
0x1800b9952  mov     ebx, eax
0x1800b9954  mov     eax, ebx
0x1800b9956  mov     rcx, [rbp+var_8]
0x1800b995a  xor     rcx, rsp; StackCookie
0x1800b995d  call    __security_check_cookie
0x1800b9962  add     rsp, 60h
0x1800b9966  pop     r15
0x1800b9968  pop     r14
0x1800b996a  pop     r12
0x1800b996c  pop     rdi
0x1800b996d  pop     rsi
0x1800b996e  pop     rbx
0x1800b996f  pop     rbp
0x1800b9970  retn
```
