# UserSecurityContext::HandleExternalCert(uchar *,ulong)

- ea: `0x180016944`
- end: `0x180016f28`
- name: `?HandleExternalCert@UserSecurityContext@@AEAAJPEAEK@Z`
- size: `1508`
- prototype: `__int64 __fastcall(UserSecurityContext *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800174e0`
- `0x18001b088`

## callees

- `0x180006fdc`
- `0x180007e10`
- `0x1800087f8`
- `0x180012e88`
- `0x180013c74`
- `0x1800161e8`
- `0x180016258`
- `0x1800163ec`
- `0x180016944`
- `0x1800175f0`
- `0x180021010`
- `0x180023c42`
- `0x180023ca0`

## import_xrefs

- `msvcrt!free` at `0x180016a26`
- `msvcrt!free` at `0x180016ac8`
- `msvcrt!free` at `0x180016c04`
- `msvcrt!free` at `0x180016c3a`
- `msvcrt!free` at `0x180016c9a`
- `msvcrt!free` at `0x180016cd0`
- `msvcrt!free` at `0x180016dbc`
- `msvcrt!free` at `0x180016df7`
- `msvcrt!free` at `0x180016e11`
- `msvcrt!free` at `0x180016e4c`
- `msvcrt!free` at `0x180016ed3`
- `msvcrt!free` at `0x180016ef8`
- `msvcrt!free` at `0x180016a26`
- `msvcrt!free` at `0x180016ac8`
- `msvcrt!free` at `0x180016c04`
- `msvcrt!free` at `0x180016c3a`
- `msvcrt!free` at `0x180016c9a`
- `msvcrt!free` at `0x180016cd0`
- `msvcrt!free` at `0x180016dbc`
- `msvcrt!free` at `0x180016df7`
- `msvcrt!free` at `0x180016e11`
- `msvcrt!free` at `0x180016e4c`
- `msvcrt!free` at `0x180016ed3`
- `msvcrt!free` at `0x180016ef8`
- `CRYPT32!CertOpenSystemStoreW` at `0x180016a3e`
- `CRYPT32!CertOpenSystemStoreW` at `0x180016a3e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016b9d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016bdd`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016b9d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016bdd`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180016ae3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180016b65`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180016ae3`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180016b65`
- `ADVAPI32!CryptAcquireContextW` at `0x1800169b3`
- `ADVAPI32!CryptAcquireContextW` at `0x180016d61`
- `ADVAPI32!CryptAcquireContextW` at `0x1800169b3`
- `ADVAPI32!CryptAcquireContextW` at `0x180016d61`
- `ADVAPI32!CryptReleaseContext` at `0x180016a19`
- `ADVAPI32!CryptReleaseContext` at `0x180016abb`
- `ADVAPI32!CryptReleaseContext` at `0x180016c2d`
- `ADVAPI32!CryptReleaseContext` at `0x180016cc3`
- `ADVAPI32!CryptReleaseContext` at `0x180016de5`
- `ADVAPI32!CryptReleaseContext` at `0x180016e3a`
- `ADVAPI32!CryptReleaseContext` at `0x180016ec6`
- `ADVAPI32!CryptReleaseContext` at `0x180016a19`
- `ADVAPI32!CryptReleaseContext` at `0x180016abb`
- `ADVAPI32!CryptReleaseContext` at `0x180016c2d`
- `ADVAPI32!CryptReleaseContext` at `0x180016cc3`
- `ADVAPI32!CryptReleaseContext` at `0x180016de5`
- `ADVAPI32!CryptReleaseContext` at `0x180016e3a`
- `ADVAPI32!CryptReleaseContext` at `0x180016ec6`
- `KERNEL32!GetLastError` at `0x1800169bd`
- `KERNEL32!GetLastError` at `0x180016a55`
- `KERNEL32!GetLastError` at `0x180016bab`
- `KERNEL32!GetLastError` at `0x180016d6f`
- `KERNEL32!GetLastError` at `0x180016e5a`
- `KERNEL32!GetLastError` at `0x1800169bd`
- `KERNEL32!GetLastError` at `0x180016a55`
- `KERNEL32!GetLastError` at `0x180016bab`
- `KERNEL32!GetLastError` at `0x180016d6f`
- `KERNEL32!GetLastError` at `0x180016e5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UserSecurityContext::HandleExternalCert(
        UserSecurityContext *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  HCERTSTORE v6; // rax
  void *v7; // rbx
  DWORD v8; // eax
  int v10; // r12d
  const CERT_CONTEXT *v11; // rdi
  const CERT_CONTEXT *v12; // rsi
  DWORD cbCertEncoded; // r15d
  void *v14; // rbx
  DWORD v15; // eax
  const wchar_t **v16; // r15
  unsigned int v17; // eax
  RTSecurityContextBase *v18; // r13
  unsigned int v19; // esi
  wchar_t *v20; // rdi
  DWORD v21; // eax
  DWORD v22; // eax
  HCRYPTPROV phProv; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-C8h] BYREF
  const CERT_CONTEXT *v25; // [rsp+40h] [rbp-C0h] BYREF
  HCERTSTORE v26; // [rsp+48h] [rbp-B8h] BYREF
  void *Buf1; // [rsp+50h] [rbp-B0h]
  RTSecurityContextBase *v28; // [rsp+58h] [rbp-A8h]
  wchar_t *v29; // [rsp+60h] [rbp-A0h]
  _BYTE pvData[256]; // [rsp+70h] [rbp-90h] BYREF

  Buf1 = a2;
  v28 = this;
  v29 = 0;
  if ( !a3 || !a2 )
  {
    v5 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"rt/rtsecctx", 0x1F4u);
    free(0);
    return v5;
  }
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, LastError);
    v5 = -1072824281;
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtsecctx", 0x1F9u);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
LABEL_9:
    phProv = 0;
    free(0);
    return v5;
  }
  v6 = CertOpenSystemStoreW(phProv, L"My");
  v7 = v6;
  v26 = v6;
  if ( v6 )
  {
    v10 = 0;
    v25 = 0;
    v11 = CertEnumCertificatesInStore(v6, 0);
    v25 = v11;
    v12 = v11;
    while ( 1 )
    {
      if ( !v12 )
      {
        v22 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v22);
        v5 = -1072824276;
        LogMsgHR(-1072824276, (wchar_t *)L"rt/rtsecctx", 0x208u);
        CPCCertContext::~CPCCertContext((CPCCertContext *)&v25);
        CHCertStore::~CHCertStore((CHCertStore *)&v26);
        if ( phProv )
          CryptReleaseContext(phProv, 0);
        goto LABEL_9;
      }
      if ( v10 )
        break;
      cbCertEncoded = v12->cbCertEncoded;
      if ( a3 == cbCertEncoded && !memcmp_0(Buf1, v12->pbCertEncoded, cbCertEncoded) )
      {
        v10 = 1;
      }
      else
      {
        v10 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_4429bf9cee813cde9fee94052f370384_Traceguids,
            a3,
            cbCertEncoded);
        v11 = CertEnumCertificatesInStore(v7, v12);
        v25 = v11;
        v12 = v11;
      }
    }
    pcbData = 256;
    v14 = 0;
    Buf1 = 0;
    if ( CertGetCertificateContextProperty(v11, 2u, pvData, &pcbData) )
    {
      v16 = (const wchar_t **)pvData;
LABEL_41:
      v17 = mqwcslen(v16[1]);
      v18 = v28;
      RTSecurityContextBase::AllocateAndCopyProviderName(v28, v16[1], v17 + 1);
      *((_DWORD *)v18 + 14) = *((_DWORD *)v16 + 4);
      *((_DWORD *)v18 + 16) = *((_DWORD *)v16 + 10);
      v19 = mqwcslen(*v16) + 1;
      v20 = (wchar_t *)MmAllocate(saturated_mul(v19, 2u));
      v29 = v20;
      StringCchCopyW(v20, v19, *v16);
      if ( CryptAcquireContextW((HCRYPTPROV *)v18 + 9, v20, *((LPCWSTR *)v18 + 3), *((_DWORD *)v18 + 14), 0) )
      {
        RTSecurityContextBase::SetDefaultProviderHelper(v18);
        free(v14);
        CPCCertContext::~CPCCertContext((CPCCertContext *)&v25);
        CHCertStore::~CHCertStore((CHCertStore *)&v26);
        if ( phProv )
          CryptReleaseContext(phProv, 0);
        phProv = 0;
        free(v20);
        return 0;
      }
      else
      {
        v21 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v21);
        LogMsgHR(-1072824272, (wchar_t *)L"rt/rtsecctx", 0x226u);
        free(v14);
        CPCCertContext::~CPCCertContext((CPCCertContext *)&v25);
        CHCertStore::~CHCertStore((CHCertStore *)&v26);
        if ( phProv )
          CryptReleaseContext(phProv, 0);
        phProv = 0;
        free(v20);
        return 3222143024LL;
      }
    }
    v15 = GetLastError();
    if ( v15 == 234 )
    {
      v14 = MmAllocate(pcbData);
      Buf1 = v14;
      if ( !CertGetCertificateContextProperty(v11, 2u, v14, &pcbData) )
      {
        LogMsgHR(-1072824271, (wchar_t *)L"rt/rtsecctx", 0x212u);
        free(v14);
        CPCCertContext::~CPCCertContext((CPCCertContext *)&v25);
        CHCertStore::~CHCertStore((CHCertStore *)&v26);
        if ( phProv )
          CryptReleaseContext(phProv, 0);
        goto LABEL_16;
      }
      v16 = (const wchar_t **)v14;
      goto LABEL_41;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 22, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v15);
    LogMsgHR(-1072824271, (wchar_t *)L"rt/rtsecctx", 0x21Cu);
    free(0);
    CPCCertContext::~CPCCertContext((CPCCertContext *)&v25);
    CHCertStore::~CHCertStore((CHCertStore *)&v26);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
  }
  else
  {
    v8 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4429bf9cee813cde9fee94052f370384_Traceguids, v8);
    LogMsgHR(-1072824271, (wchar_t *)L"rt/rtsecctx", 0x1FEu);
    CHCertStore::~CHCertStore((CHCertStore *)&v26);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
  }
LABEL_16:
  phProv = 0;
  free(0);
  return 3222143025LL;
}

```

## disassembly

```asm
0x180016944  mov     [rsp-8+arg_8], rbx
0x180016949  push    rbp
0x18001694a  push    rsi
0x18001694b  push    rdi
0x18001694c  push    r12
0x18001694e  push    r13
0x180016950  push    r14
0x180016952  push    r15
0x180016954  lea     rbp, [rsp-80h]
0x180016959  sub     rsp, 180h
0x180016960  mov     rax, cs:__security_cookie
0x180016967  xor     rax, rsp
0x18001696a  mov     [rbp+0B0h+var_40], rax
0x18001696e  mov     r13d, r8d
0x180016971  mov     rax, rdx
0x180016974  mov     [rsp+1B0h+Buf1], rdx
0x180016979  mov     [rsp+1B0h+var_158], rcx
0x18001697e  xor     r15d, r15d
0x180016981  mov     [rsp+1B0h+var_150], r15
0x180016986  test    r8d, r8d
0x180016989  jz      loc_180016EDC
0x18001698f  test    rax, rax
0x180016992  jz      loc_180016EDC
0x180016998  mov     [rsp+1B0h+phProv], r15
0x18001699d  mov     [rsp+1B0h+dwFlags], 0F0000000h; dwFlags
0x1800169a5  lea     r9d, [r15+18h]; dwProvType
0x1800169a9  xor     r8d, r8d; szProvider
0x1800169ac  xor     edx, edx; szContainer
0x1800169ae  lea     rcx, [rsp+1B0h+phProv]; phProv
0x1800169b3  call    cs:__imp_CryptAcquireContextW
0x1800169b9  test    eax, eax
0x1800169bb  jnz     short loc_180016A32
0x1800169bd  call    cs:__imp_GetLastError
0x1800169c3  lea     r14, WPP_GLOBAL_Control
0x1800169ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169d1  cmp     rcx, r14
0x1800169d4  jz      short loc_1800169F3
0x1800169d6  test    byte ptr [rcx+1Ch], 1
0x1800169da  jz      short loc_1800169F3
0x1800169dc  lea     edx, [r15+12h]
0x1800169e0  mov     r9d, eax
0x1800169e3  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x1800169ea  mov     rcx, [rcx+10h]
0x1800169ee  call    WPP_SF_d
0x1800169f3  mov     r8d, 1F9h; unsigned __int16
0x1800169f9  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016a00  mov     ebx, 0C00E0027h
0x180016a05  mov     ecx, ebx; int
0x180016a07  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016a0c  nop
0x180016a0d  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016a12  test    rcx, rcx
0x180016a15  jz      short loc_180016A1F
0x180016a17  xor     edx, edx; dwFlags
0x180016a19  call    cs:__imp_CryptReleaseContext
0x180016a1f  mov     [rsp+1B0h+phProv], r15
0x180016a24  xor     ecx, ecx; Block
0x180016a26  call    cs:__imp_free
0x180016a2c  nop
0x180016a2d  jmp     loc_180016EFF
0x180016a32  lea     rdx, szSubsystemProtocol; "My"
0x180016a39  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016a3e  call    cs:__imp_CertOpenSystemStoreW
0x180016a44  mov     rbx, rax
0x180016a47  mov     [rsp+1B0h+var_168], rax
0x180016a4c  test    rax, rax
0x180016a4f  jnz     loc_180016AD6
0x180016a55  call    cs:__imp_GetLastError
0x180016a5b  lea     r14, WPP_GLOBAL_Control
0x180016a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a69  cmp     rcx, r14
0x180016a6c  jz      short loc_180016A8A
0x180016a6e  test    byte ptr [rcx+1Ch], 1
0x180016a72  jz      short loc_180016A8A
0x180016a74  lea     edx, [rbx+13h]
0x180016a77  mov     r9d, eax
0x180016a7a  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016a81  mov     rcx, [rcx+10h]
0x180016a85  call    WPP_SF_d
0x180016a8a  mov     r8d, 1FEh; unsigned __int16
0x180016a90  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016a97  mov     edi, 0C00E0031h
0x180016a9c  mov     ecx, edi; int
0x180016a9e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016aa3  nop
0x180016aa4  lea     rcx, [rsp+1B0h+var_168]; this
0x180016aa9  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180016aae  nop
0x180016aaf  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016ab4  test    rcx, rcx
0x180016ab7  jz      short loc_180016AC1
0x180016ab9  xor     edx, edx; dwFlags
0x180016abb  call    cs:__imp_CryptReleaseContext
0x180016ac1  mov     [rsp+1B0h+phProv], r15
0x180016ac6  xor     ecx, ecx; Block
0x180016ac8  call    cs:__imp_free
0x180016ace  nop
0x180016acf  mov     eax, edi
0x180016ad1  jmp     loc_180016F01
0x180016ad6  mov     r12d, r15d
0x180016ad9  mov     [rsp+1B0h+var_170], r15
0x180016ade  xor     edx, edx; pPrevCertContext
0x180016ae0  mov     rcx, rbx; hCertStore
0x180016ae3  call    cs:__imp_CertEnumCertificatesInStore
0x180016ae9  mov     rdi, rax
0x180016aec  mov     [rsp+1B0h+var_170], rax
0x180016af1  mov     rsi, rax
0x180016af4  lea     r14, WPP_GLOBAL_Control
0x180016afb  test    rsi, rsi
0x180016afe  jz      loc_180016E5A
0x180016b04  test    r12d, r12d
0x180016b07  jnz     short loc_180016B7B
0x180016b09  mov     r15d, [rsi+10h]
0x180016b0d  cmp     r13d, r15d
0x180016b10  jnz     short loc_180016B2D
0x180016b12  mov     r8d, r15d; Size
0x180016b15  mov     rdx, [rsi+8]; Buf2
0x180016b19  mov     rcx, [rsp+1B0h+Buf1]; Buf1
0x180016b1e  call    memcmp_0
0x180016b23  test    eax, eax
0x180016b25  jnz     short loc_180016B2D
0x180016b27  lea     r12d, [rax+1]
0x180016b2b  jmp     short loc_180016B76
0x180016b2d  xor     r12d, r12d
0x180016b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b37  cmp     rcx, r14
0x180016b3a  jz      short loc_180016B5F
0x180016b3c  test    byte ptr [rcx+1Ch], 2
0x180016b40  jz      short loc_180016B5F
0x180016b42  lea     edx, [r12+14h]
0x180016b47  mov     [rsp+1B0h+dwFlags], r15d
0x180016b4c  mov     r9d, r13d
0x180016b4f  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016b56  mov     rcx, [rcx+10h]
0x180016b5a  call    WPP_SF_dd
0x180016b5f  mov     rdx, rsi; pPrevCertContext
0x180016b62  mov     rcx, rbx; hCertStore
0x180016b65  call    cs:__imp_CertEnumCertificatesInStore
0x180016b6b  mov     rdi, rax
0x180016b6e  mov     [rsp+1B0h+var_170], rax
0x180016b73  mov     rsi, rax
0x180016b76  xor     r15d, r15d
0x180016b79  jmp     short loc_180016AFB
0x180016b7b  mov     [rsp+1B0h+pcbData], 100h
0x180016b83  mov     rbx, r15
0x180016b86  mov     [rsp+1B0h+Buf1], rbx
0x180016b8b  lea     r9, [rsp+1B0h+pcbData]; pcbData
0x180016b90  lea     r8, [rsp+1B0h+pvData]; pvData
0x180016b95  mov     edx, 2; dwPropId
0x180016b9a  mov     rcx, rdi; pCertContext
0x180016b9d  call    cs:__imp_CertGetCertificateContextProperty
0x180016ba3  test    eax, eax
0x180016ba5  jnz     loc_180016CDC
0x180016bab  call    cs:__imp_GetLastError
0x180016bb1  cmp     eax, 0EAh
0x180016bb6  jnz     loc_180016C4E
0x180016bbc  mov     ecx, [rsp+1B0h+pcbData]; unsigned __int64
0x180016bc0  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016bc5  mov     rbx, rax
0x180016bc8  mov     [rsp+1B0h+Buf1], rax
0x180016bcd  lea     r9, [rsp+1B0h+pcbData]; pcbData
0x180016bd2  mov     r8, rax; pvData
0x180016bd5  mov     edx, 2; dwPropId
0x180016bda  mov     rcx, rdi; pCertContext
0x180016bdd  call    cs:__imp_CertGetCertificateContextProperty
0x180016be3  test    eax, eax
0x180016be5  jnz     short loc_180016C46
0x180016be7  mov     r8d, 212h; unsigned __int16
0x180016bed  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016bf4  mov     edi, 0C00E0031h
0x180016bf9  mov     ecx, edi; int
0x180016bfb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016c00  nop
0x180016c01  mov     rcx, rbx; Block
0x180016c04  call    cs:__imp_free
0x180016c0a  nop
0x180016c0b  lea     rcx, [rsp+1B0h+var_170]; this
0x180016c10  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180016c15  nop
0x180016c16  lea     rcx, [rsp+1B0h+var_168]; this
0x180016c1b  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180016c20  nop
0x180016c21  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016c26  test    rcx, rcx
0x180016c29  jz      short loc_180016C33
0x180016c2b  xor     edx, edx; dwFlags
0x180016c2d  call    cs:__imp_CryptReleaseContext
0x180016c33  mov     [rsp+1B0h+phProv], r15
0x180016c38  xor     ecx, ecx; Block
0x180016c3a  call    cs:__imp_free
0x180016c40  nop
0x180016c41  jmp     loc_180016ACF
0x180016c46  mov     r15, rbx
0x180016c49  jmp     loc_180016CE1
0x180016c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c55  cmp     rcx, r14
0x180016c58  jz      short loc_180016C7E
0x180016c5a  test    byte ptr [rcx+10Ch], 1
0x180016c61  jz      short loc_180016C7E
0x180016c63  mov     edx, 16h
0x180016c68  mov     r9d, eax
0x180016c6b  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016c72  mov     rcx, [rcx+100h]
0x180016c79  call    WPP_SF_d
0x180016c7e  mov     r8d, 21Ch; unsigned __int16
0x180016c84  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016c8b  mov     edi, 0C00E0031h
0x180016c90  mov     ecx, edi; int
0x180016c92  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016c97  nop
0x180016c98  xor     ecx, ecx; Block
0x180016c9a  call    cs:__imp_free
0x180016ca0  nop
0x180016ca1  lea     rcx, [rsp+1B0h+var_170]; this
0x180016ca6  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180016cab  nop
0x180016cac  lea     rcx, [rsp+1B0h+var_168]; this
0x180016cb1  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180016cb6  nop
0x180016cb7  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016cbc  test    rcx, rcx
0x180016cbf  jz      short loc_180016CC9
0x180016cc1  xor     edx, edx; dwFlags
0x180016cc3  call    cs:__imp_CryptReleaseContext
0x180016cc9  mov     [rsp+1B0h+phProv], r15
0x180016cce  xor     ecx, ecx; Block
0x180016cd0  call    cs:__imp_free
0x180016cd6  nop
0x180016cd7  jmp     loc_180016ACF
0x180016cdc  lea     r15, [rsp+1B0h+pvData]
0x180016ce1  mov     rcx, [r15+8]; wchar_t *
0x180016ce5  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180016cea  lea     r8d, [rax+1]; unsigned int
0x180016cee  mov     rdx, [r15+8]; wchar_t *
0x180016cf2  mov     r13, [rsp+1B0h+var_158]
0x180016cf7  mov     rcx, r13; this
0x180016cfa  call    ?AllocateAndCopyProviderName@RTSecurityContextBase@@IEAAXPEB_WK@Z; RTSecurityContextBase::AllocateAndCopyProviderName(wchar_t const *,ulong)
0x180016cff  mov     ecx, [r15+10h]
0x180016d03  mov     [r13+38h], ecx
0x180016d07  mov     ecx, [r15+28h]
0x180016d0b  mov     [r13+40h], ecx
0x180016d0f  mov     rcx, [r15]; wchar_t *
0x180016d12  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180016d17  lea     esi, [rax+1]
0x180016d1a  mov     eax, 2
0x180016d1f  mul     rsi
0x180016d22  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016d29  cmovb   rax, rcx
0x180016d2d  mov     rcx, rax; unsigned __int64
0x180016d30  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016d35  mov     rdi, rax
0x180016d38  mov     [rsp+1B0h+var_150], rax
0x180016d3d  mov     r8, [r15]; wchar_t *
0x180016d40  mov     edx, esi; unsigned __int64
0x180016d42  mov     rcx, rax; wchar_t *
0x180016d45  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180016d4a  lea     rcx, [r13+48h]; phProv
0x180016d4e  mov     [rsp+1B0h+dwFlags], 0; dwFlags
0x180016d56  mov     r9d, [r13+38h]; dwProvType
0x180016d5a  mov     r8, [r13+18h]; szProvider
0x180016d5e  mov     rdx, rdi; szContainer
0x180016d61  call    cs:__imp_CryptAcquireContextW
0x180016d67  test    eax, eax
0x180016d69  jnz     loc_180016E05
0x180016d6f  call    cs:__imp_GetLastError
0x180016d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d7c  cmp     rcx, r14
0x180016d7f  jz      short loc_180016D9F
0x180016d81  test    byte ptr [rcx+1Ch], 1
0x180016d85  jz      short loc_180016D9F
0x180016d87  mov     edx, 17h
0x180016d8c  mov     r9d, eax
0x180016d8f  lea     r8, WPP_4429bf9cee813cde9fee94052f370384_Traceguids
0x180016d96  mov     rcx, [rcx+10h]
0x180016d9a  call    WPP_SF_d
0x180016d9f  mov     r8d, 226h; unsigned __int16
0x180016da5  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x180016dac  mov     esi, 0C00E0030h
0x180016db1  mov     ecx, esi; int
0x180016db3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180016db8  nop
0x180016db9  mov     rcx, rbx; Block
0x180016dbc  call    cs:__imp_free
0x180016dc2  nop
0x180016dc3  lea     rcx, [rsp+1B0h+var_170]; this
0x180016dc8  call    ??1CPCCertContext@@QEAA@XZ; CPCCertContext::~CPCCertContext(void)
0x180016dcd  nop
0x180016dce  lea     rcx, [rsp+1B0h+var_168]; this
0x180016dd3  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x180016dd8  nop
0x180016dd9  mov     rcx, [rsp+1B0h+phProv]; hProv
0x180016dde  test    rcx, rcx
0x180016de1  jz      short loc_180016DEB
0x180016de3  xor     edx, edx; dwFlags
0x180016de5  call    cs:__imp_CryptReleaseContext
0x180016deb  mov     [rsp+1B0h+phProv], 0
0x180016df4  mov     rcx, rdi; Block
0x180016df7  call    cs:__imp_free
0x180016dfd  nop
0x180016dfe  mov     eax, esi
  ... truncated ...
```
