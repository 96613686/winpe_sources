# Microsoft::Diagnostics::XmlFileSignatureVerifier::ExtractSigningDate(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_FILETIME *)

- ea: `0x180117760`
- end: `0x1801179e3`
- name: `?ExtractSigningDate@XmlFileSignatureVerifier@Diagnostics@Microsoft@@CAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAU_FILETIME@@@Z`
- size: `643`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180117564`

## callees

- `0x180064e8c`
- `0x180117760`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801179cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117953`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117960`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180117972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801179cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801177bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180117880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801177bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180117880`
- `CRYPT32!CryptStringToBinaryW` at `0x1801177ac`
- `CRYPT32!CryptStringToBinaryW` at `0x1801177f5`
- `CRYPT32!CryptStringToBinaryW` at `0x1801177ac`
- `CRYPT32!CryptStringToBinaryW` at `0x1801177f5`
- `CRYPT32!CryptMsgClose` at `0x18011794a`
- `CRYPT32!CryptMsgClose` at `0x180117969`
- `CRYPT32!CryptMsgClose` at `0x1801179c6`
- `CRYPT32!CryptMsgClose` at `0x18011794a`
- `CRYPT32!CryptMsgClose` at `0x180117969`
- `CRYPT32!CryptMsgClose` at `0x1801179c6`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180117822`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180117822`
- `CRYPT32!CryptMsgUpdate` at `0x180117841`
- `CRYPT32!CryptMsgUpdate` at `0x180117841`
- `CRYPT32!CryptMsgGetParam` at `0x18011786f`
- `CRYPT32!CryptMsgGetParam` at `0x1801178a7`
- `CRYPT32!CryptMsgGetParam` at `0x18011786f`
- `CRYPT32!CryptMsgGetParam` at `0x1801178a7`
- `CRYPT32!CryptDecodeObject` at `0x18011792c`
- `CRYPT32!CryptDecodeObject` at `0x18011792c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1801178d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1801178d5`

## string_xrefs

- `0x180117986`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`
- `0x1801179aa`: `onecore\base\telemetry\utc\service\common\xmlfilesignatureverifier.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::XmlFileSignatureVerifier::ExtractSigningDate(__int64 a1, _QWORD *a2)
{
  DWORD v2; // ebx
  const WCHAR *v3; // rsi
  const WCHAR *v5; // rcx
  void *v6; // rdi
  HCRYPTMSG v7; // rax
  void *v8; // rsi
  _QWORD *v9; // rbx
  __int64 i; // r14
  __int64 v11; // r8
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int pcbBinary; // [rsp+20h] [rbp-30h]
  __int64 pvStructInfo; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  DWORD pcbStructInfo; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *(_DWORD *)(a1 + 8);
  v3 = *(const WCHAR **)a1;
  v5 = *(const WCHAR **)a1;
  cbData = 0;
  if ( CryptStringToBinaryW(v5, v2, 1u, 0, &cbData, 0, 0) )
  {
    v6 = CoTaskMemAlloc(cbData);
    if ( !v6 )
    {
      v13 = -2147024882;
      v14 = 84;
      goto LABEL_19;
    }
    if ( CryptStringToBinaryW(v3, v2, 1u, (BYTE *)v6, &cbData, 0, 0) )
    {
      v7 = CryptMsgOpenToDecode(0x10000u, 0, 0, 0, 0, 0);
      v8 = v7;
      if ( v7 )
      {
        if ( CryptMsgUpdate(v7, (const BYTE *)v6, cbData, 1) )
        {
          pcbData = 0;
          if ( CryptMsgGetParam(v8, 6u, 0, 0, &pcbData) )
          {
            v9 = CoTaskMemAlloc(pcbData);
            if ( !v9 )
            {
              v13 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x66,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
                (const char *)0x8007000ELL,
                pcbBinary);
              CryptMsgClose(v8);
              CoTaskMemFree(v6);
              return v13;
            }
            if ( CryptMsgGetParam(v8, 6u, 0, v9, &pcbData) )
            {
              for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 26); i = (unsigned int)(i + 1) )
              {
                if ( !lstrcmpA("1.2.840.113549.1.9.5", *(LPCSTR *)(v9[14] + 24 * i)) )
                {
                  _mm_lfence();
                  pvStructInfo = 0;
                  pcbStructInfo = 8;
                  v11 = *(_QWORD *)(v9[14] + 24 * i + 16);
                  if ( !CryptDecodeObject(
                          0x10001u,
                          "1.2.840.113549.1.9.5",
                          *(const BYTE **)(v11 + 8),
                          *(_DWORD *)v11,
                          0,
                          &pvStructInfo,
                          &pcbStructInfo) )
                    break;
                  *a2 = pvStructInfo;
                  CoTaskMemFree(v9);
                  CryptMsgClose(v8);
                  CoTaskMemFree(v6);
                  return 0;
                }
              }
            }
            CoTaskMemFree(v9);
          }
        }
        CryptMsgClose(v8);
      }
    }
    CoTaskMemFree(v6);
  }
  v13 = -2147418113;
  v14 = 130;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\common\\xmlfilesignatureverifier.cpp",
    (const char *)v13,
    pcbBinary);
  return v13;
}

```

## disassembly

```asm
0x180117760  push    rbp
0x180117762  push    rbx
0x180117763  push    rsi
0x180117764  push    rdi
0x180117765  push    r12
0x180117767  push    r14
0x180117769  push    r15
0x18011776b  mov     rbp, rsp
0x18011776e  sub     rsp, 50h
0x180117772  mov     ebx, [rcx+8]
0x180117775  lea     rax, [rbp+cbData]
0x180117779  mov     rsi, [rcx]
0x18011777c  xor     r9d, r9d; pbBinary
0x18011777f  mov     r12, rdx
0x180117782  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x18011778b  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x180117794  mov     edx, ebx; cchString
0x180117796  mov     rcx, rsi; pszString
0x180117799  mov     [rbp+cbData], 0
0x1801177a0  lea     r14d, [r9+1]
0x1801177a4  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x1801177a9  mov     r8d, r14d; dwFlags
0x1801177ac  call    cs:__imp_CryptStringToBinaryW
0x1801177b2  test    eax, eax
0x1801177b4  jz      loc_180117978
0x1801177ba  mov     ecx, [rbp+cbData]; cb
0x1801177bd  call    cs:__imp_CoTaskMemAlloc
0x1801177c3  mov     rdi, rax
0x1801177c6  test    rax, rax
0x1801177c9  jz      loc_1801179D7
0x1801177cf  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x1801177d8  lea     rax, [rbp+cbData]
0x1801177dc  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x1801177e5  mov     r9, rdi; pbBinary
0x1801177e8  mov     r8d, r14d; dwFlags
0x1801177eb  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x1801177f0  mov     edx, ebx; cchString
0x1801177f2  mov     rcx, rsi; pszString
0x1801177f5  call    cs:__imp_CryptStringToBinaryW
0x1801177fb  test    eax, eax
0x1801177fd  jz      loc_18011796F
0x180117803  mov     [rsp+50h+pdwSkip], 0; pStreamInfo
0x18011780c  xor     r9d, r9d; hCryptProv
0x18011780f  xor     r8d, r8d; dwMsgType
0x180117812  mov     [rsp+50h+pcbBinary], 0; pRecipientInfo
0x18011781b  xor     edx, edx; dwFlags
0x18011781d  mov     ecx, 10000h; dwMsgEncodingType
0x180117822  call    cs:__imp_CryptMsgOpenToDecode
0x180117828  mov     rsi, rax
0x18011782b  test    rax, rax
0x18011782e  jz      loc_18011796F
0x180117834  mov     r8d, [rbp+cbData]; cbData
0x180117838  mov     r9d, r14d; fFinal
0x18011783b  mov     rdx, rdi; pbData
0x18011783e  mov     rcx, rax; hCryptMsg
0x180117841  call    cs:__imp_CryptMsgUpdate
0x180117847  test    eax, eax
0x180117849  jz      loc_180117966
0x18011784f  xor     r9d, r9d; pvData
0x180117852  mov     [rbp+pcbData], 0
0x180117859  lea     rax, [rbp+pcbData]
0x18011785d  xor     r8d, r8d; dwIndex
0x180117860  mov     rcx, rsi; hCryptMsg
0x180117863  mov     [rsp+50h+pcbBinary], rax; int
0x180117868  lea     r14d, [r9+6]
0x18011786c  mov     edx, r14d; dwParamType
0x18011786f  call    cs:__imp_CryptMsgGetParam
0x180117875  test    eax, eax
0x180117877  jz      loc_180117966
0x18011787d  mov     ecx, [rbp+pcbData]; cb
0x180117880  call    cs:__imp_CoTaskMemAlloc
0x180117886  mov     rbx, rax
0x180117889  test    rax, rax
0x18011788c  jz      loc_1801179A6
0x180117892  lea     rax, [rbp+pcbData]
0x180117896  mov     r9, rbx; pvData
0x180117899  xor     r8d, r8d; dwIndex
0x18011789c  mov     [rsp+50h+pcbBinary], rax; int
0x1801178a1  mov     edx, r14d; dwParamType
0x1801178a4  mov     rcx, rsi; hCryptMsg
0x1801178a7  call    cs:__imp_CryptMsgGetParam
0x1801178ad  test    eax, eax
0x1801178af  jz      loc_18011795D
0x1801178b5  xor     r14d, r14d
0x1801178b8  cmp     r14d, [rbx+68h]
0x1801178bc  jnb     loc_18011795D
0x1801178c2  mov     rdx, [rbx+70h]
0x1801178c6  lea     r15, [r14+r14*2]
0x1801178ca  lea     rcx, szStructType; "1.2.840.113549.1.9.5"
0x1801178d1  mov     rdx, [rdx+r15*8]; lpString2
0x1801178d5  call    cs:__imp_lstrcmpA
0x1801178db  test    eax, eax
0x1801178dd  jz      short loc_1801178E4
0x1801178df  inc     r14d
0x1801178e2  jmp     short loc_1801178B8
0x1801178e4  lfence
0x1801178e7  mov     [rbp+pvStructInfo], 0
0x1801178ef  lea     rdx, szStructType; "1.2.840.113549.1.9.5"
0x1801178f6  mov     [rbp+pcbStructInfo], 8
0x1801178fd  mov     ecx, 10001h; dwCertEncodingType
0x180117902  mov     rax, [rbx+70h]
0x180117906  mov     r8, [rax+r15*8+10h]
0x18011790b  lea     rax, [rbp+pcbStructInfo]
0x18011790f  mov     [rsp+50h+pdwFlags], rax; pcbStructInfo
0x180117914  lea     rax, [rbp+pvStructInfo]
0x180117918  mov     [rsp+50h+pdwSkip], rax; pvStructInfo
0x18011791d  mov     dword ptr [rsp+50h+pcbBinary], 0; dwFlags
0x180117925  mov     r9d, [r8]; cbEncoded
0x180117928  mov     r8, [r8+8]; pbEncoded
0x18011792c  call    cs:__imp_CryptDecodeObject
0x180117932  test    eax, eax
0x180117934  jz      short loc_18011795D
0x180117936  mov     rax, [rbp+pvStructInfo]
0x18011793a  mov     rcx, rbx; pv
0x18011793d  mov     [r12], rax
0x180117941  call    cs:__imp_CoTaskMemFree
0x180117947  mov     rcx, rsi; hCryptMsg
0x18011794a  call    cs:__imp_CryptMsgClose
0x180117950  mov     rcx, rdi; pv
0x180117953  call    cs:__imp_CoTaskMemFree
0x180117959  xor     eax, eax
0x18011795b  jmp     short loc_180117997
0x18011795d  mov     rcx, rbx; pv
0x180117960  call    cs:__imp_CoTaskMemFree
0x180117966  mov     rcx, rsi; hCryptMsg
0x180117969  call    cs:__imp_CryptMsgClose
0x18011796f  mov     rcx, rdi; pv
0x180117972  call    cs:__imp_CoTaskMemFree
0x180117978  mov     ebx, 8000FFFFh
0x18011797d  mov     edx, 82h; void *
0x180117982  mov     rcx, [rbp+38h]; this
0x180117986  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x18011798d  mov     r9d, ebx; char *
0x180117990  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117995  mov     eax, ebx
0x180117997  add     rsp, 50h
0x18011799b  pop     r15
0x18011799d  pop     r14
0x18011799f  pop     r12
0x1801179a1  pop     rdi
0x1801179a2  pop     rsi
0x1801179a3  pop     rbx
0x1801179a4  pop     rbp
0x1801179a5  retn
0x1801179a6  mov     rcx, [rbp+38h]; this
0x1801179aa  lea     r8, aOnecoreBaseTel_211; "onecore\\base\\telemetry\\utc\\service"...
0x1801179b1  mov     ebx, 8007000Eh
0x1801179b6  mov     edx, 66h ; 'f'; void *
0x1801179bb  mov     r9d, ebx; char *
0x1801179be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801179c3  mov     rcx, rsi; hCryptMsg
0x1801179c6  call    cs:__imp_CryptMsgClose
0x1801179cc  mov     rcx, rdi; pv
0x1801179cf  call    cs:__imp_CoTaskMemFree
0x1801179d5  jmp     short loc_180117995
0x1801179d7  mov     ebx, 8007000Eh
0x1801179dc  mov     edx, 54h ; 'T'
0x1801179e1  jmp     short loc_180117982
```
