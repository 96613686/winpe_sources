# CSharedMemoryBlock::InitUnMarshal(void *,ulong,ulong)

- ea: `0x180034698`
- end: `0x180034aa6`
- name: `?InitUnMarshal@CSharedMemoryBlock@@QEAAJPEAXKK@Z`
- size: `1038`
- prototype: `__int64 __fastcall(LPHANDLE lpTargetHandle, HANDLE hSourceHandle, DWORD dwProcessId, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f5cc`

## callees

- `0x180034698`
- `0x180034ad8`
- `0x18003f54c`
- `0x18003f62c`
- `0x180042800`
- `0x180043100`
- `0x18004388c`
- `0x18004a0a0`
- `0x18004a0c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348ea`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800348a4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800348a4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180034a0f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180034a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003470b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003470b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800346da`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180034718`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800346da`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180034718`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800347e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800347e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034880`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003479b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003479b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800349af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800349af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003476d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003483e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003476d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003483e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034857`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800349c9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180034857`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800349c9`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800348e4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180034975`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800348e4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180034975`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003491f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003491f`

## string_xrefs

- `0x1800346ed`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x18003477b`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x1800347b8`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x1800347f5`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x180034865`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x1800348f9`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x180034940`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`
- `0x180034988`: `onecoreuap\com\coml2\stg\docfile\smblock.cxx`

## pseudocode

```c
__int64 __fastcall CSharedMemoryBlock::InitUnMarshal(
        LPHANDLE lpTargetHandle,
        HANDLE hSourceHandle,
        DWORD dwProcessId,
        int a4)
{
  __int64 v8; // rdx
  unsigned int LastError; // edi
  DWORD CurrentProcessId; // eax
  const char *v11; // r9
  HANDLE v13; // rbx
  const char *v14; // r9
  const char *v15; // r9
  __int64 v16; // rdx
  HANDLE CurrentProcess; // rax
  CSharedMemoryBlock **v18; // rax
  HANDLE v19; // rcx
  CSharedMemoryBlock *v20; // rbx
  const char *v21; // r9
  PSECURITY_DESCRIPTOR v22; // rdi
  __int64 v23; // rdx
  const char *v24; // r9
  __int64 v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nLengthNeeded; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR v34; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v35; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pSessionId; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v37; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+64h] [rbp-9Ch] BYREF
  PSID pOwner; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v40[2]; // [rsp+70h] [rbp-90h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  PSID pSid1[12]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  pSessionId = 0;
  if ( ProcessIdToSessionId(dwProcessId, &pSessionId) )
  {
    v35 = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &v35) )
    {
      v8 = 243;
      goto LABEL_3;
    }
    if ( pSessionId != v35 )
    {
      v8 = 245;
      goto LABEL_3;
    }
    memset_0(TokenInformation, 0, 0x58u);
    v37 = 0;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, TokenInformation, 0x54u, &v37) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xFF,
               (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
               v11);
    v13 = OpenProcess(0x1040u, 0, dwProcessId);
    v40[0] = v13;
    if ( (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x102,
                    (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
                    v14);
LABEL_45:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v40);
      return LastError;
    }
    TokenHandle = 0;
    if ( !OpenProcessToken(v13, 8u, &TokenHandle) )
    {
      v16 = 270;
LABEL_14:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v16,
                    (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
                    v15);
LABEL_15:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_45;
    }
    memset_0(pSid1, 0, 0x58u);
    if ( !GetTokenInformation(TokenHandle, TokenUser, pSid1, 0x54u, &v37) )
    {
      v16 = 279;
      goto LABEL_14;
    }
    if ( !EqualSid(pSid1[0], TokenInformation[0]) )
    {
      LastError = -2147024891;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
        (const char *)0x80070005LL,
        ReturnLengtha);
      goto LABEL_15;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v13, hSourceHandle, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
    {
      v16 = 284;
      goto LABEL_14;
    }
    v18 = (CSharedMemoryBlock **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                   &v34,
                                   lpTargetHandle);
    v19 = *lpTargetHandle;
    v20 = *v18;
    nLengthNeeded = 0;
    GetKernelObjectSecurity(v19, 1u, 0, 0, &nLengthNeeded);
    if ( GetLastError() != 122 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x12C,
                    (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
                    v21);
LABEL_24:
      CSharedMemoryBlock::CloseMapping(v20);
      goto LABEL_15;
    }
    v34 = LocalAlloc(0, nLengthNeeded);
    v22 = v34;
    if ( !v34 )
    {
      LastError = -2147024882;
      v23 = 304;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
        (const char *)LastError,
        ReturnLengthb);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
      goto LABEL_24;
    }
    if ( GetKernelObjectSecurity(*lpTargetHandle, 1u, v34, nLengthNeeded, &nLengthNeeded) )
    {
      pOwner = 0;
      bOwnerDefaulted = 0;
      if ( GetSecurityDescriptorOwner(v22, &pOwner, &bOwnerDefaulted) )
      {
        if ( !EqualSid(pOwner, TokenInformation[0]) )
        {
          LastError = -2147024891;
          v23 = 313;
          goto LABEL_27;
        }
        if ( bOwnerDefaulted )
        {
          LastError = -2147024891;
          v23 = 314;
          goto LABEL_27;
        }
        v26 = MapViewOfFileEx(*lpTargetHandle, 6u, 0, 0, 0, 0);
        lpTargetHandle[1] = v26;
        v27 = v26;
        if ( v26 )
        {
          v28 = v26[1] - *(_QWORD *)&GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac.Data1;
          if ( !v28 )
            v28 = v27[2] - *(_QWORD *)GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac.Data4;
          if ( !v28 )
          {
            *((_DWORD *)lpTargetHandle + 4) = *(_DWORD *)v27;
            *((_DWORD *)lpTargetHandle + 5) = a4;
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v34);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            LastError = 0;
            goto LABEL_45;
          }
          LastError = -2147024891;
          v23 = 324;
          goto LABEL_27;
        }
        v25 = 320;
      }
      else
      {
        v25 = 311;
      }
    }
    else
    {
      v25 = 307;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v25,
                  (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
                  v24);
    goto LABEL_28;
  }
  v8 = 240;
LABEL_3:
  LastError = -2147024891;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\com\\coml2\\stg\\docfile\\smblock.cxx",
    (const char *)0x80070005LL,
    ReturnLength);
  return LastError;
}

```

## disassembly

```asm
0x180034698  mov     [rsp-8+arg_18], rbx
0x18003469d  push    rbp
0x18003469e  push    rsi
0x18003469f  push    rdi
0x1800346a0  push    r14
0x1800346a2  push    r15
0x1800346a4  lea     rbp, [rsp-50h]
0x1800346a9  sub     rsp, 150h
0x1800346b0  mov     rax, cs:__security_cookie
0x1800346b7  xor     rax, rsp
0x1800346ba  mov     [rbp+70h+var_30], rax
0x1800346be  mov     rdi, rdx
0x1800346c1  mov     rsi, rcx
0x1800346c4  xor     r15d, r15d
0x1800346c7  lea     rdx, [rsp+170h+pSessionId]; pSessionId
0x1800346cc  mov     ecx, r8d; dwProcessId
0x1800346cf  mov     [rsp+170h+pSessionId], r15d
0x1800346d4  mov     r14d, r9d
0x1800346d7  mov     ebx, r8d
0x1800346da  call    cs:__imp_ProcessIdToSessionId
0x1800346e0  test    eax, eax
0x1800346e2  jnz     short loc_180034706
0x1800346e4  mov     edx, 0F0h; void *
0x1800346e9  mov     rcx, [rbp+78h]; this
0x1800346ed  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x1800346f4  mov     edi, 80070005h
0x1800346f9  mov     r9d, edi; char *
0x1800346fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034701  jmp     loc_180034A81
0x180034706  mov     [rsp+170h+var_118], r15d
0x18003470b  call    cs:__imp_GetCurrentProcessId
0x180034711  mov     ecx, eax; dwProcessId
0x180034713  lea     rdx, [rsp+170h+var_118]; pSessionId
0x180034718  call    cs:__imp_ProcessIdToSessionId
0x18003471e  test    eax, eax
0x180034720  jnz     short loc_180034729
0x180034722  mov     edx, 0F3h
0x180034727  jmp     short loc_1800346E9
0x180034729  mov     eax, [rsp+170h+var_118]
0x18003472d  cmp     [rsp+170h+pSessionId], eax
0x180034731  jz      short loc_18003473A
0x180034733  mov     edx, 0F5h
0x180034738  jmp     short loc_1800346E9
0x18003473a  xor     edx, edx; Val
0x18003473c  lea     rcx, [rbp+70h+TokenInformation]; void *
0x180034740  lea     r8d, [rdx+58h]; Size
0x180034744  call    memset_0
0x180034749  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18003474f  mov     [rsp+170h+var_110], r15d
0x180034754  lea     rax, [rsp+170h+var_110]
0x180034759  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180034760  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x180034764  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180034769  lea     edx, [r9-53h]; TokenInformationClass
0x18003476d  call    cs:__imp_GetTokenInformation
0x180034773  test    eax, eax
0x180034775  jnz     short loc_180034791
0x180034777  mov     rcx, [rbp+78h]; this
0x18003477b  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x180034782  mov     edx, 0FFh; void *
0x180034787  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003478c  jmp     loc_180034A83
0x180034791  mov     r8d, ebx; dwProcessId
0x180034794  xor     edx, edx; bInheritHandle
0x180034796  mov     ecx, 1040h; dwDesiredAccess
0x18003479b  call    cs:__imp_OpenProcess
0x1800347a1  mov     rbx, rax
0x1800347a4  mov     [rsp+170h+var_100], rax
0x1800347a9  inc     rax
0x1800347ac  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800347b2  jnz     short loc_1800347D0
0x1800347b4  mov     rcx, [rbp+78h]; this
0x1800347b8  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x1800347bf  mov     edx, 102h; void *
0x1800347c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800347c9  mov     edi, eax
0x1800347cb  jmp     loc_180034A77
0x1800347d0  lea     r8, [rsp+170h+TokenHandle]; TokenHandle
0x1800347d5  mov     [rsp+170h+TokenHandle], r15
0x1800347da  mov     edx, 8; DesiredAccess
0x1800347df  mov     rcx, rbx; ProcessHandle
0x1800347e2  call    cs:__imp_OpenProcessToken
0x1800347e8  test    eax, eax
0x1800347ea  jnz     short loc_180034812
0x1800347ec  mov     edx, 10Eh; void *
0x1800347f1  mov     rcx, [rbp+78h]; this
0x1800347f5  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x1800347fc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034801  mov     edi, eax
0x180034803  lea     rcx, [rsp+170h+TokenHandle]
0x180034808  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003480d  jmp     loc_180034A77
0x180034812  xor     edx, edx; Val
0x180034814  lea     rcx, [rbp+70h+pSid1]; void *
0x180034818  lea     r8d, [rdx+58h]; Size
0x18003481c  call    memset_0
0x180034821  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x180034826  lea     rax, [rsp+170h+var_110]
0x18003482b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180034831  mov     [rsp+170h+ReturnLength], rax; int
0x180034836  lea     r8, [rbp+70h+pSid1]; TokenInformation
0x18003483a  lea     edx, [r9-53h]; TokenInformationClass
0x18003483e  call    cs:__imp_GetTokenInformation
0x180034844  test    eax, eax
0x180034846  jnz     short loc_18003484F
0x180034848  mov     edx, 117h
0x18003484d  jmp     short loc_1800347F1
0x18003484f  mov     rdx, [rbp+70h+TokenInformation]; pSid2
0x180034853  mov     rcx, [rbp+70h+pSid1]; pSid1
0x180034857  call    cs:__imp_EqualSid
0x18003485d  test    eax, eax
0x18003485f  jnz     short loc_180034880
0x180034861  mov     rcx, [rbp+78h]; this
0x180034865  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18003486c  mov     edi, 80070005h
0x180034871  mov     edx, 118h; void *
0x180034876  mov     r9d, edi; char *
0x180034879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003487e  jmp     short loc_180034803
0x180034880  call    cs:__imp_GetCurrentProcess
0x180034886  mov     [rsp+170h+dwOptions], 2; dwOptions
0x18003488e  mov     r9, rsi; lpTargetHandle
0x180034891  mov     r8, rax; hTargetProcessHandle
0x180034894  mov     [rsp+170h+bInheritHandle], r15d; bInheritHandle
0x180034899  mov     rdx, rdi; hSourceHandle
0x18003489c  mov     dword ptr [rsp+170h+ReturnLength], r15d; dwDesiredAccess
0x1800348a1  mov     rcx, rbx; hSourceProcessHandle
0x1800348a4  call    cs:__imp_DuplicateHandle
0x1800348aa  test    eax, eax
0x1800348ac  jnz     short loc_1800348B8
0x1800348ae  mov     edx, 11Ch
0x1800348b3  jmp     loc_1800347F1
0x1800348b8  mov     rdx, rsi
0x1800348bb  lea     rcx, [rsp+170h+var_120]
0x1800348c0  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800348c5  mov     rcx, [rsi]; Handle
0x1800348c8  xor     r9d, r9d; nLength
0x1800348cb  xor     r8d, r8d; pSecurityDescriptor
0x1800348ce  mov     rbx, [rax]
0x1800348d1  lea     rax, [rsp+170h+nLengthNeeded]
0x1800348d6  lea     edx, [r9+1]; RequestedInformation
0x1800348da  mov     [rsp+170h+ReturnLength], rax; int
0x1800348df  mov     [rsp+170h+nLengthNeeded], r15d
0x1800348e4  call    cs:__imp_GetKernelObjectSecurity
0x1800348ea  call    cs:__imp_GetLastError
0x1800348f0  cmp     eax, 7Ah ; 'z'
0x1800348f3  jz      short loc_180034919
0x1800348f5  mov     rcx, [rbp+78h]; this
0x1800348f9  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x180034900  mov     edx, 12Ch; void *
0x180034905  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003490a  mov     edi, eax
0x18003490c  mov     rcx, rbx; this
0x18003490f  call    ?CloseMapping@CSharedMemoryBlock@@AEAAXXZ; CSharedMemoryBlock::CloseMapping(void)
0x180034914  jmp     loc_180034803
0x180034919  mov     edx, [rsp+170h+nLengthNeeded]; uBytes
0x18003491d  xor     ecx, ecx; uFlags
0x18003491f  call    cs:__imp_LocalAlloc
0x180034925  mov     [rsp+170h+var_120], rax
0x18003492a  mov     rdi, rax
0x18003492d  test    rax, rax
0x180034930  jnz     short loc_18003495B
0x180034932  mov     edi, 8007000Eh
0x180034937  mov     edx, 130h; void *
0x18003493c  mov     rcx, [rbp+78h]; this
0x180034940  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x180034947  mov     r9d, edi; char *
0x18003494a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003494f  lea     rcx, [rsp+170h+var_120]
0x180034954  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180034959  jmp     short loc_18003490C
0x18003495b  mov     r9d, [rsp+170h+nLengthNeeded]; nLength
0x180034960  lea     rax, [rsp+170h+nLengthNeeded]
0x180034965  mov     rcx, [rsi]; Handle
0x180034968  mov     r8, rdi; pSecurityDescriptor
0x18003496b  mov     edx, 1; RequestedInformation
0x180034970  mov     [rsp+170h+ReturnLength], rax; lpnLengthNeeded
0x180034975  call    cs:__imp_GetKernelObjectSecurity
0x18003497b  test    eax, eax
0x18003497d  jnz     short loc_180034998
0x18003497f  mov     edx, 133h; void *
0x180034984  mov     rcx, [rbp+78h]; this
0x180034988  lea     r8, aOnecoreuapComC_4; "onecoreuap\\com\\coml2\\stg\\docfile\\s"...
0x18003498f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034994  mov     edi, eax
0x180034996  jmp     short loc_18003494F
0x180034998  lea     r8, [rsp+170h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18003499d  mov     [rsp+170h+pOwner], r15
0x1800349a2  lea     rdx, [rsp+170h+pOwner]; pOwner
0x1800349a7  mov     [rsp+170h+bOwnerDefaulted], r15d
0x1800349ac  mov     rcx, rdi; pSecurityDescriptor
0x1800349af  call    cs:__imp_GetSecurityDescriptorOwner
0x1800349b5  test    eax, eax
0x1800349b7  jnz     short loc_1800349C0
0x1800349b9  mov     edx, 137h
0x1800349be  jmp     short loc_180034984
0x1800349c0  mov     rdx, [rbp+70h+TokenInformation]; pSid2
0x1800349c4  mov     rcx, [rsp+170h+pOwner]; pSid1
0x1800349c9  call    cs:__imp_EqualSid
0x1800349cf  test    eax, eax
0x1800349d1  jnz     short loc_1800349E2
0x1800349d3  mov     edi, 80070005h
0x1800349d8  mov     edx, 139h
0x1800349dd  jmp     loc_18003493C
0x1800349e2  cmp     [rsp+170h+bOwnerDefaulted], r15d
0x1800349e7  jz      short loc_1800349F8
0x1800349e9  mov     edi, 80070005h
0x1800349ee  mov     edx, 13Ah
0x1800349f3  jmp     loc_18003493C
0x1800349f8  mov     rcx, [rsi]; hFileMappingObject
0x1800349fb  xor     r9d, r9d; dwFileOffsetLow
0x1800349fe  mov     qword ptr [rsp+170h+bInheritHandle], r15; lpBaseAddress
0x180034a03  xor     r8d, r8d; dwFileOffsetHigh
0x180034a06  mov     [rsp+170h+ReturnLength], r15; dwNumberOfBytesToMap
0x180034a0b  lea     edx, [r9+6]; dwDesiredAccess
0x180034a0f  call    cs:__imp_MapViewOfFileEx
0x180034a15  mov     [rsi+8], rax
0x180034a19  mov     rcx, rax
0x180034a1c  test    rax, rax
0x180034a1f  jnz     short loc_180034A2B
0x180034a21  mov     edx, 140h
0x180034a26  jmp     loc_180034984
0x180034a2b  mov     rax, [rax+8]
0x180034a2f  sub     rax, qword ptr cs:_GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac.Data1
0x180034a36  jnz     short loc_180034A43
0x180034a38  mov     rax, [rcx+10h]
0x180034a3c  sub     rax, qword ptr cs:_GUID_edc0cbd7_ba5f_49c2_b7ff_6cbeb1cc2dac.Data4
0x180034a43  test    rax, rax
0x180034a46  jz      short loc_180034A57
0x180034a48  mov     edi, 80070005h
0x180034a4d  mov     edx, 144h
0x180034a52  jmp     loc_18003493C
0x180034a57  mov     eax, [rcx]
0x180034a59  lea     rcx, [rsp+170h+var_120]
0x180034a5e  mov     [rsi+10h], eax
0x180034a61  mov     [rsi+14h], r14d
0x180034a65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180034a6a  lea     rcx, [rsp+170h+TokenHandle]
0x180034a6f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034a74  mov     edi, r15d
0x180034a77  lea     rcx, [rsp+170h+var_100]
0x180034a7c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034a81  mov     eax, edi
0x180034a83  mov     rcx, [rbp+70h+var_30]
0x180034a87  xor     rcx, rsp; StackCookie
0x180034a8a  call    __security_check_cookie
0x180034a8f  mov     rbx, [rsp+170h+arg_18]
0x180034a97  add     rsp, 150h
0x180034a9e  pop     r15
0x180034aa0  pop     r14
0x180034aa2  pop     rdi
0x180034aa3  pop     rsi
0x180034aa4  pop     rbp
0x180034aa5  retn
```
