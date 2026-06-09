# CertHelper::GetKSPName(unsigned __int64,ushort * *)

- ea: `0x180095fbc`
- end: `0x180096432`
- name: `?GetKSPName@CertHelper@@YAJ_KPEAPEAG@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CertHelper *__hidden this, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180095a8c`

## callees

- `0x180001aa0`
- `0x1800787d4`
- `0x180078820`
- `0x180095fbc`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180096417`
- `ncrypt!NCryptFreeObject` at `0x180096417`
- `ncrypt!NCryptGetProperty` at `0x18009612e`
- `ncrypt!NCryptGetProperty` at `0x1800961ed`
- `ncrypt!NCryptGetProperty` at `0x180096361`
- `ncrypt!NCryptGetProperty` at `0x18009612e`
- `ncrypt!NCryptGetProperty` at `0x1800961ed`
- `ncrypt!NCryptGetProperty` at `0x180096361`

## string_xrefs

- `0x18009602f`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1800960c6`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x18009617f`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x18009623e`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1800962f2`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1800963ae`: `onecore\termsrv\rdp\win\security\certhelper.cpp`

## pseudocode

```c
__int64 __fastcall CertHelper::GetKSPName(CertHelper *this, BYTE **a2, unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 *v5; // rdx
  const char **v6; // rax
  SECURITY_STATUS Property; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  SECURITY_STATUS v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  BYTE *v16; // rdi
  int v17; // r8d
  int v18; // r9d
  SECURITY_STATUS v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  const char **v24; // [rsp+30h] [rbp-50h]
  const char **v25; // [rsp+40h] [rbp-40h]
  const char **v26; // [rsp+48h] [rbp-38h]
  DWORD pcbResult; // [rsp+50h] [rbp-30h] BYREF
  BYTE pbOutput[8]; // [rsp+58h] [rbp-28h] BYREF
  const char *v29; // [rsp+60h] [rbp-20h] BYREF
  const char *v30; // [rsp+68h] [rbp-18h] BYREF
  const char *v31; // [rsp+70h] [rbp-10h] BYREF
  const char *v32; // [rsp+78h] [rbp-8h] BYREF
  DWORD cbOutput; // [rsp+A0h] [rbp+20h] BYREF
  int v34; // [rsp+B0h] [rbp+30h] BYREF
  int v35; // [rsp+B8h] [rbp+38h] BYREF

  *(_QWORD *)pbOutput = 0;
  pcbResult = 8;
  cbOutput = 0;
  if ( !this )
  {
    v4 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    v34 = 616;
    v29 = "hKey is not specified";
    v5 = qword_1801B0010;
    v30 = "GetKSPName";
    v31 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
    v32 = "Error condition failed";
    v26 = &v29;
    v25 = &v30;
    v24 = &v31;
    v6 = &v32;
    goto LABEL_4;
  }
  if ( a2 )
  {
    Property = NCryptGetProperty((NCRYPT_HANDLE)this, L"Provider Handle", pbOutput, 8u, &pcbResult, 0x40u);
    v4 = Property;
    if ( Property )
    {
      if ( Property > 0 )
        v4 = (unsigned __int16)Property | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v34 = 627;
        v32 = "NCryptGetProperty(NCRYPT_PROVIDER_HANDLE_PROPERTY) failed";
        v35 = v4;
        v31 = "GetKSPName";
        v30 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
        v29 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)word_1801AFF7A,
          v9,
          v10,
          (__int64)&v29,
          (__int64)&v35,
          (__int64)&v30,
          (__int64)&v34,
          (__int64)&v31,
          (__int64)&v32);
      }
    }
    else
    {
      v11 = NCryptGetProperty(*(NCRYPT_HANDLE *)pbOutput, L"Name", 0, 0, &cbOutput, 0x40u);
      v4 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v4 = (unsigned __int16)v11 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v34 = 640;
          v32 = "NCryptGetProperty(NCRYPT_NAME_PROPERTY) failed";
          v35 = v4;
          v31 = "GetKSPName";
          v30 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
          v29 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)&byte_1801AFF2F,
            v13,
            v14,
            (__int64)&v29,
            (__int64)&v35,
            (__int64)&v30,
            (__int64)&v34,
            (__int64)&v31,
            (__int64)&v32);
        }
      }
      else
      {
        v16 = (BYTE *)operator new(saturated_mul((unsigned __int64)cbOutput >> 1, 2u));
        if ( v16 )
        {
          v19 = NCryptGetProperty(*(NCRYPT_HANDLE *)pbOutput, L"Name", v16, cbOutput, &cbOutput, 0x40u);
          v4 = v19;
          if ( v19 )
          {
            if ( v19 > 0 )
              v4 = (unsigned __int16)v19 | 0x80070000;
            if ( (unsigned int)CallbackContext > 2 )
            {
              v34 = 653;
              v32 = "NCryptGetProperty(NCRYPT_NAME_PROPERTY) failed";
              v35 = v4;
              v31 = "GetKSPName";
              v30 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
              v29 = "Error condition failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v20,
                (unsigned int)byte_1801AFE99,
                v21,
                v22,
                (__int64)&v29,
                (__int64)&v35,
                (__int64)&v30,
                (__int64)&v34,
                (__int64)&v31,
                (__int64)&v32);
            }
            operator delete(v16);
          }
          else
          {
            *a2 = v16;
            v4 = 0;
          }
        }
        else
        {
          v4 = -2147024882;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v34 = 643;
            v32 = "pwszKSPName allocation failed";
            v35 = -2147024882;
            v31 = "GetKSPName";
            v30 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
            v29 = "Error condition failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v15,
              (unsigned int)&dword_1801AFEE4,
              v17,
              v18,
              (__int64)&v29,
              (__int64)&v35,
              (__int64)&v30,
              (__int64)&v34,
              (__int64)&v31,
              (__int64)&v32);
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = 617;
      v32 = "ppKSPName is not specified";
      v5 = (__int64 *)byte_1801AFFC5;
      v31 = "GetKSPName";
      v30 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      v29 = "Error condition failed";
      v26 = &v32;
      v25 = &v31;
      v24 = &v30;
      v6 = &v29;
LABEL_4:
      v35 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (_DWORD)v5,
        (_DWORD)a3,
        8,
        (__int64)v6,
        (__int64)&v35,
        (__int64)v24,
        (__int64)&v34,
        (__int64)v25,
        (__int64)v26);
    }
  }
LABEL_28:
  if ( *(_QWORD *)pbOutput )
    NCryptFreeObject(*(NCRYPT_HANDLE *)pbOutput);
  return v4;
}

```

## disassembly

```asm
0x180095fbc  mov     r11, rsp
0x180095fbf  mov     [r11+10h], rbx
0x180095fc3  push    rbp
0x180095fc4  push    rsi
0x180095fc5  push    rdi
0x180095fc6  mov     rbp, rsp
0x180095fc9  sub     rsp, 80h
0x180095fd0  mov     qword ptr [rbp+pbOutput], 0
0x180095fd8  mov     r9d, 8; cbOutput
0x180095fde  mov     [rbp+var_30], r9d
0x180095fe2  mov     rsi, rdx
0x180095fe5  mov     [rbp+cbOutput], 0
0x180095fec  test    rcx, rcx
0x180095fef  jnz     loc_180096083
0x180095ff5  mov     eax, cs:CallbackContext
0x180095ffb  mov     ecx, 80070057h
0x180096000  mov     ebx, ecx
0x180096002  cmp     eax, 2
0x180096005  jbe     loc_18009640E
0x18009600b  lea     rax, aHkeyIsNotSpeci; "hKey is not specified"
0x180096012  mov     [rbp+arg_10], 268h
0x180096019  mov     [rbp+var_20], rax
0x18009601d  lea     rdx, qword_1801B0010
0x180096024  lea     rax, aGetkspname; "GetKSPName"
0x18009602b  mov     [rbp+var_18], rax
0x18009602f  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180096036  mov     [rbp+var_10], rax
0x18009603a  lea     rax, aErrorCondition; "Error condition failed"
0x180096041  mov     [rbp+var_8], rax
0x180096045  lea     rax, [rbp+var_20]
0x180096049  mov     [r11-50h], rax
0x18009604d  lea     rax, [rbp+var_18]
0x180096051  mov     [r11-58h], rax
0x180096055  lea     rax, [rbp+arg_10]
0x180096059  mov     [r11-60h], rax
0x18009605d  lea     rax, [rbp+var_10]
0x180096061  mov     [r11-68h], rax
0x180096065  lea     rax, [rbp+arg_18]
0x180096069  mov     [r11-70h], rax
0x18009606d  lea     rax, [rbp+var_8]
0x180096071  mov     [rbp+arg_18], ecx
0x180096074  mov     [rsp+80h+pcbResult], rax
0x180096079  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009607e  jmp     loc_18009640E
0x180096083  test    rsi, rsi
0x180096086  jnz     loc_180096112
0x18009608c  mov     eax, cs:CallbackContext
0x180096092  mov     ecx, 80070057h; hObject
0x180096097  mov     ebx, ecx
0x180096099  cmp     eax, 2
0x18009609c  jbe     loc_18009640E
0x1800960a2  lea     rax, aPpkspnameIsNot; "ppKSPName is not specified"
0x1800960a9  mov     [rbp+arg_10], 269h
0x1800960b0  mov     [rbp+var_8], rax
0x1800960b4  lea     rdx, byte_1801AFFC5
0x1800960bb  lea     rax, aGetkspname; "GetKSPName"
0x1800960c2  mov     [rbp+var_10], rax
0x1800960c6  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800960cd  mov     [rbp+var_18], rax
0x1800960d1  lea     rax, aErrorCondition; "Error condition failed"
0x1800960d8  mov     [rbp+var_20], rax
0x1800960dc  lea     rax, [rbp+var_8]
0x1800960e0  mov     [rsp+80h+var_38], rax
0x1800960e5  lea     rax, [rbp+var_10]
0x1800960e9  mov     [rsp+80h+var_40], rax
0x1800960ee  lea     rax, [rbp+arg_10]
0x1800960f2  mov     [rsp+80h+var_48], rax
0x1800960f7  lea     rax, [rbp+var_18]
0x1800960fb  mov     [rsp+80h+var_50], rax
0x180096100  lea     rax, [rbp+arg_18]
0x180096104  mov     qword ptr [rsp+80h+dwFlags], rax
0x180096109  lea     rax, [rbp+var_20]
0x18009610d  jmp     loc_180096071
0x180096112  lea     rax, [rbp+var_30]
0x180096116  mov     [rsp+80h+dwFlags], 40h ; '@'; dwFlags
0x18009611e  lea     r8, [rbp+pbOutput]; pbOutput
0x180096122  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180096127  lea     rdx, pszProperty; "Provider Handle"
0x18009612e  call    cs:__imp_NCryptGetProperty
0x180096134  mov     ebx, eax
0x180096136  test    eax, eax
0x180096138  jz      loc_1800961CB
0x18009613e  jle     short loc_180096149
0x180096140  movzx   ebx, ax
0x180096143  or      ebx, 80070000h
0x180096149  mov     eax, cs:CallbackContext
0x18009614f  cmp     eax, 2
0x180096152  jbe     loc_18009640E
0x180096158  lea     rax, aNcryptgetprope_1; "NCryptGetProperty(NCRYPT_PROVIDER_HANDL"...
0x18009615f  mov     [rbp+arg_10], 273h
0x180096166  mov     [rbp+var_8], rax
0x18009616a  lea     rdx, word_1801AFF7A
0x180096171  lea     rax, aGetkspname; "GetKSPName"
0x180096178  mov     [rbp+arg_18], ebx
0x18009617b  mov     [rbp+var_10], rax
0x18009617f  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180096186  mov     [rbp+var_18], rax
0x18009618a  lea     rax, aErrorCondition; "Error condition failed"
0x180096191  mov     [rbp+var_20], rax
0x180096195  lea     rax, [rbp+var_8]
0x180096199  mov     [rsp+80h+var_38], rax
0x18009619e  lea     rax, [rbp+var_10]
0x1800961a2  mov     [rsp+80h+var_40], rax
0x1800961a7  lea     rax, [rbp+arg_10]
0x1800961ab  mov     [rsp+80h+var_48], rax
0x1800961b0  lea     rax, [rbp+var_18]
0x1800961b4  mov     [rsp+80h+var_50], rax
0x1800961b9  lea     rax, [rbp+arg_18]
0x1800961bd  mov     qword ptr [rsp+80h+dwFlags], rax
0x1800961c2  lea     rax, [rbp+var_20]
0x1800961c6  jmp     loc_180096074
0x1800961cb  mov     rcx, qword ptr [rbp+pbOutput]; hObject
0x1800961cf  lea     rax, [rbp+cbOutput]
0x1800961d3  mov     [rsp+80h+dwFlags], 40h ; '@'; dwFlags
0x1800961db  lea     rdx, aName; "Name"
0x1800961e2  xor     r9d, r9d; cbOutput
0x1800961e5  mov     [rsp+80h+pcbResult], rax; pcbResult
0x1800961ea  xor     r8d, r8d; pbOutput
0x1800961ed  call    cs:__imp_NCryptGetProperty
0x1800961f3  mov     ebx, eax
0x1800961f5  test    eax, eax
0x1800961f7  jz      loc_18009628A
0x1800961fd  jle     short loc_180096208
0x1800961ff  movzx   ebx, ax
0x180096202  or      ebx, 80070000h
0x180096208  mov     eax, cs:CallbackContext
0x18009620e  cmp     eax, 2
0x180096211  jbe     loc_18009640E
0x180096217  lea     rax, aNcryptgetprope_2; "NCryptGetProperty(NCRYPT_NAME_PROPERTY)"...
0x18009621e  mov     [rbp+arg_10], 280h
0x180096225  mov     [rbp+var_8], rax
0x180096229  lea     rdx, byte_1801AFF2F
0x180096230  lea     rax, aGetkspname; "GetKSPName"
0x180096237  mov     [rbp+arg_18], ebx
0x18009623a  mov     [rbp+var_10], rax
0x18009623e  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180096245  mov     [rbp+var_18], rax
0x180096249  lea     rax, aErrorCondition; "Error condition failed"
0x180096250  mov     [rbp+var_20], rax
0x180096254  lea     rax, [rbp+var_8]
0x180096258  mov     [rsp+80h+var_38], rax
0x18009625d  lea     rax, [rbp+var_10]
0x180096261  mov     [rsp+80h+var_40], rax
0x180096266  lea     rax, [rbp+arg_10]
0x18009626a  mov     [rsp+80h+var_48], rax
0x18009626f  lea     rax, [rbp+var_18]
0x180096273  mov     [rsp+80h+var_50], rax
0x180096278  lea     rax, [rbp+arg_18]
0x18009627c  mov     qword ptr [rsp+80h+dwFlags], rax
0x180096281  lea     rax, [rbp+var_20]
0x180096285  jmp     loc_180096074
0x18009628a  mov     ecx, [rbp+cbOutput]
0x18009628d  mov     eax, 2
0x180096292  shr     rcx, 1
0x180096295  mul     rcx
0x180096298  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009629f  cmovb   rax, rcx
0x1800962a3  mov     rcx, rax; Size
0x1800962a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800962ab  mov     rdi, rax
0x1800962ae  test    rax, rax
0x1800962b1  jnz     loc_18009633E
0x1800962b7  mov     eax, cs:CallbackContext
0x1800962bd  mov     ebx, 8007000Eh
0x1800962c2  cmp     eax, 2
0x1800962c5  jbe     loc_18009640E
0x1800962cb  lea     rax, aPwszkspnameAll; "pwszKSPName allocation failed"
0x1800962d2  mov     [rbp+arg_10], 283h
0x1800962d9  mov     [rbp+var_8], rax
0x1800962dd  lea     rdx, dword_1801AFEE4
0x1800962e4  lea     rax, aGetkspname; "GetKSPName"
0x1800962eb  mov     [rbp+arg_18], ebx
0x1800962ee  mov     [rbp+var_10], rax
0x1800962f2  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800962f9  mov     [rbp+var_18], rax
0x1800962fd  lea     rax, aErrorCondition; "Error condition failed"
0x180096304  mov     [rbp+var_20], rax
0x180096308  lea     rax, [rbp+var_8]
0x18009630c  mov     [rsp+80h+var_38], rax
0x180096311  lea     rax, [rbp+var_10]
0x180096315  mov     [rsp+80h+var_40], rax
0x18009631a  lea     rax, [rbp+arg_10]
0x18009631e  mov     [rsp+80h+var_48], rax
0x180096323  lea     rax, [rbp+var_18]
0x180096327  mov     [rsp+80h+var_50], rax
0x18009632c  lea     rax, [rbp+arg_18]
0x180096330  mov     qword ptr [rsp+80h+dwFlags], rax
0x180096335  lea     rax, [rbp+var_20]
0x180096339  jmp     loc_180096074
0x18009633e  mov     r9d, [rbp+cbOutput]; cbOutput
0x180096342  lea     rax, [rbp+cbOutput]
0x180096346  mov     rcx, qword ptr [rbp+pbOutput]; hObject
0x18009634a  lea     rdx, aName; "Name"
0x180096351  mov     [rsp+80h+dwFlags], 40h ; '@'; dwFlags
0x180096359  mov     r8, rdi; pbOutput
0x18009635c  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180096361  call    cs:__imp_NCryptGetProperty
0x180096367  mov     ebx, eax
0x180096369  test    eax, eax
0x18009636b  jz      loc_180096409
0x180096371  jle     short loc_18009637C
0x180096373  movzx   ebx, ax
0x180096376  or      ebx, 80070000h
0x18009637c  mov     eax, cs:CallbackContext
0x180096382  cmp     eax, 2
0x180096385  jbe     short loc_1800963FF
0x180096387  lea     rax, aNcryptgetprope_2; "NCryptGetProperty(NCRYPT_NAME_PROPERTY)"...
0x18009638e  mov     [rbp+arg_10], 28Dh
0x180096395  mov     [rbp+var_8], rax
0x180096399  lea     rdx, byte_1801AFE99
0x1800963a0  lea     rax, aGetkspname; "GetKSPName"
0x1800963a7  mov     [rbp+arg_18], ebx
0x1800963aa  mov     [rbp+var_10], rax
0x1800963ae  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800963b5  mov     [rbp+var_18], rax
0x1800963b9  lea     rax, aErrorCondition; "Error condition failed"
0x1800963c0  mov     [rbp+var_20], rax
0x1800963c4  lea     rax, [rbp+var_8]
0x1800963c8  mov     [rsp+80h+var_38], rax
0x1800963cd  lea     rax, [rbp+var_10]
0x1800963d1  mov     [rsp+80h+var_40], rax
0x1800963d6  lea     rax, [rbp+arg_10]
0x1800963da  mov     [rsp+80h+var_48], rax
0x1800963df  lea     rax, [rbp+var_18]
0x1800963e3  mov     [rsp+80h+var_50], rax
0x1800963e8  lea     rax, [rbp+arg_18]
0x1800963ec  mov     qword ptr [rsp+80h+dwFlags], rax
0x1800963f1  lea     rax, [rbp+var_20]
0x1800963f5  mov     [rsp+80h+pcbResult], rax
0x1800963fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800963ff  mov     rcx, rdi; Block
0x180096402  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180096407  jmp     short loc_18009640E
0x180096409  mov     [rsi], rdi
0x18009640c  xor     ebx, ebx
0x18009640e  mov     rcx, qword ptr [rbp+pbOutput]; hObject
0x180096412  test    rcx, rcx
0x180096415  jz      short loc_18009641D
0x180096417  call    cs:__imp_NCryptFreeObject
0x18009641d  mov     eax, ebx
0x18009641f  mov     rbx, [rsp+80h+arg_8]
0x180096427  add     rsp, 80h
0x18009642e  pop     rdi
0x18009642f  pop     rsi
0x180096430  pop     rbp
0x180096431  retn
```
