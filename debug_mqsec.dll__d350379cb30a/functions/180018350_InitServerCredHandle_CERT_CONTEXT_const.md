# InitServerCredHandle(_CERT_CONTEXT const *)

- ea: `0x180018350`
- end: `0x18001852a`
- name: `?InitServerCredHandle@@YAJPEBU_CERT_CONTEXT@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018b40`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18000b95c`
- `0x180013940`
- `0x180017430`
- `0x1800181c4`
- `0x180018350`
- `0x18002f0ba`

## import_xrefs

- `Secur32!AcquireCredentialsHandleW` at `0x1800184a4`
- `Secur32!AcquireCredentialsHandleW` at `0x1800184a4`
- `KERNEL32!LeaveCriticalSection` at `0x180018427`
- `KERNEL32!LeaveCriticalSection` at `0x1800184b9`
- `KERNEL32!LeaveCriticalSection` at `0x180018427`
- `KERNEL32!LeaveCriticalSection` at `0x1800184b9`

## string_xrefs

- `0x18001849b`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitServerCredHandle(const struct _CERT_CONTEXT *a1)
{
  int inited; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _DWORD pAuthData[2]; // [rsp+60h] [rbp-19h] BYREF
  const struct _CERT_CONTEXT **v7; // [rsp+68h] [rbp-11h]
  int v8; // [rsp+98h] [rbp+1Fh]
  const struct _CERT_CONTEXT *v9; // [rsp+E0h] [rbp+67h] BYREF
  __int16 v10; // [rsp+E8h] [rbp+6Fh] BYREF
  int v11; // [rsp+F0h] [rbp+77h] BYREF
  _RTL_CRITICAL_SECTION *v12; // [rsp+F8h] [rbp+7Fh]

  v9 = a1;
  if ( g_fInitServerCredHandle )
    return 0;
  v12 = &stru_180042D38;
  CCriticalSection::Lock((CCriticalSection *)&stru_180042D38);
  if ( g_fInitServerCredHandle )
    goto LABEL_11;
  inited = InitSecInterface();
  if ( !inited )
  {
    memset_0(pAuthData, 0, 0x50u);
    pAuthData[0] = 4;
    pAuthData[1] = 1;
    v7 = &v9;
    v8 = 0;
    v4 = AcquireCredentialsHandleW(
           0,
           (LPWSTR)L"Microsoft Unified Security Protocol Provider",
           1u,
           0,
           pAuthData,
           0,
           0,
           &g_hServerCred,
           0);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, &WPP_8b1a3c8841a63a11de5e51343bea216a_Traceguids, v4);
      if ( !g_fInitServerCredHandle )
      {
        v5 = -1072822997;
        LogMsgHR(-1072822997, (wchar_t *)L"srvauthn/sspi.cpp", 0x96u);
        goto LABEL_12;
      }
    }
    else
    {
      g_fInitServerCredHandle = 1;
    }
LABEL_11:
    v5 = 0;
LABEL_12:
    LeaveCriticalSection(&stru_180042D38);
    return v5;
  }
  if ( inited < 0 )
  {
    v10 = 140;
    v11 = inited;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v3 = mqwcslen(L"srvauthn/sspi.cpp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v3 + 1),
        L"srvauthn/sspi.cpp",
        2,
        &v10,
        4,
        &v11,
        0,
        0);
    }
  }
  LeaveCriticalSection(&stru_180042D38);
  return 3222144299LL;
}

```

## disassembly

```asm
0x180018350  mov     [rsp-8+arg_0], rcx
0x180018355  push    rbp
0x180018356  push    rbx
0x180018357  push    rdi
0x180018358  push    r14
0x18001835a  lea     rbp, [rsp-3Fh]
0x18001835f  sub     rsp, 0B8h
0x180018366  cmp     cs:?g_fInitServerCredHandle@@3HA, 0; int g_fInitServerCredHandle
0x18001836d  jz      short loc_180018376
0x18001836f  xor     eax, eax
0x180018371  jmp     loc_1800184C2
0x180018376  lea     r14, stru_180042D38
0x18001837d  mov     [rbp+57h+arg_18], r14
0x180018381  mov     rcx, r14; this
0x180018384  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180018389  nop
0x18001838a  cmp     cs:?g_fInitServerCredHandle@@3HA, 0; int g_fInitServerCredHandle
0x180018391  jnz     loc_1800184B4
0x180018397  call    ?InitSecInterface@@YAJXZ; InitSecInterface(void)
0x18001839c  test    eax, eax
0x18001839e  jz      loc_180018438
0x1800183a4  jns     short loc_180018424
0x1800183a6  mov     ecx, 8Ch
0x1800183ab  mov     [rbp+57h+arg_8], cx
0x1800183af  mov     [rbp+57h+arg_10], eax
0x1800183b2  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800183ba  jz      short loc_180018424
0x1800183bc  lea     rdi, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x1800183c3  mov     rcx, rdi; wchar_t *
0x1800183c6  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800183cb  mov     ebx, 1
0x1800183d0  lea     r9d, [rbx+rax]
0x1800183d4  add     r9, r9
0x1800183d7  mov     [rsp+0D0h+var_80], 0
0x1800183e0  mov     [rsp+0D0h+var_88], 0
0x1800183e9  lea     rax, [rbp+57h+arg_10]
0x1800183ed  mov     [rsp+0D0h+ptsExpiry], rax
0x1800183f2  mov     [rsp+0D0h+phCredential], 4
0x1800183fb  lea     rax, [rbp+57h+arg_8]
0x1800183ff  mov     [rsp+0D0h+pvGetKeyArgument], rax
0x180018404  mov     [rsp+0D0h+pGetKeyFn], 2
0x18001840d  mov     [rsp+0D0h+pAuthData], rdi
0x180018412  mov     r8d, ebx
0x180018415  mov     edx, ebx
0x180018417  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001841e  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180018423  nop
0x180018424  mov     rcx, r14; lpCriticalSection
0x180018427  call    cs:__imp_LeaveCriticalSection
0x18001842d  nop
0x18001842e  mov     eax, 0C00E052Bh
0x180018433  jmp     loc_1800184C2
0x180018438  xor     edx, edx; Val
0x18001843a  lea     r8d, [rdx+50h]; Size
0x18001843e  lea     rcx, [rbp+57h+var_70]; void *
0x180018442  call    memset_0
0x180018447  mov     [rbp+57h+var_70], 4
0x18001844e  mov     ebx, 1
0x180018453  mov     [rbp+57h+var_6C], ebx
0x180018456  lea     rax, [rbp+57h+arg_0]
0x18001845a  mov     [rbp+57h+var_68], rax
0x18001845e  mov     [rbp+57h+var_38], 0
0x180018465  mov     [rsp+0D0h+ptsExpiry], 0; ptsExpiry
0x18001846e  lea     rax, ?g_hServerCred@@3U_SecHandle@@A; _SecHandle g_hServerCred
0x180018475  mov     [rsp+0D0h+phCredential], rax; phCredential
0x18001847a  mov     [rsp+0D0h+pvGetKeyArgument], 0; pvGetKeyArgument
0x180018483  mov     [rsp+0D0h+pGetKeyFn], 0; pGetKeyFn
0x18001848c  lea     rax, [rbp+57h+var_70]
0x180018490  mov     [rsp+0D0h+pAuthData], rax; pAuthData
0x180018495  xor     r9d, r9d; pvLogonId
0x180018498  mov     r8d, ebx; fCredentialUse
0x18001849b  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x1800184a2  xor     ecx, ecx; pszPrincipal
0x1800184a4  call    cs:__imp_AcquireCredentialsHandleW
0x1800184aa  test    eax, eax
0x1800184ac  jnz     short loc_1800184CF
0x1800184ae  mov     cs:?g_fInitServerCredHandle@@3HA, ebx; int g_fInitServerCredHandle
0x1800184b4  xor     ebx, ebx
0x1800184b6  mov     rcx, r14; lpCriticalSection
0x1800184b9  call    cs:__imp_LeaveCriticalSection
0x1800184bf  nop
0x1800184c0  mov     eax, ebx
0x1800184c2  add     rsp, 0B8h
0x1800184c9  pop     r14
0x1800184cb  pop     rdi
0x1800184cc  pop     rbx
0x1800184cd  pop     rbp
0x1800184ce  retn
0x1800184cf  lea     rdx, WPP_GLOBAL_Control
0x1800184d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184dd  cmp     rcx, rdx
0x1800184e0  jz      short loc_180018505
0x1800184e2  test    [rcx+10Ch], bl
0x1800184e8  jz      short loc_180018505
0x1800184ea  mov     edx, 0Ah
0x1800184ef  mov     r9d, eax
0x1800184f2  lea     r8, WPP_8b1a3c8841a63a11de5e51343bea216a_Traceguids
0x1800184f9  mov     rcx, [rcx+100h]
0x180018500  call    WPP_SF_d
0x180018505  cmp     cs:?g_fInitServerCredHandle@@3HA, 0; int g_fInitServerCredHandle
0x18001850c  jnz     short loc_1800184B4
0x18001850e  mov     ebx, 0C00E052Bh
0x180018513  mov     r8d, 96h; unsigned __int16
0x180018519  lea     rdx, aSrvauthnSspiCp; "srvauthn/sspi.cpp"
0x180018520  mov     ecx, ebx; int
0x180018522  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018527  jmp     short loc_1800184B6
```
