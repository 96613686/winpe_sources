# MQSigCreateCertificate

- ea: `0x18001b240`
- end: `0x18001b4b1`
- name: `MQSigCreateCertificate`
- size: `625`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180018a90`
- `0x18001cbac`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18001722c`
- `0x180017430`
- `0x18001adf4`
- `0x18001b240`
- `0x18001c344`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x18001b30c`
- `CRYPT32!CertCreateCertificateContext` at `0x18001b30c`
- `KERNEL32!GetLastError` at `0x18001b336`
- `KERNEL32!GetLastError` at `0x18001b336`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MQSigCreateCertificate(
        CMQSigCertificate **a1,
        const struct _CERT_CONTEXT *a2,
        const BYTE *a3,
        DWORD a4)
{
  const struct _CERT_CONTEXT *CertificateContext; // rsi
  __int16 v6; // ax
  unsigned int v7; // eax
  DWORD LastError; // eax
  CMQSigCertificate *v10; // rax
  CMQSigCertificate *v11; // rbx
  __int64 v12; // r9
  int v13; // esi
  unsigned int v14; // eax
  int v15; // [rsp+60h] [rbp-10h] BYREF
  CMQSigCertificate *v16; // [rsp+68h] [rbp-8h] BYREF
  CMQSigCertificate *v17; // [rsp+90h] [rbp+20h] BYREF

  CertificateContext = a2;
  if ( !a1 )
  {
    v6 = 40;
LABEL_6:
    v15 = -1072824314;
    LOWORD(v17) = v6;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v7 = mqwcslen(L"certifct/mqcert");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v7 + 1),
        L"certifct/mqcert",
        2,
        &v17,
        4,
        &v15,
        0,
        0);
    }
    return 3222142982LL;
  }
  *a1 = 0;
  if ( !a3 )
    goto LABEL_14;
  if ( a2 )
  {
    v6 = 50;
    goto LABEL_6;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, a3, a4);
  if ( CertificateContext )
  {
LABEL_14:
    v10 = (CMQSigCertificate *)MmAllocate(0x78u);
    v11 = v10;
    v17 = v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 2) = 1;
      *(_QWORD *)v10 = &CMQSigCertificate::`vftable';
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_DWORD *)v10 + 8) = 0;
      *((_QWORD *)v10 + 6) = 0;
      *((_QWORD *)v10 + 10) = 0;
      *((_QWORD *)v10 + 11) = 0;
      *((_DWORD *)v10 + 24) = 0;
      *((_QWORD *)v10 + 13) = 0;
      *((_QWORD *)v10 + 14) = 0;
      *((_QWORD *)v10 + 5) = 0;
    }
    else
    {
      v11 = 0;
    }
    v16 = v11;
    v12 = ++g_cOpenCert;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_86566bda1ed937851fe3e12247986184_Traceguids, v12);
    v13 = CMQSigCertificate::_Create(v11, CertificateContext);
    if ( v13 < 0 )
    {
      LOWORD(v17) = 70;
      v15 = v13;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v14 = mqwcslen(L"certifct/mqcert");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v14 + 1),
          L"certifct/mqcert",
          2,
          &v17,
          4,
          &v15,
          0,
          0);
      }
    }
    else
    {
      v16 = 0;
      *a1 = v11;
    }
    P<CImpersonate>::~P<CImpersonate>(&v16);
    return (unsigned int)v13;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_86566bda1ed937851fe3e12247986184_Traceguids, LastError);
    }
    return 3222143020LL;
  }
}

```

## disassembly

```asm
0x18001b240  mov     [rsp-18h+arg_8], rbx
0x18001b245  mov     [rsp-18h+arg_10], rsi
0x18001b24a  push    rbp
0x18001b24b  push    r14
0x18001b24d  push    r15
0x18001b24f  mov     rbp, rsp
0x18001b252  sub     rsp, 70h
0x18001b256  mov     rax, r8
0x18001b259  mov     rsi, rdx
0x18001b25c  mov     r14, rcx
0x18001b25f  xor     r15d, r15d
0x18001b262  test    rcx, rcx
0x18001b265  jnz     short loc_18001B26C
0x18001b267  lea     eax, [rcx+28h]
0x18001b26a  jmp     short loc_18001B286
0x18001b26c  mov     [rcx], r15
0x18001b26f  test    rax, rax
0x18001b272  jz      loc_18001B366
0x18001b278  test    rdx, rdx
0x18001b27b  jz      loc_18001B301
0x18001b281  mov     eax, 32h ; '2'
0x18001b286  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b28d  mov     [rbp+var_10], 0C00E0006h
0x18001b294  mov     word ptr [rbp+arg_0], ax
0x18001b298  jz      short loc_18001B2F7
0x18001b29a  lea     rbx, aCertifctMqcert; "certifct/mqcert"
0x18001b2a1  mov     rcx, rbx; wchar_t *
0x18001b2a4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001b2a9  mov     [rsp+70h+var_20], r15
0x18001b2ae  lea     r9d, [rax+1]
0x18001b2b2  mov     [rsp+70h+var_28], r15
0x18001b2b7  lea     rax, [rbp+var_10]
0x18001b2bb  mov     [rsp+70h+var_30], rax
0x18001b2c0  mov     [rsp+70h+var_38], 4
0x18001b2c9  lea     rax, [rbp+arg_0]
0x18001b2cd  mov     [rsp+70h+var_40], rax
0x18001b2d2  mov     [rsp+70h+var_48], 2
0x18001b2db  mov     edx, 1
0x18001b2e0  mov     [rsp+70h+var_50], rbx
0x18001b2e5  add     r9, r9
0x18001b2e8  mov     r8d, edx
0x18001b2eb  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b2f2  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001b2f7  mov     eax, 0C00E0006h
0x18001b2fc  jmp     loc_18001B49B
0x18001b301  mov     r8d, r9d; cbCertEncoded
0x18001b304  mov     rdx, rax; pbCertEncoded
0x18001b307  mov     ecx, 10001h; dwCertEncodingType
0x18001b30c  call    cs:__imp_CertCreateCertificateContext
0x18001b312  mov     rsi, rax
0x18001b315  test    rax, rax
0x18001b318  jnz     short loc_18001B366
0x18001b31a  lea     rax, WPP_GLOBAL_Control
0x18001b321  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b328  cmp     rcx, rax
0x18001b32b  jz      short loc_18001B35C
0x18001b32d  test    byte ptr [rcx+10Ch], 1
0x18001b334  jz      short loc_18001B35C
0x18001b336  call    cs:__imp_GetLastError
0x18001b33c  lea     edx, [rsi+0Ah]
0x18001b33f  mov     r9d, eax
0x18001b342  lea     r8, WPP_86566bda1ed937851fe3e12247986184_Traceguids
0x18001b349  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b350  mov     rcx, [rcx+100h]
0x18001b357  call    WPP_SF_d
0x18001b35c  mov     eax, 0C00E002Ch
0x18001b361  jmp     loc_18001B49B
0x18001b366  mov     ecx, 78h ; 'x'; unsigned __int64
0x18001b36b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001b370  mov     rbx, rax
0x18001b373  mov     [rbp+arg_0], rax
0x18001b377  test    rax, rax
0x18001b37a  jz      short loc_18001B3B7
0x18001b37c  mov     dword ptr [rax+8], 1
0x18001b383  lea     rax, ??_7CMQSigCertificate@@6B@; const CMQSigCertificate::`vftable'
0x18001b38a  mov     [rbx], rax
0x18001b38d  mov     [rbx+10h], r15
0x18001b391  mov     [rbx+18h], r15
0x18001b395  mov     [rbx+20h], r15d
0x18001b399  mov     [rbx+30h], r15
0x18001b39d  mov     [rbx+50h], r15
0x18001b3a1  mov     [rbx+58h], r15
0x18001b3a5  mov     [rbx+60h], r15d
0x18001b3a9  mov     [rbx+68h], r15
0x18001b3ad  mov     [rbx+70h], r15
0x18001b3b1  mov     [rbx+28h], r15
0x18001b3b5  jmp     short loc_18001B3BA
0x18001b3b7  mov     rbx, r15
0x18001b3ba  mov     [rbp+var_8], rbx
0x18001b3be  mov     r9d, cs:?g_cOpenCert@@3KA; ulong g_cOpenCert
0x18001b3c5  inc     r9d
0x18001b3c8  mov     cs:?g_cOpenCert@@3KA, r9d; ulong g_cOpenCert
0x18001b3cf  lea     rax, WPP_GLOBAL_Control
0x18001b3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3dd  cmp     rcx, rax
0x18001b3e0  jz      short loc_18001B403
0x18001b3e2  test    byte ptr [rcx+10Ch], 4
0x18001b3e9  jz      short loc_18001B403
0x18001b3eb  mov     edx, 0Bh
0x18001b3f0  lea     r8, WPP_86566bda1ed937851fe3e12247986184_Traceguids
0x18001b3f7  mov     rcx, [rcx+100h]
0x18001b3fe  call    WPP_SF_d
0x18001b403  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18001b406  mov     rcx, rbx; this
0x18001b409  call    ?_Create@CMQSigCertificate@@AEAAJPEBU_CERT_CONTEXT@@@Z; CMQSigCertificate::_Create(_CERT_CONTEXT const *)
0x18001b40e  mov     esi, eax
0x18001b410  test    eax, eax
0x18001b412  js      short loc_18001B41D
0x18001b414  mov     [rbp+var_8], r15
0x18001b418  mov     [r14], rbx
0x18001b41b  jmp     short loc_18001B490
0x18001b41d  mov     eax, 46h ; 'F'
0x18001b422  mov     word ptr [rbp+arg_0], ax
0x18001b426  mov     [rbp+var_10], esi
0x18001b429  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b430  jz      short loc_18001B490
0x18001b432  lea     rbx, aCertifctMqcert; "certifct/mqcert"
0x18001b439  mov     rcx, rbx; wchar_t *
0x18001b43c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001b441  lea     r9d, [rax+1]
0x18001b445  add     r9, r9
0x18001b448  mov     [rsp+70h+var_20], r15
0x18001b44d  mov     [rsp+70h+var_28], r15
0x18001b452  lea     rax, [rbp+var_10]
0x18001b456  mov     [rsp+70h+var_30], rax
0x18001b45b  mov     [rsp+70h+var_38], 4
0x18001b464  lea     rax, [rbp+arg_0]
0x18001b468  mov     [rsp+70h+var_40], rax
0x18001b46d  mov     [rsp+70h+var_48], 2
0x18001b476  mov     [rsp+70h+var_50], rbx
0x18001b47b  mov     edx, 1
0x18001b480  mov     r8d, edx
0x18001b483  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b48a  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001b48f  nop
0x18001b490  lea     rcx, [rbp+var_8]
0x18001b494  call    ??1?$P@VCImpersonate@@@@QEAA@XZ; P<CImpersonate>::~P<CImpersonate>(void)
0x18001b499  mov     eax, esi
0x18001b49b  lea     r11, [rsp+70h+var_s0]
0x18001b4a0  mov     rbx, [r11+28h]
0x18001b4a4  mov     rsi, [r11+30h]
0x18001b4a8  mov     rsp, r11
0x18001b4ab  pop     r15
0x18001b4ad  pop     r14
0x18001b4af  pop     rbp
0x18001b4b0  retn
```
