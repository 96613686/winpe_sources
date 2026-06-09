# CHttpParameters::CHttpParameters(CHttpParameters const &)

- ea: `0x18002776c`
- end: `0x18002794d`
- name: `??0CHttpParameters@@QEAA@AEBV0@@Z`
- size: `481`
- prototype: `CHttpParameters *__fastcall(CHttpParameters *__hidden this, const struct CHttpParameters *)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027a18`
- `0x18002a08c`
- `0x18005f4f8`
- `0x1800944a8`
- `0x1800bb160`

## callees

- `0x1800190d4`
- `0x18001d5fc`
- `0x18002776c`
- `0x180039b68`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002780e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027886`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002780e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800278be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800278be`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180027856`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180027856`
- `CRYPT32!CertFreeCertificateContext` at `0x1800278b6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800278b6`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180027895`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180027895`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CHttpParameters *__fastcall CHttpParameters::CHttpParameters(CHttpParameters *this, const struct CHttpParameters *a2)
{
  char *v4; // r15
  char *v5; // r12
  void *v6; // rbp
  DWORD LastError; // ebx
  void *v8; // rcx
  const char *v9; // r9
  const CERT_CONTEXT *v10; // rcx
  PCCERT_CONTEXT v11; // rbp
  const CERT_CONTEXT *v12; // r14
  DWORD v13; // ebx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  HANDLE hObject; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)this = 0;
  v4 = (char *)this + 8;
  *(_OWORD *)((char *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 15;
  *((_BYTE *)this + 8) = 0;
  v5 = (char *)this + 40;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 15;
  *((_BYTE *)this + 40) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 21) = 1;
  v6 = *(void **)this;
  if ( *(_QWORD *)this && v6 != (void *)-1LL )
  {
    LastError = GetLastError();
    CloseHandle(v6);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v8 = *(void **)a2;
  if ( *(_QWORD *)a2 && v8 != (void *)-1LL )
  {
    hObject = 0;
    if ( !DuplicateTokenEx(v8, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x24,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\HttpParameters.h",
        v9);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      this,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  v10 = (const CERT_CONTEXT *)*((_QWORD *)a2 + 9);
  if ( v10 )
    v11 = CertDuplicateCertificateContext(v10);
  else
    v11 = 0;
  v12 = (const CERT_CONTEXT *)*((_QWORD *)this + 9);
  if ( v12 )
  {
    v13 = GetLastError();
    CertFreeCertificateContext(v12);
    SetLastError(v13);
  }
  *((_QWORD *)this + 9) = v11;
  v14 = (_QWORD *)((char *)a2 + 8);
  if ( v4 != (char *)a2 + 8 )
  {
    if ( *((_QWORD *)a2 + 4) > 0xFu )
      v14 = (_QWORD *)*v14;
    std::string::assign(v4, v14, *((_QWORD *)a2 + 3));
  }
  v15 = (_QWORD *)((char *)a2 + 40);
  if ( v5 != (char *)a2 + 40 )
  {
    if ( *((_QWORD *)a2 + 8) > 0xFu )
      v15 = (_QWORD *)*v15;
    std::string::assign(v5, v15, *((_QWORD *)a2 + 7));
  }
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
  *((_DWORD *)this + 21) = *((_DWORD *)a2 + 21);
  return this;
}

```

## disassembly

```asm
0x18002776c  mov     [rsp+arg_10], rbx
0x180027771  mov     [rsp+arg_18], rbp
0x180027776  push    rsi
0x180027777  push    rdi
0x180027778  push    r12
0x18002777a  push    r14
0x18002777c  push    r15
0x18002777e  sub     rsp, 50h
0x180027782  mov     rax, cs:__security_cookie
0x180027789  xor     rax, rsp
0x18002778c  mov     [rsp+78h+var_38], rax
0x180027791  mov     rsi, rdx
0x180027794  mov     rdi, rcx
0x180027797  mov     [rsp+78h+var_48], rcx
0x18002779c  mov     qword ptr [rcx], 0
0x1800277a3  lea     r15, [rcx+8]
0x1800277a7  xorps   xmm0, xmm0
0x1800277aa  movups  xmmword ptr [r15], xmm0
0x1800277ae  mov     qword ptr [r15+10h], 0
0x1800277b6  mov     eax, 0Fh
0x1800277bb  mov     [r15+18h], rax
0x1800277bf  mov     byte ptr [r15], 0
0x1800277c3  lea     r12, [rcx+28h]
0x1800277c7  movups  xmmword ptr [r12], xmm0
0x1800277cc  mov     qword ptr [r12+10h], 0
0x1800277d5  mov     [r12+18h], rax
0x1800277da  mov     byte ptr [r12], 0
0x1800277df  mov     qword ptr [rcx+48h], 0
0x1800277e7  mov     dword ptr [rcx+50h], 0
0x1800277ee  mov     dword ptr [rcx+54h], 1
0x1800277f5  mov     rbp, [rcx]
0x1800277f8  test    rbp, rbp
0x1800277fb  jz      short loc_18002781C
0x1800277fd  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180027801  jz      short loc_18002781C
0x180027803  call    cs:__imp_GetLastError
0x180027809  mov     ebx, eax
0x18002780b  mov     rcx, rbp; hObject
0x18002780e  call    cs:__imp_CloseHandle
0x180027814  mov     ecx, ebx; dwErrCode
0x180027816  call    cs:__imp_SetLastError
0x18002781c  mov     qword ptr [rdi], 0
0x180027823  mov     rcx, [rsi]; hExistingToken
0x180027826  test    rcx, rcx
0x180027829  jz      short loc_18002788C
0x18002782b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002782f  jz      short loc_18002788C
0x180027831  mov     [rsp+78h+hObject], 0
0x18002783a  lea     rax, [rsp+78h+hObject]
0x18002783f  mov     [rsp+78h+phNewToken], rax; phNewToken
0x180027844  mov     r9d, 2; ImpersonationLevel
0x18002784a  mov     [rsp+78h+TokenType], r9d; TokenType
0x18002784f  xor     r8d, r8d; lpTokenAttributes
0x180027852  lea     edx, [r9+0Ch]; dwDesiredAccess
0x180027856  call    cs:__imp_DuplicateTokenEx
0x18002785c  mov     rcx, [rsp+78h]; this
0x180027861  test    eax, eax
0x180027863  jz      loc_18002793B
0x180027869  lea     rdx, [rsp+78h+hObject]
0x18002786e  mov     rcx, rdi
0x180027871  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180027876  nop
0x180027877  mov     rcx, [rsp+78h+hObject]; hObject
0x18002787c  lea     rax, [rcx-1]
0x180027880  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180027884  ja      short loc_18002788C
0x180027886  call    cs:__imp_CloseHandle
0x18002788c  mov     rcx, [rsi+48h]; pCertContext
0x180027890  test    rcx, rcx
0x180027893  jz      short loc_1800278A0
0x180027895  call    cs:__imp_CertDuplicateCertificateContext
0x18002789b  mov     rbp, rax
0x18002789e  jmp     short loc_1800278A2
0x1800278a0  xor     ebp, ebp
0x1800278a2  mov     r14, [rdi+48h]
0x1800278a6  test    r14, r14
0x1800278a9  jz      short loc_1800278C4
0x1800278ab  call    cs:__imp_GetLastError
0x1800278b1  mov     ebx, eax
0x1800278b3  mov     rcx, r14; pCertContext
0x1800278b6  call    cs:__imp_CertFreeCertificateContext
0x1800278bc  mov     ecx, ebx; dwErrCode
0x1800278be  call    cs:__imp_SetLastError
0x1800278c4  mov     [rdi+48h], rbp
0x1800278c8  lea     rdx, [rsi+8]
0x1800278cc  cmp     r15, rdx
0x1800278cf  jz      short loc_1800278E7
0x1800278d1  mov     r8, [rdx+10h]; Size
0x1800278d5  cmp     qword ptr [rdx+18h], 0Fh
0x1800278da  jbe     short loc_1800278DF
0x1800278dc  mov     rdx, [rdx]; Src
0x1800278df  mov     rcx, r15; void *
0x1800278e2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800278e7  lea     rdx, [rsi+28h]
0x1800278eb  cmp     r12, rdx
0x1800278ee  jz      short loc_180027906
0x1800278f0  mov     r8, [rdx+10h]; Size
0x1800278f4  cmp     qword ptr [rdx+18h], 0Fh
0x1800278f9  jbe     short loc_1800278FE
0x1800278fb  mov     rdx, [rdx]; Src
0x1800278fe  mov     rcx, r12; void *
0x180027901  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180027906  mov     ecx, [rsi+50h]
0x180027909  mov     [rdi+50h], ecx
0x18002790c  mov     ecx, [rsi+54h]
0x18002790f  mov     [rdi+54h], ecx
0x180027912  mov     rax, rdi
0x180027915  mov     rcx, [rsp+78h+var_38]
0x18002791a  xor     rcx, rsp; StackCookie
0x18002791d  call    __security_check_cookie
0x180027922  lea     r11, [rsp+78h+var_28]
0x180027927  mov     rbx, [r11+40h]
0x18002792b  mov     rbp, [r11+48h]
0x18002792f  mov     rsp, r11
0x180027932  pop     r15
0x180027934  pop     r14
0x180027936  pop     r12
0x180027938  pop     rdi
0x180027939  pop     rsi
0x18002793a  retn
0x18002793b  lea     r8, aCW1SSrcDeliver_103; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180027942  mov     edx, 24h ; '$'; void *
0x180027947  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
