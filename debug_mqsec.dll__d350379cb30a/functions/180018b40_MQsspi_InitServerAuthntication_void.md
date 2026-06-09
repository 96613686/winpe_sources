# MQsspi_InitServerAuthntication(void)

- ea: `0x180018b40`
- end: `0x180018ebe`
- name: `?MQsspi_InitServerAuthntication@@YAJXZ`
- size: `894`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180004074`
- `0x1800049ec`
- `0x180005d68`
- `0x180005d8c`
- `0x18000d650`
- `0x1800110e0`
- `0x18001353c`
- `0x180017430`
- `0x180018350`
- `0x180018a90`
- `0x180018b40`
- `0x18002f096`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180018c6a`
- `CRYPT32!CertOpenStore` at `0x180018c6a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180018d29`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180018d29`
- `KERNEL32!GetLastError` at `0x180018c7e`
- `KERNEL32!GetLastError` at `0x180018c7e`

## string_xrefs

- `0x180018b8b`: `security\ServerCertStore`
- `0x180018bc3`: `security\ServerCertStore`
- `0x180018bfa`: `security\ServerCertDigest`
- `0x180018c2b`: `security\ServerCertDigest`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 MQsspi_InitServerAuthntication(void)
{
  int FalconKeyValue; // eax
  _QWORD *v1; // rcx
  HCERTSTORE v3; // rax
  DWORD LastError; // eax
  unsigned int v5; // eax
  int inited; // ebx
  int v7; // esi
  CReference *v8; // rdi
  const struct _CERT_CONTEXT *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // [rsp+60h] [rbp-A0h] BYREF
  CReference *v12; // [rsp+68h] [rbp-98h] BYREF
  HCERTSTORE v13; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v14[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 Buf2; // [rsp+88h] [rbp-78h] BYREF
  __int128 Buf1; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pvPara[96]; // [rsp+B0h] [rbp-50h] BYREF

  LODWORD(v12) = 1;
  v11 = 96;
  FalconKeyValue = GetFalconKeyValue(L"security\\ServerCertStore", (unsigned int *)&v12, pvPara, &v11, 0);
  if ( FalconKeyValue )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
      return 3222146080LL;
    goto LABEL_8;
  }
  Buf2 = 0;
  LODWORD(v12) = 3;
  v11 = 16;
  FalconKeyValue = GetFalconKeyValue(L"security\\ServerCertDigest", (unsigned int *)&v12, &Buf2, &v11, 0);
  if ( FalconKeyValue )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
      return 3222146080LL;
LABEL_8:
    WPP_SF_Sd(v1[32], FalconKeyValue);
    return 3222146080LL;
  }
  v3 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, pvPara);
  v13 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    g_dwSALastError = LastError;
    if ( LastError )
    {
      LOWORD(v11) = 30;
      LODWORD(v12) = LastError;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v5 = mqwcslen(L"srvauthn/srvauthn");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          2,
          2LL * (v5 + 1),
          L"srvauthn/srvauthn",
          2,
          &v11,
          4,
          &v12,
          0,
          0);
      }
    }
    inited = -1072821209;
    goto LABEL_34;
  }
  inited = 0;
  v7 = 0;
  v14[1] = v3;
  v14[0] = CertEnumCertificatesInStore(v3, 0);
  while ( 1 )
  {
    CCertEnum::GetNextCertificate(v14, &v12);
    v8 = v12;
    if ( !v12 )
      break;
    Buf1 = 0;
    inited = (*(__int64 (__fastcall **)(CReference *, __int128 *))(*(_QWORD *)v12 + 16LL))(v12, &Buf1);
    if ( inited >= 0 && !memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      v9 = (const struct _CERT_CONTEXT *)(*(__int64 (__fastcall **)(CReference *))(*(_QWORD *)v8 + 160LL))(v8);
      inited = InitServerCredHandle(v9);
      if ( inited >= 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
      v7 = 1;
      break;
    }
    if ( v8 )
      CReference::Release(v8);
  }
  if ( v8 )
    CReference::Release(v8);
  if ( !v7 )
  {
    inited = -1072821138;
    goto LABEL_31;
  }
  if ( inited < 0 )
  {
LABEL_31:
    LOWORD(v11) = 40;
    LODWORD(v12) = inited;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v10 = mqwcslen(L"srvauthn/srvauthn");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v10 + 1),
        L"srvauthn/srvauthn",
        2,
        &v11,
        4,
        &v12,
        0,
        0);
    }
  }
  CPCCertContext::~CPCCertContext((CPCCertContext *)v14);
LABEL_34:
  CHCertStore::~CHCertStore((CHCertStore *)&v13);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180018b40  push    rbp
0x180018b42  push    rbx
0x180018b43  push    rsi
0x180018b44  push    rdi
0x180018b45  push    r15
0x180018b47  lea     rbp, [rsp-20h]
0x180018b4c  sub     rsp, 120h
0x180018b53  mov     rax, cs:__security_cookie
0x180018b5a  xor     rax, rsp
0x180018b5d  mov     [rbp+40h+var_30], rax
0x180018b61  mov     r15d, 1
0x180018b67  mov     dword ptr [rsp+140h+var_D8], r15d
0x180018b6c  mov     [rsp+140h+var_E0], 60h ; '`'
0x180018b74  mov     [rsp+140h+pvPara], 0; wchar_t *
0x180018b7d  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x180018b82  lea     r8, [rbp+40h+var_90]; void *
0x180018b86  lea     rdx, [rsp+140h+var_D8]; unsigned int *
0x180018b8b  lea     rcx, aSecurityServer; "security\\ServerCertStore"
0x180018b92  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180018b97  test    eax, eax
0x180018b99  jz      short loc_180018BCC
0x180018b9b  lea     rdx, WPP_GLOBAL_Control
0x180018ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ba9  cmp     rcx, rdx
0x180018bac  jz      loc_180018C49
0x180018bb2  test    [rcx+10Ch], r15b
0x180018bb9  jz      loc_180018C49
0x180018bbf  lea     edx, [r15+9]
0x180018bc3  lea     r9, aSecurityServer; "security\\ServerCertStore"
0x180018bca  jmp     short loc_180018C32
0x180018bcc  xorps   xmm0, xmm0
0x180018bcf  movups  [rbp+40h+Buf2], xmm0
0x180018bd3  mov     dword ptr [rsp+140h+var_D8], 3
0x180018bdb  mov     [rsp+140h+var_E0], 10h
0x180018be3  mov     [rsp+140h+pvPara], 0; wchar_t *
0x180018bec  lea     r9, [rsp+140h+var_E0]; unsigned int *
0x180018bf1  lea     r8, [rbp+40h+Buf2]; void *
0x180018bf5  lea     rdx, [rsp+140h+var_D8]; unsigned int *
0x180018bfa  lea     rcx, aSecurityServer_0; "security\\ServerCertDigest"
0x180018c01  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180018c06  test    eax, eax
0x180018c08  jz      short loc_180018C53
0x180018c0a  lea     rdx, WPP_GLOBAL_Control
0x180018c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c18  cmp     rcx, rdx
0x180018c1b  jz      short loc_180018C49
0x180018c1d  test    [rcx+10Ch], r15b
0x180018c24  jz      short loc_180018C49
0x180018c26  mov     edx, 0Bh
0x180018c2b  lea     r9, aSecurityServer_0; "security\\ServerCertDigest"
0x180018c32  mov     dword ptr [rsp+140h+pvPara], eax; char
0x180018c36  lea     r8, WPP_0ac2a6a22660317cb6675a425da7b000_Traceguids
0x180018c3d  mov     rcx, [rcx+100h]; LoggerHandle
0x180018c44  call    WPP_SF_Sd
0x180018c49  mov     eax, 0C00E0C20h
0x180018c4e  jmp     loc_180018EA4
0x180018c53  lea     rax, [rbp+40h+var_90]
0x180018c57  mov     [rsp+140h+pvPara], rax; pvPara
0x180018c5c  mov     r9d, 20000h; dwFlags
0x180018c62  xor     r8d, r8d; hCryptProv
0x180018c65  xor     edx, edx; dwEncodingType
0x180018c67  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180018c6a  call    cs:__imp_CertOpenStore
0x180018c70  mov     [rsp+140h+var_D0], rax
0x180018c75  test    rax, rax
0x180018c78  jnz     loc_180018D1C
0x180018c7e  call    cs:__imp_GetLastError
0x180018c84  mov     cs:?g_dwSALastError@@3KA, eax; ulong g_dwSALastError
0x180018c8a  test    eax, eax
0x180018c8c  jz      loc_180018D12
0x180018c92  mov     ecx, 1Eh
0x180018c97  mov     word ptr [rsp+140h+var_E0], cx
0x180018c9c  mov     dword ptr [rsp+140h+var_D8], eax
0x180018ca0  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018ca8  jz      short loc_180018D12
0x180018caa  lea     rdi, aSrvauthnSrvaut; "srvauthn/srvauthn"
0x180018cb1  mov     rcx, rdi; wchar_t *
0x180018cb4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180018cb9  lea     r9d, [r15+rax]
0x180018cbd  add     r9, r9
0x180018cc0  mov     [rsp+140h+var_F0], 0
0x180018cc9  mov     [rsp+140h+var_F8], 0
0x180018cd2  lea     rax, [rsp+140h+var_D8]
0x180018cd7  mov     [rsp+140h+var_100], rax
0x180018cdc  mov     [rsp+140h+var_108], 4
0x180018ce5  lea     rax, [rsp+140h+var_E0]
0x180018cea  mov     [rsp+140h+var_110], rax
0x180018cef  mov     [rsp+140h+var_118], 2
0x180018cf8  mov     [rsp+140h+pvPara], rdi
0x180018cfd  mov     r8d, 2
0x180018d03  mov     edx, r15d
0x180018d06  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018d0d  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180018d12  mov     ebx, 0C00E0C27h
0x180018d17  jmp     loc_180018E98
0x180018d1c  xor     ebx, ebx
0x180018d1e  xor     esi, esi
0x180018d20  mov     [rbp+40h+var_C0], rax
0x180018d24  xor     edx, edx; pPrevCertContext
0x180018d26  mov     rcx, rax; hCertStore
0x180018d29  call    cs:__imp_CertEnumCertificatesInStore
0x180018d2f  mov     [rsp+140h+var_C8], rax
0x180018d34  lea     rdx, [rsp+140h+var_D8]
0x180018d39  lea     rcx, [rsp+140h+var_C8]
0x180018d3e  call    ?GetNextCertificate@CCertEnum@@QEAA?AV?$R@VCMQSigCertificate@@@@XZ; CCertEnum::GetNextCertificate(void)
0x180018d43  nop
0x180018d44  mov     rdi, [rsp+140h+var_D8]
0x180018d49  test    rdi, rdi
0x180018d4c  jz      loc_180018DF3
0x180018d52  xorps   xmm0, xmm0
0x180018d55  movups  [rbp+40h+Buf1], xmm0
0x180018d59  mov     rax, [rdi]
0x180018d5c  lea     rdx, [rbp+40h+Buf1]
0x180018d60  mov     rcx, rdi
0x180018d63  mov     rax, [rax+10h]
0x180018d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d6c  mov     ebx, eax
0x180018d6e  test    eax, eax
0x180018d70  js      short loc_180018D89
0x180018d72  mov     r8d, 10h; Size
0x180018d78  lea     rdx, [rbp+40h+Buf2]; Buf2
0x180018d7c  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180018d80  call    memcmp_0
0x180018d85  test    eax, eax
0x180018d87  jz      short loc_180018D98
0x180018d89  test    rdi, rdi
0x180018d8c  jz      short loc_180018D34
0x180018d8e  mov     rcx, rdi; this
0x180018d91  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180018d96  jmp     short loc_180018D34
0x180018d98  mov     rax, [rdi]
0x180018d9b  mov     rcx, rdi
0x180018d9e  mov     rax, [rax+0A0h]
0x180018da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018daa  mov     rcx, rax; struct _CERT_CONTEXT *
0x180018dad  call    ?InitServerCredHandle@@YAJPEBU_CERT_CONTEXT@@@Z; InitServerCredHandle(_CERT_CONTEXT const *)
0x180018db2  mov     ebx, eax
0x180018db4  test    eax, eax
0x180018db6  js      short loc_180018DF0
0x180018db8  lea     rdx, WPP_GLOBAL_Control
0x180018dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dc6  cmp     rcx, rdx
0x180018dc9  jz      short loc_180018DF0
0x180018dcb  test    byte ptr [rcx+10Ch], 4
0x180018dd2  jz      short loc_180018DF0
0x180018dd4  mov     edx, 0Ch
0x180018dd9  lea     r9, [rbp+40h+var_90]
0x180018ddd  lea     r8, WPP_0ac2a6a22660317cb6675a425da7b000_Traceguids
0x180018de4  mov     rcx, [rcx+100h]; LoggerHandle
0x180018deb  call    WPP_SF_S
0x180018df0  mov     esi, r15d
0x180018df3  test    rdi, rdi
0x180018df6  jz      short loc_180018E00
0x180018df8  mov     rcx, rdi; this
0x180018dfb  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x180018e00  test    esi, esi
0x180018e02  jnz     short loc_180018E0B
0x180018e04  mov     ebx, 0C00E0C6Eh
0x180018e09  jmp     short loc_180018E0F
0x180018e0b  test    ebx, ebx
0x180018e0d  jns     short loc_180018E8D
0x180018e0f  mov     eax, 28h ; '('
0x180018e14  mov     word ptr [rsp+140h+var_E0], ax
0x180018e19  mov     dword ptr [rsp+140h+var_D8], ebx
0x180018e1d  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018e25  jz      short loc_180018E8D
0x180018e27  lea     rdi, aSrvauthnSrvaut; "srvauthn/srvauthn"
0x180018e2e  mov     rcx, rdi; wchar_t *
0x180018e31  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180018e36  lea     r9d, [r15+rax]
0x180018e3a  add     r9, r9
0x180018e3d  mov     [rsp+140h+var_F0], 0
0x180018e46  mov     [rsp+140h+var_F8], 0
0x180018e4f  lea     rax, [rsp+140h+var_D8]
0x180018e54  mov     [rsp+140h+var_100], rax
0x180018e59  mov     [rsp+140h+var_108], 4
0x180018e62  lea     rax, [rsp+140h+var_E0]
0x180018e67  mov     [rsp+140h+var_110], rax
0x180018e6c  mov     [rsp+140h+var_118], 2
0x180018e75  mov     [rsp+140h+pvPara], rdi
0x180018e7a  mov     r8d, r15d
0x180018e7d  mov     edx, r15d
0x180018e80  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018e87  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180018e8c  nop
0x180018e8d  lea     rcx, [rsp+140h+var_C8]; this
0x180018e92  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180018e97  nop
0x180018e98  lea     rcx, [rsp+140h+var_D0]; this
0x180018e9d  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180018ea2  mov     eax, ebx
0x180018ea4  mov     rcx, [rbp+40h+var_30]
0x180018ea8  xor     rcx, rsp; StackCookie
0x180018eab  call    __security_check_cookie
0x180018eb0  add     rsp, 120h
0x180018eb7  pop     r15
0x180018eb9  pop     rdi
0x180018eba  pop     rsi
0x180018ebb  pop     rbx
0x180018ebc  pop     rbp
0x180018ebd  retn
```
