# CWinHttpHelperBase::CreateRequest(wchar_t const *,wchar_t const *,void * *,Mso::Http::IAuthHandler *,bool)

- ea: `0x1800f02d0`
- end: `0x1800f04d3`
- name: `?CreateRequest@CWinHttpHelperBase@@QEAAKPEB_W0PEAPEAXPEAVIAuthHandler@Http@Mso@@_N@Z`
- size: `515`
- prototype: `unsigned int __usercall@<eax>(CWinHttpHelperBase *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, void **@<r9>, struct Mso::Http::IAuthHandler *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800e3610`

## callees

- `0x18000adf0`
- `0x1800258b4`
- `0x18003e690`
- `0x1800f02d0`
- `0x1800f09e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f0344`
- `KERNEL32!GetLastError` at `0x1800f03c5`
- `KERNEL32!GetLastError` at `0x1800f0403`
- `KERNEL32!GetLastError` at `0x1800f0344`
- `KERNEL32!GetLastError` at `0x1800f03c5`
- `KERNEL32!GetLastError` at `0x1800f0403`
- `WINHTTP!WinHttpOpenRequest` at `0x1800f033b`
- `WINHTTP!WinHttpOpenRequest` at `0x1800f033b`
- `WINHTTP!WinHttpSetOption` at `0x1800f0491`
- `WINHTTP!WinHttpSetOption` at `0x1800f0491`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800f03f7`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800f03f7`

## string_xrefs

- `0x1800f0442`: `Error: CreateRequest failed in WinHttpSetStatusCallback`
- `0x1800f038a`: `Error: CreateRequest failed in WinHttpOpenRequest`

## pseudocode

```c
DWORD __fastcall CWinHttpHelperBase::CreateRequest(
        CWinHttpHelperBase *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void **a4,
        struct Mso::Http::IAuthHandler *a5,
        bool a6)
{
  int v9; // edx
  DWORD LastError; // esi
  int v11; // r9d
  DWORD v12; // eax
  int v13; // edx
  int v14; // r9d
  DWORD v15; // ebx
  const char *v16; // [rsp+40h] [rbp-39h] BYREF
  CWinHttpHelperBase *Buffer; // [rsp+48h] [rbp-31h] BYREF
  void **v18; // [rsp+50h] [rbp-29h] BYREF
  const char *v19; // [rsp+58h] [rbp-21h]
  DWORD v20; // [rsp+60h] [rbp-19h]
  __int16 v21; // [rsp+64h] [rbp-15h]
  __int128 v22; // [rsp+68h] [rbp-11h] BYREF
  __int64 v23; // [rsp+78h] [rbp-1h]
  __int64 v24; // [rsp+80h] [rbp+7h]

  if ( !a4 )
    return 87;
  *a4 = 0;
  *a4 = WinHttpOpenRequest(*((HINTERNET *)this + 23), a2, a3, 0, 0, 0, *((_BYTE *)this + 216) != 0 ? 0x800000 : 0);
  LastError = GetLastError();
  if ( LastError )
  {
    v19 = "SH_ErrorCode";
    v20 = LastError;
    v21 = 4;
    v22 = 0;
    v23 = 0;
    v24 = 7;
    LOWORD(v22) = 0;
    v18 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
    v16 = "Error: CreateRequest failed in WinHttpOpenRequest";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
      6062342,
      v9,
      15,
      v11,
      (__int64)&v16,
      (__int64)&v18);
    std::wstring::~wstring(&v22);
  }
  if ( !*a4 )
    return GetLastError();
  if ( *((_BYTE *)this + 218) )
    *((_DWORD *)this + 52) |= 0x97E0C00u;
  if ( WinHttpSetStatusCallback(*a4, *((WINHTTP_STATUS_CALLBACK *)this + 30), *((_DWORD *)this + 52), 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    v12 = GetLastError();
    v15 = v12;
    if ( v12 )
    {
      v19 = "SH_ErrorCode";
      v20 = v12;
      v21 = 4;
      v22 = 0;
      v23 = 0;
      v24 = 7;
      LOWORD(v22) = 0;
      v18 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v16 = "Error: CreateRequest failed in WinHttpSetStatusCallback";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
        6062343,
        v13,
        15,
        v14,
        (__int64)&v16,
        (__int64)&v18);
      std::wstring::~wstring(&v22);
    }
    return v15;
  }
  else
  {
    Buffer = this;
    if ( !WinHttpSetOption(*a4, 0x2Du, &Buffer, 8u) )
      return GetLastError();
    if ( !a6 )
      CWinHttpHelperBase::SetCookies(this, *a4, a5);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800f02d0  push    rbp
0x1800f02d2  push    rbx
0x1800f02d3  push    rsi
0x1800f02d4  push    rdi
0x1800f02d5  push    r12
0x1800f02d7  push    r14
0x1800f02d9  push    r15
0x1800f02db  lea     rbp, [rsp-17h]
0x1800f02e0  sub     rsp, 90h
0x1800f02e7  mov     rax, cs:__security_cookie
0x1800f02ee  xor     rax, rsp
0x1800f02f1  mov     [rbp+47h+var_38], rax
0x1800f02f5  mov     rdi, r9
0x1800f02f8  mov     rbx, rcx
0x1800f02fb  mov     r14, [rbp+47h+arg_20]
0x1800f02ff  xor     r15d, r15d
0x1800f0302  test    r9, r9
0x1800f0305  jnz     short loc_1800F0310
0x1800f0307  lea     eax, [r9+57h]
0x1800f030b  jmp     loc_1800F04B5
0x1800f0310  mov     [r9], r15
0x1800f0313  mov     al, [rcx+0D8h]
0x1800f0319  neg     al
0x1800f031b  sbb     ecx, ecx
0x1800f031d  and     ecx, 800000h
0x1800f0323  mov     [rsp+0C0h+dwFlags], ecx; dwFlags
0x1800f0327  mov     [rsp+0C0h+ppwszAcceptTypes], r15; ppwszAcceptTypes
0x1800f032c  mov     [rsp+0C0h+pwszReferrer], r15; pwszReferrer
0x1800f0331  xor     r9d, r9d; pwszVersion
0x1800f0334  mov     rcx, [rbx+0B8h]; hConnect
0x1800f033b  call    cs:__imp_WinHttpOpenRequest
0x1800f0341  mov     [rdi], rax
0x1800f0344  call    cs:__imp_GetLastError
0x1800f034a  mov     esi, eax
0x1800f034c  lea     r12, aShErrorcode; "SH_ErrorCode"
0x1800f0353  mov     eax, 4
0x1800f0358  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x1800f035f  test    esi, esi
0x1800f0361  jz      short loc_1800F03C0
0x1800f0363  mov     [rbp+47h+var_68], r12
0x1800f0367  mov     [rbp+47h+var_60], esi
0x1800f036a  mov     [rbp+47h+var_5C], ax
0x1800f036e  xorps   xmm0, xmm0
0x1800f0371  movups  [rbp+47h+var_58], xmm0
0x1800f0375  mov     [rbp+47h+var_48], r15
0x1800f0379  mov     [rbp+47h+var_40], 7
0x1800f0381  mov     word ptr [rbp+47h+var_58], r15w
0x1800f0386  mov     [rbp+47h+var_70], rcx
0x1800f038a  lea     rax, aErrorCreatereq_0; "Error: CreateRequest failed in WinHttpO"...
0x1800f0391  mov     [rbp+47h+var_80], rax
0x1800f0395  lea     rax, [rbp+47h+var_70]
0x1800f0399  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x1800f039e  lea     rax, [rbp+47h+var_80]
0x1800f03a2  mov     [rsp+0C0h+pwszReferrer], rax
0x1800f03a7  mov     ecx, 5C8106h
0x1800f03ac  mov     r8d, 0Fh
0x1800f03b2  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800f03b7  lea     rcx, [rbp+47h+var_58]; void *
0x1800f03bb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f03c0  cmp     [rdi], r15
0x1800f03c3  jnz     short loc_1800F03D0
0x1800f03c5  call    cs:__imp_GetLastError
0x1800f03cb  jmp     loc_1800F04B5
0x1800f03d0  cmp     [rbx+0DAh], r15b
0x1800f03d7  jz      short loc_1800F03E3
0x1800f03d9  or      dword ptr [rbx+0D0h], 97E0C00h
0x1800f03e3  xor     r9d, r9d; dwReserved
0x1800f03e6  mov     r8d, [rbx+0D0h]; dwNotificationFlags
0x1800f03ed  mov     rdx, [rbx+0F0h]; lpfnInternetCallback
0x1800f03f4  mov     rcx, [rdi]; hInternet
0x1800f03f7  call    cs:__imp_WinHttpSetStatusCallback
0x1800f03fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f0401  jnz     short loc_1800F047C
0x1800f0403  call    cs:__imp_GetLastError
0x1800f0409  mov     ebx, eax
0x1800f040b  test    eax, eax
0x1800f040d  jz      short loc_1800F0478
0x1800f040f  mov     [rbp+47h+var_68], r12
0x1800f0413  mov     [rbp+47h+var_60], eax
0x1800f0416  mov     eax, 4
0x1800f041b  mov     [rbp+47h+var_5C], ax
0x1800f041f  xorps   xmm0, xmm0
0x1800f0422  movups  [rbp+47h+var_58], xmm0
0x1800f0426  mov     [rbp+47h+var_48], r15
0x1800f042a  mov     [rbp+47h+var_40], 7
0x1800f0432  mov     word ptr [rbp+47h+var_58], r15w
0x1800f0437  lea     rax, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x1800f043e  mov     [rbp+47h+var_70], rax
0x1800f0442  lea     rax, aErrorCreatereq; "Error: CreateRequest failed in WinHttpS"...
0x1800f0449  mov     [rbp+47h+var_80], rax
0x1800f044d  lea     rax, [rbp+47h+var_70]
0x1800f0451  mov     [rsp+0C0h+ppwszAcceptTypes], rax
0x1800f0456  lea     rax, [rbp+47h+var_80]
0x1800f045a  mov     [rsp+0C0h+pwszReferrer], rax
0x1800f045f  mov     ecx, 5C8107h
0x1800f0464  mov     r8d, 0Fh
0x1800f046a  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800f046f  lea     rcx, [rbp+47h+var_58]; void *
0x1800f0473  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f0478  mov     eax, ebx
0x1800f047a  jmp     short loc_1800F04B5
0x1800f047c  mov     [rbp+47h+Buffer], rbx
0x1800f0480  mov     r9d, 8; dwBufferLength
0x1800f0486  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x1800f048a  lea     edx, [r9+25h]; dwOption
0x1800f048e  mov     rcx, [rdi]; hInternet
0x1800f0491  call    cs:__imp_WinHttpSetOption
0x1800f0497  test    eax, eax
0x1800f0499  jz      loc_1800F03C5
0x1800f049f  cmp     [rbp+47h+arg_28], r15b
0x1800f04a3  jnz     short loc_1800F04B3
0x1800f04a5  mov     r8, r14; struct Mso::Http::IAuthHandler *
0x1800f04a8  mov     rdx, [rdi]; void *
0x1800f04ab  mov     rcx, rbx; this
0x1800f04ae  call    ?SetCookies@CWinHttpHelperBase@@AEAAKPEAXPEAVIAuthHandler@Http@Mso@@@Z; CWinHttpHelperBase::SetCookies(void *,Mso::Http::IAuthHandler *)
0x1800f04b3  mov     eax, esi
0x1800f04b5  mov     rcx, [rbp+47h+var_38]
0x1800f04b9  xor     rcx, rsp; StackCookie
0x1800f04bc  call    __security_check_cookie
0x1800f04c1  add     rsp, 90h
0x1800f04c8  pop     r15
0x1800f04ca  pop     r14
0x1800f04cc  pop     r12
0x1800f04ce  pop     rdi
0x1800f04cf  pop     rsi
0x1800f04d0  pop     rbx
0x1800f04d1  pop     rbp
0x1800f04d2  retn
```
