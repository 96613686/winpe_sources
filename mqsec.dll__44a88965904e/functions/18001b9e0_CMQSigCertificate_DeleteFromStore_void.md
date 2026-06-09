# CMQSigCertificate::DeleteFromStore(void)

- ea: `0x18001b9e0`
- end: `0x18001bba6`
- name: `?DeleteFromStore@CMQSigCertificate@@UEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(CMQSigCertificate *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004074`
- `0x180017430`
- `0x18001b9e0`

## import_xrefs

- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001ba89`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18001ba89`
- `KERNEL32!GetLastError` at `0x18001baa7`
- `KERNEL32!GetLastError` at `0x18001baa7`

## pseudocode

```c
__int64 __fastcall CMQSigCertificate::DeleteFromStore(CMQSigCertificate *this)
{
  const CERT_CONTEXT *v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // r9
  BOOL v6; // eax
  DWORD LastError; // eax
  CMSMQTrace *v8; // rcx
  DWORD v9; // edi
  unsigned int v10; // eax
  __int16 v11; // ax
  __int16 v12; // [rsp+90h] [rbp+30h] BYREF
  int v13; // [rsp+98h] [rbp+38h] BYREF

  v2 = (const CERT_CONTEXT *)*((_QWORD *)this + 13);
  if ( !v2 )
  {
    v3 = -1072821241;
    v12 = 60;
    v13 = -1072821241;
    if ( !g_pMSMQErrorLoggingTrace )
      return v3;
LABEL_3:
    v4 = mqwcslen(L"certifct/cmqcert") + 1;
    CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2 * v4, L"certifct/cmqcert", 2, &v12, 4, &v13, 0, 0);
    return v3;
  }
  v6 = CertDeleteCertificateFromStore(v2);
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 29) = 1;
  if ( !v6 )
  {
    LastError = GetLastError();
    v8 = g_pMSMQErrorLoggingTrace;
    v9 = LastError;
    if ( !LastError )
      goto LABEL_13;
    v13 = LastError;
    v12 = 65;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v10 = mqwcslen(L"certifct/cmqcert");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        2,
        2LL * (v10 + 1),
        L"certifct/cmqcert",
        2,
        &v12,
        4,
        &v13,
        0,
        0);
      v8 = g_pMSMQErrorLoggingTrace;
    }
    if ( v9 == -2147024891 )
    {
      v11 = 70;
      v3 = -1072824283;
    }
    else
    {
LABEL_13:
      v11 = 80;
      v3 = -1072821146;
    }
    v12 = v11;
    v13 = v3;
    if ( !v8 )
      return v3;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001b9e0  mov     [rsp-28h+arg_10], rbx
0x18001b9e5  push    rbp
0x18001b9e6  push    rsi
0x18001b9e7  push    rdi
0x18001b9e8  push    r14
0x18001b9ea  push    r15
0x18001b9ec  mov     rbp, rsp
0x18001b9ef  sub     rsp, 60h
0x18001b9f3  mov     rdi, rcx
0x18001b9f6  mov     rcx, [rcx+68h]; pCertContext
0x18001b9fa  test    rcx, rcx
0x18001b9fd  jnz     loc_18001BA89
0x18001ba03  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rcx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001ba0a  lea     eax, [rcx+3Ch]
0x18001ba0d  mov     edi, 0C00E0C07h
0x18001ba12  mov     [rbp+arg_0], ax
0x18001ba16  mov     [rbp+arg_8], edi
0x18001ba19  jz      short loc_18001BA82
0x18001ba1b  lea     rsi, aCertifctCmqcer; "certifct/cmqcert"
0x18001ba22  mov     rcx, rsi; wchar_t *
0x18001ba25  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001ba2a  mov     ebx, 1
0x18001ba2f  mov     [rsp+60h+var_10], 0
0x18001ba38  mov     [rsp+60h+var_18], 0
0x18001ba41  lea     r9d, [rbx+rax]
0x18001ba45  lea     rax, [rbp+arg_8]
0x18001ba49  mov     [rsp+60h+var_20], rax
0x18001ba4e  lea     r15d, [rbx+3]
0x18001ba52  lea     r14d, [rbx+1]
0x18001ba56  mov     [rsp+60h+var_28], r15
0x18001ba5b  lea     rcx, [rbp+arg_0]
0x18001ba5f  mov     [rsp+60h+var_30], rcx
0x18001ba64  add     r9, r9
0x18001ba67  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001ba6e  mov     r8d, ebx
0x18001ba71  mov     [rsp+60h+var_38], r14
0x18001ba76  mov     edx, ebx
0x18001ba78  mov     [rsp+60h+var_40], rsi
0x18001ba7d  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001ba82  mov     eax, edi
0x18001ba84  jmp     loc_18001BB92
0x18001ba89  call    cs:__imp_CertDeleteCertificateFromStore
0x18001ba8f  mov     ebx, 1
0x18001ba94  mov     qword ptr [rdi+68h], 0
0x18001ba9c  mov     [rdi+74h], ebx
0x18001ba9f  test    eax, eax
0x18001baa1  jnz     loc_18001BB90
0x18001baa7  call    cs:__imp_GetLastError
0x18001baad  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001bab4  lea     rsi, aCertifctCmqcer; "certifct/cmqcert"
0x18001babb  lea     r15d, [rbx+3]
0x18001babf  mov     edi, eax
0x18001bac1  lea     r14d, [rbx+1]
0x18001bac5  test    eax, eax
0x18001bac7  jz      loc_18001BB84
0x18001bacd  mov     [rbp+arg_8], edi
0x18001bad0  lea     eax, [rbx+40h]
0x18001bad3  mov     [rbp+arg_0], ax
0x18001bad7  test    rcx, rcx
0x18001bada  jz      short loc_18001BB36
0x18001badc  mov     rcx, rsi; wchar_t *
0x18001badf  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001bae4  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001baeb  mov     r8d, r14d
0x18001baee  mov     [rsp+60h+var_10], 0
0x18001baf7  mov     edx, ebx
0x18001baf9  mov     [rsp+60h+var_18], 0
0x18001bb02  lea     r9d, [rbx+rax]
0x18001bb06  lea     rax, [rbp+arg_8]
0x18001bb0a  add     r9, r9
0x18001bb0d  mov     [rsp+60h+var_20], rax
0x18001bb12  lea     rax, [rbp+arg_0]
0x18001bb16  mov     [rsp+60h+var_28], r15
0x18001bb1b  mov     [rsp+60h+var_30], rax
0x18001bb20  mov     [rsp+60h+var_38], r14
0x18001bb25  mov     [rsp+60h+var_40], rsi
0x18001bb2a  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001bb2f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001bb36  cmp     edi, 80070005h
0x18001bb3c  jnz     short loc_18001BB84
0x18001bb3e  mov     eax, 46h ; 'F'
0x18001bb43  mov     edi, 0C00E0025h
0x18001bb48  mov     [rbp+arg_0], ax
0x18001bb4c  mov     [rbp+arg_8], edi
0x18001bb4f  test    rcx, rcx
0x18001bb52  jz      loc_18001BA82
0x18001bb58  mov     rcx, rsi; wchar_t *
0x18001bb5b  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001bb60  mov     [rsp+60h+var_10], 0
0x18001bb69  lea     rcx, [rbp+arg_8]
0x18001bb6d  mov     [rsp+60h+var_18], 0
0x18001bb76  mov     [rsp+60h+var_20], rcx
0x18001bb7b  lea     r9d, [rbx+rax]
0x18001bb7f  jmp     loc_18001BA56
0x18001bb84  mov     eax, 50h ; 'P'
0x18001bb89  mov     edi, 0C00E0C66h
0x18001bb8e  jmp     short loc_18001BB48
0x18001bb90  xor     eax, eax
0x18001bb92  mov     rbx, [rsp+60h+arg_10]
0x18001bb9a  add     rsp, 60h
0x18001bb9e  pop     r15
0x18001bba0  pop     r14
0x18001bba2  pop     rdi
0x18001bba3  pop     rsi
0x18001bba4  pop     rbp
0x18001bba5  retn
```
