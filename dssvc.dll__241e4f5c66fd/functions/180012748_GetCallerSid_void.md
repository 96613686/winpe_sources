# GetCallerSid(void * *)

- ea: `0x180012748`
- end: `0x1800129f5`
- name: `?GetCallerSid@@YAJPEAPEAX@Z`
- size: `685`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800129fc`

## callees

- `0x18000417c`
- `0x180006b84`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c93c`
- `0x18000dee8`
- `0x18000e674`
- `0x180012364`
- `0x1800123f8`
- `0x180012748`
- `0x180012d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001290b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001290b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012972`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800127a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800127a0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800127b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800127b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012830`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012895`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800128fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012968`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012830`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012895`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800128fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012968`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800128cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012934`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800128cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012934`

## string_xrefs

- `0x1800127da`: `Unable to get client token! HR=0x%x`
- `0x1800127eb`: `GetCallerSid`
- `0x180012861`: `GetCallerSid`
- `0x180012850`: `Unabled to determine if caller TokenIsAppContainer. HR=0x%x`

## pseudocode

```c
__int64 __fastcall GetCallerSid(void ***a1)
{
  int v2; // edi
  void **v3; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v6; // rcx
  int *v7; // rax
  signed int v8; // eax
  __int64 v9; // rcx
  int *v10; // rax
  signed int v11; // eax
  HLOCAL v12; // rax
  void **v13; // rbx
  TOKEN_INFORMATION_CLASS v14; // edx
  signed int v15; // eax
  HLOCAL v16; // rax
  signed int v17; // eax
  void *v18; // rdi
  void **v19; // rax
  void **v20; // rsi
  PDWORD ReturnLength; // [rsp+20h] [rbp-20h]
  LPVOID v23[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  void **v25; // [rsp+78h] [rbp+38h] BYREF
  int TokenInformation; // [rsp+80h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp+48h] BYREF

  *a1 = 0;
  v23[0] = 0;
  TokenHandle = 0;
  LODWORD(v25) = 0;
  v2 = AutoImpersonate<1>::ImpersonateClient(&v25);
  if ( v2 < 0 )
    goto LABEL_2;
  v3 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&TokenHandle);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, v3) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v6);
    DSLogger::LogError((DSLogger *)v7, L"GetCallerSid", 0xF6u, L"Unable to get client token! HR=0x%x", v2);
    if ( v2 < 0 )
    {
LABEL_2:
      AutoImpersonate<1>::RevertToSelf(&v25);
      goto LABEL_35;
    }
  }
  AutoImpersonate<1>::RevertToSelf(&v25);
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength) )
  {
    v8 = GetLastError();
    v2 = v8;
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    v10 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9);
    LODWORD(ReturnLength) = v2;
    DSLogger::LogError(
      (DSLogger *)v10,
      L"GetCallerSid",
      0x100u,
      L"Unabled to determine if caller TokenIsAppContainer. HR=0x%x",
      ReturnLength);
    if ( v2 < 0 )
      goto LABEL_35;
  }
  if ( TokenInformation )
  {
    if ( !GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    {
      if ( GetLastError() == 122 )
        goto LABEL_17;
      v11 = GetLastError();
      v2 = v11;
      if ( v11 > 0 )
        v2 = (unsigned __int16)v11 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_17:
        v12 = LocalAlloc(0, TokenInformationLength);
        tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::reset(v23, v12);
        v13 = (void **)v23[0];
        if ( !v23[0] )
        {
LABEL_18:
          v2 = -2147024882;
          goto LABEL_35;
        }
        v14 = TokenAppContainerSid;
        goto LABEL_27;
      }
      goto LABEL_35;
    }
LABEL_34:
    v2 = -2147418113;
    goto LABEL_35;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_34;
  if ( GetLastError() == 122 )
    goto LABEL_25;
  v15 = GetLastError();
  v2 = v15;
  if ( v15 > 0 )
    v2 = (unsigned __int16)v15 | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_25:
    v16 = LocalAlloc(0, TokenInformationLength);
    tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::reset(v23, v16);
    v13 = (void **)v23[0];
    if ( !v23[0] )
      goto LABEL_18;
    v14 = TokenUser;
LABEL_27:
    if ( GetTokenInformation(TokenHandle, v14, v13, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_31;
    v17 = GetLastError();
    v2 = v17;
    if ( v17 > 0 )
      v2 = (unsigned __int16)v17 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_31:
      v25 = 0;
      v18 = *v13;
      v19 = (void **)tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&v25);
      v2 = AllocCopySid(v18, v19);
      if ( v2 >= 0 )
      {
        v20 = v25;
        v25 = v13;
        tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete((void **)&v25);
        v23[0] = 0;
        *a1 = v20;
      }
      else
      {
        tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete((void **)&v25);
      }
    }
  }
LABEL_35:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&TokenHandle);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(v23);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012748  push    rbp
0x18001274a  push    rbx
0x18001274b  push    rsi
0x18001274c  push    rdi
0x18001274d  push    r14
0x18001274f  mov     rbp, rsp
0x180012752  sub     rsp, 40h
0x180012756  mov     r14, rcx
0x180012759  mov     qword ptr [rcx], 0
0x180012760  lea     rcx, [rbp+arg_8]
0x180012764  mov     [rbp+var_10], 0
0x18001276c  mov     [rbp+TokenHandle], 0
0x180012774  mov     dword ptr [rbp+arg_8], 0
0x18001277b  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x180012780  mov     edi, eax
0x180012782  test    eax, eax
0x180012784  jns     short loc_180012794
0x180012786  lea     rcx, [rbp+arg_8]
0x18001278a  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18001278f  jmp     loc_1800129D6
0x180012794  lea     rcx, [rbp+TokenHandle]
0x180012798  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18001279d  mov     rbx, rax
0x1800127a0  call    cs:__imp_GetCurrentThread
0x1800127a6  mov     edx, 8; DesiredAccess
0x1800127ab  mov     r9, rbx; TokenHandle
0x1800127ae  mov     rcx, rax; ThreadHandle
0x1800127b1  lea     r8d, [rdx-7]; OpenAsSelf
0x1800127b5  call    cs:__imp_OpenThreadToken
0x1800127bb  mov     esi, 80070000h
0x1800127c0  test    eax, eax
0x1800127c2  jnz     short loc_1800127FE
0x1800127c4  call    cs:__imp_GetLastError
0x1800127ca  mov     edi, eax
0x1800127cc  test    eax, eax
0x1800127ce  jle     short loc_1800127D5
0x1800127d0  movzx   edi, ax
0x1800127d3  or      edi, esi
0x1800127d5  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800127da  lea     r9, aUnableToGetCli; "Unable to get client token! HR=0x%x"
0x1800127e1  mov     dword ptr [rsp+40h+ReturnLength], edi
0x1800127e5  mov     r8d, 0F6h; unsigned int
0x1800127eb  lea     rdx, aGetcallersid; "GetCallerSid"
0x1800127f2  mov     rcx, rax; this
0x1800127f5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800127fa  test    edi, edi
0x1800127fc  js      short loc_180012786
0x1800127fe  lea     rcx, [rbp+arg_8]
0x180012802  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x180012807  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001280b  lea     rax, [rbp+TokenInformationLength]
0x18001280f  mov     r9d, 4; TokenInformationLength
0x180012815  mov     [rbp+TokenInformation], 0
0x18001281c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180012820  mov     [rbp+TokenInformationLength], 0
0x180012827  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18001282c  lea     edx, [r9+19h]; TokenInformationClass
0x180012830  call    cs:__imp_GetTokenInformation
0x180012836  test    eax, eax
0x180012838  jnz     short loc_180012878
0x18001283a  call    cs:__imp_GetLastError
0x180012840  mov     edi, eax
0x180012842  test    eax, eax
0x180012844  jle     short loc_18001284B
0x180012846  movzx   edi, ax
0x180012849  or      edi, esi
0x18001284b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012850  lea     r9, aUnabledToDeter; "Unabled to determine if caller TokenIsA"...
0x180012857  mov     dword ptr [rsp+40h+ReturnLength], edi
0x18001285b  mov     r8d, 100h; unsigned int
0x180012861  lea     rdx, aGetcallersid; "GetCallerSid"
0x180012868  mov     rcx, rax; this
0x18001286b  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012870  test    edi, edi
0x180012872  js      loc_1800129D6
0x180012878  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001287c  lea     rax, [rbp+TokenInformationLength]
0x180012880  xor     r9d, r9d; TokenInformationLength
0x180012883  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180012888  xor     r8d, r8d; TokenInformation
0x18001288b  cmp     [rbp+TokenInformation], r8d
0x18001288f  jz      short loc_1800128F8
0x180012891  lea     edx, [r9+1Fh]; TokenInformationClass
0x180012895  call    cs:__imp_GetTokenInformation
0x18001289b  test    eax, eax
0x18001289d  jnz     loc_1800129D1
0x1800128a3  call    cs:__imp_GetLastError
0x1800128a9  cmp     eax, 7Ah ; 'z'
0x1800128ac  jz      short loc_1800128C7
0x1800128ae  call    cs:__imp_GetLastError
0x1800128b4  mov     edi, eax
0x1800128b6  test    eax, eax
0x1800128b8  jle     short loc_1800128BF
0x1800128ba  movzx   edi, ax
0x1800128bd  or      edi, esi
0x1800128bf  test    edi, edi
0x1800128c1  js      loc_1800129D6
0x1800128c7  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1800128ca  xor     ecx, ecx; uFlags
0x1800128cc  call    cs:__imp_LocalAlloc
0x1800128d2  mov     rdx, rax
0x1800128d5  lea     rcx, [rbp+var_10]
0x1800128d9  call    ?reset@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::reset(void *)
0x1800128de  mov     rbx, [rbp+var_10]
0x1800128e2  test    rbx, rbx
0x1800128e5  jnz     short loc_1800128F1
0x1800128e7  mov     edi, 8007000Eh
0x1800128ec  jmp     loc_1800129D6
0x1800128f1  mov     edx, 1Fh
0x1800128f6  jmp     short loc_180012954
0x1800128f8  mov     edx, 1; TokenInformationClass
0x1800128fd  call    cs:__imp_GetTokenInformation
0x180012903  test    eax, eax
0x180012905  jnz     loc_1800129D1
0x18001290b  call    cs:__imp_GetLastError
0x180012911  cmp     eax, 7Ah ; 'z'
0x180012914  jz      short loc_18001292F
0x180012916  call    cs:__imp_GetLastError
0x18001291c  mov     edi, eax
0x18001291e  test    eax, eax
0x180012920  jle     short loc_180012927
0x180012922  movzx   edi, ax
0x180012925  or      edi, esi
0x180012927  test    edi, edi
0x180012929  js      loc_1800129D6
0x18001292f  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180012932  xor     ecx, ecx; uFlags
0x180012934  call    cs:__imp_LocalAlloc
0x18001293a  mov     rdx, rax
0x18001293d  lea     rcx, [rbp+var_10]
0x180012941  call    ?reset@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::reset(void *)
0x180012946  mov     rbx, [rbp+var_10]
0x18001294a  test    rbx, rbx
0x18001294d  jz      short loc_1800128E7
0x18001294f  mov     edx, 1; TokenInformationClass
0x180012954  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180012958  lea     rax, [rbp+TokenInformationLength]
0x18001295c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180012960  mov     r8, rbx; TokenInformation
0x180012963  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180012968  call    cs:__imp_GetTokenInformation
0x18001296e  test    eax, eax
0x180012970  jnz     short loc_180012987
0x180012972  call    cs:__imp_GetLastError
0x180012978  mov     edi, eax
0x18001297a  test    eax, eax
0x18001297c  jle     short loc_180012983
0x18001297e  movzx   edi, ax
0x180012981  or      edi, esi
0x180012983  test    edi, edi
0x180012985  js      short loc_1800129D6
0x180012987  mov     [rbp+arg_8], 0
0x18001298f  lea     rcx, [rbp+arg_8]
0x180012993  mov     rdi, [rbx]
0x180012996  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x18001299b  mov     rdx, rax; void **
0x18001299e  mov     rcx, rdi; pSourceSid
0x1800129a1  call    ?AllocCopySid@@YAJPEAXPEAPEAX@Z; AllocCopySid(void *,void * *)
0x1800129a6  lea     rcx, [rbp+arg_8]
0x1800129aa  mov     edi, eax
0x1800129ac  test    eax, eax
0x1800129ae  jns     short loc_1800129B7
0x1800129b0  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x1800129b5  jmp     short loc_1800129D6
0x1800129b7  mov     rsi, [rbp+arg_8]
0x1800129bb  mov     [rbp+arg_8], rbx
0x1800129bf  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x1800129c4  mov     [rbp+var_10], 0
0x1800129cc  mov     [r14], rsi
0x1800129cf  jmp     short loc_1800129D6
0x1800129d1  mov     edi, 8000FFFFh
0x1800129d6  lea     rcx, [rbp+TokenHandle]
0x1800129da  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800129df  lea     rcx, [rbp+var_10]
0x1800129e3  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x1800129e8  mov     eax, edi
0x1800129ea  add     rsp, 40h
0x1800129ee  pop     r14
0x1800129f0  pop     rdi
0x1800129f1  pop     rsi
0x1800129f2  pop     rbx
0x1800129f3  pop     rbp
0x1800129f4  retn
```
