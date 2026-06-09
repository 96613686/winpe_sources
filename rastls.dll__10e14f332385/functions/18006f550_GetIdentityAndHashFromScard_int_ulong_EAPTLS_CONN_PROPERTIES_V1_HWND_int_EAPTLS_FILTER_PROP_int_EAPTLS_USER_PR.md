# GetIdentityAndHashFromScard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,int,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x18006f550`
- end: `0x18006f7a0`
- name: `?GetIdentityAndHashFromScard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@HPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU5@@Z`
- size: `592`
- prototype: `unsigned int(int, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 *, HWND, int, struct _EAPTLS_FILTER_PROP *, int, struct _EAPTLS_USER_PROPERTIES **, const struct _CERT_CONTEXT **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800136f0`
- `0x18006f7a8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18006ec4c`
- `0x18006f550`
- `0x180072510`
- `0x180072e48`
- `0x180073538`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x18006f73c`
- `CRYPT32!CertCloseStore` at `0x18006f73c`
- `CRYPT32!CertOpenStore` at `0x18006f716`
- `CRYPT32!CertOpenStore` at `0x18006f716`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18006f731`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18006f731`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18006f5e2`
- `ext-ms-win-security-winscard-l1-1-0!SCardEstablishContext` at `0x18006f5e2`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18006f601`
- `ext-ms-win-security-winscard-l1-1-0!SCardListReadersW` at `0x18006f601`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18006f625`
- `ext-ms-win-security-winscard-l1-1-0!SCardReleaseContext` at `0x18006f625`

## pseudocode

```c
__int64 __fastcall GetIdentityAndHashFromScard(
        DWORD a1,
        unsigned int a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3,
        HWND a4,
        int a5,
        struct _CERT_CONTEXT *a6,
        int a7,
        struct _EAPTLS_USER_PROPERTIES **a8,
        struct _CERT_CONTEXT **a9,
        unsigned int *phContext)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v11; // rax
  int v13; // r15d
  BOOL v14; // edi
  unsigned int DefaultCertFromCard; // ebx
  const struct _CERT_CONTEXT **v16; // rsi
  struct _EAPTLS_HASH *v17; // rdx
  unsigned __int16 *v18; // r8
  bool v19; // zf
  struct _CERT_CONTEXT *v20; // r13
  int v21; // edi
  unsigned int ValidCertFromSCard; // eax
  const CERT_CONTEXT *v23; // rbx
  HCERTSTORE v24; // rax
  void *v25; // rdi
  DWORD pcchReaders; // [rsp+90h] [rbp+8h] BYREF
  struct _EAPTLS_CONN_PROPERTIES_V1 *v28; // [rsp+A0h] [rbp+18h]

  v28 = a3;
  pcchReaders = a1;
  v11 = a3;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c4e812f99669349517681909258710e2_Traceguids);
    v11 = v28;
  }
  v13 = a7;
  if ( g_UseDefaultSCardCert )
  {
    pcchReaders = 0;
    phContext = 0;
    v14 = 0;
    if ( !SCardEstablishContext(0, 0, 0, (LPSCARDCONTEXT)&phContext)
      && !SCardListReadersW((SCARDCONTEXT)phContext, 0, 0, &pcchReaders) )
    {
      v14 = pcchReaders > 4;
    }
    if ( phContext )
      SCardReleaseContext((SCARDCONTEXT)phContext);
    if ( !v14 )
    {
      DefaultCertFromCard = 764;
      goto LABEL_27;
    }
    v16 = (const struct _CERT_CONTEXT **)a9;
    DefaultCertFromCard = GetDefaultCertFromCard(a2, a4, (const struct _CERT_CONTEXT **)a9);
    v19 = DefaultCertFromCard == 0;
  }
  else
  {
    v16 = (const struct _CERT_CONTEXT **)a9;
    v20 = a6;
    v21 = 1;
    do
    {
      ValidCertFromSCard = GetValidCertFromSCard(0, a2, v11, a4, v13, v20, v16);
      DefaultCertFromCard = ValidCertFromSCard;
      if ( (a2 & 2) != 0 )
        break;
      if ( !ValidCertFromSCard )
        goto LABEL_21;
      if ( ValidCertFromSCard != -2146435026 && ValidCertFromSCard != -2146435060 || !v21 )
        goto LABEL_27;
      v21 = 0;
      DefaultCertFromCard = DetectSmartCard(a2, a4);
      v11 = v28;
    }
    while ( !DefaultCertFromCard );
    v19 = DefaultCertFromCard == 0;
  }
  if ( v19 )
  {
LABEL_21:
    if ( g_UseDefaultSCardCert || v13 )
    {
      v23 = *v16;
      if ( *v16 )
      {
        v24 = CertOpenStore((LPCSTR)9, 0, 0, 0x10000u, "MY");
        v25 = v24;
        if ( v24 )
        {
          CertAddCertificateContextToStore(v24, v23, 5u, 0);
          CertCloseStore(v25, 0);
        }
      }
    }
    DefaultCertFromCard = CreateUserBlobWithHashAndIdentity(a2, v17, v18, a8, *v16);
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_c4e812f99669349517681909258710e2_Traceguids,
      DefaultCertFromCard);
  return DefaultCertFromCard;
}

```

## disassembly

```asm
0x18006f550  mov     [rsp+arg_8], rbx
0x18006f555  mov     [rsp+arg_10], r8
0x18006f55a  mov     [rsp+pcchReaders], ecx
0x18006f55e  push    rbp
0x18006f55f  push    rsi
0x18006f560  push    rdi
0x18006f561  push    r12
0x18006f563  push    r13
0x18006f565  push    r14
0x18006f567  push    r15
0x18006f569  sub     rsp, 50h
0x18006f56d  mov     r12, r9
0x18006f570  mov     rax, r8
0x18006f573  mov     ebp, edx
0x18006f575  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f57c  lea     rdx, WPP_GLOBAL_Control
0x18006f583  cmp     rcx, rdx
0x18006f586  jz      short loc_18006F5A5
0x18006f588  mov     rcx, [rcx+10h]
0x18006f58c  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f593  mov     edx, 11h
0x18006f598  call    WPP_SF_
0x18006f59d  mov     rax, [rsp+88h+arg_10]
0x18006f5a5  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x18006f5ac  mov     r15d, [rsp+88h+arg_30]
0x18006f5b4  jz      loc_18006F657
0x18006f5ba  lea     r9, [rsp+88h+phContext]; phContext
0x18006f5c2  mov     [rsp+88h+pcchReaders], 0
0x18006f5cd  xor     r8d, r8d; pvReserved2
0x18006f5d0  mov     [rsp+88h+phContext], 0
0x18006f5dc  xor     edx, edx; pvReserved1
0x18006f5de  xor     ecx, ecx; dwScope
0x18006f5e0  xor     edi, edi
0x18006f5e2  call    cs:__imp_SCardEstablishContext
0x18006f5e8  test    eax, eax
0x18006f5ea  jnz     short loc_18006F618
0x18006f5ec  mov     rcx, [rsp+88h+phContext]; hContext
0x18006f5f4  lea     r9, [rsp+88h+pcchReaders]; pcchReaders
0x18006f5fc  xor     r8d, r8d; mszReaders
0x18006f5ff  xor     edx, edx; mszGroups
0x18006f601  call    cs:__imp_SCardListReadersW
0x18006f607  test    eax, eax
0x18006f609  jnz     short loc_18006F618
0x18006f60b  cmp     [rsp+88h+pcchReaders], 4
0x18006f613  jbe     short loc_18006F618
0x18006f615  lea     edi, [rax+1]
0x18006f618  mov     rcx, [rsp+88h+phContext]; hContext
0x18006f620  test    rcx, rcx
0x18006f623  jz      short loc_18006F62B
0x18006f625  call    cs:__imp_SCardReleaseContext
0x18006f62b  test    edi, edi
0x18006f62d  jnz     short loc_18006F639
0x18006f62f  mov     ebx, 2FCh
0x18006f634  jmp     loc_18006F75B
0x18006f639  mov     rsi, [rsp+88h+arg_40]
0x18006f641  mov     rdx, r12; HWND
0x18006f644  mov     r8, rsi; struct _CERT_CONTEXT **
0x18006f647  mov     ecx, ebp; unsigned int
0x18006f649  call    ?GetDefaultCertFromCard@@YAKKPEAUHWND__@@PEAPEBU_CERT_CONTEXT@@@Z; GetDefaultCertFromCard(ulong,HWND__ *,_CERT_CONTEXT const * *)
0x18006f64e  mov     ebx, eax
0x18006f650  test    eax, eax
0x18006f652  jmp     loc_18006F6E4
0x18006f657  mov     rsi, [rsp+88h+arg_40]
0x18006f65f  mov     r14d, ebp
0x18006f662  mov     r13, [rsp+88h+arg_28]
0x18006f66a  and     r14d, 2
0x18006f66e  mov     edi, 1
0x18006f673  mov     [rsp+88h+var_48], 0; struct _CERT_CONTEXT ***
0x18006f67c  mov     r9, r12; HWND
0x18006f67f  mov     [rsp+88h+var_50], 0; unsigned int *
0x18006f688  mov     r8, rax; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18006f68b  mov     [rsp+88h+var_58], rsi; struct _CERT_CONTEXT **
0x18006f690  mov     edx, ebp; unsigned int
0x18006f692  mov     [rsp+88h+var_60], r13; struct _EAPTLS_FILTER_PROP *
0x18006f697  xor     ecx, ecx; int
0x18006f699  mov     dword ptr [rsp+88h+pvPara], r15d; int
0x18006f69e  call    ?GetValidCertFromSCard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU4@@Z; GetValidCertFromSCard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)
0x18006f6a3  mov     ebx, eax
0x18006f6a5  test    r14d, r14d
0x18006f6a8  jnz     short loc_18006F6E2
0x18006f6aa  test    eax, eax
0x18006f6ac  jz      short loc_18006F6E6
0x18006f6ae  cmp     eax, 8010002Eh
0x18006f6b3  jz      short loc_18006F6C0
0x18006f6b5  cmp     eax, 8010000Ch
0x18006f6ba  jnz     loc_18006F75B
0x18006f6c0  test    edi, edi
0x18006f6c2  jz      loc_18006F75B
0x18006f6c8  mov     rdx, r12; HWND
0x18006f6cb  mov     ecx, ebp; unsigned int
0x18006f6cd  call    ?DetectSmartCard@@YAKKPEAUHWND__@@@Z; DetectSmartCard(ulong,HWND__ *)
0x18006f6d2  xor     edi, edi
0x18006f6d4  mov     ebx, eax
0x18006f6d6  test    eax, eax
0x18006f6d8  mov     rax, [rsp+88h+arg_10]
0x18006f6e0  jz      short loc_18006F673
0x18006f6e2  test    ebx, ebx
0x18006f6e4  jnz     short loc_18006F75B
0x18006f6e6  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x18006f6ed  jnz     short loc_18006F6F4
0x18006f6ef  test    r15d, r15d
0x18006f6f2  jz      short loc_18006F742
0x18006f6f4  mov     rbx, [rsi]
0x18006f6f7  test    rbx, rbx
0x18006f6fa  jz      short loc_18006F742
0x18006f6fc  xor     edx, edx; dwEncodingType
0x18006f6fe  lea     rax, aMy; "MY"
0x18006f705  mov     r9d, 10000h; dwFlags
0x18006f70b  mov     [rsp+88h+pvPara], rax; pvPara
0x18006f710  xor     r8d, r8d; hCryptProv
0x18006f713  lea     ecx, [rdx+9]; lpszStoreProvider
0x18006f716  call    cs:__imp_CertOpenStore
0x18006f71c  mov     rdi, rax
0x18006f71f  test    rax, rax
0x18006f722  jz      short loc_18006F742
0x18006f724  xor     r9d, r9d; ppStoreContext
0x18006f727  mov     rdx, rbx; pCertContext
0x18006f72a  mov     rcx, rax; hCertStore
0x18006f72d  lea     r8d, [r9+5]; dwAddDisposition
0x18006f731  call    cs:__imp_CertAddCertificateContextToStore
0x18006f737  xor     edx, edx; dwFlags
0x18006f739  mov     rcx, rdi; hCertStore
0x18006f73c  call    cs:__imp_CertCloseStore
0x18006f742  mov     rax, [rsi]
0x18006f745  mov     ecx, ebp; unsigned int
0x18006f747  mov     r9, [rsp+88h+arg_38]; struct _EAPTLS_USER_PROPERTIES **
0x18006f74f  mov     [rsp+88h+pvPara], rax; struct _CERT_CONTEXT *
0x18006f754  call    ?CreateUserBlobWithHashAndIdentity@@YAKKPEAU_EAPTLS_HASH@@PEAGPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBU_CERT_CONTEXT@@@Z; CreateUserBlobWithHashAndIdentity(ulong,_EAPTLS_HASH *,ushort *,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const *)
0x18006f759  mov     ebx, eax
0x18006f75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f762  lea     rax, WPP_GLOBAL_Control
0x18006f769  cmp     rcx, rax
0x18006f76c  jz      short loc_18006F786
0x18006f76e  mov     rcx, [rcx+10h]
0x18006f772  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f779  mov     edx, 12h
0x18006f77e  mov     r9d, ebx
0x18006f781  call    WPP_SF_d
0x18006f786  mov     eax, ebx
0x18006f788  mov     rbx, [rsp+88h+arg_8]
0x18006f790  add     rsp, 50h
0x18006f794  pop     r15
0x18006f796  pop     r14
0x18006f798  pop     r13
0x18006f79a  pop     r12
0x18006f79c  pop     rdi
0x18006f79d  pop     rsi
0x18006f79e  pop     rbp
0x18006f79f  retn
```
