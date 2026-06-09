# GetTokenForDJPP(ushort const *,ushort const *,ushort const *,ushort const *,_DSR_INSTANCE,ushort const *,_GUID const &,void (*)(ulong,ushort const *),ushort * *)

- ea: `0x140003bc0`
- end: `0x140003f6f`
- name: `?GetTokenForDJPP@@YAJPEBG000W4_DSR_INSTANCE@@0AEBU_GUID@@P6AXK0@ZPEAPEAG@Z`
- size: `943`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, _WORD *, int, unsigned __int16 *, GUID *rguid, void (*)(unsigned int, const unsigned __int16 *), unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x140001820`
- `0x1400028b8`
- `0x140003044`
- `0x140003458`
- `0x140003b80`
- `0x140003bc0`
- `0x140003f78`
- `0x14000651c`
- `0x140006818`
- `0x140006ad0`
- `0x140006cdc`
- `0x140006d24`
- `0x140006e10`
- `0x140006e8c`
- `0x140006f24`
- `0x140006fb8`

## string_xrefs

- `0x140003c57`: `AdalAuthentiationContext failed, unable to create ADAL context`
- `0x140003ca8`: `Unable to update query string parameters`
- `0x140003d01`: `ADALAcquireToken failed`
- `0x140003e97`: `Memory allocation for token data failed.`
- `0x140003ef4`: `ADALGetAccessToken failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall GetTokenForDJPP(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _WORD *a4,
        int a5,
        unsigned __int16 *a6,
        GUID *rguid,
        void (*a8)(unsigned int, const unsigned __int16 *),
        unsigned __int16 **a9)
{
  __int64 result; // rax
  __int64 v14; // rax
  void *v15; // rbx
  _QWORD *v16; // rax
  unsigned int LastADALError; // ebx
  _QWORD *v18; // rax
  unsigned int v19; // edi
  struct HADALREQUEST__ *v20; // rax
  struct HADALREQUEST__ *v21; // rdi
  _QWORD *v22; // rax
  unsigned int v23; // edi
  _QWORD *v24; // rax
  unsigned int v25; // edi
  _QWORD *v26; // rax
  unsigned int v27; // edi
  unsigned int v28; // r15d
  _QWORD *v29; // rax
  __int64 v30; // r15
  unsigned __int64 v31; // rax
  unsigned __int16 *v32; // rax
  _QWORD *v33; // rax
  unsigned int v34; // r15d
  _QWORD *v35; // rax
  unsigned int v36; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v37[2]; // [rsp+28h] [rbp-80h] BYREF
  __int64 v38; // [rsp+38h] [rbp-70h] BYREF
  int v39; // [rsp+40h] [rbp-68h]
  __int64 v40; // [rsp+44h] [rbp-64h]
  int v41; // [rsp+4Ch] [rbp-5Ch]
  void *v42; // [rsp+50h] [rbp-58h]
  __int64 v43; // [rsp+58h] [rbp-50h]
  __int64 v44; // [rsp+60h] [rbp-48h]

  if ( !a9 )
    return 2147942487LL;
  *a9 = 0;
  g_logCallback = a8;
  v40 = 0;
  v41 = 0;
  v43 = 0;
  v44 = 3;
  v38 = 48;
  v39 = 0;
  v42 = &AdalLogCallback;
  ADALSetLogOptions(&v38);
  v14 = ADALCreateAuthenticationContextNoUI(a1, a2);
  v15 = (void *)v14;
  v37[1] = v14;
  if ( !v14 )
  {
    v16 = std::wstring::wstring(&v38, L"AdalAuthentiationContext failed, unable to create ADAL context");
    LogFatalAuthError(v16, 0);
    LastADALError = GetLastADALError();
    ADALReleaseAuthenticationContext(0);
    g_logCallback = 0;
    return LastADALError;
  }
  if ( a4 && *a4 && !(unsigned int)ADALSetAdditionalTokenQueryParams(v14, a4) )
  {
    v18 = std::wstring::wstring(&v38, L"Unable to update query string parameters");
    LogFatalAuthError(v18, 0);
    v19 = GetLastADALError();
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return v19;
  }
  v20 = (struct HADALREQUEST__ *)ADALAcquireToken((struct HADALCONTEXT__ *)v15, a3, rguid);
  v21 = v20;
  v37[0] = v20;
  if ( !v20 )
  {
    v22 = std::wstring::wstring(&v38, L"ADALAcquireToken failed");
    LogFatalAuthError(v22, 0);
    v23 = GetLastADALError();
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return v23;
  }
  if ( a5 )
  {
    if ( !(unsigned int)ADALUseWindowsAuthenticationEnterprise(v20, a6) )
    {
      v26 = std::wstring::wstring(
              &v38,
              L"ADALUseWindowsAuthenticationNonHybrid failed, unable to preform integrated auth");
      LogFatalAuthError(v26, v21);
      v27 = GetLastADALError();
      AdalRequest::~AdalRequest((AdalRequest *)v37);
      ADALReleaseAuthenticationContext(v15);
      g_logCallback = 0;
      return v27;
    }
  }
  else if ( !(unsigned int)ADALUseWindowsAuthenticationTenant(v20, a6) )
  {
    v24 = std::wstring::wstring(&v38, L"ADALUseWindowsAuthenticationTenant failed, unable to preform integrated auth");
    LogFatalAuthError(v24, v21);
    v25 = GetLastADALError();
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return v25;
  }
  v28 = ADALGetRequestStatus(v21);
  if ( v28 )
  {
    v29 = std::wstring::wstring(&v38, L"GetStatus returned failure");
    LogFatalAuthError(v29, v21);
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return v28;
  }
  v36 = 0;
  if ( (unsigned int)ADALGetAccessToken(v21, 0, &v36) != 122 )
    goto LABEL_25;
  v30 = v36;
  v31 = 2LL * (v36 + 1);
  if ( !is_mul_ok(v36 + 1, 2u) )
    v31 = -1;
  v32 = (unsigned __int16 *)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
  *a9 = v32;
  if ( !v32 )
  {
    v33 = std::wstring::wstring(&v38, L"Memory allocation for token data failed.");
    LogFatalAuthError(v33, 0);
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return 2147942414LL;
  }
  v32[v30] = 0;
  v34 = ADALGetAccessToken(v21, *a9, &v36);
  if ( v34 )
  {
    v35 = std::wstring::wstring(&v38, L"ADALGetAccessToken failed");
    LogFatalAuthError(v35, v21);
    operator delete(*a9);
    *a9 = 0;
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    g_logCallback = 0;
    return v34;
  }
  else
  {
LABEL_25:
    AdalRequest::~AdalRequest((AdalRequest *)v37);
    ADALReleaseAuthenticationContext(v15);
    result = 0;
    g_logCallback = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003bc0  push    rbx
0x140003bc2  push    rsi
0x140003bc3  push    rdi
0x140003bc4  push    r12
0x140003bc6  push    r14
0x140003bc8  push    r15
0x140003bca  sub     rsp, 78h
0x140003bce  mov     rdi, r9
0x140003bd1  mov     r12, r8
0x140003bd4  mov     rbx, rdx
0x140003bd7  mov     r15, rcx
0x140003bda  mov     r14, [rsp+0A8h+arg_40]
0x140003be2  xor     esi, esi
0x140003be4  test    r14, r14
0x140003be7  jnz     short loc_140003BF3
0x140003be9  mov     eax, 80070057h
0x140003bee  jmp     loc_140003F61
0x140003bf3  mov     [r14], rsi
0x140003bf6  mov     rax, [rsp+0A8h+arg_38]
0x140003bfe  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rax; void (*g_logCallback)(ulong,ushort const *)
0x140003c05  mov     [rsp+0A8h+var_64], rsi
0x140003c0a  mov     [rsp+0A8h+var_5C], esi
0x140003c0e  mov     [rsp+0A8h+var_50], rsi
0x140003c13  mov     [rsp+0A8h+var_48], 3
0x140003c1c  mov     [rsp+0A8h+var_70], 30h ; '0'
0x140003c25  mov     [rsp+0A8h+var_68], esi
0x140003c29  lea     rax, ?AdalLogCallback@@YAXPEBG0W4ADAL_LOGLEVEL@@KPEAX@Z; AdalLogCallback(ushort const *,ushort const *,ADAL_LOGLEVEL,ulong,void *)
0x140003c30  mov     [rsp+0A8h+var_58], rax
0x140003c35  lea     rcx, [rsp+0A8h+var_70]
0x140003c3a  call    ADALSetLogOptions
0x140003c3f  mov     rdx, rbx; unsigned __int16 *
0x140003c42  mov     rcx, r15; unsigned __int16 *
0x140003c45  call    ADALCreateAuthenticationContextNoUI
0x140003c4a  mov     rbx, rax
0x140003c4d  mov     [rsp+0A8h+var_78], rax
0x140003c52  test    rax, rax
0x140003c55  jnz     short loc_140003C8F
0x140003c57  lea     rdx, aAdalauthentiat; "AdalAuthentiationContext failed, unable"...
0x140003c5e  lea     rcx, [rsp+0A8h+var_70]
0x140003c63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003c68  xor     edx, edx
0x140003c6a  mov     rcx, rax
0x140003c6d  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003c72  call    ?GetLastADALError@@YAJXZ; GetLastADALError(void)
0x140003c77  mov     ebx, eax
0x140003c79  xor     ecx, ecx; Block
0x140003c7b  call    ADALReleaseAuthenticationContext
0x140003c80  nop
0x140003c81  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003c88  mov     eax, ebx
0x140003c8a  jmp     loc_140003F61
0x140003c8f  test    rdi, rdi
0x140003c92  jz      short loc_140003CE1
0x140003c94  cmp     [rdi], si
0x140003c97  jz      short loc_140003CE1
0x140003c99  mov     rdx, rdi
0x140003c9c  mov     rcx, rbx
0x140003c9f  call    ADALSetAdditionalTokenQueryParams
0x140003ca4  test    eax, eax
0x140003ca6  jnz     short loc_140003CE1
0x140003ca8  lea     rdx, aUnableToUpdate; "Unable to update query string parameter"...
0x140003caf  lea     rcx, [rsp+0A8h+var_70]
0x140003cb4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003cb9  xor     edx, edx
0x140003cbb  mov     rcx, rax
0x140003cbe  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003cc3  call    ?GetLastADALError@@YAJXZ; GetLastADALError(void)
0x140003cc8  mov     edi, eax
0x140003cca  mov     rcx, rbx; Block
0x140003ccd  call    ADALReleaseAuthenticationContext
0x140003cd2  nop
0x140003cd3  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003cda  mov     eax, edi
0x140003cdc  jmp     loc_140003F61
0x140003ce1  mov     r8, [rsp+0A8h+rguid]; rguid
0x140003ce9  mov     rdx, r12; unsigned __int16 *
0x140003cec  mov     rcx, rbx; struct HADALCONTEXT__ *
0x140003cef  call    ADALAcquireToken
0x140003cf4  mov     rdi, rax
0x140003cf7  mov     [rsp+0A8h+var_80], rax
0x140003cfc  test    rax, rax
0x140003cff  jnz     short loc_140003D45
0x140003d01  lea     rdx, aAdalacquiretok; "ADALAcquireToken failed"
0x140003d08  lea     rcx, [rsp+0A8h+var_70]
0x140003d0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003d12  xor     edx, edx
0x140003d14  mov     rcx, rax
0x140003d17  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003d1c  call    ?GetLastADALError@@YAJXZ; GetLastADALError(void)
0x140003d21  mov     edi, eax
0x140003d23  lea     rcx, [rsp+0A8h+var_80]; this
0x140003d28  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003d2d  nop
0x140003d2e  mov     rcx, rbx; Block
0x140003d31  call    ADALReleaseAuthenticationContext
0x140003d36  nop
0x140003d37  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003d3e  mov     eax, edi
0x140003d40  jmp     loc_140003F61
0x140003d45  mov     rdx, [rsp+0A8h+arg_28]; unsigned __int16 *
0x140003d4d  mov     rcx, rdi; struct HADALREQUEST__ *
0x140003d50  cmp     [rsp+0A8h+arg_20], esi
0x140003d57  jnz     short loc_140003DAB
0x140003d59  call    ADALUseWindowsAuthenticationTenant
0x140003d5e  test    eax, eax
0x140003d60  jnz     loc_140003DF9
0x140003d66  lea     rdx, aAdalusewindows; "ADALUseWindowsAuthenticationTenant fail"...
0x140003d6d  lea     rcx, [rsp+0A8h+var_70]
0x140003d72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003d77  mov     rdx, rdi
0x140003d7a  mov     rcx, rax
0x140003d7d  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003d82  call    ?GetLastADALError@@YAJXZ; GetLastADALError(void)
0x140003d87  mov     edi, eax
0x140003d89  lea     rcx, [rsp+0A8h+var_80]; this
0x140003d8e  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003d93  nop
0x140003d94  mov     rcx, rbx; Block
0x140003d97  call    ADALReleaseAuthenticationContext
0x140003d9c  nop
0x140003d9d  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003da4  mov     eax, edi
0x140003da6  jmp     loc_140003F61
0x140003dab  call    ADALUseWindowsAuthenticationEnterprise
0x140003db0  test    eax, eax
0x140003db2  jnz     short loc_140003DF9
0x140003db4  lea     rdx, aAdalusewindows_0; "ADALUseWindowsAuthenticationNonHybrid f"...
0x140003dbb  lea     rcx, [rsp+0A8h+var_70]
0x140003dc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003dc5  mov     rdx, rdi
0x140003dc8  mov     rcx, rax
0x140003dcb  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003dd0  call    ?GetLastADALError@@YAJXZ; GetLastADALError(void)
0x140003dd5  mov     edi, eax
0x140003dd7  lea     rcx, [rsp+0A8h+var_80]; this
0x140003ddc  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003de1  nop
0x140003de2  mov     rcx, rbx; Block
0x140003de5  call    ADALReleaseAuthenticationContext
0x140003dea  nop
0x140003deb  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003df2  mov     eax, edi
0x140003df4  jmp     loc_140003F61
0x140003df9  mov     rcx, rdi; struct HADALREQUEST__ *
0x140003dfc  call    ADALGetRequestStatus
0x140003e01  mov     r15d, eax
0x140003e04  test    eax, eax
0x140003e06  jz      short loc_140003E48
0x140003e08  lea     rdx, aGetstatusRetur; "GetStatus returned failure"
0x140003e0f  lea     rcx, [rsp+0A8h+var_70]
0x140003e14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003e19  mov     rdx, rdi
0x140003e1c  mov     rcx, rax
0x140003e1f  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003e24  nop
0x140003e25  lea     rcx, [rsp+0A8h+var_80]; this
0x140003e2a  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003e2f  nop
0x140003e30  mov     rcx, rbx; Block
0x140003e33  call    ADALReleaseAuthenticationContext
0x140003e38  nop
0x140003e39  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003e40  mov     eax, r15d
0x140003e43  jmp     loc_140003F61
0x140003e48  mov     [rsp+0A8h+var_88], esi
0x140003e4c  lea     r8, [rsp+0A8h+var_88]; unsigned int *
0x140003e51  xor     edx, edx; unsigned __int16 *
0x140003e53  mov     rcx, rdi; struct HADALREQUEST__ *
0x140003e56  call    ADALGetAccessToken
0x140003e5b  cmp     eax, 7Ah ; 'z'
0x140003e5e  jnz     loc_140003F3B
0x140003e64  mov     r15d, [rsp+0A8h+var_88]
0x140003e69  lea     ecx, [r15+1]
0x140003e6d  mov     eax, 2
0x140003e72  mul     rcx
0x140003e75  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140003e7c  cmovb   rax, rcx
0x140003e80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003e87  mov     rcx, rax; unsigned __int64
0x140003e8a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140003e8f  mov     [r14], rax
0x140003e92  test    rax, rax
0x140003e95  jnz     short loc_140003ED8
0x140003e97  lea     rdx, aMemoryAllocati; "Memory allocation for token data failed"...
0x140003e9e  lea     rcx, [rsp+0A8h+var_70]
0x140003ea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003ea8  xor     edx, edx
0x140003eaa  mov     rcx, rax
0x140003ead  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003eb2  nop
0x140003eb3  lea     rcx, [rsp+0A8h+var_80]; this
0x140003eb8  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003ebd  nop
0x140003ebe  mov     rcx, rbx; Block
0x140003ec1  call    ADALReleaseAuthenticationContext
0x140003ec6  nop
0x140003ec7  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003ece  mov     eax, 8007000Eh
0x140003ed3  jmp     loc_140003F61
0x140003ed8  mov     [rax+r15*2], si
0x140003edd  lea     r8, [rsp+0A8h+var_88]; unsigned int *
0x140003ee2  mov     rdx, [r14]; unsigned __int16 *
0x140003ee5  mov     rcx, rdi; struct HADALREQUEST__ *
0x140003ee8  call    ADALGetAccessToken
0x140003eed  mov     r15d, eax
0x140003ef0  test    eax, eax
0x140003ef2  jz      short loc_140003F3B
0x140003ef4  lea     rdx, aAdalgetaccesst; "ADALGetAccessToken failed"
0x140003efb  lea     rcx, [rsp+0A8h+var_70]
0x140003f00  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140003f05  mov     rdx, rdi
0x140003f08  mov     rcx, rax
0x140003f0b  call    ?LogFatalAuthError@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHADALREQUEST__@@@Z; LogFatalAuthError(std::wstring,HADALREQUEST__ *)
0x140003f10  mov     rcx, [r14]; Block
0x140003f13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003f18  mov     [r14], rsi
0x140003f1b  lea     rcx, [rsp+0A8h+var_80]; this
0x140003f20  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003f25  nop
0x140003f26  mov     rcx, rbx; Block
0x140003f29  call    ADALReleaseAuthenticationContext
0x140003f2e  nop
0x140003f2f  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003f36  mov     eax, r15d
0x140003f39  jmp     short loc_140003F61
0x140003f3b  lea     rcx, [rsp+0A8h+var_80]; this
0x140003f40  call    ??1AdalRequest@@QEAA@XZ; AdalRequest::~AdalRequest(void)
0x140003f45  nop
0x140003f46  mov     rcx, rbx; Block
0x140003f49  call    ADALReleaseAuthenticationContext
0x140003f4e  nop
0x140003f4f  xor     eax, eax
0x140003f51  jmp     short loc_140003F5A
0x140003f53  xor     esi, esi
0x140003f55  mov     eax, 801C0516h
0x140003f5a  mov     cs:?g_logCallback@@3P6AXKPEBG@ZEA, rsi; void (*g_logCallback)(ulong,ushort const *)
0x140003f61  add     rsp, 78h
0x140003f65  pop     r15
0x140003f67  pop     r14
0x140003f69  pop     r12
0x140003f6b  pop     rdi
0x140003f6c  pop     rsi
0x140003f6d  pop     rbx
0x140003f6e  retn
```
