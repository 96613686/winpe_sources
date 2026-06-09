# MQSigCloneCertFromSysStore

- ea: `0x18001b060`
- end: `0x18001b231`
- name: `MQSigCloneCertFromSysStore`
- size: `465`
- prototype: `__int64 __fastcall(struct CMQSigCertificate **, LPCWSTR szSubsystemProtocol, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004074`
- `0x1800049ec`
- `0x180005d68`
- `0x180017430`
- `0x18001b060`
- `0x18001cbac`
- `0x18001cd70`

## import_xrefs

- `CRYPT32!CertOpenSystemStoreW` at `0x18001b128`
- `CRYPT32!CertOpenSystemStoreW` at `0x18001b128`
- `KERNEL32!GetLastError` at `0x18001b137`
- `KERNEL32!GetLastError` at `0x18001b137`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MQSigCloneCertFromSysStore(struct CMQSigCertificate **a1, LPCWSTR szSubsystemProtocol, int a3)
{
  int v6; // ebx
  unsigned int v7; // eax
  HCERTSTORE v8; // rax
  char LastError; // al
  unsigned int v10; // eax
  HCERTSTORE v12[2]; // [rsp+60h] [rbp-10h] BYREF
  HCRYPTPROV_LEGACY hProv; // [rsp+90h] [rbp+20h] BYREF
  int v14; // [rsp+A8h] [rbp+38h] BYREF

  *a1 = 0;
  hProv = 0;
  if ( (unsigned int)_CryptAcquireVerContext(&hProv) )
  {
    v8 = CertOpenSystemStoreW(hProv, szSubsystemProtocol);
    v12[0] = v8;
    if ( v8 )
    {
      v6 = _CloneCertFromStore(a1, v8, a3);
      if ( v6 < 0 )
      {
        LOWORD(hProv) = 140;
        v14 = v6;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v10 = mqwcslen(L"certifct/mqcert");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v10 + 1),
            L"certifct/mqcert",
            2,
            &hProv,
            4,
            &v14,
            0,
            0);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), LastError);
      v6 = -1072821223;
    }
    CHCertStore::~CHCertStore((CHCertStore *)v12);
  }
  else
  {
    LOWORD(hProv) = 120;
    v6 = -1072821148;
    v14 = -1072821148;
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
        &hProv,
        4,
        &v14,
        0,
        0);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b060  mov     [rsp-18h+arg_8], rbx
0x18001b065  push    rbp
0x18001b066  push    rsi
0x18001b067  push    rdi
0x18001b068  mov     rbp, rsp
0x18001b06b  sub     rsp, 70h
0x18001b06f  mov     esi, r8d
0x18001b072  mov     rbx, rdx
0x18001b075  mov     rdi, rcx
0x18001b078  mov     qword ptr [rcx], 0
0x18001b07f  mov     [rbp+hProv], 0
0x18001b087  lea     rcx, [rbp+hProv]; unsigned __int64 *
0x18001b08b  call    ?_CryptAcquireVerContext@@YAHPEA_K@Z; _CryptAcquireVerContext(unsigned __int64 *)
0x18001b090  test    eax, eax
0x18001b092  jnz     loc_18001B121
0x18001b098  mov     eax, 78h ; 'x'
0x18001b09d  mov     word ptr [rbp+hProv], ax
0x18001b0a1  mov     ebx, 0C00E0C64h
0x18001b0a6  mov     [rbp+arg_18], ebx
0x18001b0a9  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b0b1  jz      loc_18001B21F
0x18001b0b7  lea     rdi, aCertifctMqcert; "certifct/mqcert"
0x18001b0be  mov     rcx, rdi; wchar_t *
0x18001b0c1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001b0c6  mov     edx, 1
0x18001b0cb  lea     r9d, [rdx+rax]
0x18001b0cf  add     r9, r9
0x18001b0d2  mov     [rsp+70h+var_20], 0
0x18001b0db  mov     [rsp+70h+var_28], 0
0x18001b0e4  lea     rax, [rbp+arg_18]
0x18001b0e8  mov     [rsp+70h+var_30], rax
0x18001b0ed  mov     [rsp+70h+var_38], 4
0x18001b0f6  lea     rcx, [rbp+hProv]
0x18001b0fa  mov     [rsp+70h+var_40], rcx
0x18001b0ff  mov     [rsp+70h+var_48], 2
0x18001b108  mov     qword ptr [rsp+70h+var_50], rdi
0x18001b10d  mov     r8d, edx
0x18001b110  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b117  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001b11c  jmp     loc_18001B21F
0x18001b121  mov     rdx, rbx; szSubsystemProtocol
0x18001b124  mov     rcx, [rbp+hProv]; hProv
0x18001b128  call    cs:__imp_CertOpenSystemStoreW
0x18001b12e  mov     [rbp+var_10], rax
0x18001b132  test    rax, rax
0x18001b135  jnz     short loc_18001B186
0x18001b137  call    cs:__imp_GetLastError
0x18001b13d  lea     rdx, WPP_GLOBAL_Control
0x18001b144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b14b  cmp     rcx, rdx
0x18001b14e  jz      short loc_18001B17C
0x18001b150  mov     edx, 1
0x18001b155  test    [rcx+10Ch], dl
0x18001b15b  jz      short loc_18001B17C
0x18001b15d  mov     edx, 0Dh
0x18001b162  mov     dword ptr [rsp+70h+var_50], eax; char
0x18001b166  mov     r9, rbx
0x18001b169  lea     r8, WPP_86566bda1ed937851fe3e12247986184_Traceguids
0x18001b170  mov     rcx, [rcx+100h]; LoggerHandle
0x18001b177  call    WPP_SF_Sd
0x18001b17c  mov     ebx, 0C00E0C19h
0x18001b181  jmp     loc_18001B216
0x18001b186  mov     r8d, esi; int
0x18001b189  mov     rdx, rax; void *
0x18001b18c  mov     rcx, rdi; struct CMQSigCertificate **
0x18001b18f  call    ?_CloneCertFromStore@@YAJPEAPEAVCMQSigCertificate@@PEAXJ@Z; _CloneCertFromStore(CMQSigCertificate * *,void *,long)
0x18001b194  mov     ebx, eax
0x18001b196  test    eax, eax
0x18001b198  jns     short loc_18001B216
0x18001b19a  mov     eax, 8Ch
0x18001b19f  mov     word ptr [rbp+hProv], ax
0x18001b1a3  mov     [rbp+arg_18], ebx
0x18001b1a6  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b1ae  jz      short loc_18001B216
0x18001b1b0  lea     rdi, aCertifctMqcert; "certifct/mqcert"
0x18001b1b7  mov     rcx, rdi; wchar_t *
0x18001b1ba  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001b1bf  mov     edx, 1
0x18001b1c4  lea     r9d, [rdx+rax]
0x18001b1c8  add     r9, r9
0x18001b1cb  mov     [rsp+70h+var_20], 0
0x18001b1d4  mov     [rsp+70h+var_28], 0
0x18001b1dd  lea     rax, [rbp+arg_18]
0x18001b1e1  mov     [rsp+70h+var_30], rax
0x18001b1e6  mov     [rsp+70h+var_38], 4
0x18001b1ef  lea     rax, [rbp+hProv]
0x18001b1f3  mov     [rsp+70h+var_40], rax
0x18001b1f8  mov     [rsp+70h+var_48], 2
0x18001b201  mov     qword ptr [rsp+70h+var_50], rdi
0x18001b206  mov     r8d, edx
0x18001b209  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001b210  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001b215  nop
0x18001b216  lea     rcx, [rbp+var_10]; this
0x18001b21a  call    ??1CHCertStore@@QEAA@XZ; CHCertStore::~CHCertStore(void)
0x18001b21f  mov     eax, ebx
0x18001b221  mov     rbx, [rsp+70h+arg_8]
0x18001b229  add     rsp, 70h
0x18001b22d  pop     rdi
0x18001b22e  pop     rsi
0x18001b22f  pop     rbp
0x18001b230  retn
```
