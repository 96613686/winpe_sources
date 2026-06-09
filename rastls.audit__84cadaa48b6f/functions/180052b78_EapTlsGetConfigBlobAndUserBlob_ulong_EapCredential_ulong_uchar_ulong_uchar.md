# EapTlsGetConfigBlobAndUserBlob(ulong,_EapCredential,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x180052b78`
- end: `0x180052e5a`
- name: `?EapTlsGetConfigBlobAndUserBlob@@YAKKU_EapCredential@@PEAKPEAPEAE12@Z`
- size: `738`
- prototype: `unsigned int __fastcall(unsigned int, struct _EapCredential *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005d140`

## callees

- `0x180005010`
- `0x1800080a0`
- `0x180008420`
- `0x18001fa30`
- `0x18002318c`
- `0x180033f40`
- `0x180052b78`
- `0x180075a04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052bf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052dd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052de1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052bf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052dc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052dd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052de1`
- `CRYPT32!CertCloseStore` at `0x180052df7`
- `CRYPT32!CertCloseStore` at `0x180052df7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180052d6d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180052d6d`
- `CRYPT32!CertFreeCertificateContext` at `0x180052e0c`
- `CRYPT32!CertFreeCertificateContext` at `0x180052e0c`
- `CRYPT32!CertOpenStore` at `0x180052d11`
- `CRYPT32!CertOpenStore` at `0x180052d11`
- `CRYPT32!CryptProtectData` at `0x180052cb2`
- `CRYPT32!CryptProtectData` at `0x180052cb2`

## pseudocode

```c
__int64 __fastcall EapTlsGetConfigBlobAndUserBlob(
        unsigned int a1,
        struct _EapCredential *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v8; // r15
  struct _EAPTLS_USER_PROPERTIES *v9; // rdi
  void *v10; // rsi
  char v11; // r12
  DWORD ConnectionData; // ebx
  EapUsernamePasswordCredential username_password; // xmm0
  int v14; // eax
  BYTE *password; // rcx
  __int64 v16; // rax
  HCERTSTORE v17; // rax
  DWORD *v18; // r9
  unsigned __int8 *v19; // rcx
  struct _EAPTLS_USER_PROPERTIES *v21; // [rsp+40h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  struct _EAPTLS_CONN_PROPERTIES_V1 *v23; // [rsp+50h] [rbp-29h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-21h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-19h] BYREF
  DATA_BLOB pDataIn; // [rsp+70h] [rbp-9h] BYREF

  hMem = 0;
  v23 = 0;
  v21 = 0;
  pCertContext = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = a1;
  pDataIn = 0;
  pDataOut = 0;
  ConnectionData = EapTlsReadConnectionData(a1, 0, 0, (struct _EAPTLS_CONN_PROPERTIES **)&hMem);
  if ( !ConnectionData )
  {
    ConnectionData = ConnPropGetV1Struct((struct _EAPTLS_CONN_PROPERTIES *)hMem, &v23);
    if ( !ConnectionData )
    {
      LocalFree(hMem);
      v8 = v23;
      hMem = 0;
      ConnectionData = ConnPropGetV0Struct(v23, (struct _EAPTLS_CONN_PROPERTIES **)&hMem);
      if ( ConnectionData )
        goto LABEL_22;
      ConnectionData = EapTlsReadUserData(0, 0, &v21);
      if ( !ConnectionData )
      {
        if ( (v11 & 0x20) != 0 )
        {
          v17 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x28000u, L"MY");
          v10 = v17;
          if ( v17 )
          {
            ConnectionData = GetDefaultClientMachineCert(v17, 0, 0, &pCertContext);
            if ( !ConnectionData )
            {
              v9 = v21;
              v18 = (DWORD *)((char *)v21 + 16);
              *((_DWORD *)v21 + 4) = 20;
              if ( !CertGetCertificateContextProperty(pCertContext, 3u, v18 + 1, v18) )
              {
LABEL_12:
                ConnectionData = GetLastError();
                goto LABEL_22;
              }
              goto LABEL_20;
            }
          }
          else
          {
            ConnectionData = GetLastError();
          }
        }
        else
        {
          v9 = v21;
          if ( a2->credType != EAP_CERTIFICATE_CREDENTIAL )
          {
            ConnectionData = 87;
            goto LABEL_22;
          }
          username_password = a2->credData.username_password;
          v14 = *((_DWORD *)&a2->credData.sim + 4);
          password = (BYTE *)a2->credData.certificate.password;
          *((_DWORD *)v21 + 4) = 20;
          *(EapUsernamePasswordCredential *)((char *)v9 + 20) = username_password;
          *((_DWORD *)v9 + 9) = v14;
          if ( !password )
            goto LABEL_20;
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)&password[2 * v16] );
          pDataIn.pbData = password;
          pDataIn.cbData = 2 * v16;
          if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
            goto LABEL_12;
          ConnectionData = SaveAuthBuffer(&v21, pDataOut.pbData, pDataOut.cbData);
          if ( !ConnectionData )
          {
            v9 = v21;
LABEL_20:
            v19 = (unsigned __int8 *)hMem;
            hMem = 0;
            *a3 = *((_DWORD *)v19 + 1);
            *a4 = v19;
            *a5 = *((_DWORD *)v9 + 2);
            *a6 = (unsigned __int8 *)v9;
            v9 = 0;
            goto LABEL_22;
          }
        }
      }
      v9 = v21;
      goto LABEL_22;
    }
    v8 = v23;
  }
LABEL_22:
  LocalFree(hMem);
  LocalFree(v8);
  LocalFree(v9);
  LocalFree(pDataOut.pbData);
  if ( v10 )
    CertCloseStore(v10, 0);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 890, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, ConnectionData);
  return ConnectionData;
}

```

## disassembly

```asm
0x180052b78  mov     [rsp-8+arg_10], r8
0x180052b7d  push    rbp
0x180052b7e  push    rbx
0x180052b7f  push    rsi
0x180052b80  push    rdi
0x180052b81  push    r12
0x180052b83  push    r13
0x180052b85  push    r14
0x180052b87  push    r15
0x180052b89  lea     rbp, [rsp-0Fh]
0x180052b8e  sub     rsp, 88h
0x180052b95  xor     eax, eax
0x180052b97  mov     r13, r9
0x180052b9a  mov     r14, rdx
0x180052b9d  mov     [rbp+47h+hMem], rax
0x180052ba1  xorps   xmm0, xmm0
0x180052ba4  mov     [rbp+47h+var_70], rax
0x180052ba8  xorps   xmm1, xmm1
0x180052bab  mov     [rbp+47h+var_80], rax
0x180052baf  lea     r9, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES **
0x180052bb3  mov     [rbp+47h+pCertContext], rax
0x180052bb7  xor     edx, edx; unsigned __int8 *
0x180052bb9  xor     r8d, r8d; unsigned int
0x180052bbc  mov     r15d, eax
0x180052bbf  mov     edi, eax
0x180052bc1  mov     esi, eax
0x180052bc3  mov     r12d, ecx
0x180052bc6  movups  xmmword ptr [rbp+47h+pDataIn.cbData], xmm0
0x180052bca  movups  xmmword ptr [rbp+47h+var_60.cbData], xmm1
0x180052bce  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x180052bd3  mov     ebx, eax
0x180052bd5  test    eax, eax
0x180052bd7  jnz     loc_180052DAF
0x180052bdd  mov     rcx, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES *
0x180052be1  lea     rdx, [rbp+47h+var_70]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180052be5  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180052bea  mov     ebx, eax
0x180052bec  test    eax, eax
0x180052bee  jnz     loc_180052DAB
0x180052bf4  mov     rcx, [rbp+47h+hMem]; hMem
0x180052bf8  call    cs:__imp_LocalFree
0x180052bff  nop     dword ptr [rax+rax+00h]
0x180052c04  mov     r15, [rbp+47h+var_70]
0x180052c08  lea     rdx, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES **
0x180052c0c  mov     rcx, r15; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x180052c0f  mov     [rbp+47h+hMem], rsi
0x180052c13  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x180052c18  mov     ebx, eax
0x180052c1a  test    eax, eax
0x180052c1c  jnz     loc_180052DAF
0x180052c22  lea     r8, [rbp+47h+var_80]; struct _EAPTLS_USER_PROPERTIES **
0x180052c26  xor     edx, edx; unsigned int
0x180052c28  xor     ecx, ecx; Src
0x180052c2a  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x180052c2f  mov     ebx, eax
0x180052c31  test    eax, eax
0x180052c33  jnz     loc_180052D36
0x180052c39  test    r12b, 20h
0x180052c3d  jnz     loc_180052CF5
0x180052c43  cmp     dword ptr [r14], 3
0x180052c47  mov     rdi, [rbp+47h+var_80]
0x180052c4b  jz      short loc_180052C55
0x180052c4d  lea     ebx, [rsi+57h]
0x180052c50  jmp     loc_180052DAF
0x180052c55  movups  xmm0, xmmword ptr [r14+8]
0x180052c5a  mov     eax, [r14+18h]
0x180052c5e  mov     rcx, [r14+20h]
0x180052c62  xor     r14d, r14d
0x180052c65  mov     dword ptr [rdi+10h], 14h
0x180052c6c  movups  xmmword ptr [rdi+14h], xmm0
0x180052c70  mov     [rdi+24h], eax
0x180052c73  test    rcx, rcx
0x180052c76  jz      loc_180052D81
0x180052c7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052c80  inc     rax
0x180052c83  cmp     [rcx+rax*2], r14w
0x180052c88  jnz     short loc_180052C80
0x180052c8a  add     eax, eax
0x180052c8c  mov     [rbp+47h+pDataIn.pbData], rcx
0x180052c90  mov     [rbp+47h+pDataIn.cbData], eax
0x180052c93  lea     rcx, [rbp+47h+pDataIn]; pDataIn
0x180052c97  lea     rax, [rbp+47h+var_60]
0x180052c9b  xor     r9d, r9d; pvReserved
0x180052c9e  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x180052ca3  xor     r8d, r8d; pOptionalEntropy
0x180052ca6  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x180052cab  xor     edx, edx; szDataDescr
0x180052cad  mov     [rsp+0C0h+pPromptStruct], r14; pPromptStruct
0x180052cb2  call    cs:__imp_CryptProtectData
0x180052cb9  nop     dword ptr [rax+rax+00h]
0x180052cbe  test    eax, eax
0x180052cc0  jnz     short loc_180052CD5
0x180052cc2  call    cs:__imp_GetLastError
0x180052cc9  nop     dword ptr [rax+rax+00h]
0x180052cce  mov     ebx, eax
0x180052cd0  jmp     loc_180052DAF
0x180052cd5  mov     r8d, [rbp+47h+var_60.cbData]; unsigned int
0x180052cd9  lea     rcx, [rbp+47h+var_80]; struct _EAPTLS_USER_PROPERTIES **
0x180052cdd  mov     rdx, [rbp+47h+var_60.pbData]; unsigned __int8 *
0x180052ce1  call    ?SaveAuthBuffer@@YAKPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBEK@Z; SaveAuthBuffer(_EAPTLS_USER_PROPERTIES * *,uchar const *,ulong)
0x180052ce6  mov     ebx, eax
0x180052ce8  test    eax, eax
0x180052cea  jnz     short loc_180052D36
0x180052cec  mov     rdi, [rbp+47h+var_80]
0x180052cf0  jmp     loc_180052D81
0x180052cf5  xor     r8d, r8d; hCryptProv
0x180052cf8  lea     rax, aMy_1; "MY"
0x180052cff  mov     r9d, 28000h; dwFlags
0x180052d05  mov     [rsp+0C0h+pPromptStruct], rax; pvPara
0x180052d0a  lea     edx, [r8+1]; dwEncodingType
0x180052d0e  lea     ecx, [rdx+9]; lpszStoreProvider
0x180052d11  call    cs:__imp_CertOpenStore
0x180052d18  nop     dword ptr [rax+rax+00h]
0x180052d1d  xor     r14d, r14d
0x180052d20  mov     rsi, rax
0x180052d23  test    rax, rax
0x180052d26  jnz     short loc_180052D3C
0x180052d28  call    cs:__imp_GetLastError
0x180052d2f  nop     dword ptr [rax+rax+00h]
0x180052d34  mov     ebx, eax
0x180052d36  mov     rdi, [rbp+47h+var_80]
0x180052d3a  jmp     short loc_180052DAF
0x180052d3c  lea     r9, [rbp+47h+pCertContext]; struct _CERT_CONTEXT **
0x180052d40  xor     r8d, r8d; struct _EAPTLS_FILTER_PROP *
0x180052d43  xor     edx, edx; int
0x180052d45  mov     rcx, rax; hStore
0x180052d48  call    ?GetDefaultClientMachineCert@@YAKPEAXHPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@@Z; GetDefaultClientMachineCert(void *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *)
0x180052d4d  mov     ebx, eax
0x180052d4f  test    eax, eax
0x180052d51  jnz     short loc_180052D36
0x180052d53  mov     rdi, [rbp+47h+var_80]
0x180052d57  lea     edx, [rax+3]; dwPropId
0x180052d5a  lea     r9, [rdi+10h]; pcbData
0x180052d5e  mov     dword ptr [r9], 14h
0x180052d65  lea     r8, [r9+4]; pvData
0x180052d69  mov     rcx, [rbp+47h+pCertContext]; pCertContext
0x180052d6d  call    cs:__imp_CertGetCertificateContextProperty
0x180052d74  nop     dword ptr [rax+rax+00h]
0x180052d79  test    eax, eax
0x180052d7b  jz      loc_180052CC2
0x180052d81  mov     rcx, [rbp+47h+hMem]
0x180052d85  mov     rdx, [rbp+47h+arg_10]
0x180052d89  mov     [rbp+47h+hMem], r14
0x180052d8d  mov     eax, [rcx+4]
0x180052d90  mov     [rdx], eax
0x180052d92  mov     rax, [rbp+47h+arg_20]
0x180052d96  mov     [r13+0], rcx
0x180052d9a  mov     ecx, [rdi+8]
0x180052d9d  mov     [rax], ecx
0x180052d9f  mov     rax, [rbp+47h+arg_28]
0x180052da3  mov     [rax], rdi
0x180052da6  mov     rdi, r14
0x180052da9  jmp     short loc_180052DAF
0x180052dab  mov     r15, [rbp+47h+var_70]
0x180052daf  mov     rcx, [rbp+47h+hMem]; hMem
0x180052db3  call    cs:__imp_LocalFree
0x180052dba  nop     dword ptr [rax+rax+00h]
0x180052dbf  mov     rcx, r15; hMem
0x180052dc2  call    cs:__imp_LocalFree
0x180052dc9  nop     dword ptr [rax+rax+00h]
0x180052dce  mov     rcx, rdi; hMem
0x180052dd1  call    cs:__imp_LocalFree
0x180052dd8  nop     dword ptr [rax+rax+00h]
0x180052ddd  mov     rcx, [rbp+47h+var_60.pbData]; hMem
0x180052de1  call    cs:__imp_LocalFree
0x180052de8  nop     dword ptr [rax+rax+00h]
0x180052ded  test    rsi, rsi
0x180052df0  jz      short loc_180052E03
0x180052df2  xor     edx, edx; dwFlags
0x180052df4  mov     rcx, rsi; hCertStore
0x180052df7  call    cs:__imp_CertCloseStore
0x180052dfe  nop     dword ptr [rax+rax+00h]
0x180052e03  mov     rcx, [rbp+47h+pCertContext]; pCertContext
0x180052e07  test    rcx, rcx
0x180052e0a  jz      short loc_180052E18
0x180052e0c  call    cs:__imp_CertFreeCertificateContext
0x180052e13  nop     dword ptr [rax+rax+00h]
0x180052e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e1f  lea     rax, WPP_GLOBAL_Control
0x180052e26  cmp     rcx, rax
0x180052e29  jz      short loc_180052E43
0x180052e2b  mov     rcx, [rcx+10h]
0x180052e2f  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180052e36  mov     edx, 37Ah
0x180052e3b  mov     r9d, ebx
0x180052e3e  call    WPP_SF_d
0x180052e43  mov     eax, ebx
0x180052e45  add     rsp, 88h
0x180052e4c  pop     r15
0x180052e4e  pop     r14
0x180052e50  pop     r13
0x180052e52  pop     r12
0x180052e54  pop     rdi
0x180052e55  pop     rsi
0x180052e56  pop     rbx
0x180052e57  pop     rbp
0x180052e58  retn
```
