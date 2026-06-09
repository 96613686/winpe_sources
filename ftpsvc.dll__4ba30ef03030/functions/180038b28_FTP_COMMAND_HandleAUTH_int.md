# FTP_COMMAND::HandleAUTH(int *)

- ea: `0x180038b28`
- end: `0x180038d6c`
- name: `?HandleAUTH@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `580`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x1800344bc`
- `0x180038ac0`
- `0x180038b28`
- `0x18003e564`
- `0x180041544`

## import_xrefs

- `msvcrt!_stricmp` at `0x180038b6c`
- `msvcrt!_stricmp` at `0x180038b80`
- `msvcrt!_stricmp` at `0x180038b94`
- `msvcrt!_stricmp` at `0x180038ba8`
- `msvcrt!_stricmp` at `0x180038b6c`
- `msvcrt!_stricmp` at `0x180038b80`
- `msvcrt!_stricmp` at `0x180038b94`
- `msvcrt!_stricmp` at `0x180038ba8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180038d54`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180038d54`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180038ced`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180038ced`
- `iisutil!WriteRefTraceLog` at `0x180038d32`
- `iisutil!WriteRefTraceLog` at `0x180038d32`

## string_xrefs

- `0x180038c26`: `SSL certificate was not configured.`
- `0x180038c81`: `SSL certificate was not configured.`
- `0x180038bb9`: `Security mechanism not implemented.`
- `0x180038bda`: `Secure connection was already negotiated.`
- `0x180038cbe`: `AUTH command ok. Expecting TLS Negotiation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_COMMAND::HandleAUTH(FTP_SESSION **this, int *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // r15
  int v5; // ebx
  const unsigned __int16 *v6; // rdi
  const char *v7; // rsi
  const char *v8; // r14
  const char *v9; // rsi
  int v10; // eax
  FTP_SESSION *v11; // rcx
  unsigned __int32 v12; // ebx

  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(this[132]);
  v5 = 0;
  v6 = &WideCharStr;
  v7 = (const char *)this[20];
  if ( _stricmp(v7, "SSL") && _stricmp(v7, "TLS-P") && _stricmp(v7, "TLS") && _stricmp(v7, "TLS-C") )
  {
    v8 = "504";
    v9 = "Security mechanism not implemented.";
    v10 = -2147024776;
    goto LABEL_26;
  }
  v11 = this[132];
  if ( *((_DWORD *)v11 + 275) == 2 )
  {
    v9 = "Secure connection was already negotiated.";
LABEL_8:
    v8 = "534";
    v10 = -2147024891;
    goto LABEL_26;
  }
  v10 = FTP_SESSION::InitializeOrResetFtpSession(v11, 0);
  if ( v10 < 0 )
  {
    v8 = "451";
LABEL_11:
    v9 = "Failed to setup secure session.";
    goto LABEL_26;
  }
  if ( !**((_WORD **)ReferencedSiteConfig + 12) )
  {
    v9 = "Local policy on server does not allow TLS secure connections.";
    v5 = 31;
    v6 = L"SSL certificate was not configured.";
    goto LABEL_8;
  }
  v10 = FTP_CONTROL_CHANNEL::EnableSslSession((FTP_SESSION *)((char *)this[132] + 1064), 1);
  if ( v10 < 0 )
  {
    switch ( v10 )
    {
      case -2146885628:
        v5 = 44;
        v6 = L"SSL certificate was not found.";
        break;
      case -2146893042:
        v5 = 45;
        v6 = L"Private key was not found for the specified SSL certificate.";
        break;
      case -2147024809:
        v5 = 31;
        v6 = L"SSL certificate was not configured.";
        break;
      case -2147023434:
        v5 = 46;
        v6 = L"SSL certificate hash has invalid length.";
        break;
      default:
        v5 = 32;
        v6 = L"SSL initialization failed.";
        break;
    }
    v8 = "431";
    goto LABEL_11;
  }
  v8 = "234";
  v9 = "AUTH command ok. Expecting TLS Negotiation.";
LABEL_26:
  if ( !*((_DWORD *)this + 292) )
    *((_DWORD *)this + 292) = v10;
  if ( !*((_DWORD *)this + 274) )
  {
    *((_DWORD *)this + 274) = v5;
    STRU::Copy((STRU *)(this + 139), v6);
    this[138] = this[143];
  }
  FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, v8, v9);
  *a2 = 1;
  v12 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v12);
  if ( !v12 )
  {
    if ( ReferencedSiteConfig )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
    }
  }
}

```

## disassembly

```asm
0x180038b28  push    rbx
0x180038b2a  push    rbp
0x180038b2b  push    rsi
0x180038b2c  push    rdi
0x180038b2d  push    r12
0x180038b2f  push    r13
0x180038b31  push    r14
0x180038b33  push    r15
0x180038b35  sub     rsp, 28h
0x180038b39  mov     r12, rdx
0x180038b3c  mov     rbp, rcx
0x180038b3f  mov     rcx, [rcx+420h]; this
0x180038b46  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x180038b4b  mov     r15, rax
0x180038b4e  xor     r13d, r13d
0x180038b51  mov     ebx, r13d
0x180038b54  lea     rdi, WideCharStr
0x180038b5b  mov     rsi, [rbp+0A0h]
0x180038b62  lea     rdx, aSsl_0; "SSL"
0x180038b69  mov     rcx, rsi; String1
0x180038b6c  call    cs:__imp__stricmp
0x180038b72  test    eax, eax
0x180038b74  jz      short loc_180038BCA
0x180038b76  lea     rdx, aTlsP; "TLS-P"
0x180038b7d  mov     rcx, rsi; String1
0x180038b80  call    cs:__imp__stricmp
0x180038b86  test    eax, eax
0x180038b88  jz      short loc_180038BCA
0x180038b8a  lea     rdx, aTls; "TLS"
0x180038b91  mov     rcx, rsi; String1
0x180038b94  call    cs:__imp__stricmp
0x180038b9a  test    eax, eax
0x180038b9c  jz      short loc_180038BCA
0x180038b9e  lea     rdx, aTlsC; "TLS-C"
0x180038ba5  mov     rcx, rsi; String1
0x180038ba8  call    cs:__imp__stricmp
0x180038bae  test    eax, eax
0x180038bb0  jz      short loc_180038BCA
0x180038bb2  lea     r14, a504; "504"
0x180038bb9  lea     rsi, aSecurityMechan; "Security mechanism not implemented."
0x180038bc0  mov     eax, 80070078h
0x180038bc5  jmp     loc_180038CC5
0x180038bca  mov     rcx, [rbp+420h]; this
0x180038bd1  cmp     dword ptr [rcx+44Ch], 2
0x180038bd8  jnz     short loc_180038BF2
0x180038bda  lea     rsi, aSecureConnecti; "Secure connection was already negotiate"...
0x180038be1  lea     r14, a534; "534"
0x180038be8  mov     eax, 80070005h
0x180038bed  jmp     loc_180038CC5
0x180038bf2  xor     edx, edx; int
0x180038bf4  call    ?InitializeOrResetFtpSession@FTP_SESSION@@QEAAJH@Z; FTP_SESSION::InitializeOrResetFtpSession(int)
0x180038bf9  test    eax, eax
0x180038bfb  jns     short loc_180038C10
0x180038bfd  lea     r14, a451; "451"
0x180038c04  lea     rsi, aFailedToSetupS; "Failed to setup secure session."
0x180038c0b  jmp     loc_180038CC5
0x180038c10  mov     rax, [r15+60h]
0x180038c14  cmp     [rax], r13w
0x180038c18  jnz     short loc_180038C2F
0x180038c1a  lea     rsi, aLocalPolicyOnS; "Local policy on server does not allow T"...
0x180038c21  mov     ebx, 1Fh
0x180038c26  lea     rdi, aSslCertificate; "SSL certificate was not configured."
0x180038c2d  jmp     short loc_180038BE1
0x180038c2f  mov     rcx, [rbp+420h]
0x180038c36  add     rcx, 428h; this
0x180038c3d  mov     edx, 1; int
0x180038c42  call    ?EnableSslSession@FTP_CONTROL_CHANNEL@@QEAAJH@Z; FTP_CONTROL_CHANNEL::EnableSslSession(int)
0x180038c47  test    eax, eax
0x180038c49  jns     short loc_180038CB7
0x180038c4b  cmp     eax, 80092004h
0x180038c50  jnz     short loc_180038C60
0x180038c52  mov     ebx, 2Ch ; ','
0x180038c57  lea     rdi, aSslCertificate_0; "SSL certificate was not found."
0x180038c5e  jmp     short loc_180038CAB
0x180038c60  cmp     eax, 8009030Eh
0x180038c65  jnz     short loc_180038C75
0x180038c67  mov     ebx, 2Dh ; '-'
0x180038c6c  lea     rdi, aPrivateKeyWasN; "Private key was not found for the speci"...
0x180038c73  jmp     short loc_180038CAB
0x180038c75  cmp     eax, 80070057h
0x180038c7a  jnz     short loc_180038C8A
0x180038c7c  mov     ebx, 1Fh
0x180038c81  lea     rdi, aSslCertificate; "SSL certificate was not configured."
0x180038c88  jmp     short loc_180038CAB
0x180038c8a  cmp     eax, 800705B6h
0x180038c8f  jnz     short loc_180038C9F
0x180038c91  mov     ebx, 2Eh ; '.'
0x180038c96  lea     rdi, aSslCertificate_1; "SSL certificate hash has invalid length"...
0x180038c9d  jmp     short loc_180038CAB
0x180038c9f  mov     ebx, 20h ; ' '
0x180038ca4  lea     rdi, aSslInitializat; "SSL initialization failed."
0x180038cab  lea     r14, a431; "431"
0x180038cb2  jmp     loc_180038C04
0x180038cb7  lea     r14, a234; "234"
0x180038cbe  lea     rsi, aAuthCommandOkE; "AUTH command ok. Expecting TLS Negotiat"...
0x180038cc5  cmp     [rbp+490h], r13d
0x180038ccc  jnz     short loc_180038CD4
0x180038cce  mov     [rbp+490h], eax
0x180038cd4  cmp     [rbp+448h], r13d
0x180038cdb  jnz     short loc_180038D01
0x180038cdd  mov     [rbp+448h], ebx
0x180038ce3  lea     rcx, [rbp+458h]
0x180038cea  mov     rdx, rdi
0x180038ced  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180038cf3  mov     rax, [rbp+478h]
0x180038cfa  mov     [rbp+450h], rax
0x180038d01  mov     r8, rsi; char *
0x180038d04  mov     rdx, r14; char *
0x180038d07  mov     rcx, rbp; this
0x180038d0a  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180038d0f  mov     dword ptr [r12], 1
0x180038d17  or      ebx, 0FFFFFFFFh
0x180038d1a  lock xadd [r15], ebx
0x180038d1f  dec     ebx
0x180038d21  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180038d28  test    rcx, rcx
0x180038d2b  jz      short loc_180038D38
0x180038d2d  mov     r8, r15
0x180038d30  mov     edx, ebx
0x180038d32  call    cs:__imp_WriteRefTraceLog
0x180038d38  test    ebx, ebx
0x180038d3a  jnz     short loc_180038D5B
0x180038d3c  test    r15, r15
0x180038d3f  jz      short loc_180038D5B
0x180038d41  mov     rcx, r15; this
0x180038d44  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180038d49  nop
0x180038d4a  mov     rdx, r15
0x180038d4d  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180038d54  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180038d5a  nop
0x180038d5b  add     rsp, 28h
0x180038d5f  pop     r15
0x180038d61  pop     r14
0x180038d63  pop     r13
0x180038d65  pop     r12
0x180038d67  pop     rdi
0x180038d68  pop     rsi
0x180038d69  pop     rbp
0x180038d6a  pop     rbx
0x180038d6b  retn
```
