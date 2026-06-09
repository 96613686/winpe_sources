# CCertRequest::GetCACertificate(long,ushort * const,long,ushort * *)

- ea: `0x18000dcc0`
- end: `0x18000e130`
- name: `?GetCACertificate@CCertRequest@@UEAAJJQEAGJPEAPEAG@Z`
- size: `1136`
- prototype: `__int64 __usercall@<rax>(CCertRequest *__hidden this@<rcx>, int@<edx>, unsigned __int16 *const@<r8>, int@<r9d>, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ba10`
- `0x18000dcc0`
- `0x18000f3b8`
- `0x18001053c`
- `0x1800119dc`
- `0x180014cac`
- `0x18001d14c`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000dec4`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000defc`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000dec4`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18000defc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e0e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e0e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0f9`
- `certca!__imp_?myGetErrorMessageText@@YAPEAGJK@Z` at `0x18000dd74`
- `certca!__imp_?myGetErrorMessageText@@YAPEAGJK@Z` at `0x18000dd74`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e0cb`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18000e0cb`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000df3d`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18000df3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCertRequest::GetCACertificate(
        CCertRequest *this,
        unsigned int a2,
        CertEnrollHttp *a3,
        int a4,
        unsigned __int16 **a5)
{
  int v5; // r15d
  unsigned int v7; // esi
  CCertRequest *v8; // rbx
  BYTE *pb; // r8
  unsigned __int16 *ErrorMessageText; // r12
  int v11; // edi
  int v12; // edx
  unsigned int v13; // ecx
  BOOL v14; // r13d
  _QWORD *v15; // rax
  int CAExchangeCertificate; // eax
  void (*v17)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r9
  BYTE **v22; // rdx
  unsigned int *v23; // rcx
  unsigned int v24; // r15d
  unsigned int cb; // edx
  BYTE *v26; // rcx
  unsigned __int16 **v28; // [rsp+20h] [rbp-148h]
  unsigned int v29; // [rsp+30h] [rbp-138h]
  int v30; // [rsp+38h] [rbp-130h]
  int v31; // [rsp+40h] [rbp-128h]
  unsigned int v32; // [rsp+48h] [rbp-120h]
  struct _CERTTRANSBLOB v33; // [rsp+50h] [rbp-118h] BYREF
  void (*v34)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+60h] [rbp-108h]
  unsigned __int16 *v35; // [rsp+68h] [rbp-100h] BYREF
  CCertRequest *v36; // [rsp+70h] [rbp-F8h]
  unsigned __int16 *v37; // [rsp+78h] [rbp-F0h]
  unsigned __int16 **v38; // [rsp+80h] [rbp-E8h]
  CCertRequest *v39; // [rsp+88h] [rbp-E0h]
  const struct _EXCEPTION_POINTERS *v40; // [rsp+90h] [rbp-D8h] BYREF
  unsigned __int16 v41[64]; // [rsp+A0h] [rbp-C8h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  v36 = this;
  v39 = this;
  v29 = a2;
  v31 = a4;
  v38 = a5;
  *(_QWORD *)&v33.cb = 0;
  pb = 0;
  v33.pb = 0;
  v35 = 0;
  ErrorMessageText = 0;
  v37 = 0;
  if ( !a5 )
  {
    v11 = -2147467261;
    v12 = -2147467261;
    v13 = 184091332;
LABEL_62:
    CSPrintErrorLineFile(v13, v12);
    goto LABEL_63;
  }
  if ( a2 == 1701999153 || a2 == 1701999154 )
  {
    ErrorMessageText = myGetErrorMessageText(a4, a2 == 1701999154);
    v37 = ErrorMessageText;
    if ( !ErrorMessageText )
    {
      v11 = -2147024882;
      v12 = -2147024882;
      v13 = 185205444;
      goto LABEL_62;
    }
    v5 = 2;
    v31 = 2;
    v14 = 0;
    v30 = 0;
    pb = v33.pb;
  }
  else
  {
    v14 = 1;
    v30 = 1;
  }
  if ( (v7 & 0x7F7F0000) == 0x736C0000 || (v7 & 0x7F7F0000) == 0x73740000 )
  {
    LODWORD(v34) = v5 & 0x100;
    if ( (v5 & 0x100) != 0 )
    {
      v12 = -2147024809;
      v11 = -2147024809;
      v13 = 186188484;
      goto LABEL_62;
    }
    v32 = (unsigned __int16)v7;
    v7 &= 0xFFFF0000;
    v29 = v7;
    v15 = (_QWORD *)((char *)v8 + 232);
    if ( v7 != 1936982016 )
      v15 = (_QWORD *)((char *)v8 + 264);
    v14 = *v15 == 0;
    v30 = v14;
  }
  else
  {
    v32 = -1;
    LODWORD(v34) = v5 & 0x100;
  }
  if ( v14 )
  {
    if ( IsWebServer((const unsigned __int16 *)a3) )
    {
      CAExchangeCertificate = CertEnrollHttp::CEnrollmentWebProxy::GetCAExchangeCertificate(
                                a3,
                                *((struct IClientCred **)v8 + 47),
                                v5,
                                &v33);
      v11 = CAExchangeCertificate;
      if ( CAExchangeCertificate )
      {
        v13 = 187433668;
LABEL_61:
        v12 = CAExchangeCertificate;
        goto LABEL_62;
      }
    }
    else
    {
      CAExchangeCertificate = CCertRequest::_OpenConnection(v8, 0, (const unsigned __int16 *)a3, 1u, &v35);
      v11 = CAExchangeCertificate;
      if ( CAExchangeCertificate )
      {
        v13 = 187761348;
        goto LABEL_61;
      }
      if ( (_DWORD)v34 )
      {
        v7 |= 0x80000000;
        v29 = v7;
        if ( (v5 & 0x200) != 0 )
        {
          v7 |= 0x800000u;
          v29 = v7;
        }
      }
      try
      {
        v17 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
        v34 = v17;
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, struct _CERTTRANSBLOB *))(**((_QWORD **)v36 + 10) + 32LL))(
                *((_QWORD *)v36 + 10),
                v7,
                v35,
                &v33);
        _set_se_translator(v17);
      }
      catch ( const StructuredException *v40 )
      {
        v11 = myHExceptionCodePrint(v40 + 77, 0, 0x2C4u, 0xB48u);
        ErrorMessageText = v37;
        v14 = v30;
        v8 = v39;
        v7 = v29;
        v5 = v31;
        goto LABEL_27;
      }
      v8 = v36;
LABEL_27:
      if ( v11 )
      {
        CSPrintErrorLineFile2(0xB4E02C4u, v11, -2147024894);
        goto LABEL_63;
      }
    }
    pb = v33.pb;
    v18 = (unsigned __int16 *)v33.pb;
  }
  else
  {
    v18 = ErrorMessageText;
  }
  switch ( v7 )
  {
    case 0x6363726Cu:
LABEL_37:
      if ( (v5 & 0xFFFFFEFF) == 0 )
        v5 = 9;
LABEL_39:
      LODWORD(v19) = 0;
      if ( !ErrorMessageText )
        goto LABEL_57;
      goto LABEL_40;
    case 0x696E666Fu:
      if ( *(_DWORD *)v18 < 0xCu )
      {
        v11 = -2147024883;
        v12 = -2147024883;
        v13 = 191562436;
        goto LABEL_62;
      }
      LODWORD(v28) = *((_DWORD *)v18 + 2);
      StringCchPrintfW(v41, 0x3Cu, L"%u,%u", *((unsigned int *)v18 + 1), v28);
      goto LABEL_46;
    case 0x736C0000u:
      v22 = (BYTE **)((char *)v8 + 264);
      v23 = (unsigned int *)((char *)v8 + 272);
      break;
    case 0x73740000u:
      v22 = (BYTE **)((char *)v8 + 232);
      v23 = (unsigned int *)((char *)v8 + 240);
      break;
    case 0x74797065u:
      v21 = *(unsigned int *)v18;
      goto LABEL_45;
    default:
      if ( (v7 & 0x7F7F0000) != 0x636C0000 )
        goto LABEL_39;
      goto LABEL_37;
  }
  if ( v14 )
  {
    *v23 = v33.cb;
    *v22 = pb;
    v33.pb = 0;
  }
  if ( v32 >= *v23 )
  {
    v12 = -2147024809;
    v11 = -2147024809;
    v13 = 194118340;
    goto LABEL_62;
  }
  v21 = (*v22)[v32];
LABEL_45:
  StringCchPrintfW(v41, 0x3Cu, L"%u", v21);
LABEL_46:
  ErrorMessageText = v41;
  v18 = v41;
LABEL_40:
  v20 = -1;
  do
    ++v20;
  while ( ErrorMessageText[v20] );
  v19 = 2 * v20;
  if ( v19 > 0x61A8000 )
  {
    v11 = -2147024362;
    v12 = -2147024362;
    v13 = 196215492;
    goto LABEL_62;
  }
LABEL_57:
  v24 = v5 & 0xFFFFFEFF;
  cb = v33.cb;
  if ( v18 == ErrorMessageText )
    cb = v19;
  CAExchangeCertificate = EncodeCertString((const unsigned __int8 *)v18, cb, v24, v38);
  v11 = CAExchangeCertificate;
  if ( CAExchangeCertificate )
  {
    v13 = 196805316;
    goto LABEL_61;
  }
LABEL_63:
  *((_DWORD *)v8 + 27) = v11;
  if ( ErrorMessageText && v41 != ErrorMessageText )
    LocalFree(ErrorMessageText);
  v26 = v33.pb;
  if ( v33.pb )
    CoTaskMemFree(v33.pb);
  return CCertRequest::_SetErrorInfo((CCertRequest *)v26, v11, L"CCertRequest::GetCACertificate");
}

```

## disassembly

```asm
0x18000dcc0  push    rbx
0x18000dcc2  push    rsi
0x18000dcc3  push    rdi
0x18000dcc4  push    r12
0x18000dcc6  push    r13
0x18000dcc8  push    r14
0x18000dcca  push    r15
0x18000dccc  sub     rsp, 130h
0x18000dcd3  mov     rax, cs:__security_cookie
0x18000dcda  xor     rax, rsp
0x18000dcdd  mov     [rsp+168h+var_48], rax
0x18000dce5  mov     r15d, r9d
0x18000dce8  mov     rdi, r8
0x18000dceb  mov     esi, edx
0x18000dced  mov     rbx, rcx
0x18000dcf0  mov     [rsp+168h+var_F8], rcx
0x18000dcf5  mov     [rsp+168h+var_E0], rcx
0x18000dcfd  mov     [rsp+168h+var_138], edx
0x18000dd01  mov     [rsp+168h+var_128], r9d
0x18000dd06  mov     rax, [rsp+168h+arg_20]
0x18000dd0e  mov     [rsp+168h+var_E8], rax
0x18000dd16  xor     r14d, r14d
0x18000dd19  mov     qword ptr [rsp+168h+var_118.cb], r14
0x18000dd1e  mov     r8d, r14d
0x18000dd21  mov     [rsp+168h+var_118.pb], r14
0x18000dd26  mov     [rsp+168h+var_100], r14
0x18000dd2b  mov     r12d, r14d
0x18000dd2e  mov     [rsp+168h+var_F0], r14
0x18000dd33  test    rax, rax
0x18000dd36  jnz     short loc_18000DD49
0x18000dd38  mov     edi, 80004003h
0x18000dd3d  mov     edx, edi
0x18000dd3f  mov     ecx, 0AF902C4h
0x18000dd44  jmp     loc_18000E0CB
0x18000dd49  mov     ecx, esi
0x18000dd4b  sub     ecx, 65727231h
0x18000dd51  jz      short loc_18000DD65
0x18000dd53  cmp     ecx, 1
0x18000dd56  jz      short loc_18000DD65
0x18000dd58  mov     r13d, 1
0x18000dd5e  mov     [rsp+168h+var_130], r13d
0x18000dd63  jmp     short loc_18000DDB0
0x18000dd65  mov     edx, r14d
0x18000dd68  cmp     esi, 65727232h
0x18000dd6e  setz    dl
0x18000dd71  mov     ecx, r9d
0x18000dd74  call    cs:__imp_?myGetErrorMessageText@@YAPEAGJK@Z; myGetErrorMessageText(long,ulong)
0x18000dd7a  mov     r12, rax
0x18000dd7d  mov     [rsp+168h+var_F0], rax
0x18000dd82  test    rax, rax
0x18000dd85  jnz     short loc_18000DD98
0x18000dd87  mov     edi, 8007000Eh
0x18000dd8c  mov     edx, edi
0x18000dd8e  mov     ecx, 0B0A02C4h
0x18000dd93  jmp     loc_18000E0CB
0x18000dd98  mov     r15d, 2
0x18000dd9e  mov     [rsp+168h+var_128], r15d
0x18000dda3  mov     r13d, r14d
0x18000dda6  mov     [rsp+168h+var_130], r14d
0x18000ddab  mov     r8, [rsp+168h+var_118.pb]
0x18000ddb0  mov     eax, esi
0x18000ddb2  and     eax, 7F7F0000h
0x18000ddb7  cmp     eax, 736C0000h
0x18000ddbc  jz      short loc_18000DDDB
0x18000ddbe  cmp     eax, 73740000h
0x18000ddc3  jz      short loc_18000DDDB
0x18000ddc5  mov     [rsp+168h+var_120], 0FFFFFFFFh
0x18000ddcd  mov     eax, r15d
0x18000ddd0  and     eax, 100h
0x18000ddd5  mov     dword ptr [rsp+168h+var_108], eax
0x18000ddd9  jmp     short loc_18000DE30
0x18000dddb  mov     eax, r15d
0x18000ddde  and     eax, 100h
0x18000dde3  mov     dword ptr [rsp+168h+var_108], eax
0x18000dde7  jz      short loc_18000DDFA
0x18000dde9  mov     edx, 80070057h
0x18000ddee  mov     edi, edx
0x18000ddf0  mov     ecx, 0B1902C4h
0x18000ddf5  jmp     loc_18000E0CB
0x18000ddfa  movzx   eax, si
0x18000ddfd  mov     [rsp+168h+var_120], eax
0x18000de01  and     esi, 0FFFF0000h
0x18000de07  mov     [rsp+168h+var_138], esi
0x18000de0b  cmp     esi, 73740000h
0x18000de11  lea     rax, [rbx+0E8h]
0x18000de18  jz      short loc_18000DE21
0x18000de1a  lea     rax, [rbx+108h]
0x18000de21  mov     r13d, r14d
0x18000de24  cmp     [rax], r14
0x18000de27  setz    r13b
0x18000de2b  mov     [rsp+168h+var_130], r13d
0x18000de30  test    r13d, r13d
0x18000de33  jz      loc_18000DF52
0x18000de39  mov     rcx, rdi; unsigned __int16 *
0x18000de3c  call    ?IsWebServer@@YA_NPEBG@Z; IsWebServer(ushort const *)
0x18000de41  test    al, al
0x18000de43  jz      short loc_18000DE70
0x18000de45  lea     r9, [rsp+168h+var_118]; struct _CERTTRANSBLOB *
0x18000de4a  mov     r8d, r15d; unsigned int
0x18000de4d  mov     rdx, [rbx+178h]; struct IClientCred *
0x18000de54  mov     rcx, rdi; this
0x18000de57  call    ?GetCAExchangeCertificate@CEnrollmentWebProxy@CertEnrollHttp@@SAJPEBGPEAUIClientCred@@KPEAU_CERTTRANSBLOB@@@Z; CertEnrollHttp::CEnrollmentWebProxy::GetCAExchangeCertificate(ushort const *,IClientCred *,ulong,_CERTTRANSBLOB *)
0x18000de5c  mov     edi, eax
0x18000de5e  test    eax, eax
0x18000de60  jz      loc_18000DF48
0x18000de66  mov     ecx, 0B2C02C4h
0x18000de6b  jmp     loc_18000E0C9
0x18000de70  lea     rax, [rsp+168h+var_100]
0x18000de75  mov     [rsp+168h+var_148], rax; unsigned __int16 **
0x18000de7a  mov     r9d, 1; unsigned int
0x18000de80  mov     r8, rdi; unsigned __int16 *
0x18000de83  xor     edx, edx; int
0x18000de85  mov     rcx, rbx; this
0x18000de88  call    ?_OpenConnection@CCertRequest@@AEAAJHPEBGKPEAPEBG@Z; CCertRequest::_OpenConnection(int,ushort const *,ulong,ushort const * *)
0x18000de8d  mov     edi, eax
0x18000de8f  test    eax, eax
0x18000de91  jz      short loc_18000DE9D
0x18000de93  mov     ecx, 0B3102C4h
0x18000de98  jmp     loc_18000E0C9
0x18000de9d  cmp     dword ptr [rsp+168h+var_108], r14d
0x18000dea2  jz      short loc_18000DEBD
0x18000dea4  or      esi, 80000000h
0x18000deaa  mov     [rsp+168h+var_138], esi
0x18000deae  bt      r15d, 9
0x18000deb3  jnb     short loc_18000DEBD
0x18000deb5  bts     esi, 17h
0x18000deb9  mov     [rsp+168h+var_138], esi
0x18000debd  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18000dec4  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000deca  mov     rbx, rax
0x18000decd  mov     [rsp+168h+var_108], rax
0x18000ded2  mov     rcx, [rsp+168h+var_F8]
0x18000ded7  mov     rcx, [rcx+50h]
0x18000dedb  mov     rax, [rcx]
0x18000dede  lea     r9, [rsp+168h+var_118]
0x18000dee3  mov     r8, [rsp+168h+var_100]
0x18000dee8  mov     edx, esi
0x18000deea  mov     rax, [rax+20h]
0x18000deee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000def3  mov     edi, eax
0x18000def5  mov     [rsp+168h+var_12C], eax
0x18000def9  mov     rcx, rbx
0x18000defc  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18000df02  nop
0x18000df03  mov     rbx, [rsp+168h+var_F8]
0x18000df08  jmp     short loc_18000DF2C
0x18000df0a  xor     r14d, r14d
0x18000df0d  mov     edi, [rsp+168h+var_12C]
0x18000df11  mov     r12, [rsp+168h+var_F0]
0x18000df16  mov     r13d, [rsp+168h+var_130]
0x18000df1b  mov     rbx, [rsp+168h+var_E0]
0x18000df23  mov     esi, [rsp+168h+var_138]
0x18000df27  mov     r15d, [rsp+168h+var_128]
0x18000df2c  test    edi, edi
0x18000df2e  jz      short loc_18000DF48
0x18000df30  mov     r8d, 80070002h
0x18000df36  mov     edx, edi
0x18000df38  mov     ecx, 0B4E02C4h
0x18000df3d  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18000df43  jmp     loc_18000E0D1
0x18000df48  mov     r8, [rsp+168h+var_118.pb]
0x18000df4d  mov     rcx, r8
0x18000df50  jmp     short loc_18000DF55
0x18000df52  mov     rcx, r12; unsigned __int8 *
0x18000df55  cmp     esi, 6363726Ch
0x18000df5b  jz      short loc_18000DF97
0x18000df5d  cmp     esi, 696E666Fh
0x18000df63  jz      loc_18000E063
0x18000df69  cmp     esi, 736C0000h
0x18000df6f  jz      loc_18000E01F
0x18000df75  cmp     esi, 73740000h
0x18000df7b  jz      loc_18000E00F
0x18000df81  cmp     esi, 74797065h
0x18000df87  jz      short loc_18000DFE1
0x18000df89  and     esi, 7F7F0000h
0x18000df8f  cmp     esi, 636C0000h
0x18000df95  jnz     short loc_18000DFA7
0x18000df97  test    r15d, 0FFFFFEFFh
0x18000df9e  mov     eax, 9
0x18000dfa3  cmovz   r15d, eax
0x18000dfa7  mov     eax, r14d
0x18000dfaa  test    r12, r12
0x18000dfad  jz      loc_18000E09F
0x18000dfb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dfb7  inc     rax
0x18000dfba  cmp     [r12+rax*2], r14w
0x18000dfbf  jnz     short loc_18000DFB7
0x18000dfc1  add     rax, rax
0x18000dfc4  cmp     rax, 61A8000h
0x18000dfca  jbe     loc_18000E09F
0x18000dfd0  mov     edi, 80070216h
0x18000dfd5  mov     edx, edi
0x18000dfd7  mov     ecx, 0BB202C4h
0x18000dfdc  jmp     loc_18000E0CB
0x18000dfe1  mov     r9d, [rcx]
0x18000dfe4  lea     r8, aU; "%u"
0x18000dfeb  mov     edx, 3Ch ; '<'; unsigned __int64
0x18000dff0  lea     rcx, [rsp+168h+var_C8]; unsigned __int16 *
0x18000dff8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dffd  lea     r12, [rsp+168h+var_C8]
0x18000e005  lea     rcx, [rsp+168h+var_C8]
0x18000e00d  jmp     short loc_18000DFB3
0x18000e00f  lea     rdx, [rbx+0E8h]
0x18000e016  lea     rcx, [rbx+0F0h]
0x18000e01d  jmp     short loc_18000E02D
0x18000e01f  lea     rdx, [rbx+108h]
0x18000e026  lea     rcx, [rbx+110h]
0x18000e02d  test    r13d, r13d
0x18000e030  jz      short loc_18000E040
0x18000e032  mov     eax, [rsp+168h+var_118.cb]
0x18000e036  mov     [rcx], eax
0x18000e038  mov     [rdx], r8
0x18000e03b  mov     [rsp+168h+var_118.pb], r14
0x18000e040  mov     eax, [rsp+168h+var_120]
0x18000e044  cmp     eax, [rcx]
0x18000e046  jb      short loc_18000E056
0x18000e048  mov     edx, 80070057h
0x18000e04d  mov     edi, edx
0x18000e04f  mov     ecx, 0B9202C4h
0x18000e054  jmp     short loc_18000E0CB
0x18000e056  mov     rcx, rax
0x18000e059  mov     rax, [rdx]
0x18000e05c  movzx   r9d, byte ptr [rcx+rax]
0x18000e061  jmp     short loc_18000DFE4
0x18000e063  cmp     dword ptr [rcx], 0Ch
0x18000e066  jnb     short loc_18000E076
0x18000e068  mov     edi, 8007000Dh
0x18000e06d  mov     edx, edi
0x18000e06f  mov     ecx, 0B6B02C4h
0x18000e074  jmp     short loc_18000E0CB
0x18000e076  mov     eax, [rcx+8]
0x18000e079  mov     dword ptr [rsp+168h+var_148], eax
0x18000e07d  mov     r9d, [rcx+4]
0x18000e081  lea     r8, aUU; "%u,%u"
0x18000e088  mov     edx, 3Ch ; '<'; unsigned __int64
0x18000e08d  lea     rcx, [rsp+168h+var_C8]; unsigned __int16 *
0x18000e095  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e09a  jmp     loc_18000DFFD
0x18000e09f  btr     r15d, 8
0x18000e0a4  mov     edx, [rsp+168h+var_118.cb]
0x18000e0a8  cmp     rcx, r12
0x18000e0ab  cmovz   edx, eax; unsigned int
0x18000e0ae  mov     r9, [rsp+168h+var_E8]; unsigned __int16 **
0x18000e0b6  mov     r8d, r15d; unsigned int
0x18000e0b9  call    ?EncodeCertString@@YAJPEBEKKPEAPEAG@Z; EncodeCertString(uchar const *,ulong,ulong,ushort * *)
0x18000e0be  mov     edi, eax
0x18000e0c0  test    eax, eax
0x18000e0c2  jz      short loc_18000E0D1
0x18000e0c4  mov     ecx, 0BBB02C4h
0x18000e0c9  mov     edx, eax
0x18000e0cb  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18000e0d1  mov     [rbx+6Ch], edi
0x18000e0d4  test    r12, r12
0x18000e0d7  jz      short loc_18000E0EF
0x18000e0d9  lea     rax, [rsp+168h+var_C8]
0x18000e0e1  cmp     rax, r12
0x18000e0e4  jz      short loc_18000E0EF
0x18000e0e6  mov     rcx, r12; hMem
0x18000e0e9  call    cs:__imp_LocalFree
0x18000e0ef  mov     rcx, [rsp+168h+var_118.pb]; pv
0x18000e0f4  test    rcx, rcx
0x18000e0f7  jz      short loc_18000E0FF
0x18000e0f9  call    cs:__imp_CoTaskMemFree
0x18000e0ff  lea     r8, aCcertrequestGe_1; "CCertRequest::GetCACertificate"
0x18000e106  mov     edx, edi; int
0x18000e108  call    ?_SetErrorInfo@CCertRequest@@AEAAJJPEBG@Z; CCertRequest::_SetErrorInfo(long,ushort const *)
0x18000e10d  mov     rcx, [rsp+168h+var_48]
0x18000e115  xor     rcx, rsp; StackCookie
0x18000e118  call    __security_check_cookie
0x18000e11d  add     rsp, 130h
0x18000e124  pop     r15
0x18000e126  pop     r14
0x18000e128  pop     r13
0x18000e12a  pop     r12
0x18000e12c  pop     rdi
0x18000e12d  pop     rsi
0x18000e12e  pop     rbx
0x18000e12f  retn
```
