# GetIdentityAndHashFromScard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,int,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)

- ea: `0x180074168`
- end: `0x180074350`
- name: `?GetIdentityAndHashFromScard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@HPEAPEAU_EAPTLS_USER_PROPERTIES@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU5@@Z`
- size: `488`
- prototype: `unsigned int(int, unsigned int, struct _EAPTLS_CONN_PROPERTIES_V1 *, HWND, int, struct _EAPTLS_FILTER_PROP *, int, struct _EAPTLS_USER_PROPERTIES **, const struct _CERT_CONTEXT **, unsigned int *, const struct _CERT_CONTEXT ***)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180014a70`
- `0x180074358`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18006d990`
- `0x1800736e0`
- `0x180074168`
- `0x180077470`
- `0x180077eb8`
- `0x18007865c`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x1800742ec`
- `CRYPT32!CertCloseStore` at `0x1800742ec`
- `CRYPT32!CertOpenStore` at `0x1800742ba`
- `CRYPT32!CertOpenStore` at `0x1800742ba`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800742db`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800742db`

## pseudocode

```c
__int64 __fastcall GetIdentityAndHashFromScard(
        __int64 a1,
        unsigned int a2,
        struct _EAPTLS_CONN_PROPERTIES_V1 *a3,
        HWND a4,
        int a5,
        struct _CERT_CONTEXT *a6,
        int a7,
        struct _EAPTLS_USER_PROPERTIES **a8,
        struct _CERT_CONTEXT **a9)
{
  struct _EAPTLS_CONN_PROPERTIES_V1 *v10; // rax
  unsigned int DefaultCertFromCard; // ebx
  const struct _CERT_CONTEXT **v13; // rdi
  struct _EAPTLS_HASH *v14; // rdx
  unsigned __int16 *v15; // r8
  bool v16; // zf
  int v17; // r12d
  unsigned int ValidCertFromSCard; // eax
  const CERT_CONTEXT *v19; // rbx
  HCERTSTORE v20; // rax
  void *v21; // rsi

  v10 = a3;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c4e812f99669349517681909258710e2_Traceguids);
    v10 = a3;
  }
  if ( g_UseDefaultSCardCert )
  {
    if ( !FSmartCardReaderInstalled() )
    {
      DefaultCertFromCard = 764;
      goto LABEL_22;
    }
    v13 = (const struct _CERT_CONTEXT **)a9;
    DefaultCertFromCard = GetDefaultCertFromCard(a2, a4, (const struct _CERT_CONTEXT **)a9);
    v16 = DefaultCertFromCard == 0;
  }
  else
  {
    v13 = (const struct _CERT_CONTEXT **)a9;
    v17 = 1;
    do
    {
      ValidCertFromSCard = GetValidCertFromSCard(0, a2, v10, a4, a7, a6, (const struct _CERT_CONTEXT **)a9);
      DefaultCertFromCard = ValidCertFromSCard;
      if ( (a2 & 2) != 0 )
        break;
      if ( !ValidCertFromSCard )
        goto LABEL_16;
      if ( ValidCertFromSCard != -2146435026 && ValidCertFromSCard != -2146435060 || !v17 )
        goto LABEL_22;
      v17 = 0;
      DefaultCertFromCard = DetectSmartCard(a2, a4);
      v10 = a3;
    }
    while ( !DefaultCertFromCard );
    v16 = DefaultCertFromCard == 0;
  }
  if ( v16 )
  {
LABEL_16:
    if ( g_UseDefaultSCardCert || a7 )
    {
      v19 = *v13;
      if ( *v13 )
      {
        v20 = CertOpenStore((LPCSTR)9, 0, 0, 0x10000u, "MY");
        v21 = v20;
        if ( v20 )
        {
          CertAddCertificateContextToStore(v20, v19, 5u, 0);
          CertCloseStore(v21, 0);
        }
      }
    }
    DefaultCertFromCard = CreateUserBlobWithHashAndIdentity(a2, v14, v15, a8, *v13);
  }
LABEL_22:
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
0x180074168  mov     [rsp+arg_10], r8
0x18007416d  push    rbx
0x18007416e  push    rbp
0x18007416f  push    rsi
0x180074170  push    rdi
0x180074171  push    r12
0x180074173  push    r13
0x180074175  push    r14
0x180074177  push    r15
0x180074179  sub     rsp, 58h
0x18007417d  mov     r15, r9
0x180074180  mov     rax, r8
0x180074183  mov     ebp, edx
0x180074185  mov     rcx, cs:WPP_GLOBAL_Control
0x18007418c  lea     rdx, WPP_GLOBAL_Control
0x180074193  cmp     rcx, rdx
0x180074196  jz      short loc_1800741B5
0x180074198  mov     rcx, [rcx+10h]
0x18007419c  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800741a3  mov     edx, 11h
0x1800741a8  call    WPP_SF_
0x1800741ad  mov     rax, [rsp+98h+arg_10]
0x1800741b5  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x1800741bc  mov     r14d, [rsp+98h+arg_30]
0x1800741c4  jz      short loc_1800741F7
0x1800741c6  call    ?FSmartCardReaderInstalled@@YAHXZ; FSmartCardReaderInstalled(void)
0x1800741cb  test    eax, eax
0x1800741cd  jnz     short loc_1800741D9
0x1800741cf  mov     ebx, 2FCh
0x1800741d4  jmp     loc_180074311
0x1800741d9  mov     rdi, [rsp+98h+arg_40]
0x1800741e1  mov     rdx, r15; HWND
0x1800741e4  mov     r8, rdi; struct _CERT_CONTEXT **
0x1800741e7  mov     ecx, ebp; unsigned int
0x1800741e9  call    ?GetDefaultCertFromCard@@YAKKPEAUHWND__@@PEAPEBU_CERT_CONTEXT@@@Z; GetDefaultCertFromCard(ulong,HWND__ *,_CERT_CONTEXT const * *)
0x1800741ee  mov     ebx, eax
0x1800741f0  test    eax, eax
0x1800741f2  jmp     loc_180074284
0x1800741f7  mov     rdi, [rsp+98h+arg_40]
0x1800741ff  mov     esi, ebp
0x180074201  mov     r13, [rsp+98h+arg_28]
0x180074209  and     esi, 2
0x18007420c  mov     r12d, 1
0x180074212  mov     [rsp+98h+var_58], 0; struct _CERT_CONTEXT ***
0x18007421b  mov     r9, r15; HWND
0x18007421e  mov     [rsp+98h+var_60], 0; unsigned int *
0x180074227  mov     r8, rax; struct _EAPTLS_CONN_PROPERTIES_V1 *
0x18007422a  mov     [rsp+98h+var_68], rdi; struct _CERT_CONTEXT **
0x18007422f  mov     edx, ebp; unsigned int
0x180074231  mov     [rsp+98h+var_70], r13; struct _EAPTLS_FILTER_PROP *
0x180074236  xor     ecx, ecx; int
0x180074238  mov     dword ptr [rsp+98h+pvPara], r14d; int
0x18007423d  call    ?GetValidCertFromSCard@@YAKHKPEAU_EAPTLS_CONN_PROPERTIES_V1@@PEAUHWND__@@HPEAU_EAPTLS_FILTER_PROP@@PEAPEBU_CERT_CONTEXT@@PEAKPEAPEAPEBU4@@Z; GetValidCertFromSCard(int,ulong,_EAPTLS_CONN_PROPERTIES_V1 *,HWND__ *,int,_EAPTLS_FILTER_PROP *,_CERT_CONTEXT const * *,ulong *,_CERT_CONTEXT const * * *)
0x180074242  mov     ebx, eax
0x180074244  test    esi, esi
0x180074246  jnz     short loc_180074282
0x180074248  test    eax, eax
0x18007424a  jz      short loc_18007428A
0x18007424c  cmp     eax, 8010002Eh
0x180074251  jz      short loc_18007425E
0x180074253  cmp     eax, 8010000Ch
0x180074258  jnz     loc_180074311
0x18007425e  test    r12d, r12d
0x180074261  jz      loc_180074311
0x180074267  mov     rdx, r15; HWND
0x18007426a  mov     ecx, ebp; unsigned int
0x18007426c  call    ?DetectSmartCard@@YAKKPEAUHWND__@@@Z; DetectSmartCard(ulong,HWND__ *)
0x180074271  xor     r12d, r12d
0x180074274  mov     ebx, eax
0x180074276  test    eax, eax
0x180074278  mov     rax, [rsp+98h+arg_10]
0x180074280  jz      short loc_180074212
0x180074282  test    ebx, ebx
0x180074284  jnz     loc_180074311
0x18007428a  cmp     cs:?g_UseDefaultSCardCert@@3HA, 0; int g_UseDefaultSCardCert
0x180074291  jnz     short loc_180074298
0x180074293  test    r14d, r14d
0x180074296  jz      short loc_1800742F8
0x180074298  mov     rbx, [rdi]
0x18007429b  test    rbx, rbx
0x18007429e  jz      short loc_1800742F8
0x1800742a0  xor     edx, edx; dwEncodingType
0x1800742a2  lea     rax, aMy; "MY"
0x1800742a9  mov     r9d, 10000h; dwFlags
0x1800742af  mov     [rsp+98h+pvPara], rax; pvPara
0x1800742b4  xor     r8d, r8d; hCryptProv
0x1800742b7  lea     ecx, [rdx+9]; lpszStoreProvider
0x1800742ba  call    cs:__imp_CertOpenStore
0x1800742c1  nop     dword ptr [rax+rax+00h]
0x1800742c6  mov     rsi, rax
0x1800742c9  test    rax, rax
0x1800742cc  jz      short loc_1800742F8
0x1800742ce  xor     r9d, r9d; ppStoreContext
0x1800742d1  mov     rdx, rbx; pCertContext
0x1800742d4  mov     rcx, rax; hCertStore
0x1800742d7  lea     r8d, [r9+5]; dwAddDisposition
0x1800742db  call    cs:__imp_CertAddCertificateContextToStore
0x1800742e2  nop     dword ptr [rax+rax+00h]
0x1800742e7  xor     edx, edx; dwFlags
0x1800742e9  mov     rcx, rsi; hCertStore
0x1800742ec  call    cs:__imp_CertCloseStore
0x1800742f3  nop     dword ptr [rax+rax+00h]
0x1800742f8  mov     rax, [rdi]
0x1800742fb  mov     ecx, ebp; unsigned int
0x1800742fd  mov     r9, [rsp+98h+arg_38]; struct _EAPTLS_USER_PROPERTIES **
0x180074305  mov     [rsp+98h+pvPara], rax; struct _CERT_CONTEXT *
0x18007430a  call    ?CreateUserBlobWithHashAndIdentity@@YAKKPEAU_EAPTLS_HASH@@PEAGPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBU_CERT_CONTEXT@@@Z; CreateUserBlobWithHashAndIdentity(ulong,_EAPTLS_HASH *,ushort *,_EAPTLS_USER_PROPERTIES * *,_CERT_CONTEXT const *)
0x18007430f  mov     ebx, eax
0x180074311  mov     rcx, cs:WPP_GLOBAL_Control
0x180074318  lea     rax, WPP_GLOBAL_Control
0x18007431f  cmp     rcx, rax
0x180074322  jz      short loc_18007433C
0x180074324  mov     rcx, [rcx+10h]
0x180074328  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007432f  mov     edx, 12h
0x180074334  mov     r9d, ebx
0x180074337  call    WPP_SF_d
0x18007433c  mov     eax, ebx
0x18007433e  add     rsp, 58h
0x180074342  pop     r15
0x180074344  pop     r14
0x180074346  pop     r13
0x180074348  pop     r12
0x18007434a  pop     rdi
0x18007434b  pop     rsi
0x18007434c  pop     rbp
0x18007434d  pop     rbx
0x18007434e  retn
```
