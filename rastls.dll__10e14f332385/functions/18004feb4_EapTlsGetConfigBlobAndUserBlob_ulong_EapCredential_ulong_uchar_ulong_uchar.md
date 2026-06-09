# EapTlsGetConfigBlobAndUserBlob(ulong,_EapCredential,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x18004feb4`
- end: `0x18005014a`
- name: `?EapTlsGetConfigBlobAndUserBlob@@YAKKU_EapCredential@@PEAKPEAPEAE12@Z`
- size: `662`
- prototype: `unsigned int __fastcall(unsigned int, struct _EapCredential *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180059db0`

## callees

- `0x180004bd0`
- `0x180007910`
- `0x180007c60`
- `0x18001dec0`
- `0x18002131c`
- `0x1800316cc`
- `0x18004feb4`
- `0x180070c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050049`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ff34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ff34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800500e4`
- `CRYPT32!CertCloseStore` at `0x1800500f4`
- `CRYPT32!CertCloseStore` at `0x1800500f4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180050088`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180050088`
- `CRYPT32!CertFreeCertificateContext` at `0x180050103`
- `CRYPT32!CertFreeCertificateContext` at `0x180050103`
- `CRYPT32!CertOpenStore` at `0x180050038`
- `CRYPT32!CertOpenStore` at `0x180050038`
- `CRYPT32!CryptProtectData` at `0x18004ffe8`
- `CRYPT32!CryptProtectData` at `0x18004ffe8`

## pseudocode

```c
__int64 __fastcall EapTlsGetConfigBlobAndUserBlob(
        char a1,
        struct _EapCredential *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v8; // r15
  struct _EAPTLS_USER_PROPERTIES *v9; // rdi
  void *v10; // rsi
  unsigned int ConnectionData; // ebx
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
        if ( (a1 & 0x20) != 0 )
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 890, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, ConnectionData);
  return ConnectionData;
}

```

## disassembly

```asm
0x18004feb4  mov     [rsp-8+arg_10], r8
0x18004feb9  push    rbp
0x18004feba  push    rbx
0x18004febb  push    rsi
0x18004febc  push    rdi
0x18004febd  push    r12
0x18004febf  push    r13
0x18004fec1  push    r14
0x18004fec3  push    r15
0x18004fec5  lea     rbp, [rsp-0Fh]
0x18004feca  sub     rsp, 88h
0x18004fed1  xor     eax, eax
0x18004fed3  mov     r13, r9
0x18004fed6  mov     r14, rdx
0x18004fed9  mov     [rbp+47h+hMem], rax
0x18004fedd  xorps   xmm0, xmm0
0x18004fee0  mov     [rbp+47h+var_70], rax
0x18004fee4  xorps   xmm1, xmm1
0x18004fee7  mov     [rbp+47h+var_80], rax
0x18004feeb  lea     r9, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES **
0x18004feef  mov     [rbp+47h+pCertContext], rax
0x18004fef3  xor     edx, edx; unsigned __int8 *
0x18004fef5  xor     r8d, r8d; unsigned int
0x18004fef8  mov     r15d, eax
0x18004fefb  mov     edi, eax
0x18004fefd  mov     esi, eax
0x18004feff  mov     r12d, ecx
0x18004ff02  movups  xmmword ptr [rbp+47h+pDataIn.cbData], xmm0
0x18004ff06  movups  xmmword ptr [rbp+47h+var_60.cbData], xmm1
0x18004ff0a  call    ?EapTlsReadConnectionData@@YAKKPEAEKPEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; EapTlsReadConnectionData(ulong,uchar *,ulong,_EAPTLS_CONN_PROPERTIES * *)
0x18004ff0f  mov     ebx, eax
0x18004ff11  test    eax, eax
0x18004ff13  jnz     loc_1800500C4
0x18004ff19  mov     rcx, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES *
0x18004ff1d  lea     rdx, [rbp+47h+var_70]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x18004ff21  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x18004ff26  mov     ebx, eax
0x18004ff28  test    eax, eax
0x18004ff2a  jnz     loc_1800500C0
0x18004ff30  mov     rcx, [rbp+47h+hMem]; hMem
0x18004ff34  call    cs:__imp_LocalFree
0x18004ff3a  mov     r15, [rbp+47h+var_70]
0x18004ff3e  lea     rdx, [rbp+47h+hMem]; struct _EAPTLS_CONN_PROPERTIES **
0x18004ff42  mov     rcx, r15; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18004ff45  mov     [rbp+47h+hMem], rsi
0x18004ff49  call    ?ConnPropGetV0Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@@Z; ConnPropGetV0Struct(_EAPTLS_CONN_PROPERTIES_V1 *,_EAPTLS_CONN_PROPERTIES * *)
0x18004ff4e  mov     ebx, eax
0x18004ff50  test    eax, eax
0x18004ff52  jnz     loc_1800500C4
0x18004ff58  lea     r8, [rbp+47h+var_80]; struct _EAPTLS_USER_PROPERTIES **
0x18004ff5c  xor     edx, edx; unsigned int
0x18004ff5e  xor     ecx, ecx; Src
0x18004ff60  call    ?EapTlsReadUserData@@YAKPEAEKPEAPEAU_EAPTLS_USER_PROPERTIES@@@Z; EapTlsReadUserData(uchar *,ulong,_EAPTLS_USER_PROPERTIES * *)
0x18004ff65  mov     ebx, eax
0x18004ff67  test    eax, eax
0x18004ff69  jnz     loc_180050051
0x18004ff6f  test    r12b, 20h
0x18004ff73  jnz     loc_18005001C
0x18004ff79  cmp     dword ptr [r14], 3
0x18004ff7d  mov     rdi, [rbp+47h+var_80]
0x18004ff81  jz      short loc_18004FF8B
0x18004ff83  lea     ebx, [rsi+57h]
0x18004ff86  jmp     loc_1800500C4
0x18004ff8b  movups  xmm0, xmmword ptr [r14+8]
0x18004ff90  mov     eax, [r14+18h]
0x18004ff94  mov     rcx, [r14+20h]
0x18004ff98  xor     r14d, r14d
0x18004ff9b  mov     dword ptr [rdi+10h], 14h
0x18004ffa2  movups  xmmword ptr [rdi+14h], xmm0
0x18004ffa6  mov     [rdi+24h], eax
0x18004ffa9  test    rcx, rcx
0x18004ffac  jz      loc_180050096
0x18004ffb2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ffb6  inc     rax
0x18004ffb9  cmp     [rcx+rax*2], r14w
0x18004ffbe  jnz     short loc_18004FFB6
0x18004ffc0  add     eax, eax
0x18004ffc2  mov     [rbp+47h+pDataIn.pbData], rcx
0x18004ffc6  mov     [rbp+47h+pDataIn.cbData], eax
0x18004ffc9  lea     rcx, [rbp+47h+pDataIn]; pDataIn
0x18004ffcd  lea     rax, [rbp+47h+var_60]
0x18004ffd1  xor     r9d, r9d; pvReserved
0x18004ffd4  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x18004ffd9  xor     r8d, r8d; pOptionalEntropy
0x18004ffdc  mov     [rsp+0C0h+dwFlags], r14d; dwFlags
0x18004ffe1  xor     edx, edx; szDataDescr
0x18004ffe3  mov     [rsp+0C0h+pPromptStruct], r14; pPromptStruct
0x18004ffe8  call    cs:__imp_CryptProtectData
0x18004ffee  test    eax, eax
0x18004fff0  jnz     short loc_18004FFFF
0x18004fff2  call    cs:__imp_GetLastError
0x18004fff8  mov     ebx, eax
0x18004fffa  jmp     loc_1800500C4
0x18004ffff  mov     r8d, [rbp+47h+var_60.cbData]; unsigned int
0x180050003  lea     rcx, [rbp+47h+var_80]; struct _EAPTLS_USER_PROPERTIES **
0x180050007  mov     rdx, [rbp+47h+var_60.pbData]; unsigned __int8 *
0x18005000b  call    ?SaveAuthBuffer@@YAKPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBEK@Z; SaveAuthBuffer(_EAPTLS_USER_PROPERTIES * *,uchar const *,ulong)
0x180050010  mov     ebx, eax
0x180050012  test    eax, eax
0x180050014  jnz     short loc_180050051
0x180050016  mov     rdi, [rbp+47h+var_80]
0x18005001a  jmp     short loc_180050096
0x18005001c  xor     r8d, r8d; hCryptProv
0x18005001f  lea     rax, aMy_1; "MY"
0x180050026  mov     r9d, 28000h; dwFlags
0x18005002c  mov     [rsp+0C0h+pPromptStruct], rax; pvPara
0x180050031  lea     edx, [r8+1]; dwEncodingType
0x180050035  lea     ecx, [rdx+9]; lpszStoreProvider
0x180050038  call    cs:__imp_CertOpenStore
0x18005003e  xor     r14d, r14d
0x180050041  mov     rsi, rax
0x180050044  test    rax, rax
0x180050047  jnz     short loc_180050057
0x180050049  call    cs:__imp_GetLastError
0x18005004f  mov     ebx, eax
0x180050051  mov     rdi, [rbp+47h+var_80]
0x180050055  jmp     short loc_1800500C4
0x180050057  lea     r9, [rbp+47h+pCertContext]; struct _CERT_CONTEXT **
0x18005005b  xor     r8d, r8d; struct _EAPTLS_FILTER_PROP *
0x18005005e  xor     edx, edx; int
0x180050060  mov     rcx, rax; hStore
0x180050063  call    ?GetDefaultClientMachineCert@@YAKPEAXHPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@@Z; GetDefaultClientMachineCert(void *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *)
0x180050068  mov     ebx, eax
0x18005006a  test    eax, eax
0x18005006c  jnz     short loc_180050051
0x18005006e  mov     rdi, [rbp+47h+var_80]
0x180050072  lea     edx, [rax+3]; dwPropId
0x180050075  lea     r9, [rdi+10h]; pcbData
0x180050079  mov     dword ptr [r9], 14h
0x180050080  lea     r8, [r9+4]; pvData
0x180050084  mov     rcx, [rbp+47h+pCertContext]; pCertContext
0x180050088  call    cs:__imp_CertGetCertificateContextProperty
0x18005008e  test    eax, eax
0x180050090  jz      loc_18004FFF2
0x180050096  mov     rcx, [rbp+47h+hMem]
0x18005009a  mov     rdx, [rbp+47h+arg_10]
0x18005009e  mov     [rbp+47h+hMem], r14
0x1800500a2  mov     eax, [rcx+4]
0x1800500a5  mov     [rdx], eax
0x1800500a7  mov     rax, [rbp+47h+arg_20]
0x1800500ab  mov     [r13+0], rcx
0x1800500af  mov     ecx, [rdi+8]
0x1800500b2  mov     [rax], ecx
0x1800500b4  mov     rax, [rbp+47h+arg_28]
0x1800500b8  mov     [rax], rdi
0x1800500bb  mov     rdi, r14
0x1800500be  jmp     short loc_1800500C4
0x1800500c0  mov     r15, [rbp+47h+var_70]
0x1800500c4  mov     rcx, [rbp+47h+hMem]; hMem
0x1800500c8  call    cs:__imp_LocalFree
0x1800500ce  mov     rcx, r15; hMem
0x1800500d1  call    cs:__imp_LocalFree
0x1800500d7  mov     rcx, rdi; hMem
0x1800500da  call    cs:__imp_LocalFree
0x1800500e0  mov     rcx, [rbp+47h+var_60.pbData]; hMem
0x1800500e4  call    cs:__imp_LocalFree
0x1800500ea  test    rsi, rsi
0x1800500ed  jz      short loc_1800500FA
0x1800500ef  xor     edx, edx; dwFlags
0x1800500f1  mov     rcx, rsi; hCertStore
0x1800500f4  call    cs:__imp_CertCloseStore
0x1800500fa  mov     rcx, [rbp+47h+pCertContext]; pCertContext
0x1800500fe  test    rcx, rcx
0x180050101  jz      short loc_180050109
0x180050103  call    cs:__imp_CertFreeCertificateContext
0x180050109  mov     rcx, cs:WPP_GLOBAL_Control
0x180050110  lea     rax, WPP_GLOBAL_Control
0x180050117  cmp     rcx, rax
0x18005011a  jz      short loc_180050134
0x18005011c  mov     rcx, [rcx+10h]
0x180050120  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180050127  mov     edx, 37Ah
0x18005012c  mov     r9d, ebx
0x18005012f  call    WPP_SF_d
0x180050134  mov     eax, ebx
0x180050136  add     rsp, 88h
0x18005013d  pop     r15
0x18005013f  pop     r14
0x180050141  pop     r13
0x180050143  pop     r12
0x180050145  pop     rdi
0x180050146  pop     rsi
0x180050147  pop     rbx
0x180050148  pop     rbp
0x180050149  retn
```
