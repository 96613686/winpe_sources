# UpdateAllSelectedItems

- ea: `0x1800222fc`
- end: `0x18002247b`
- name: `UpdateAllSelectedItems`
- size: `383`
- prototype: `__int64 __fastcall(HWND hWnd, HCERTSTORE hCertStore)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001fda0`

## callees

- `0x1800222fc`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002241e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002241e`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180022438`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180022438`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800223c3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022414`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800223c3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022414`
- `CRYPT32!CertFindCertificateInStore` at `0x1800223f1`
- `CRYPT32!CertFindCertificateInStore` at `0x1800223f1`
- `CRYPT32!CertFreeCertificateContext` at `0x180022441`
- `CRYPT32!CertFreeCertificateContext` at `0x180022441`
- `USER32!SendMessageA` at `0x180022364`
- `USER32!SendMessageA` at `0x180022388`
- `USER32!SendMessageA` at `0x180022364`
- `USER32!SendMessageA` at `0x180022388`

## pseudocode

```c
__int64 __fastcall UpdateAllSelectedItems(HWND hWnd, HCERTSTORE hCertStore)
{
  unsigned int v2; // ebx
  int v5; // r15d
  int v6; // eax
  const CERT_CONTEXT *v7; // rdi
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v9; // r14
  DWORD v11; // [rsp+30h] [rbp-69h] BYREF
  DWORD pcbData[2]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE *v13; // [rsp+40h] [rbp-59h]
  int lParam; // [rsp+50h] [rbp-49h] BYREF
  int lParam_4; // [rsp+54h] [rbp-45h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-21h]
  _BYTE pvData[24]; // [rsp+B0h] [rbp+17h] BYREF

  v2 = 0;
  if ( hWnd )
  {
    memset_0(&lParam_4, 0, 0x54u);
    v5 = -1;
    lParam = 4;
    while ( 1 )
    {
      v6 = SendMessageA(hWnd, 0x100Cu, v5, 2);
      v5 = v6;
      if ( v6 == -1 )
        break;
      lParam_4 = v6;
      if ( !(unsigned int)SendMessageA(hWnd, 0x1005u, 0, (LPARAM)&lParam) )
        return v2;
      v7 = pCertContext;
      if ( !pCertContext )
        return v2;
      *(_QWORD *)pcbData = 20;
      v13 = pvData;
      if ( CertGetCertificateContextProperty(pCertContext, 3u, pvData, pcbData) )
      {
        if ( pcbData[0] == 20 )
        {
          CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, pcbData, 0);
          v9 = CertificateInStore;
          if ( CertificateInStore )
          {
            v11 = 0;
            if ( !CertGetCertificateContextProperty(CertificateInStore, 2u, 0, &v11) && GetLastError() == -2146885628 )
              CertSetCertificateContextProperty(v7, 2u, 0, 0);
            CertFreeCertificateContext(v9);
          }
        }
      }
    }
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x1800222fc  mov     [rsp-8+arg_10], rbx
0x180022301  mov     [rsp-8+arg_18], rsi
0x180022306  push    rbp
0x180022307  push    rdi
0x180022308  push    r12
0x18002230a  push    r14
0x18002230c  push    r15
0x18002230e  lea     rbp, [rsp-37h]
0x180022313  sub     rsp, 0D0h
0x18002231a  mov     rax, cs:__security_cookie
0x180022321  xor     rax, rsp
0x180022324  mov     [rbp+57h+var_28], rax
0x180022328  xor     ebx, ebx
0x18002232a  mov     r12, rdx
0x18002232d  mov     rsi, rcx
0x180022330  test    rcx, rcx
0x180022333  jz      loc_180022451
0x180022339  xor     edx, edx; Val
0x18002233b  lea     r8d, [rbx+54h]; Size
0x18002233f  lea     rcx, [rbp+57h+lParam+4]; void *
0x180022343  call    memset_0
0x180022348  or      r15d, 0FFFFFFFFh
0x18002234c  mov     dword ptr [rbp+57h+lParam], 4
0x180022353  movsxd  r8, r15d; wParam
0x180022356  mov     edx, 100Ch; Msg
0x18002235b  mov     r9d, 2; lParam
0x180022361  mov     rcx, rsi; hWnd
0x180022364  call    cs:__imp_SendMessageA
0x18002236a  mov     r15, rax
0x18002236d  cmp     eax, 0FFFFFFFFh
0x180022370  jz      loc_18002244C
0x180022376  lea     r9, [rbp+57h+lParam]; lParam
0x18002237a  mov     dword ptr [rbp+57h+lParam+4], eax
0x18002237d  xor     r8d, r8d; wParam
0x180022380  mov     edx, 1005h; Msg
0x180022385  mov     rcx, rsi; hWnd
0x180022388  call    cs:__imp_SendMessageA
0x18002238e  test    eax, eax
0x180022390  jz      loc_180022451
0x180022396  mov     rdi, [rbp+57h+pCertContext]
0x18002239a  test    rdi, rdi
0x18002239d  jz      loc_180022451
0x1800223a3  lea     rax, [rbp+57h+pvData]
0x1800223a7  mov     qword ptr [rbp+57h+pcbData], 14h
0x1800223af  lea     r9, [rbp+57h+pcbData]; pcbData
0x1800223b3  mov     [rbp+57h+var_B0], rax
0x1800223b7  lea     r8, [rbp+57h+pvData]; pvData
0x1800223bb  mov     edx, 3; dwPropId
0x1800223c0  mov     rcx, rdi; pCertContext
0x1800223c3  call    cs:__imp_CertGetCertificateContextProperty
0x1800223c9  test    eax, eax
0x1800223cb  jz      short loc_180022353
0x1800223cd  cmp     [rbp+57h+pcbData], 14h
0x1800223d1  jnz     short loc_180022353
0x1800223d3  mov     r9d, 10000h; dwFindType
0x1800223d9  mov     [rsp+0F0h+pPrevCertContext], rbx; pPrevCertContext
0x1800223de  lea     rax, [rbp+57h+pcbData]
0x1800223e2  xor     r8d, r8d; dwFindFlags
0x1800223e5  mov     rcx, r12; hCertStore
0x1800223e8  mov     [rsp+0F0h+pvFindPara], rax; pvFindPara
0x1800223ed  lea     edx, [r9+1]; dwCertEncodingType
0x1800223f1  call    cs:__imp_CertFindCertificateInStore
0x1800223f7  mov     r14, rax
0x1800223fa  test    rax, rax
0x1800223fd  jz      loc_180022353
0x180022403  xor     r8d, r8d; pvData
0x180022406  mov     [rbp+57h+var_C0], ebx
0x180022409  lea     r9, [rbp+57h+var_C0]; pcbData
0x18002240d  mov     rcx, rax; pCertContext
0x180022410  lea     edx, [r8+2]; dwPropId
0x180022414  call    cs:__imp_CertGetCertificateContextProperty
0x18002241a  test    eax, eax
0x18002241c  jnz     short loc_18002243E
0x18002241e  call    cs:__imp_GetLastError
0x180022424  cmp     eax, 80092004h
0x180022429  jnz     short loc_18002243E
0x18002242b  xor     r9d, r9d; pvData
0x18002242e  xor     r8d, r8d; dwFlags
0x180022431  mov     rcx, rdi; pCertContext
0x180022434  lea     edx, [r9+2]; dwPropId
0x180022438  call    cs:__imp_CertSetCertificateContextProperty
0x18002243e  mov     rcx, r14; pCertContext
0x180022441  call    cs:__imp_CertFreeCertificateContext
0x180022447  jmp     loc_180022353
0x18002244c  mov     ebx, 1
0x180022451  mov     eax, ebx
0x180022453  mov     rcx, [rbp+57h+var_28]
0x180022457  xor     rcx, rsp; StackCookie
0x18002245a  call    __security_check_cookie
0x18002245f  lea     r11, [rsp+0F0h+var_20]
0x180022467  mov     rbx, [r11+40h]
0x18002246b  mov     rsi, [r11+48h]
0x18002246f  mov     rsp, r11
0x180022472  pop     r15
0x180022474  pop     r14
0x180022476  pop     r12
0x180022478  pop     rdi
0x180022479  pop     rbp
0x18002247a  retn
```
