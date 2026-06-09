# _lambda_ddfb173e8f53b73a738df8ebe301e581_::operator()

- ea: `0x18000971c`
- end: `0x1800098be`
- name: `_lambda_ddfb173e8f53b73a738df8ebe301e581_::operator()`
- size: `418`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800096e8`

## callees

- `0x1800066d8`
- `0x180008554`
- `0x1800085c4`
- `0x1800085f4`
- `0x18000970c`
- `0x18000971c`
- `0x1800098c4`
- `0x180013b14`
- `0x180013e70`
- `0x1800150ec`
- `0x180015114`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009750`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000975a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000975a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800097d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800097d5`

## pseudocode

```c
__int64 __fastcall lambda_ddfb173e8f53b73a738df8ebe301e581_::operator()(__int64 a1)
{
  unsigned int LastError; // edi
  unsigned int SmartCardUserLogonCertificateHash; // ebx
  __int64 v4; // rax
  __int64 v6; // [rsp+20h] [rbp-58h] BYREF
  __int64 v7; // [rsp+28h] [rbp-50h] BYREF
  __int128 v8; // [rsp+38h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-30h]
  _BYTE v10[40]; // [rsp+50h] [rbp-28h] BYREF
  char v11; // [rsp+A0h] [rbp+28h] BYREF
  __int16 v12; // [rsp+A1h] [rbp+29h]
  unsigned int v13; // [rsp+A8h] [rbp+30h] BYREF
  int v14; // [rsp+ACh] [rbp+34h]
  __int64 v15; // [rsp+B0h] [rbp+38h] BYREF

  v13 = 0;
  v14 = 1;
  LastError = 0;
  if ( !**(_QWORD **)a1 )
    goto LABEL_15;
  if ( SetThreadToken(0, **(HANDLE **)(a1 + 8)) )
  {
    v12 = 258;
    std::vector<unsigned char>::vector<unsigned char>(&v6);
    SmartCardUserLogonCertificateHash = I_GetSmartCardUserLogonCertificateHash(&v6);
    v15 = SmartCardUserLogonCertificateHash | 0x200000000LL;
    if ( SmartCardUserLogonCertificateHash )
      errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>();
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v15);
    v13 = SmartCardUserLogonCertificateHash;
    v15 = 0x100000000LL;
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v15);
    v14 = 3;
    if ( SmartCardUserLogonCertificateHash )
      goto LABEL_12;
    if ( v6 == v7 )
    {
      LastError = 0;
    }
    else
    {
      RevertToSelf();
      HIBYTE(v12) = 0;
      v15 = (__int64)&v8;
      v8 = 0;
      v9 = 0;
      std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(&v8, v7 - v6, &v6, &v7);
      v4 = std::wstring::wstring(v10, **(_QWORD **)a1);
      LastError = I_AddHashToUserDB(v4, (__int64)&v8);
      v15 = LastError | 0x200000000LL;
      if ( LastError )
        errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>();
      errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v15);
      v13 = LastError;
      v15 = 0x300000000LL;
      errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v15);
      v14 = 3;
      if ( LastError )
      {
        SmartCardUserLogonCertificateHash = LastError;
LABEL_12:
        std::vector<unsigned char>::_Tidy(&v6);
        wil::details::ScopeExitFnGuard__lambda_a83eb169826cf6e0f926cd4de2b91688___::operator()(&v11);
        return SmartCardUserLogonCertificateHash;
      }
    }
    std::vector<unsigned char>::_Tidy(&v6);
    wil::details::ScopeExitFnGuard__lambda_a83eb169826cf6e0f926cd4de2b91688___::operator()(&v11);
LABEL_15:
    errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v13);
    v14 = 4;
    goto LABEL_16;
  }
  LastError = GetLastError();
LABEL_16:
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v13);
  return LastError;
}

```

## disassembly

```asm
0x18000971c  push    rbp
0x18000971e  push    rbx
0x18000971f  push    rsi
0x180009720  push    rdi
0x180009721  mov     rbp, rsp
0x180009724  sub     rsp, 78h
0x180009728  mov     rsi, rcx
0x18000972b  mov     [rbp+arg_8], 0
0x180009732  mov     [rbp+arg_C], 1
0x180009739  xor     edi, edi
0x18000973b  mov     rax, [rcx]
0x18000973e  cmp     [rax], rdi
0x180009741  jz      loc_18000989A
0x180009747  mov     rdx, [rcx+8]
0x18000974b  mov     rdx, [rdx]; Token
0x18000974e  xor     ecx, ecx; Thread
0x180009750  call    cs:__imp_SetThreadToken
0x180009756  test    eax, eax
0x180009758  jnz     short loc_180009767
0x18000975a  call    cs:__imp_GetLastError
0x180009760  mov     edi, eax
0x180009762  jmp     loc_1800098AA
0x180009767  mov     [rbp+arg_1], 102h
0x18000976d  lea     rcx, [rbp+var_58]
0x180009771  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x180009776  nop
0x180009777  lea     rcx, [rbp+var_58]
0x18000977b  call    ?I_GetSmartCardUserLogonCertificateHash@@YAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; I_GetSmartCardUserLogonCertificateHash(std::vector<uchar> &)
0x180009780  mov     ebx, eax
0x180009782  mov     dword ptr [rbp+arg_10], eax
0x180009785  mov     dword ptr [rbp+arg_10+4], 2
0x18000978c  test    eax, eax
0x18000978e  jz      short loc_180009795
0x180009790  call    ??$error_received@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x180009795  lea     rcx, [rbp+arg_10]
0x180009799  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x18000979e  mov     [rbp+arg_8], ebx
0x1800097a1  mov     dword ptr [rbp+arg_10], 0
0x1800097a8  mov     dword ptr [rbp+arg_10+4], 1
0x1800097af  lea     rcx, [rbp+arg_10]
0x1800097b3  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800097b8  mov     [rbp+arg_C], 3
0x1800097bf  test    ebx, ebx
0x1800097c1  jnz     loc_18000986D
0x1800097c7  mov     rax, [rbp+var_50]
0x1800097cb  cmp     [rbp+var_58], rax
0x1800097cf  jz      loc_180009885
0x1800097d5  call    cs:__imp_RevertToSelf
0x1800097db  mov     byte ptr [rbp+arg_1+1], bl
0x1800097de  lea     rax, [rbp+var_40]
0x1800097e2  mov     [rbp+arg_10], rax
0x1800097e6  xorps   xmm0, xmm0
0x1800097e9  movdqu  [rbp+var_40], xmm0
0x1800097ee  mov     [rbp+var_30], 0
0x1800097f6  mov     rdx, [rbp+var_50]
0x1800097fa  sub     rdx, [rbp+var_58]
0x1800097fe  lea     r9, [rbp+var_50]
0x180009802  lea     r8, [rbp+var_58]
0x180009806  lea     rcx, [rbp+var_40]
0x18000980a  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x18000980f  nop
0x180009810  mov     rdx, [rsi]
0x180009813  mov     rdx, [rdx]
0x180009816  lea     rcx, [rbp+var_28]
0x18000981a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000981f  nop
0x180009820  lea     rdx, [rbp+var_40]
0x180009824  mov     rcx, rax
0x180009827  call    ?I_AddHashToUserDB@@YAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@EV?$allocator@E@std@@@2@@Z; I_AddHashToUserDB(std::wstring,std::vector<uchar>)
0x18000982c  mov     edi, eax
0x18000982e  mov     dword ptr [rbp+arg_10], eax
0x180009831  mov     dword ptr [rbp+arg_10+4], 2
0x180009838  test    eax, eax
0x18000983a  jz      short loc_180009841
0x18000983c  call    ??$error_received@V?$scoped_error@Utag@winerror_error@@@errorlib@@@errorlib@@YAXAEBV?$scoped_error@Utag@winerror_error@@@0@AEBUtag@winerror_error@@@Z; errorlib::error_received<errorlib::scoped_error<winerror_error::tag>>(errorlib::scoped_error<winerror_error::tag> const &,winerror_error::tag const &)
0x180009841  lea     rcx, [rbp+arg_10]
0x180009845  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x18000984a  mov     [rbp+arg_8], edi
0x18000984d  mov     dword ptr [rbp+arg_10], ebx
0x180009850  mov     dword ptr [rbp+arg_10+4], 3
0x180009857  lea     rcx, [rbp+arg_10]
0x18000985b  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180009860  mov     [rbp+arg_C], 3
0x180009867  test    edi, edi
0x180009869  jz      short loc_180009887
0x18000986b  mov     ebx, edi
0x18000986d  lea     rcx, [rbp+var_58]
0x180009871  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180009876  nop
0x180009877  lea     rcx, [rbp+arg_0]
0x18000987b  call    wil__details__ScopeExitFnGuard__lambda_a83eb169826cf6e0f926cd4de2b91688_____operator__
0x180009880  nop
0x180009881  mov     eax, ebx
0x180009883  jmp     short loc_1800098B5
0x180009885  mov     edi, ebx
0x180009887  lea     rcx, [rbp+var_58]
0x18000988b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180009890  nop
0x180009891  lea     rcx, [rbp+arg_0]
0x180009895  call    wil__details__ScopeExitFnGuard__lambda_a83eb169826cf6e0f926cd4de2b91688_____operator__
0x18000989a  lea     rcx, [rbp+arg_8]
0x18000989e  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800098a3  mov     [rbp+arg_C], 4
0x1800098aa  lea     rcx, [rbp+arg_8]
0x1800098ae  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800098b3  mov     eax, edi
0x1800098b5  add     rsp, 78h
0x1800098b9  pop     rdi
0x1800098ba  pop     rsi
0x1800098bb  pop     rbx
0x1800098bc  pop     rbp
0x1800098bd  retn
```
