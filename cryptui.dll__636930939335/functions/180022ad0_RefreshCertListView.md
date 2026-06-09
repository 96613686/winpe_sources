# RefreshCertListView

- ea: `0x180022ad0`
- end: `0x180022f4b`
- name: `RefreshCertListView`
- size: `1147`
- prototype: `__int64 __fastcall(HWND, struct _CERT_MGR_INFO *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012f80`
- `0x18001fda0`

## callees

- `0x180005840`
- `0x18001f538`
- `0x180021c24`
- `0x180021e08`
- `0x1800226a8`
- `0x180022ad0`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180022c1e`
- `CRYPT32!CertOpenStore` at `0x180022c6f`
- `CRYPT32!CertOpenStore` at `0x180022ca0`
- `CRYPT32!CertOpenStore` at `0x180022cdc`
- `CRYPT32!CertOpenStore` at `0x180022c1e`
- `CRYPT32!CertOpenStore` at `0x180022c6f`
- `CRYPT32!CertOpenStore` at `0x180022ca0`
- `CRYPT32!CertOpenStore` at `0x180022cdc`
- `CRYPT32!CertCloseStore` at `0x180022f0c`
- `CRYPT32!CertCloseStore` at `0x180022f0c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180022de6`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180022de6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180022d08`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180022e23`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180022d08`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180022e23`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022db5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022dd3`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022db5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180022dd3`
- `USER32!SetClassLongPtrA` at `0x180022b22`
- `USER32!SetClassLongPtrA` at `0x180022b22`
- `USER32!LoadCursorA` at `0x180022b36`
- `USER32!LoadCursorA` at `0x180022b36`
- `USER32!SetDlgItemTextW` at `0x180022b92`
- `USER32!SetDlgItemTextW` at `0x180022b92`
- `USER32!SendDlgItemMessageA` at `0x180022ef5`
- `USER32!SendDlgItemMessageA` at `0x180022ef5`
- `USER32!SendMessageA` at `0x180022b7d`
- `USER32!SendMessageA` at `0x180022bc5`
- `USER32!SendMessageA` at `0x180022e77`
- `USER32!SendMessageA` at `0x180022b7d`
- `USER32!SendMessageA` at `0x180022bc5`
- `USER32!SendMessageA` at `0x180022e77`
- `USER32!SetWindowLongPtrA` at `0x180022f2d`
- `USER32!SetWindowLongPtrA` at `0x180022f2d`
- `USER32!GetDlgItem` at `0x180022b51`
- `USER32!GetDlgItem` at `0x180022bb1`
- `USER32!GetDlgItem` at `0x180022e89`
- `USER32!GetDlgItem` at `0x180022ea2`
- `USER32!GetDlgItem` at `0x180022ebb`
- `USER32!GetDlgItem` at `0x180022b51`
- `USER32!GetDlgItem` at `0x180022bb1`
- `USER32!GetDlgItem` at `0x180022e89`
- `USER32!GetDlgItem` at `0x180022ea2`
- `USER32!GetDlgItem` at `0x180022ebb`
- `USER32!EnableWindow` at `0x180022e94`
- `USER32!EnableWindow` at `0x180022ead`
- `USER32!EnableWindow` at `0x180022ec6`
- `USER32!EnableWindow` at `0x180022e94`
- `USER32!EnableWindow` at `0x180022ead`
- `USER32!EnableWindow` at `0x180022ec6`
- `USER32!SetCursor` at `0x180022b3f`
- `USER32!SetCursor` at `0x180022f1c`
- `USER32!SetCursor` at `0x180022b3f`
- `USER32!SetCursor` at `0x180022f1c`
- `WINTRUST!TrustIsCertificateSelfSigned` at `0x180022d65`
- `WINTRUST!TrustIsCertificateSelfSigned` at `0x180022d65`

## pseudocode

```c
void __fastcall RefreshCertListView(HWND a1, struct _CERT_MGR_INFO *a2)
{
  __int64 v4; // rdi
  unsigned int v5; // esi
  LONG_PTR v6; // r12
  HCURSOR CursorA; // rax
  HWND v8; // r14
  int v9; // r13d
  HWND DlgItem; // rax
  const wchar_t *pvPara; // rax
  HCERTSTORE v12; // rax
  void *v13; // rdx
  __int64 v14; // r14
  PCCERT_CONTEXT v15; // rdi
  int IsCertificateSelfSigned; // eax
  bool v17; // zf
  BOOL v18; // ecx
  PCCERT_CONTEXT v19; // r12
  _QWORD *v20; // rax
  HWND v21; // r14
  __int64 i; // rdi
  HWND v23; // rax
  HWND v24; // rax
  HWND v25; // rax
  unsigned int v26; // ecx
  __int64 j; // rbx
  LONG_PTR v28; // [rsp+30h] [rbp-30h]
  HCERTSTORE v29; // [rsp+38h] [rbp-28h]
  HCURSOR hCursor; // [rsp+40h] [rbp-20h]
  HCERTSTORE hCertStore[3]; // [rsp+48h] [rbp-18h]
  unsigned int v32; // [rsp+A0h] [rbp+40h]
  DWORD pcbData; // [rsp+B0h] [rbp+50h] BYREF
  HWND hWnd; // [rsp+B8h] [rbp+58h]

  if ( a1 )
  {
    pcbData = 0;
    *(_OWORD *)hCertStore = 0;
    if ( a2 )
    {
      v4 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        v5 = 0;
        v6 = SetClassLongPtrA(a1, -12, 0);
        v28 = v6;
        CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
        hCursor = SetCursor(CursorA);
        hWnd = GetDlgItem(a1, 1111);
        v8 = hWnd;
        if ( !hWnd )
          goto LABEL_60;
        FreeCerts(a2);
        SendMessageA(v8, 0x1009u, 0, 0);
        SetDlgItemTextW(a1, 1121, L" ");
        if ( (*(_DWORD *)(v4 + 16) & 0x8000) != 0 )
        {
          v9 = *(_DWORD *)(v4 + 16) & 0xF;
        }
        else
        {
          DlgItem = GetDlgItem(a1, 1113);
          v9 = SendMessageA(DlgItem, 0x130Bu, 0, 0);
          if ( v9 == -1 )
            goto LABEL_60;
        }
        switch ( v9 )
        {
          case 0:
            hCertStore[0] = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x11004u, L"my");
            if ( !hCertStore[0] )
              goto LABEL_60;
            goto LABEL_25;
          case 1:
            hCertStore[0] = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x11004u, L"ca");
            if ( !hCertStore[0] )
              goto LABEL_62;
            v12 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x15004u, L"ADDRESSBOOK");
            v13 = v12;
            if ( !v12 )
              v13 = 0;
            LOBYTE(v5) = v12 != 0;
            hCertStore[1] = v13;
            ++v5;
            goto LABEL_26;
          case 2:
            pvPara = L"ca";
            break;
          case 3:
            pvPara = L"root";
            break;
          case 4:
            pvPara = L"TrustedPublisher";
            break;
          case 5:
            pvPara = L"Disallowed";
            break;
          default:
            goto LABEL_62;
        }
        hCertStore[0] = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x11004u, pvPara);
        if ( hCertStore[0] )
        {
LABEL_25:
          v5 = 1;
LABEL_26:
          v32 = v5;
          v14 = 0;
          while ( 1 )
          {
            v29 = hCertStore[v14];
            v15 = CertEnumCertificatesInStore(v29, 0);
            if ( !v15 )
              goto LABEL_52;
            do
            {
              if ( !IsValidUsage(v15, a1, a2) )
                goto LABEL_50;
              if ( v9 )
              {
                if ( v9 == 1 )
                {
                  if ( !(_DWORD)v14 )
                  {
                    IsCertificateSelfSigned = IsCertificateEndEntity(v15);
                    goto LABEL_35;
                  }
                  if ( (_DWORD)v14 != 1 )
                    goto LABEL_50;
                  v18 = 1;
LABEL_41:
                  v17 = !v18;
                  goto LABEL_46;
                }
                if ( v9 == 2 )
                {
                  v18 = IsCertificateEndEntity(v15) == 0;
                  goto LABEL_41;
                }
                if ( v9 == 3 || (unsigned int)(v9 - 4) >= 2 )
                {
                  IsCertificateSelfSigned = TrustIsCertificateSelfSigned(v15, v15->dwCertEncodingType, 0);
LABEL_35:
                  v17 = IsCertificateSelfSigned == 0;
                  goto LABEL_46;
                }
              }
              else
              {
                pcbData = 0;
                if ( !CertGetCertificateContextProperty(v15, 2u, 0, &pcbData) || !pcbData )
                {
                  if ( !CertGetCertificateContextProperty(v15, 0xCu, 0, &pcbData) )
                    goto LABEL_50;
                  v17 = pcbData == 0;
LABEL_46:
                  if ( v17 )
                    goto LABEL_50;
                }
              }
              v19 = CertDuplicateCertificateContext(v15);
              v20 = AggressiveLocalRealloc(*((HLOCAL *)a2 + 2), (unsigned int)(8 * *((_DWORD *)a2 + 2) + 8));
              *((_QWORD *)a2 + 2) = v20;
              if ( v20 )
                v20[(*((_DWORD *)a2 + 2))++] = v19;
              else
                *((_DWORD *)a2 + 2) = 0;
LABEL_50:
              v15 = CertEnumCertificatesInStore(v29, v15);
            }
            while ( v15 );
            v5 = v32;
LABEL_52:
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= v5 )
            {
              v21 = hWnd;
              for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 2); i = (unsigned int)(i + 1) )
                AddCertToListView(v21, *(PCCERT_CONTEXT *)(*((_QWORD *)a2 + 2) + 8 * i), i);
              if ( !(unsigned int)SendMessageA(v21, 0x1032u, 0, 0) )
              {
                v23 = GetDlgItem(a1, 1116);
                EnableWindow(v23, 0);
                v24 = GetDlgItem(a1, 1115);
                EnableWindow(v24, 0);
                v25 = GetDlgItem(a1, 1117);
                EnableWindow(v25, 0);
              }
              v26 = *((_DWORD *)a2 + *((int *)a2 + 18) + 13);
              if ( v26 )
                SendDlgItemMessageA(a1, 1111, 0x1030u, v26, (LPARAM)CompareCertificate);
              v6 = v28;
LABEL_60:
              for ( j = 0; (unsigned int)j < v5; j = (unsigned int)(j + 1) )
                CertCloseStore(hCertStore[j], 0);
              break;
            }
          }
        }
LABEL_62:
        SetCursor(hCursor);
        SetWindowLongPtrA(a1, -12, v6);
      }
    }
  }
}

```

## disassembly

```asm
0x180022ad0  test    rcx, rcx
0x180022ad3  jz      locret_180022F4A
0x180022ad9  mov     [rsp-38h+arg_8], rbx
0x180022ade  push    rbp
0x180022adf  push    rsi
0x180022ae0  push    rdi
0x180022ae1  push    r12
0x180022ae3  push    r13
0x180022ae5  push    r14
0x180022ae7  push    r15
0x180022ae9  mov     rbp, rsp
0x180022aec  sub     rsp, 60h
0x180022af0  mov     [rbp+pcbData], 0
0x180022af7  xorps   xmm0, xmm0
0x180022afa  mov     rbx, rdx
0x180022afd  mov     r15, rcx
0x180022b00  movdqu  xmmword ptr [rbp+hCertStore], xmm0
0x180022b05  test    rdx, rdx
0x180022b08  jz      loc_180022F33
0x180022b0e  mov     rdi, [rdx]
0x180022b11  test    rdi, rdi
0x180022b14  jz      loc_180022F33
0x180022b1a  xor     esi, esi
0x180022b1c  xor     r8d, r8d; dwNewLong
0x180022b1f  lea     edx, [rsi-0Ch]; nIndex
0x180022b22  call    cs:__imp_SetClassLongPtrA
0x180022b28  mov     edx, 7F02h; lpCursorName
0x180022b2d  xor     ecx, ecx; hInstance
0x180022b2f  mov     r12, rax
0x180022b32  mov     [rbp+var_30], rax
0x180022b36  call    cs:__imp_LoadCursorA
0x180022b3c  mov     rcx, rax; hCursor
0x180022b3f  call    cs:__imp_SetCursor
0x180022b45  mov     edx, 457h; nIDDlgItem
0x180022b4a  mov     rcx, r15; hDlg
0x180022b4d  mov     [rbp+hCursor], rax
0x180022b51  call    cs:__imp_GetDlgItem
0x180022b57  mov     [rbp+hWnd], rax
0x180022b5b  mov     r14, rax
0x180022b5e  test    rax, rax
0x180022b61  jz      loc_180022EFF
0x180022b67  mov     rcx, rbx
0x180022b6a  call    FreeCerts
0x180022b6f  xor     r9d, r9d; lParam
0x180022b72  xor     r8d, r8d; wParam
0x180022b75  mov     edx, 1009h; Msg
0x180022b7a  mov     rcx, r14; hWnd
0x180022b7d  call    cs:__imp_SendMessageA
0x180022b83  lea     r8, String; " "
0x180022b8a  mov     edx, 461h; nIDDlgItem
0x180022b8f  mov     rcx, r15; hDlg
0x180022b92  call    cs:__imp_SetDlgItemTextW
0x180022b98  mov     r13d, [rdi+10h]
0x180022b9c  bt      r13d, 0Fh
0x180022ba1  jnb     short loc_180022BA9
0x180022ba3  and     r13d, 0Fh
0x180022ba7  jmp     short loc_180022BD7
0x180022ba9  mov     edx, 459h; nIDDlgItem
0x180022bae  mov     rcx, r15; hDlg
0x180022bb1  call    cs:__imp_GetDlgItem
0x180022bb7  xor     r9d, r9d; lParam
0x180022bba  xor     r8d, r8d; wParam
0x180022bbd  mov     rcx, rax; hWnd
0x180022bc0  mov     edx, 130Bh; Msg
0x180022bc5  call    cs:__imp_SendMessageA
0x180022bcb  mov     r13, rax
0x180022bce  cmp     eax, 0FFFFFFFFh
0x180022bd1  jz      loc_180022EFF
0x180022bd7  mov     ecx, r13d
0x180022bda  test    r13d, r13d
0x180022bdd  jz      loc_180022CBE
0x180022be3  sub     ecx, 1
0x180022be6  jz      short loc_180022C51
0x180022be8  sub     ecx, 1
0x180022beb  jz      short loc_180022C48
0x180022bed  sub     ecx, 1
0x180022bf0  jz      short loc_180022C3F
0x180022bf2  sub     ecx, 1
0x180022bf5  jz      short loc_180022C36
0x180022bf7  cmp     ecx, 1
0x180022bfa  jnz     loc_180022F18
0x180022c00  lea     rax, aDisallowed; "Disallowed"
0x180022c07  xor     r8d, r8d; hCryptProv
0x180022c0a  mov     [rsp+60h+pvPara], rax; pvPara
0x180022c0f  mov     r9d, 11004h; dwFlags
0x180022c15  mov     edx, 10001h; dwEncodingType
0x180022c1a  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180022c1e  call    cs:__imp_CertOpenStore
0x180022c24  mov     [rbp+hCertStore], rax
0x180022c28  test    rax, rax
0x180022c2b  jz      loc_180022F18
0x180022c31  jmp     loc_180022CEF
0x180022c36  lea     rax, aTrustedpublish; "TrustedPublisher"
0x180022c3d  jmp     short loc_180022C07
0x180022c3f  lea     rax, aRoot_0; "root"
0x180022c46  jmp     short loc_180022C07
0x180022c48  lea     rax, aCa_1; "ca"
0x180022c4f  jmp     short loc_180022C07
0x180022c51  xor     r8d, r8d; hCryptProv
0x180022c54  lea     rax, aCa_1; "ca"
0x180022c5b  mov     r9d, 11004h; dwFlags
0x180022c61  mov     [rsp+60h+pvPara], rax; pvPara
0x180022c66  mov     edx, 10001h; dwEncodingType
0x180022c6b  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180022c6f  call    cs:__imp_CertOpenStore
0x180022c75  mov     [rbp+hCertStore], rax
0x180022c79  test    rax, rax
0x180022c7c  jz      loc_180022F18
0x180022c82  xor     r8d, r8d; hCryptProv
0x180022c85  lea     rax, aAddressbook; "ADDRESSBOOK"
0x180022c8c  mov     r9d, 15004h; dwFlags
0x180022c92  mov     [rsp+60h+pvPara], rax; pvPara
0x180022c97  mov     edx, 10001h; dwEncodingType
0x180022c9c  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180022ca0  call    cs:__imp_CertOpenStore
0x180022ca6  xor     ecx, ecx
0x180022ca8  mov     rdx, rax
0x180022cab  test    rax, rax
0x180022cae  cmovz   rdx, rcx
0x180022cb2  setnz   sil
0x180022cb6  mov     [rbp+hCertStore+8], rdx
0x180022cba  inc     esi
0x180022cbc  jmp     short loc_180022CF4
0x180022cbe  xor     r8d, r8d; hCryptProv
0x180022cc1  lea     rax, aMy_1; "my"
0x180022cc8  mov     r9d, 11004h; dwFlags
0x180022cce  mov     [rsp+60h+pvPara], rax; pvPara
0x180022cd3  mov     edx, 10001h; dwEncodingType
0x180022cd8  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180022cdc  call    cs:__imp_CertOpenStore
0x180022ce2  mov     [rbp+hCertStore], rax
0x180022ce6  test    rax, rax
0x180022ce9  jz      loc_180022EFF
0x180022cef  mov     esi, 1
0x180022cf4  mov     [rbp+arg_0], esi
0x180022cf7  xor     r14d, r14d
0x180022cfa  mov     rax, [rbp+r14*8+hCertStore]
0x180022cff  xor     edx, edx; pPrevCertContext
0x180022d01  mov     rcx, rax; hCertStore
0x180022d04  mov     [rbp+var_28], rax
0x180022d08  call    cs:__imp_CertEnumCertificatesInStore
0x180022d0e  mov     rdi, rax
0x180022d11  test    rax, rax
0x180022d14  jz      loc_180022E38
0x180022d1a  mov     rsi, [rbp+var_28]
0x180022d1e  mov     r8, rbx; struct _CERT_MGR_INFO *
0x180022d21  mov     rdx, r15; HWND
0x180022d24  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180022d27  call    ?IsValidUsage@@YAHPEBU_CERT_CONTEXT@@PEAUHWND__@@PEAU_CERT_MGR_INFO@@@Z; IsValidUsage(_CERT_CONTEXT const *,HWND__ *,_CERT_MGR_INFO *)
0x180022d2c  test    eax, eax
0x180022d2e  jz      loc_180022E1D
0x180022d34  mov     ecx, r13d
0x180022d37  test    r13d, r13d
0x180022d3a  jz      short loc_180022DA0
0x180022d3c  sub     ecx, 1
0x180022d3f  jz      short loc_180022D80
0x180022d41  sub     ecx, 1
0x180022d44  jz      short loc_180022D6F
0x180022d46  sub     ecx, 1
0x180022d49  jz      short loc_180022D5D
0x180022d4b  sub     ecx, 1
0x180022d4e  jz      loc_180022DE3
0x180022d54  cmp     ecx, 1
0x180022d57  jz      loc_180022DE3
0x180022d5d  mov     edx, [rdi]
0x180022d5f  xor     r8d, r8d
0x180022d62  mov     rcx, rdi
0x180022d65  call    cs:__imp_TrustIsCertificateSelfSigned
0x180022d6b  test    eax, eax
0x180022d6d  jmp     short loc_180022DE1
0x180022d6f  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180022d72  call    ?IsCertificateEndEntity@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertificateEndEntity(_CERT_CONTEXT const *)
0x180022d77  xor     ecx, ecx
0x180022d79  test    eax, eax
0x180022d7b  setz    cl
0x180022d7e  jmp     short loc_180022D9C
0x180022d80  test    r14d, r14d
0x180022d83  jnz     short loc_180022D8F
0x180022d85  mov     rcx, rdi; struct _CERT_CONTEXT *
0x180022d88  call    ?IsCertificateEndEntity@@YAHPEBU_CERT_CONTEXT@@@Z; IsCertificateEndEntity(_CERT_CONTEXT const *)
0x180022d8d  jmp     short loc_180022D6B
0x180022d8f  cmp     r14d, 1
0x180022d93  jnz     loc_180022E1D
0x180022d99  mov     ecx, r14d
0x180022d9c  test    ecx, ecx
0x180022d9e  jmp     short loc_180022DE1
0x180022da0  xor     r8d, r8d; pvData
0x180022da3  mov     [rbp+pcbData], 0
0x180022daa  lea     r9, [rbp+pcbData]; pcbData
0x180022dae  mov     rcx, rdi; pCertContext
0x180022db1  lea     edx, [r8+2]; dwPropId
0x180022db5  call    cs:__imp_CertGetCertificateContextProperty
0x180022dbb  test    eax, eax
0x180022dbd  jz      short loc_180022DC5
0x180022dbf  cmp     [rbp+pcbData], 0
0x180022dc3  jnz     short loc_180022DE3
0x180022dc5  xor     r8d, r8d; pvData
0x180022dc8  lea     r9, [rbp+pcbData]; pcbData
0x180022dcc  mov     rcx, rdi; pCertContext
0x180022dcf  lea     edx, [r8+0Ch]; dwPropId
0x180022dd3  call    cs:__imp_CertGetCertificateContextProperty
0x180022dd9  test    eax, eax
0x180022ddb  jz      short loc_180022E1D
0x180022ddd  cmp     [rbp+pcbData], 0
0x180022de1  jz      short loc_180022E1D
0x180022de3  mov     rcx, rdi; pCertContext
0x180022de6  call    cs:__imp_CertDuplicateCertificateContext
0x180022dec  mov     edx, [rbx+8]
0x180022def  mov     r12, rax
0x180022df2  mov     rcx, [rbx+10h]; hMem
0x180022df6  lea     edx, ds:8[rdx*8]; uBytes
0x180022dfd  call    ?AggressiveLocalRealloc@@YAPEAXPEAXK@Z; AggressiveLocalRealloc(void *,ulong)
0x180022e02  mov     [rbx+10h], rax
0x180022e06  mov     rcx, rax
0x180022e09  test    rax, rax
0x180022e0c  jnz     short loc_180022E13
0x180022e0e  mov     [rbx+8], eax
0x180022e11  jmp     short loc_180022E1D
0x180022e13  mov     eax, [rbx+8]
0x180022e16  mov     [rcx+rax*8], r12
0x180022e1a  inc     dword ptr [rbx+8]
0x180022e1d  mov     rdx, rdi; pPrevCertContext
0x180022e20  mov     rcx, rsi; hCertStore
0x180022e23  call    cs:__imp_CertEnumCertificatesInStore
0x180022e29  mov     rdi, rax
0x180022e2c  test    rax, rax
0x180022e2f  jnz     loc_180022D1E
0x180022e35  mov     esi, [rbp+arg_0]
0x180022e38  inc     r14d
0x180022e3b  cmp     r14d, esi
0x180022e3e  jb      loc_180022CFA
0x180022e44  mov     r14, [rbp+hWnd]
0x180022e48  xor     edi, edi
0x180022e4a  cmp     [rbx+8], edi
0x180022e4d  jbe     short loc_180022E69
0x180022e4f  mov     rdx, [rbx+10h]
0x180022e53  mov     r8d, edi; int
0x180022e56  mov     rcx, r14; hWnd
0x180022e59  mov     rdx, [rdx+rdi*8]; pCertContext
0x180022e5d  call    ?AddCertToListView@@YAHPEAUHWND__@@PEBU_CERT_CONTEXT@@H@Z; AddCertToListView(HWND__ *,_CERT_CONTEXT const *,int)
0x180022e62  inc     edi
0x180022e64  cmp     edi, [rbx+8]
0x180022e67  jb      short loc_180022E4F
0x180022e69  xor     r9d, r9d; lParam
0x180022e6c  xor     r8d, r8d; wParam
0x180022e6f  mov     edx, 1032h; Msg
0x180022e74  mov     rcx, r14; hWnd
0x180022e77  call    cs:__imp_SendMessageA
0x180022e7d  test    eax, eax
0x180022e7f  jnz     short loc_180022ECC
0x180022e81  mov     edx, 45Ch; nIDDlgItem
0x180022e86  mov     rcx, r15; hDlg
0x180022e89  call    cs:__imp_GetDlgItem
0x180022e8f  mov     rcx, rax; hWnd
0x180022e92  xor     edx, edx; bEnable
0x180022e94  call    cs:__imp_EnableWindow
0x180022e9a  mov     edx, 45Bh; nIDDlgItem
0x180022e9f  mov     rcx, r15; hDlg
0x180022ea2  call    cs:__imp_GetDlgItem
0x180022ea8  mov     rcx, rax; hWnd
0x180022eab  xor     edx, edx; bEnable
0x180022ead  call    cs:__imp_EnableWindow
0x180022eb3  mov     edx, 45Dh; nIDDlgItem
0x180022eb8  mov     rcx, r15; hDlg
0x180022ebb  call    cs:__imp_GetDlgItem
0x180022ec1  mov     rcx, rax; hWnd
0x180022ec4  xor     edx, edx; bEnable
0x180022ec6  call    cs:__imp_EnableWindow
0x180022ecc  movsxd  rax, dword ptr [rbx+48h]
0x180022ed0  mov     ecx, [rbx+rax*4+34h]
0x180022ed4  test    ecx, ecx
0x180022ed6  jz      short loc_180022EFB
0x180022ed8  mov     r9d, ecx; wParam
0x180022edb  lea     rax, ?CompareCertificate@@YAH_J00@Z; CompareCertificate(__int64,__int64,__int64)
0x180022ee2  mov     rcx, r15; hDlg
0x180022ee5  mov     [rsp+60h+pvPara], rax; lParam
0x180022eea  mov     edx, 457h; nIDDlgItem
0x180022eef  mov     r8d, 1030h; Msg
0x180022ef5  call    cs:__imp_SendDlgItemMessageA
0x180022efb  mov     r12, [rbp+var_30]
0x180022eff  xor     ebx, ebx
0x180022f01  test    esi, esi
0x180022f03  jz      short loc_180022F18
0x180022f05  mov     rcx, [rbp+rbx*8+hCertStore]; hCertStore
0x180022f0a  xor     edx, edx; dwFlags
0x180022f0c  call    cs:__imp_CertCloseStore
0x180022f12  inc     ebx
0x180022f14  cmp     ebx, esi
0x180022f16  jb      short loc_180022F05
0x180022f18  mov     rcx, [rbp+hCursor]; hCursor
0x180022f1c  call    cs:__imp_SetCursor
0x180022f22  mov     r8, r12; dwNewLong
0x180022f25  mov     edx, 0FFFFFFF4h; nIndex
0x180022f2a  mov     rcx, r15; hWnd
0x180022f2d  call    cs:__imp_SetWindowLongPtrA
0x180022f33  mov     rbx, [rsp+60h+arg_8]
0x180022f3b  add     rsp, 60h
0x180022f3f  pop     r15
0x180022f41  pop     r14
0x180022f43  pop     r13
  ... truncated ...
```
