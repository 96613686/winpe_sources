# _DecodePkcs7(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *,ulong *,char * *,ulong *,ulong *,void * *,void * *)

- ea: `0x180003e80`
- end: `0x180004220`
- name: `?_DecodePkcs7@@YAJPEBEK0KPEAPEAEPEAK2PEAPEAD22PEAPEAX4@Z`
- size: `928`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD cbData, const unsigned __int8 *, __int64, unsigned __int8 **, unsigned int *, unsigned int *pvData, char **, unsigned int *, unsigned __int8 *hMem, void **, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180003c90`
- `0x1800062f8`

## callees

- `0x180003750`
- `0x180003e80`
- `0x1800061f4`

## import_xrefs

- `CRYPT32!CryptMsgClose` at `0x1800041d6`
- `CRYPT32!CryptMsgClose` at `0x1800041d6`
- `CRYPT32!CryptMsgUpdate` at `0x180003fde`
- `CRYPT32!CryptMsgUpdate` at `0x180003fde`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180003f8e`
- `CRYPT32!CryptMsgOpenToDecode` at `0x180003f8e`
- `CRYPT32!CertOpenStore` at `0x180003f36`
- `CRYPT32!CertOpenStore` at `0x180003f36`
- `CRYPT32!CertCloseStore` at `0x1800041e9`
- `CRYPT32!CertCloseStore` at `0x1800041e9`
- `CRYPT32!CryptMsgGetParam` at `0x1800040c1`
- `CRYPT32!CryptMsgGetParam` at `0x180004121`
- `CRYPT32!CryptMsgGetParam` at `0x1800040c1`
- `CRYPT32!CryptMsgGetParam` at `0x180004121`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000412b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000412b`

## string_xrefs

- `0x180003f5c`: `ERROR: CertOpenStore Hr=%x\n`
- `0x180004000`: `ERROR: CryptMsgUpdate Hr=%x\n`
- `0x180003fb4`: `ERROR: CryptMsgOpenToDecode Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _DecodePkcs7(
        BYTE *pbData,
        DWORD cbData,
        const unsigned __int8 *a3,
        __int64 a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned int *pvData,
        char **a8,
        unsigned int *a9,
        unsigned __int8 *hMem,
        void **a11,
        void **a12)
{
  HCERTSTORE v14; // r14
  unsigned int *v15; // r12
  unsigned __int8 **v16; // r13
  void **v17; // r15
  signed int LastError; // eax
  unsigned int v19; // ebx
  HCRYPTMSG v20; // rax
  void *v21; // rdi
  signed int v22; // eax
  unsigned int v23; // r8d
  signed int v24; // eax
  int Param; // eax
  unsigned int v26; // r8d
  unsigned int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  unsigned int v30; // eax
  HLOCAL v32; // [rsp+30h] [rbp-20h] BYREF
  _DWORD pvPara[2]; // [rsp+38h] [rbp-18h] BYREF
  BYTE *v34; // [rsp+40h] [rbp-10h]
  unsigned int v35; // [rsp+A0h] [rbp+50h] BYREF
  int v36; // [rsp+A4h] [rbp+54h]
  DWORD pcbData; // [rsp+A8h] [rbp+58h] BYREF

  v36 = HIDWORD(a3);
  hMem = 0;
  v35 = 0;
  v32 = 0;
  v14 = 0;
  pcbData = 0;
  if ( a8 )
    *a8 = 0;
  v15 = a9;
  if ( a9 )
    *a9 = 0;
  v16 = a5;
  if ( a5 )
    *a5 = 0;
  if ( pvData )
    *pvData = 0;
  v17 = a11;
  if ( a11 )
    *a11 = 0;
  if ( a12 )
    *a12 = 0;
  if ( v17 )
  {
    pvPara[1] = 0;
    v34 = pbData;
    pvPara[0] = cbData;
    v14 = CertOpenStore((LPCSTR)5, 0x10001u, 0, 0, pvPara);
    if ( !v14 )
    {
      LastError = GetLastError();
      v19 = LastError;
      if ( LastError > 0 )
        v19 = (unsigned __int16)LastError | 0x80070000;
      ekTraceFmt(0x37612C0u, 1u, "ERROR: CertOpenStore Hr=%x\n", v19);
      goto LABEL_56;
    }
  }
  v20 = CryptMsgOpenToDecode(0x10001u, 0, 0, 0, 0, 0);
  v21 = v20;
  if ( v20 )
  {
    if ( CryptMsgUpdate(v20, pbData, cbData, 1) )
    {
      Param = _CryptMsgGetParam(v21, 4u, v23, &v32, &pcbData);
      if ( Param )
        ekTraceFmt(0x3A012C0u, 1u, "ERROR: _CryptMsgGetParam(InnerContentType) Hr=%x\n", Param);
      v35 = 0;
      v27 = _CryptMsgGetParam(v21, 2u, v26, (void **)&hMem, &v35);
      v19 = v27;
      if ( v27 )
      {
        ekTraceFmt(0x3AC12C0u, 1u, "ERROR: _CryptMsgGetParam(Content) Hr=%x\n", v27);
      }
      else if ( !pvData || (pcbData = 4, CryptMsgGetParam(v21, 1u, 0, pvData, &pcbData)) )
      {
        if ( !v15 )
          goto LABEL_41;
        pcbData = 4;
        if ( CryptMsgGetParam(v21, 5u, 0, v15, &pcbData) )
          goto LABEL_41;
        v29 = GetLastError();
        v19 = v29;
        if ( v29 > 0 )
          v19 = (unsigned __int16)v29 | 0x80070000;
        *v15 = 0;
        if ( v19 == -2146889724 )
        {
LABEL_41:
          if ( a12 )
          {
            *a12 = v21;
            v21 = 0;
          }
          if ( v17 )
          {
            *v17 = v14;
            v14 = 0;
          }
          if ( a8 )
          {
            *a8 = (char *)v32;
            v32 = 0;
          }
          v30 = v35;
          if ( a6 )
            *a6 = v35;
          if ( v16 && v30 )
          {
            *v16 = hMem;
            hMem = 0;
          }
          v19 = 0;
          if ( !v21 )
            goto LABEL_54;
        }
        else
        {
          ekTraceFmt(0x3CD12C0u, 1u, "ERROR: _CryptMsgGetParam(SignerCount) Hr=%x\n", v19);
        }
      }
      else
      {
        v28 = GetLastError();
        v19 = v28;
        if ( v28 > 0 )
          v19 = (unsigned __int16)v28 | 0x80070000;
        ekTraceFmt(0x3BB12C0u, 1u, "ERROR: _CryptMsgGetParam(Type) Hr=%x\n", v19);
      }
    }
    else
    {
      v24 = GetLastError();
      v19 = v24;
      if ( v24 > 0 )
        v19 = (unsigned __int16)v24 | 0x80070000;
      ekTraceFmt(0x38C12C0u, 1u, "ERROR: CryptMsgUpdate Hr=%x\n", v19);
    }
    CryptMsgClose(v21);
  }
  else
  {
    v22 = GetLastError();
    v19 = v22;
    if ( v22 > 0 )
      v19 = (unsigned __int16)v22 | 0x80070000;
    ekTraceFmt(0x38512C0u, 1u, "ERROR: CryptMsgOpenToDecode Hr=%x\n", v19);
  }
LABEL_54:
  if ( v14 )
    CertCloseStore(v14, 2u);
LABEL_56:
  LocalFree(hMem);
  LocalFree(v32);
  return v19;
}

```

## disassembly

```asm
0x180003e80  mov     [rsp-38h+arg_0], rbx
0x180003e85  mov     [rsp-38h+pcbData], r9d
0x180003e8a  mov     qword ptr [rsp-38h+arg_10], r8
0x180003e8f  push    rbp
0x180003e90  push    rsi
0x180003e91  push    rdi
0x180003e92  push    r12
0x180003e94  push    r13
0x180003e96  push    r14
0x180003e98  push    r15
0x180003e9a  mov     rbp, rsp
0x180003e9d  sub     rsp, 50h
0x180003ea1  mov     rax, [rbp+arg_38]
0x180003ea5  xor     edi, edi
0x180003ea7  mov     [rbp+hMem], rdi
0x180003eae  mov     ebx, edx
0x180003eb0  mov     [rbp+arg_10], edi
0x180003eb3  mov     rsi, rcx
0x180003eb6  mov     [rbp+var_20], rdi
0x180003eba  mov     r14d, edi
0x180003ebd  mov     [rbp+pcbData], edi
0x180003ec0  test    rax, rax
0x180003ec3  jz      short loc_180003EC8
0x180003ec5  mov     [rax], rdi
0x180003ec8  mov     r12, [rbp+arg_40]
0x180003ecf  test    r12, r12
0x180003ed2  jz      short loc_180003ED8
0x180003ed4  mov     [r12], edi
0x180003ed8  mov     r13, [rbp+arg_20]
0x180003edc  test    r13, r13
0x180003edf  jz      short loc_180003EE5
0x180003ee1  mov     [r13+0], rdi
0x180003ee5  mov     rax, [rbp+pvData]
0x180003ee9  test    rax, rax
0x180003eec  jz      short loc_180003EF0
0x180003eee  mov     [rax], edi
0x180003ef0  mov     r15, [rbp+arg_50]
0x180003ef7  test    r15, r15
0x180003efa  jz      short loc_180003EFF
0x180003efc  mov     [r15], rdi
0x180003eff  mov     rax, [rbp+arg_58]
0x180003f06  test    rax, rax
0x180003f09  jz      short loc_180003F0E
0x180003f0b  mov     [rax], rdi
0x180003f0e  test    r15, r15
0x180003f11  jz      short loc_180003F77
0x180003f13  lea     rax, [rbp+var_18]
0x180003f17  mov     [rbp+var_14], edi
0x180003f1a  xor     r9d, r9d; dwFlags
0x180003f1d  mov     [rsp+50h+pvPara], rax; pvPara
0x180003f22  xor     r8d, r8d; hCryptProv
0x180003f25  mov     [rbp+var_10], rsi
0x180003f29  mov     edx, 10001h; dwEncodingType
0x180003f2e  mov     [rbp+var_18], ebx
0x180003f31  mov     ecx, 5; lpszStoreProvider
0x180003f36  call    cs:__imp_CertOpenStore
0x180003f3c  mov     r14, rax
0x180003f3f  test    rax, rax
0x180003f42  jnz     short loc_180003F77
0x180003f44  call    cs:__imp_GetLastError
0x180003f4a  mov     ebx, eax
0x180003f4c  test    eax, eax
0x180003f4e  jle     short loc_180003F59
0x180003f50  movzx   ebx, ax
0x180003f53  or      ebx, 80070000h
0x180003f59  mov     r9d, ebx
0x180003f5c  lea     r8, aErrorCertopens; "ERROR: CertOpenStore Hr=%x\n"
0x180003f63  mov     edx, 1; unsigned int
0x180003f68  mov     ecx, 37612C0h; unsigned int
0x180003f6d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003f72  jmp     loc_1800041EF
0x180003f77  mov     [rsp+50h+pStreamInfo], rdi; pStreamInfo
0x180003f7c  xor     r9d, r9d; hCryptProv
0x180003f7f  xor     r8d, r8d; dwMsgType
0x180003f82  mov     [rsp+50h+pvPara], rdi; pRecipientInfo
0x180003f87  xor     edx, edx; dwFlags
0x180003f89  mov     ecx, 10001h; dwMsgEncodingType
0x180003f8e  call    cs:__imp_CryptMsgOpenToDecode
0x180003f94  mov     rdi, rax
0x180003f97  test    rax, rax
0x180003f9a  jnz     short loc_180003FCF
0x180003f9c  call    cs:__imp_GetLastError
0x180003fa2  mov     ebx, eax
0x180003fa4  test    eax, eax
0x180003fa6  jle     short loc_180003FB1
0x180003fa8  movzx   ebx, ax
0x180003fab  or      ebx, 80070000h
0x180003fb1  mov     r9d, ebx
0x180003fb4  lea     r8, aErrorCryptmsgo; "ERROR: CryptMsgOpenToDecode Hr=%x\n"
0x180003fbb  mov     edx, 1; unsigned int
0x180003fc0  mov     ecx, 38512C0h; unsigned int
0x180003fc5  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003fca  jmp     loc_1800041DC
0x180003fcf  mov     r9d, 1; fFinal
0x180003fd5  mov     r8d, ebx; cbData
0x180003fd8  mov     rdx, rsi; pbData
0x180003fdb  mov     rcx, rdi; hCryptMsg
0x180003fde  call    cs:__imp_CryptMsgUpdate
0x180003fe4  test    eax, eax
0x180003fe6  jnz     short loc_18000401B
0x180003fe8  call    cs:__imp_GetLastError
0x180003fee  mov     ebx, eax
0x180003ff0  test    eax, eax
0x180003ff2  jle     short loc_180003FFD
0x180003ff4  movzx   ebx, ax
0x180003ff7  or      ebx, 80070000h
0x180003ffd  mov     r9d, ebx
0x180004000  lea     r8, aErrorCryptmsgu; "ERROR: CryptMsgUpdate Hr=%x\n"
0x180004007  mov     edx, 1; unsigned int
0x18000400c  mov     ecx, 38C12C0h; unsigned int
0x180004011  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004016  jmp     loc_1800041D3
0x18000401b  lea     rax, [rbp+pcbData]
0x18000401f  mov     edx, 4; dwParamType
0x180004024  lea     r9, [rbp+var_20]; void **
0x180004028  mov     [rsp+50h+pvPara], rax; unsigned int *
0x18000402d  mov     rcx, rdi; hCryptMsg
0x180004030  call    ?_CryptMsgGetParam@@YAJPEAXKKPEAPEAXPEAK@Z; _CryptMsgGetParam(void *,ulong,ulong,void * *,ulong *)
0x180004035  test    eax, eax
0x180004037  jz      short loc_180004052
0x180004039  mov     r9d, eax
0x18000403c  lea     r8, aErrorCryptmsgg; "ERROR: _CryptMsgGetParam(InnerContentTy"...
0x180004043  mov     edx, 1; unsigned int
0x180004048  mov     ecx, 3A012C0h; unsigned int
0x18000404d  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004052  lea     rax, [rbp+arg_10]
0x180004056  mov     [rbp+arg_10], 0
0x18000405d  lea     r9, [rbp+hMem]; void **
0x180004064  mov     [rsp+50h+pvPara], rax; unsigned int *
0x180004069  mov     edx, 2; dwParamType
0x18000406e  mov     rcx, rdi; hCryptMsg
0x180004071  call    ?_CryptMsgGetParam@@YAJPEAXKKPEAPEAXPEAK@Z; _CryptMsgGetParam(void *,ulong,ulong,void * *,ulong *)
0x180004076  mov     ebx, eax
0x180004078  test    eax, eax
0x18000407a  jz      short loc_18000409A
0x18000407c  mov     r9d, eax
0x18000407f  lea     r8, aErrorCryptmsgg_2; "ERROR: _CryptMsgGetParam(Content) Hr=%x"...
0x180004086  mov     edx, 1; unsigned int
0x18000408b  mov     ecx, 3AC12C0h; unsigned int
0x180004090  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004095  jmp     loc_1800041D3
0x18000409a  mov     rax, [rbp+pvData]
0x18000409e  test    rax, rax
0x1800040a1  jz      short loc_1800040FE
0x1800040a3  lea     rcx, [rbp+pcbData]
0x1800040a7  mov     [rbp+pcbData], 4
0x1800040ae  mov     [rsp+50h+pvPara], rcx; pcbData
0x1800040b3  mov     r9, rax; pvData
0x1800040b6  mov     rcx, rdi; hCryptMsg
0x1800040b9  xor     r8d, r8d; dwIndex
0x1800040bc  mov     edx, 1; dwParamType
0x1800040c1  call    cs:__imp_CryptMsgGetParam
0x1800040c7  test    eax, eax
0x1800040c9  jnz     short loc_1800040FE
0x1800040cb  call    cs:__imp_GetLastError
0x1800040d1  mov     ebx, eax
0x1800040d3  test    eax, eax
0x1800040d5  jle     short loc_1800040E0
0x1800040d7  movzx   ebx, ax
0x1800040da  or      ebx, 80070000h
0x1800040e0  mov     r9d, ebx
0x1800040e3  lea     r8, aErrorCryptmsgg_1; "ERROR: _CryptMsgGetParam(Type) Hr=%x\n"
0x1800040ea  mov     edx, 1; unsigned int
0x1800040ef  mov     ecx, 3BB12C0h; unsigned int
0x1800040f4  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800040f9  jmp     loc_1800041D3
0x1800040fe  test    r12, r12
0x180004101  jz      short loc_18000416B
0x180004103  lea     rax, [rbp+pcbData]
0x180004107  mov     [rbp+pcbData], 4
0x18000410e  mov     r9, r12; pvData
0x180004111  mov     [rsp+50h+pvPara], rax; pcbData
0x180004116  xor     r8d, r8d; dwIndex
0x180004119  mov     edx, 5; dwParamType
0x18000411e  mov     rcx, rdi; hCryptMsg
0x180004121  call    cs:__imp_CryptMsgGetParam
0x180004127  test    eax, eax
0x180004129  jnz     short loc_18000416B
0x18000412b  call    cs:__imp_GetLastError
0x180004131  mov     ebx, eax
0x180004133  test    eax, eax
0x180004135  jle     short loc_180004140
0x180004137  movzx   ebx, ax
0x18000413a  or      ebx, 80070000h
0x180004140  mov     dword ptr [r12], 0
0x180004148  cmp     ebx, 80091004h
0x18000414e  jz      short loc_18000416B
0x180004150  mov     r9d, ebx
0x180004153  lea     r8, aErrorCryptmsgg_4; "ERROR: _CryptMsgGetParam(SignerCount) H"...
0x18000415a  mov     edx, 1; unsigned int
0x18000415f  mov     ecx, 3CD12C0h; unsigned int
0x180004164  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180004169  jmp     short loc_1800041D3
0x18000416b  mov     rax, [rbp+arg_58]
0x180004172  test    rax, rax
0x180004175  jz      short loc_18000417C
0x180004177  mov     [rax], rdi
0x18000417a  xor     edi, edi
0x18000417c  test    r15, r15
0x18000417f  jz      short loc_180004187
0x180004181  mov     [r15], r14
0x180004184  xor     r14d, r14d
0x180004187  mov     rcx, [rbp+arg_38]
0x18000418b  test    rcx, rcx
0x18000418e  jz      short loc_18000419F
0x180004190  mov     rax, [rbp+var_20]
0x180004194  mov     [rcx], rax
0x180004197  mov     [rbp+var_20], 0
0x18000419f  mov     rcx, [rbp+arg_28]
0x1800041a3  mov     eax, [rbp+arg_10]
0x1800041a6  test    rcx, rcx
0x1800041a9  jz      short loc_1800041AD
0x1800041ab  mov     [rcx], eax
0x1800041ad  test    r13, r13
0x1800041b0  jz      short loc_1800041CC
0x1800041b2  test    eax, eax
0x1800041b4  jz      short loc_1800041CC
0x1800041b6  mov     rax, [rbp+hMem]
0x1800041bd  mov     [r13+0], rax
0x1800041c1  mov     [rbp+hMem], 0
0x1800041cc  xor     ebx, ebx
0x1800041ce  test    rdi, rdi
0x1800041d1  jz      short loc_1800041DC
0x1800041d3  mov     rcx, rdi; hCryptMsg
0x1800041d6  call    cs:__imp_CryptMsgClose
0x1800041dc  test    r14, r14
0x1800041df  jz      short loc_1800041EF
0x1800041e1  mov     edx, 2; dwFlags
0x1800041e6  mov     rcx, r14; hCertStore
0x1800041e9  call    cs:__imp_CertCloseStore
0x1800041ef  mov     rcx, [rbp+hMem]; hMem
0x1800041f6  call    cs:__imp_LocalFree
0x1800041fc  mov     rcx, [rbp+var_20]; hMem
0x180004200  call    cs:__imp_LocalFree
0x180004206  mov     eax, ebx
0x180004208  mov     rbx, [rsp+50h+arg_0]
0x180004210  add     rsp, 50h
0x180004214  pop     r15
0x180004216  pop     r14
0x180004218  pop     r13
0x18000421a  pop     r12
0x18000421c  pop     rdi
0x18000421d  pop     rsi
0x18000421e  pop     rbp
0x18000421f  retn
```
