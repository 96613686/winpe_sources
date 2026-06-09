# NTSamAuthentication::storeTokenSID(IASTL::IASRequest &,void *)

- ea: `0x18000f890`
- end: `0x18000fb7c`
- name: `?storeTokenSID@NTSamAuthentication@@CAXAEAVIASRequest@IASTL@@PEAX@Z`
- size: `748`
- prototype: `static void(struct IASTL::IASRequest *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f544`

## callees

- `0x180001c88`
- `0x18000342c`
- `0x18000a760`
- `0x18000b484`
- `0x18000c808`
- `0x18000d49c`
- `0x18000f890`
- `0x180016938`
- `0x1800254a0`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!free` at `0x18000fb57`
- `msvcrt!free` at `0x18000fb57`
- `KERNEL32!GetLastError` at `0x18000f8f6`
- `KERNEL32!GetLastError` at `0x18000f9f6`
- `KERNEL32!GetLastError` at `0x18000f8f6`
- `KERNEL32!GetLastError` at `0x18000f9f6`
- `ADVAPI32!GetTokenInformation` at `0x18000f8f0`
- `ADVAPI32!GetTokenInformation` at `0x18000f9e8`
- `ADVAPI32!GetTokenInformation` at `0x18000f8f0`
- `ADVAPI32!GetTokenInformation` at `0x18000f9e8`

## string_xrefs

- `0x18000f95b`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000fa52`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000fb0f`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18000f94a`: `GetTokenInformation`
- `0x18000fa41`: `GetTokenInformation`
- `0x18000fafe`: `IASStoreAccountSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NTSamAuthentication::storeTokenSID(struct IAttributesRaw **a1, void *a2)
{
  DWORD LastError; // eax
  const struct std::nothrow_t *v5; // rdx
  signed int v6; // ebx
  unsigned int v7; // eax
  void **v8; // rbx
  int v9; // ebx
  unsigned int v10; // eax
  signed int v11; // eax
  int v12; // edi
  unsigned int v13; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void **v15; // [rsp+38h] [rbp-C8h]
  char Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !IASPeekAttribute(a1[1], 8161, 6) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength);
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 122 )
    {
      v7 = IASFormatSysErr(LastError, Buffer);
      if ( v7 < 0x100uLL )
      {
        Buffer[v7] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"GetTokenInformation", (__int64)Buffer);
        }
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        _com_issue_error(v6);
      }
      _report_rangecheckfailure();
    }
    v8 = (void **)operator new[](TokenInformationLength, v5);
    v15 = v8;
    if ( !v8 )
      _com_issue_error(-2147024882);
    if ( !GetTokenInformation(a2, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      v9 = GetLastError();
      v10 = IASFormatSysErr(v9, Buffer);
      if ( v10 < 0x100uLL )
      {
        Buffer[v10] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"GetTokenInformation", (__int64)Buffer);
        }
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        _com_issue_error(v9);
      }
      _report_rangecheckfailure();
    }
    v11 = IASStoreAccountSID(a1[1], 0x1FE1u, *v8);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = IASFormatSysErr(v11, Buffer);
      if ( v13 < 0x100uLL )
      {
        Buffer[v13] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"IASStoreAccountSID", (__int64)Buffer);
        }
        _com_issue_error(v12);
      }
      _report_rangecheckfailure();
    }
    free(v8);
  }
}

```

## disassembly

```asm
0x18000f890  mov     [rsp-8+arg_10], rbx
0x18000f895  push    rbp
0x18000f896  push    rsi
0x18000f897  push    rdi
0x18000f898  lea     rbp, [rsp-50h]
0x18000f89d  sub     rsp, 150h
0x18000f8a4  mov     rax, cs:__security_cookie
0x18000f8ab  xor     rax, rsp
0x18000f8ae  mov     [rbp+60h+var_20], rax
0x18000f8b2  mov     rdi, rdx
0x18000f8b5  mov     rsi, rcx
0x18000f8b8  mov     edx, 1FE1h
0x18000f8bd  mov     r8d, 6
0x18000f8c3  mov     rcx, [rcx+8]
0x18000f8c7  call    ?IASPeekAttribute@@YAPEAU_IASATTRIBUTE@@PEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASPeekAttribute(IAttributesRaw *,ulong,IASTYPEENUM)
0x18000f8cc  test    rax, rax
0x18000f8cf  jnz     loc_18000FB5D
0x18000f8d5  mov     [rsp+160h+TokenInformationLength], eax
0x18000f8d9  lea     rax, [rsp+160h+TokenInformationLength]
0x18000f8de  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18000f8e3  xor     r9d, r9d; TokenInformationLength
0x18000f8e6  xor     r8d, r8d; TokenInformation
0x18000f8e9  lea     edx, [r9+1]; TokenInformationClass
0x18000f8ed  mov     rcx, rdi; TokenHandle
0x18000f8f0  call    cs:__imp_GetTokenInformation
0x18000f8f6  call    cs:__imp_GetLastError
0x18000f8fc  mov     ebx, eax
0x18000f8fe  cmp     eax, 7Ah ; 'z'
0x18000f901  jz      loc_18000F9AD
0x18000f907  lea     rdx, [rsp+160h+Buffer]; Buffer
0x18000f90c  mov     ecx, eax; dwMessageId
0x18000f90e  call    IASFormatSysErr
0x18000f913  mov     eax, eax
0x18000f915  cmp     rax, 100h
0x18000f91b  jnb     loc_18000F9A7
0x18000f921  mov     [rsp+rax+160h+Buffer], 0
0x18000f926  lea     rax, WPP_GLOBAL_Control
0x18000f92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f934  cmp     rcx, rax
0x18000f937  jz      short loc_18000F992
0x18000f939  cmp     byte ptr [rcx+19h], 2
0x18000f93d  jb      short loc_18000F992
0x18000f93f  test    byte ptr [rcx+1Ch], 4
0x18000f943  jz      short loc_18000F992
0x18000f945  lea     r9, [rsp+160h+Buffer]
0x18000f94a  lea     rdi, aGettokeninform; "GetTokenInformation"
0x18000f951  mov     r8, rdi
0x18000f954  lea     rdx, aNpssvc; "NPSSVC"
0x18000f95b  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000f962  call    WppDbgPrint
0x18000f967  mov     edx, 12h
0x18000f96c  lea     rax, [rsp+160h+Buffer]
0x18000f971  mov     [rsp+160h+var_138], rax; __int64
0x18000f976  mov     [rsp+160h+ReturnLength], rdi; __int64
0x18000f97b  lea     r8, WPP_ef5de34208083dee9ce33f3a59973eaa_Traceguids
0x18000f982  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f989  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f98d  call    WPP_SF_sss
0x18000f992  test    ebx, ebx
0x18000f994  jle     short loc_18000F99F
0x18000f996  movzx   ebx, bx
0x18000f999  or      ebx, 80070000h
0x18000f99f  mov     ecx, ebx; int
0x18000f9a1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f9a7  call    __report_rangecheckfailure
0x18000f9ad  mov     ecx, [rsp+160h+TokenInformationLength]; Size
0x18000f9b1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f9b6  mov     rbx, rax
0x18000f9b9  mov     [rsp+160h+var_128], rax
0x18000f9be  test    rax, rax
0x18000f9c1  jnz     short loc_18000F9CE
0x18000f9c3  mov     ecx, 8007000Eh; int
0x18000f9c8  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000f9ce  lea     rax, [rsp+160h+TokenInformationLength]
0x18000f9d3  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18000f9d8  mov     r9d, [rsp+160h+TokenInformationLength]; TokenInformationLength
0x18000f9dd  mov     r8, rbx; TokenInformation
0x18000f9e0  mov     edx, 1; TokenInformationClass
0x18000f9e5  mov     rcx, rdi; TokenHandle
0x18000f9e8  call    cs:__imp_GetTokenInformation
0x18000f9ee  test    eax, eax
0x18000f9f0  jnz     loc_18000FAA4
0x18000f9f6  call    cs:__imp_GetLastError
0x18000f9fc  mov     ebx, eax
0x18000f9fe  lea     rdx, [rsp+160h+Buffer]; Buffer
0x18000fa03  mov     ecx, eax; dwMessageId
0x18000fa05  call    IASFormatSysErr
0x18000fa0a  mov     eax, eax
0x18000fa0c  cmp     rax, 100h
0x18000fa12  jnb     loc_18000FA9E
0x18000fa18  mov     [rsp+rax+160h+Buffer], 0
0x18000fa1d  lea     rax, WPP_GLOBAL_Control
0x18000fa24  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa2b  cmp     rcx, rax
0x18000fa2e  jz      short loc_18000FA89
0x18000fa30  cmp     byte ptr [rcx+19h], 2
0x18000fa34  jb      short loc_18000FA89
0x18000fa36  test    byte ptr [rcx+1Ch], 4
0x18000fa3a  jz      short loc_18000FA89
0x18000fa3c  lea     r9, [rsp+160h+Buffer]
0x18000fa41  lea     rdi, aGettokeninform; "GetTokenInformation"
0x18000fa48  mov     r8, rdi
0x18000fa4b  lea     rdx, aNpssvc; "NPSSVC"
0x18000fa52  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000fa59  call    WppDbgPrint
0x18000fa5e  mov     edx, 13h
0x18000fa63  lea     rax, [rsp+160h+Buffer]
0x18000fa68  mov     [rsp+160h+var_138], rax; __int64
0x18000fa6d  mov     [rsp+160h+ReturnLength], rdi; __int64
0x18000fa72  lea     r8, WPP_ef5de34208083dee9ce33f3a59973eaa_Traceguids
0x18000fa79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa80  mov     rcx, [rcx+10h]; LoggerHandle
0x18000fa84  call    WPP_SF_sss
0x18000fa89  test    ebx, ebx
0x18000fa8b  jle     short loc_18000FA96
0x18000fa8d  movzx   ebx, bx
0x18000fa90  or      ebx, 80070000h
0x18000fa96  mov     ecx, ebx; int
0x18000fa98  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000fa9e  call    __report_rangecheckfailure
0x18000faa4  mov     r8, [rbx]; void *
0x18000faa7  mov     edx, 1FE1h; unsigned int
0x18000faac  mov     rcx, [rsi+8]; struct IAttributesRaw *
0x18000fab0  call    ?IASStoreAccountSID@@YAJPEAUIAttributesRaw@@KPEAX@Z; IASStoreAccountSID(IAttributesRaw *,ulong,void *)
0x18000fab5  mov     edi, eax
0x18000fab7  test    eax, eax
0x18000fab9  jns     loc_18000FB54
0x18000fabf  lea     rdx, [rsp+160h+Buffer]; Buffer
0x18000fac4  mov     ecx, eax; dwMessageId
0x18000fac6  call    IASFormatSysErr
0x18000facb  mov     eax, eax
0x18000facd  cmp     rax, 100h
0x18000fad3  jnb     short loc_18000FB4E
0x18000fad5  mov     [rsp+rax+160h+Buffer], 0
0x18000fada  lea     rax, WPP_GLOBAL_Control
0x18000fae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fae8  cmp     rcx, rax
0x18000faeb  jz      short loc_18000FB46
0x18000faed  cmp     byte ptr [rcx+19h], 2
0x18000faf1  jb      short loc_18000FB46
0x18000faf3  test    byte ptr [rcx+1Ch], 4
0x18000faf7  jz      short loc_18000FB46
0x18000faf9  lea     r9, [rsp+160h+Buffer]
0x18000fafe  lea     rbx, aIasstoreaccoun; "IASStoreAccountSID"
0x18000fb05  mov     r8, rbx
0x18000fb08  lea     rdx, aNpssvc; "NPSSVC"
0x18000fb0f  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18000fb16  call    WppDbgPrint
0x18000fb1b  mov     edx, 14h
0x18000fb20  lea     rax, [rsp+160h+Buffer]
0x18000fb25  mov     [rsp+160h+var_138], rax; __int64
0x18000fb2a  mov     [rsp+160h+ReturnLength], rbx; __int64
0x18000fb2f  lea     r8, WPP_ef5de34208083dee9ce33f3a59973eaa_Traceguids
0x18000fb36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb3d  mov     rcx, [rcx+10h]; LoggerHandle
0x18000fb41  call    WPP_SF_sss
0x18000fb46  mov     ecx, edi; int
0x18000fb48  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18000fb4e  call    __report_rangecheckfailure
0x18000fb54  mov     rcx, rbx; Block
0x18000fb57  call    cs:__imp_free
0x18000fb5d  mov     rcx, [rbp+60h+var_20]
0x18000fb61  xor     rcx, rsp; StackCookie
0x18000fb64  call    __security_check_cookie
0x18000fb69  mov     rbx, [rsp+160h+arg_10]
0x18000fb71  add     rsp, 150h
0x18000fb78  pop     rdi
0x18000fb79  pop     rsi
0x18000fb7a  pop     rbp
0x18000fb7b  retn
```
