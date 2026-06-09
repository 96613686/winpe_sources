# ServerAcceptSecCtx(int,void * *,uchar *,ulong *,uchar *,ulong)

- ea: `0x180018780`
- end: `0x180018a6e`
- name: `?ServerAcceptSecCtx@@YAJHPEAPEAXPEAEPEAK1K@Z`
- size: `750`
- prototype: `__int64 __fastcall(int, void **, unsigned __int8 *, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004074`
- `0x18001722c`
- `0x180017430`
- `0x180018780`

## import_xrefs

- `msvcrt!free` at `0x1800189cd`
- `msvcrt!free` at `0x1800189cd`
- `Secur32!AcceptSecurityContext` at `0x180018929`
- `Secur32!AcceptSecurityContext` at `0x180018929`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServerAcceptSecCtx(
        int a1,
        struct _SecHandle **a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  struct _SecHandle *phNewContext; // rsi
  struct _SecHandle *v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int16 v16; // [rsp+68h] [rbp-39h] BYREF
  int v17; // [rsp+70h] [rbp-31h] BYREF
  unsigned int pfContextAttr; // [rsp+78h] [rbp-29h] BYREF
  __int128 v19; // [rsp+80h] [rbp-21h] BYREF
  _DWORD v20[2]; // [rsp+90h] [rbp-11h] BYREF
  unsigned __int8 *v21; // [rsp+98h] [rbp-9h]
  struct _SecBufferDesc pOutput; // [rsp+A0h] [rbp-1h] BYREF
  _SecBufferDesc pInput; // [rsp+B0h] [rbp+Fh] BYREF

  if ( !g_fInitServerCredHandle )
  {
    v16 = 170;
    v8 = -1072822997;
    v17 = -1072822997;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v9 = mqwcslen(L"srvauthn/sspi.cpp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v9 + 1),
        L"srvauthn/sspi.cpp",
        2,
        &v16,
        4,
        &v17,
        0,
        0);
    }
    return v8;
  }
  if ( *a4 >= g_PackageInfo->cbMaxToken )
  {
    v19 = 0;
    pfContextAttr = 0;
    pInput.cBuffers = 1;
    pInput.pBuffers = (PSecBuffer)v20;
    pInput.ulVersion = 0;
    v20[1] = 2;
    v20[0] = a6;
    v21 = a5;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)&v19;
    pOutput.ulVersion = 0;
    DWORD1(v19) = 2;
    LODWORD(v19) = g_PackageInfo->cbMaxToken;
    *((_QWORD *)&v19 + 1) = a3;
    if ( a1 )
      phNewContext = (struct _SecHandle *)MmAllocate(0x10u);
    else
      phNewContext = *a2;
    v13 = 0;
    if ( !a1 )
      v13 = phNewContext;
    v8 = AcceptSecurityContext(&g_hServerCred, v13, &pInput, 0, 0x10u, phNewContext, &pOutput, &pfContextAttr, 0);
    if ( (v8 & 0x80000000) == 0 )
    {
      if ( !v8 || v8 == 590610 )
      {
        *a4 = v19;
        if ( a1 )
          *a2 = phNewContext;
        return v8;
      }
    }
    else
    {
      v16 = 175;
      v17 = v8;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v14 = mqwcslen(L"srvauthn/sspi.cpp");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v14 + 1),
          L"srvauthn/sspi.cpp",
          2,
          &v16,
          4,
          &v17,
          0,
          0);
      }
    }
    v8 = -1072822997;
    if ( a1 )
      free(phNewContext);
    v16 = 180;
    v17 = -1072822997;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v15 = mqwcslen(L"srvauthn/sspi.cpp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v15 + 1),
        L"srvauthn/sspi.cpp",
        2,
        &v16,
        4,
        &v17,
        0,
        0);
    }
    return v8;
  }
  v16 = 171;
  v17 = -2147024809;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v10 = mqwcslen(L"srvauthn/sspi.cpp");
    CMSMQTrace::MSMQTraceEvent(
      g_pMSMQErrorLoggingTrace,
      1,
      1,
      2LL * (v10 + 1),
      L"srvauthn/sspi.cpp",
      2,
      &v16,
      4,
      &v17,
      0,
      0);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180018780  mov     rax, rsp
0x180018783  mov     [rax+8], rbx
0x180018787  mov     [rax+10h], rsi
0x18001878b  mov     [rax+20h], r9
0x18001878f  push    rbp
0x180018790  push    rdi
0x180018791  push    r12
0x180018793  push    r13
0x180018795  push    r14
0x180018797  lea     rbp, [rax-4Fh]
0x18001879b  sub     rsp, 0C0h
0x1800187a2  mov     r13, rdx
0x1800187a5  mov     r12d, ecx
0x1800187a8  xor     ebx, ebx
0x1800187aa  cmp     cs:?g_fInitServerCredHandle@@3HA, ebx; int g_fInitServerCredHandle
0x1800187b0  jnz     short loc_1800187F3
0x1800187b2  mov     eax, 0AAh
0x1800187b7  mov     [rbp+47h+var_80], ax
0x1800187bb  mov     ebx, 0C00E052Bh
0x1800187c0  mov     [rbp+47h+var_78], ebx
0x1800187c3  xor     esi, esi
0x1800187c5  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800187cc  jz      loc_180018A50
0x1800187d2  lea     r14, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x1800187d9  mov     rcx, r14; wchar_t *
0x1800187dc  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800187e1  lea     edi, [rsi+1]
0x1800187e4  mov     [rsp+0E0h+var_90], rsi
0x1800187e9  mov     [rsp+0E0h+var_98], rsi
0x1800187ee  jmp     loc_1800189FB
0x1800187f3  mov     rcx, cs:?g_PackageInfo@@3PEAU_SecPkgInfoW@@EA; _SecPkgInfoW * g_PackageInfo
0x1800187fa  mov     eax, [rcx+8]
0x1800187fd  cmp     [r9], eax
0x180018800  jnb     loc_180018886
0x180018806  mov     eax, 0ABh
0x18001880b  mov     [rbp+47h+var_80], ax
0x18001880f  mov     esi, 80070057h
0x180018814  mov     [rbp+47h+var_78], esi
0x180018817  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001881e  jz      short loc_18001887F
0x180018820  lea     r14, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x180018827  mov     rcx, r14; wchar_t *
0x18001882a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001882f  mov     edi, 1
0x180018834  lea     r9d, [rdi+rax]
0x180018838  add     r9, r9
0x18001883b  mov     [rsp+0E0h+var_90], rbx
0x180018840  mov     [rsp+0E0h+var_98], rbx
0x180018845  lea     rax, [rbp+47h+var_78]
0x180018849  mov     [rsp+0E0h+ptsExpiry], rax
0x18001884e  mov     [rsp+0E0h+pfContextAttr], 4
0x180018857  lea     rcx, [rbp+47h+var_80]
0x18001885b  mov     [rsp+0E0h+pOutput], rcx
0x180018860  mov     [rsp+0E0h+phNewContext], 2
0x180018869  mov     qword ptr [rsp+0E0h+TargetDataRep], r14
0x18001886e  mov     r8d, edi
0x180018871  mov     edx, edi
0x180018873  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001887a  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001887f  mov     eax, esi
0x180018881  jmp     loc_180018A52
0x180018886  xorps   xmm0, xmm0
0x180018889  movups  [rbp+47h+var_68], xmm0
0x18001888d  mov     [rbp+47h+var_70], ebx
0x180018890  mov     edi, 1
0x180018895  mov     [rbp+47h+pInput.cBuffers], edi
0x180018898  lea     rax, [rbp+47h+var_58]
0x18001889c  mov     [rbp+47h+pInput.pBuffers], rax
0x1800188a0  mov     [rbp+47h+pInput.ulVersion], ebx
0x1800188a3  mov     [rbp+47h+var_54], 2
0x1800188aa  mov     eax, [rbp+47h+arg_28]
0x1800188ad  mov     [rbp+47h+var_58], eax
0x1800188b0  mov     rax, [rbp+47h+arg_20]
0x1800188b4  mov     [rbp+47h+var_50], rax
0x1800188b8  mov     [rbp+47h+var_48.cBuffers], edi
0x1800188bb  lea     rax, [rbp+47h+var_68]
0x1800188bf  mov     [rbp+47h+var_48.pBuffers], rax
0x1800188c3  mov     [rbp+47h+var_48.ulVersion], ebx
0x1800188c6  mov     dword ptr [rbp+47h+var_68+4], 2
0x1800188cd  mov     eax, [rcx+8]
0x1800188d0  mov     dword ptr [rbp+47h+var_68], eax
0x1800188d3  mov     qword ptr [rbp+47h+var_68+8], r8
0x1800188d7  lea     r14d, [rdi+0Fh]
0x1800188db  test    r12d, r12d
0x1800188de  jz      short loc_1800188ED
0x1800188e0  mov     ecx, r14d; unsigned __int64
0x1800188e3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800188e8  mov     rsi, rax
0x1800188eb  jmp     short loc_1800188F0
0x1800188ed  mov     rsi, [rdx]
0x1800188f0  mov     rdx, rbx
0x1800188f3  test    r12d, r12d
0x1800188f6  cmovz   rdx, rsi; phContext
0x1800188fa  mov     [rsp+0E0h+ptsExpiry], rbx; ptsExpiry
0x1800188ff  lea     rax, [rbp+47h+var_70]
0x180018903  mov     [rsp+0E0h+pfContextAttr], rax; pfContextAttr
0x180018908  lea     rax, [rbp+47h+var_48]
0x18001890c  mov     [rsp+0E0h+pOutput], rax; pOutput
0x180018911  mov     [rsp+0E0h+phNewContext], rsi; phNewContext
0x180018916  mov     [rsp+0E0h+TargetDataRep], r14d; TargetDataRep
0x18001891b  xor     r9d, r9d; fContextReq
0x18001891e  lea     r8, [rbp+47h+pInput]; pInput
0x180018922  lea     rcx, ?g_hServerCred@@3U_SecHandle@@A; phCredential
0x180018929  call    cs:__imp_AcceptSecurityContext
0x18001892f  mov     ebx, eax
0x180018931  lea     r14, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x180018938  test    eax, eax
0x18001893a  jns     short loc_1800189A9
0x18001893c  mov     eax, 0AFh
0x180018941  mov     [rbp+47h+var_80], ax
0x180018945  mov     [rbp+47h+var_78], ebx
0x180018948  xor     r13d, r13d
0x18001894b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018952  jz      short loc_1800189C0
0x180018954  mov     rcx, r14; wchar_t *
0x180018957  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001895c  lea     r9d, [rdi+rax]
0x180018960  add     r9, r9
0x180018963  mov     [rsp+0E0h+var_90], r13
0x180018968  mov     [rsp+0E0h+var_98], r13
0x18001896d  lea     rax, [rbp+47h+var_78]
0x180018971  mov     [rsp+0E0h+ptsExpiry], rax
0x180018976  mov     [rsp+0E0h+pfContextAttr], 4
0x18001897f  lea     rax, [rbp+47h+var_80]
0x180018983  mov     [rsp+0E0h+pOutput], rax
0x180018988  mov     [rsp+0E0h+phNewContext], 2
0x180018991  mov     qword ptr [rsp+0E0h+TargetDataRep], r14
0x180018996  mov     r8d, edi
0x180018999  mov     edx, edi
0x18001899b  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800189a2  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800189a7  jmp     short loc_1800189C0
0x1800189a9  test    ebx, ebx
0x1800189ab  jz      loc_180018A3E
0x1800189b1  cmp     ebx, 90312h
0x1800189b7  jz      loc_180018A3E
0x1800189bd  xor     r13d, r13d
0x1800189c0  mov     ebx, 0C00E052Bh
0x1800189c5  test    r12d, r12d
0x1800189c8  jz      short loc_1800189D4
0x1800189ca  mov     rcx, rsi; Block
0x1800189cd  call    cs:__imp_free
0x1800189d3  nop
0x1800189d4  mov     eax, 0B4h
0x1800189d9  mov     [rbp+47h+var_80], ax
0x1800189dd  mov     [rbp+47h+var_78], ebx
0x1800189e0  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800189e7  jz      short loc_180018A50
0x1800189e9  mov     rcx, r14; wchar_t *
0x1800189ec  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800189f1  mov     [rsp+0E0h+var_90], r13
0x1800189f6  mov     [rsp+0E0h+var_98], r13
0x1800189fb  lea     r9d, [rdi+rax]
0x1800189ff  add     r9, r9
0x180018a02  lea     rax, [rbp+47h+var_78]
0x180018a06  mov     [rsp+0E0h+ptsExpiry], rax
0x180018a0b  mov     [rsp+0E0h+pfContextAttr], 4
0x180018a14  lea     rax, [rbp+47h+var_80]
0x180018a18  mov     [rsp+0E0h+pOutput], rax
0x180018a1d  mov     [rsp+0E0h+phNewContext], 2
0x180018a26  mov     qword ptr [rsp+0E0h+TargetDataRep], r14
0x180018a2b  mov     r8d, edi
0x180018a2e  mov     edx, edi
0x180018a30  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180018a37  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180018a3c  jmp     short loc_180018A50
0x180018a3e  mov     ecx, dword ptr [rbp+47h+var_68]
0x180018a41  mov     rax, [rbp+47h+arg_18]
0x180018a45  mov     [rax], ecx
0x180018a47  test    r12d, r12d
0x180018a4a  jz      short loc_180018A50
0x180018a4c  mov     [r13+0], rsi
0x180018a50  mov     eax, ebx
0x180018a52  lea     r11, [rsp+0E0h+var_20]
0x180018a5a  mov     rbx, [r11+30h]
0x180018a5e  mov     rsi, [r11+38h]
0x180018a62  mov     rsp, r11
0x180018a65  pop     r14
0x180018a67  pop     r13
0x180018a69  pop     r12
0x180018a6b  pop     rdi
0x180018a6c  pop     rbp
0x180018a6d  retn
```
