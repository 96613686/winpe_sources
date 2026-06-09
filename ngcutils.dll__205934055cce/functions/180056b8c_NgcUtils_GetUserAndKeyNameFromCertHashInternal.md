# NgcUtils::GetUserAndKeyNameFromCertHashInternal

- ea: `0x180056b8c`
- end: `0x180056f98`
- name: `NgcUtils::GetUserAndKeyNameFromCertHashInternal`
- size: `1036`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180056fa0`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000530d`
- `0x18000ce74`
- `0x18000cfcc`
- `0x180013834`
- `0x180014458`
- `0x18001558c`
- `0x1800163bc`
- `0x180056b8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056df3`
- `CRYPT32!CertCloseStore` at `0x180056f72`
- `CRYPT32!CertCloseStore` at `0x180056f72`
- `CRYPT32!CertGetNameStringW` at `0x180056ed3`
- `CRYPT32!CertGetNameStringW` at `0x180056f24`
- `CRYPT32!CertGetNameStringW` at `0x180056ed3`
- `CRYPT32!CertGetNameStringW` at `0x180056f24`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180056d51`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180056de9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180056d51`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180056de9`
- `CRYPT32!CertFindCertificateInStore` at `0x180056c6a`
- `CRYPT32!CertFindCertificateInStore` at `0x180056c6a`
- `CRYPT32!CertOpenSystemStoreW` at `0x180056bc3`
- `CRYPT32!CertOpenSystemStoreW` at `0x180056bc3`
- `CRYPT32!CertFreeCertificateContext` at `0x180056dbd`
- `CRYPT32!CertFreeCertificateContext` at `0x180056f64`
- `CRYPT32!CertFreeCertificateContext` at `0x180056dbd`
- `CRYPT32!CertFreeCertificateContext` at `0x180056f64`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcUtils::GetUserAndKeyNameFromCertHashInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HCERTSTORE v7; // rdi
  signed int v8; // ebx
  PCCERT_CONTEXT CertificateInStore; // rax
  const CERT_CONTEXT *v10; // rbx
  DWORD v11; // eax
  signed int v12; // esi
  DWORD LastError; // eax
  _WORD *v14; // r9
  unsigned __int64 v15; // rdx
  __int64 v16; // rsi
  DWORD NameStringW; // esi
  WCHAR *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  HCERTSTORE v24; // [rsp+30h] [rbp-99h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-91h] BYREF
  _QWORD pvFindPara[2]; // [rsp+40h] [rbp-89h] BYREF
  void *pvData[4]; // [rsp+50h] [rbp-79h] BYREF
  __int128 v28; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int64 v29; // [rsp+80h] [rbp-49h]
  __int64 v30; // [rsp+88h] [rbp-41h]
  LPWSTR pszNameString[2]; // [rsp+90h] [rbp-39h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR v33[2]; // [rsp+B0h] [rbp-19h] BYREF
  HCERTSTORE *v34; // [rsp+D0h] [rbp+7h]
  __int64 v35; // [rsp+D8h] [rbp+Fh]

  v7 = CertOpenSystemStoreW(0, L"MY");
  v24 = v7;
  if ( v7 )
  {
    pvFindPara[0] = 20;
    pvFindPara[1] = a1;
    CertificateInStore = CertFindCertificateInStore(v7, 0x10001u, 0, 0x10000u, pvFindPara, 0);
    v10 = CertificateInStore;
    pvData[3] = (void *)CertificateInStore;
    if ( CertificateInStore )
    {
      pcbData = 0;
      if ( CertGetCertificateContextProperty(CertificateInStore, 2u, 0, &pcbData) )
      {
        std::vector<unsigned char>::vector<unsigned char>(pvData, pcbData);
        if ( CertGetCertificateContextProperty(v10, 2u, pvData[0], &pcbData) )
        {
          v28 = 0;
          v29 = 0;
          v30 = 7;
          LOWORD(v28) = 0;
          v14 = *(_WORD **)pvData[0];
          if ( *(_QWORD *)pvData[0] )
          {
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
            if ( v15 > 7 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&v28);
            }
            else
            {
              v29 = v15;
              v16 = 2 * v15;
              memmove_0(&v28, v14, 2 * v15);
              *(_WORD *)((char *)&v28 + v16) = 0;
            }
          }
          NameStringW = CertGetNameStringW(v10, 8u, 0, 0, 0, 0);
          *(_OWORD *)pszNameString = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(pszNameString[0]) = 0;
          std::wstring::resize(pszNameString);
          v18 = (WCHAR *)pszNameString;
          if ( si128.m128i_i64[1] > 7uLL )
            v18 = pszNameString[0];
          CertGetNameStringW(v10, 8u, 0, 0, v18, NameStringW);
          std::wstring::operator=(a4, &v28);
          std::wstring::operator=(a3, pszNameString);
          std::wstring::~wstring(pszNameString, v19, v20);
          std::wstring::~wstring(&v28, v21, v22);
          std::vector<unsigned char>::~vector<unsigned char>(pvData);
          CertFreeCertificateContext(v10);
          v8 = 0;
          goto LABEL_37;
        }
        LastError = GetLastError();
        v12 = LastError;
        if ( (unsigned int)dword_180075000 > 2 )
        {
          LODWORD(v24) = LastError;
          v34 = &v24;
          v35 = 4;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_180075000,
            (unsigned __int8 *)&unk_18006A158,
            0,
            0,
            3u,
            v33);
        }
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        std::vector<unsigned char>::~vector<unsigned char>(pvData);
      }
      else
      {
        v11 = GetLastError();
        v12 = v11;
        if ( (unsigned int)dword_180075000 > 2 )
        {
          LODWORD(v24) = v11;
          v34 = &v24;
          v35 = 4;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_180075000,
            (unsigned __int8 *)byte_18006A191,
            0,
            0,
            3u,
            v33);
        }
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
      }
      CertFreeCertificateContext(v10);
      v8 = v12;
    }
    else
    {
      v8 = GetLastError();
      if ( v8 == -2146885628 )
      {
        if ( (unsigned int)dword_180075000 > 3 )
        {
          LODWORD(v24) = -2146885628;
          v34 = &v24;
          v35 = 4;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_180075000,
            (unsigned __int8 *)byte_18006A201,
            0,
            0,
            3u,
            v33);
        }
      }
      else
      {
        if ( (unsigned int)dword_180075000 > 2 )
        {
          LODWORD(v24) = v8;
          v34 = &v24;
          v35 = 4;
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_180075000,
            (unsigned __int8 *)&word_18006A126,
            0,
            0,
            3u,
            v33);
        }
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
      }
    }
LABEL_37:
    CertCloseStore(v7, 0);
    return (unsigned int)v8;
  }
  v8 = GetLastError();
  if ( (unsigned int)dword_180075000 > 2 )
  {
    LODWORD(v24) = v8;
    v34 = &v24;
    v35 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)&word_18006A1D6, 0, 0, 3u, v33);
  }
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180056b8c  push    rbp
0x180056b8e  push    rbx
0x180056b8f  push    rsi
0x180056b90  push    rdi
0x180056b91  push    r13
0x180056b93  push    r14
0x180056b95  push    r15
0x180056b97  lea     rbp, [rsp-27h]
0x180056b9c  sub     rsp, 0F0h
0x180056ba3  mov     rax, cs:__security_cookie
0x180056baa  xor     rax, rsp
0x180056bad  mov     [rbp+57h+var_40], rax
0x180056bb1  mov     r15, r9
0x180056bb4  mov     r14, r8
0x180056bb7  mov     rbx, rcx
0x180056bba  lea     rdx, szSubsystemProtocol; "MY"
0x180056bc1  xor     ecx, ecx; hProv
0x180056bc3  call    cs:__imp_CertOpenSystemStoreW
0x180056bc9  mov     rdi, rax
0x180056bcc  mov     [rsp+120h+var_F0], rax
0x180056bd1  xor     r13d, r13d
0x180056bd4  test    rax, rax
0x180056bd7  jnz     short loc_180056C3D
0x180056bd9  call    cs:__imp_GetLastError
0x180056bdf  mov     ebx, eax
0x180056be1  mov     eax, cs:dword_180075000
0x180056be7  cmp     eax, 2
0x180056bea  jbe     short loc_180056C2B
0x180056bec  mov     dword ptr [rsp+120h+var_F0], ebx
0x180056bf0  lea     rax, [rsp+120h+var_F0]
0x180056bf5  mov     [rbp+57h+var_50], rax
0x180056bf9  mov     [rbp+57h+var_48], 4
0x180056c01  lea     rax, [rbp+57h+var_70]
0x180056c05  mov     [rsp+120h+pPrevCertContext], rax
0x180056c0a  mov     dword ptr [rsp+120h+pvFindPara], 3
0x180056c12  xor     r9d, r9d
0x180056c15  xor     r8d, r8d
0x180056c18  lea     rdx, word_18006A1D6
0x180056c1f  lea     rcx, dword_180075000
0x180056c26  call    _tlgWriteTransfer_EventWriteTransfer
0x180056c2b  test    ebx, ebx
0x180056c2d  jle     short loc_180056C38
0x180056c2f  movzx   ebx, bx
0x180056c32  or      ebx, 80070000h
0x180056c38  jmp     loc_180056F78
0x180056c3d  mov     [rsp+120h+var_E0], 14h
0x180056c46  mov     [rsp+120h+var_D8], rbx
0x180056c4b  mov     [rsp+120h+pPrevCertContext], r13; pPrevCertContext
0x180056c50  lea     rax, [rsp+120h+var_E0]
0x180056c55  mov     [rsp+120h+pvFindPara], rax; pvFindPara
0x180056c5a  mov     r9d, 10000h; dwFindType
0x180056c60  xor     r8d, r8d; dwFindFlags
0x180056c63  lea     edx, [r9+1]; dwCertEncodingType
0x180056c67  mov     rcx, rdi; hCertStore
0x180056c6a  call    cs:__imp_CertFindCertificateInStore
0x180056c70  mov     rbx, rax
0x180056c73  mov     [rbp+57h+var_B8], rax
0x180056c77  test    rax, rax
0x180056c7a  jnz     loc_180056D3D
0x180056c80  call    cs:__imp_GetLastError
0x180056c86  mov     ebx, eax
0x180056c88  mov     eax, 80092004h
0x180056c8d  cmp     ebx, eax
0x180056c8f  jnz     short loc_180056CE1
0x180056c91  mov     ecx, cs:dword_180075000
0x180056c97  cmp     ecx, 3
0x180056c9a  jbe     loc_180056D38
0x180056ca0  mov     dword ptr [rsp+120h+var_F0], eax
0x180056ca4  lea     rax, [rsp+120h+var_F0]
0x180056ca9  mov     [rbp+57h+var_50], rax
0x180056cad  mov     [rbp+57h+var_48], 4
0x180056cb5  lea     rax, [rbp+57h+var_70]
0x180056cb9  mov     [rsp+120h+pPrevCertContext], rax
0x180056cbe  mov     dword ptr [rsp+120h+pvFindPara], 3
0x180056cc6  xor     r9d, r9d
0x180056cc9  xor     r8d, r8d
0x180056ccc  lea     rdx, byte_18006A201
0x180056cd3  lea     rcx, dword_180075000
0x180056cda  call    _tlgWriteTransfer_EventWriteTransfer
0x180056cdf  jmp     short loc_180056D38
0x180056ce1  mov     eax, cs:dword_180075000
0x180056ce7  cmp     eax, 2
0x180056cea  jbe     short loc_180056D2B
0x180056cec  mov     dword ptr [rsp+120h+var_F0], ebx
0x180056cf0  lea     rax, [rsp+120h+var_F0]
0x180056cf5  mov     [rbp+57h+var_50], rax
0x180056cf9  mov     [rbp+57h+var_48], 4
0x180056d01  lea     rax, [rbp+57h+var_70]
0x180056d05  mov     [rsp+120h+pPrevCertContext], rax
0x180056d0a  mov     dword ptr [rsp+120h+pvFindPara], 3
0x180056d12  xor     r9d, r9d
0x180056d15  xor     r8d, r8d
0x180056d18  lea     rdx, word_18006A126
0x180056d1f  lea     rcx, dword_180075000
0x180056d26  call    _tlgWriteTransfer_EventWriteTransfer
0x180056d2b  test    ebx, ebx
0x180056d2d  jle     short loc_180056D38
0x180056d2f  movzx   ebx, bx
0x180056d32  or      ebx, 80070000h
0x180056d38  jmp     loc_180056F6D
0x180056d3d  mov     [rsp+120h+pcbData], r13d
0x180056d42  lea     r9, [rsp+120h+pcbData]; pcbData
0x180056d47  xor     r8d, r8d; pvData
0x180056d4a  lea     edx, [r8+2]; dwPropId
0x180056d4e  mov     rcx, rbx; pCertContext
0x180056d51  call    cs:__imp_CertGetCertificateContextProperty
0x180056d57  test    eax, eax
0x180056d59  jnz     short loc_180056DCA
0x180056d5b  call    cs:__imp_GetLastError
0x180056d61  mov     esi, eax
0x180056d63  mov     ecx, cs:dword_180075000
0x180056d69  cmp     ecx, 2
0x180056d6c  jbe     short loc_180056DAD
0x180056d6e  mov     dword ptr [rsp+120h+var_F0], eax
0x180056d72  lea     rax, [rsp+120h+var_F0]
0x180056d77  mov     [rbp+57h+var_50], rax
0x180056d7b  mov     [rbp+57h+var_48], 4
0x180056d83  lea     rax, [rbp+57h+var_70]
0x180056d87  mov     [rsp+120h+pPrevCertContext], rax
0x180056d8c  mov     dword ptr [rsp+120h+pvFindPara], 3
0x180056d94  xor     r9d, r9d
0x180056d97  xor     r8d, r8d
0x180056d9a  lea     rdx, byte_18006A191
0x180056da1  lea     rcx, dword_180075000
0x180056da8  call    _tlgWriteTransfer_EventWriteTransfer
0x180056dad  test    esi, esi
0x180056daf  jle     short loc_180056DBA
0x180056db1  movzx   esi, si
0x180056db4  or      esi, 80070000h
0x180056dba  mov     rcx, rbx; pCertContext
0x180056dbd  call    cs:__imp_CertFreeCertificateContext
0x180056dc3  mov     ebx, esi
0x180056dc5  jmp     loc_180056F6D
0x180056dca  mov     edx, [rsp+120h+pcbData]
0x180056dce  lea     rcx, [rbp+57h+pvData]
0x180056dd2  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180056dd7  nop
0x180056dd8  lea     r9, [rsp+120h+pcbData]; pcbData
0x180056ddd  mov     r8, [rbp+57h+pvData]; pvData
0x180056de1  mov     edx, 2; dwPropId
0x180056de6  mov     rcx, rbx; pCertContext
0x180056de9  call    cs:__imp_CertGetCertificateContextProperty
0x180056def  test    eax, eax
0x180056df1  jnz     short loc_180056E60
0x180056df3  call    cs:__imp_GetLastError
0x180056df9  mov     esi, eax
0x180056dfb  mov     ecx, cs:dword_180075000
0x180056e01  cmp     ecx, 2
0x180056e04  jbe     short loc_180056E45
0x180056e06  mov     dword ptr [rsp+120h+var_F0], eax
0x180056e0a  lea     rax, [rsp+120h+var_F0]
0x180056e0f  mov     [rbp+57h+var_50], rax
0x180056e13  mov     [rbp+57h+var_48], 4
0x180056e1b  lea     rax, [rbp+57h+var_70]
0x180056e1f  mov     [rsp+120h+pPrevCertContext], rax
0x180056e24  mov     dword ptr [rsp+120h+pvFindPara], 3
0x180056e2c  xor     r9d, r9d
0x180056e2f  xor     r8d, r8d
0x180056e32  lea     rdx, unk_18006A158
0x180056e39  lea     rcx, dword_180075000
0x180056e40  call    _tlgWriteTransfer_EventWriteTransfer
0x180056e45  test    esi, esi
0x180056e47  jle     short loc_180056E52
0x180056e49  movzx   esi, si
0x180056e4c  or      esi, 80070000h
0x180056e52  lea     rcx, [rbp+57h+pvData]
0x180056e56  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180056e5b  jmp     loc_180056DBA
0x180056e60  mov     rcx, [rbp+57h+pvData]
0x180056e64  xorps   xmm0, xmm0
0x180056e67  movups  [rbp+57h+var_B0], xmm0
0x180056e6b  mov     [rbp+57h+var_A0], r13
0x180056e6f  mov     [rbp+57h+var_98], 7
0x180056e77  mov     word ptr [rbp+57h+var_B0], r13w
0x180056e7c  mov     r9, [rcx]
0x180056e7f  test    r9, r9
0x180056e82  jz      short loc_180056EBC
0x180056e84  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180056e88  inc     rdx
0x180056e8b  cmp     [r9+rdx*2], r13w
0x180056e90  jnz     short loc_180056E88
0x180056e92  lea     rcx, [rbp+57h+var_B0]; void *
0x180056e96  cmp     rdx, 7
0x180056e9a  ja      short loc_180056EB7
0x180056e9c  mov     [rbp+57h+var_A0], rdx
0x180056ea0  lea     rsi, [rdx+rdx]
0x180056ea4  mov     r8, rsi; Size
0x180056ea7  mov     rdx, r9; Src
0x180056eaa  call    memmove_0
0x180056eaf  mov     word ptr [rbp+rsi+57h+var_B0], r13w
0x180056eb5  jmp     short loc_180056EBC
0x180056eb7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180056ebc  mov     dword ptr [rsp+120h+pPrevCertContext], r13d; cchNameString
0x180056ec1  mov     [rsp+120h+pvFindPara], r13; pszNameString
0x180056ec6  xor     r9d, r9d; pvTypePara
0x180056ec9  xor     r8d, r8d; dwFlags
0x180056ecc  lea     edx, [r9+8]; dwType
0x180056ed0  mov     rcx, rbx; pCertContext
0x180056ed3  call    cs:__imp_CertGetNameStringW
0x180056ed9  mov     esi, eax
0x180056edb  xorps   xmm0, xmm0
0x180056ede  movups  xmmword ptr [rbp+57h+pszNameString], xmm0
0x180056ee2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180056eea  movdqu  [rbp+57h+var_80], xmm1
0x180056eef  mov     word ptr [rbp+57h+pszNameString], r13w
0x180056ef4  lea     edx, [rax-1]
0x180056ef7  lea     rcx, [rbp+57h+pszNameString]; Src
0x180056efb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180056f00  lea     rax, [rbp+57h+pszNameString]
0x180056f04  cmp     qword ptr [rbp+57h+var_80+8], 7
0x180056f09  cmova   rax, [rbp+57h+pszNameString]
0x180056f0e  mov     dword ptr [rsp+120h+pPrevCertContext], esi; cchNameString
0x180056f12  mov     [rsp+120h+pvFindPara], rax; pszNameString
0x180056f17  xor     r9d, r9d; pvTypePara
0x180056f1a  xor     r8d, r8d; dwFlags
0x180056f1d  lea     edx, [r9+8]; dwType
0x180056f21  mov     rcx, rbx; pCertContext
0x180056f24  call    cs:__imp_CertGetNameStringW
0x180056f2a  lea     rdx, [rbp+57h+var_B0]
0x180056f2e  mov     rcx, r15
0x180056f31  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180056f36  lea     rdx, [rbp+57h+pszNameString]
0x180056f3a  mov     rcx, r14
0x180056f3d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180056f42  nop
0x180056f43  lea     rcx, [rbp+57h+pszNameString]
0x180056f47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056f4c  nop
0x180056f4d  lea     rcx, [rbp+57h+var_B0]
0x180056f51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056f56  nop
0x180056f57  lea     rcx, [rbp+57h+pvData]
0x180056f5b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180056f60  nop
0x180056f61  mov     rcx, rbx; pCertContext
0x180056f64  call    cs:__imp_CertFreeCertificateContext
0x180056f6a  mov     ebx, r13d
0x180056f6d  xor     edx, edx; dwFlags
0x180056f6f  mov     rcx, rdi; hCertStore
0x180056f72  call    cs:__imp_CertCloseStore
0x180056f78  mov     eax, ebx
0x180056f7a  mov     rcx, [rbp+57h+var_40]
0x180056f7e  xor     rcx, rsp; StackCookie
0x180056f81  call    __security_check_cookie
0x180056f86  add     rsp, 0F0h
0x180056f8d  pop     r15
0x180056f8f  pop     r14
0x180056f91  pop     r13
0x180056f93  pop     rdi
0x180056f94  pop     rsi
0x180056f95  pop     rbx
0x180056f96  pop     rbp
0x180056f97  retn
```
