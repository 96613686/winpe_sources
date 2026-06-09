# ISAPI_REQUEST::CreateToken(ushort const *,ushort const *,ushort const *,ulong,void * *)

- ea: `0x18000c898`
- end: `0x18000cbfd`
- name: `?CreateToken@ISAPI_REQUEST@@QEAAJPEBG00KPEAPEAX@Z`
- size: `869`
- prototype: `int(ISAPI_REQUEST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d340`
- `0x18000d5b8`

## callees

- `0x18000c324`
- `0x18000c45c`
- `0x18000c898`
- `0x180010bf4`
- `0x1800117cc`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c909`
- `msvcrt!_wcsicmp` at `0x18000c921`
- `msvcrt!_wcsicmp` at `0x18000c909`
- `msvcrt!_wcsicmp` at `0x18000c921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca89`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cb41`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000cb41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cb2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cbe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cb2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000cbe2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000cb6f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000cb6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caa8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ca7f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ca7f`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::CreateToken(
        ISAPI_REQUEST *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        void **lpTargetHandle)
{
  signed int CacheKey; // edi
  __int64 (__fastcall *v10)(struct IHttpServer *, _QWORD, _BYTE *, struct IHttpTokenEntry **, __int64); // rbx
  __int64 v11; // rax
  int v12; // esi
  IIS_LOGON_PROVIDER *v13; // rcx
  void (__fastcall *v14)(struct IHttpServer *, __int64, _BYTE *, struct IHttpTokenEntry **, __int64); // rbx
  __int64 v15; // rax
  HANDLE CurrentProcess; // r14
  void *v17; // rbx
  HANDLE v18; // rax
  signed int LastError; // eax
  HANDLE v21; // rax
  struct sockaddr *bInheritHandle; // [rsp+28h] [rbp-D8h]
  struct IHttpTokenEntry *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  void *v25; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-A0h]
  _BYTE v28[128]; // [rsp+70h] [rbp-90h] BYREF

  v27 = a4;
  v23 = 0;
  TOKEN_KEY::TOKEN_KEY((TOKEN_KEY *)v28);
  v24 = 0;
  v25 = 0;
  hObject = 0;
  if ( _wcsicmp(a2, L"IUSR") && _wcsicmp(a2, L"NT Authority\\IUSR") )
  {
    CacheKey = TOKEN_KEY::CreateCacheKey((TOKEN_KEY *)v28, a2, a3, a5);
    if ( CacheKey < 0 )
      goto LABEL_12;
    v10 = *(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, _BYTE *, struct IHttpTokenEntry **, __int64))(*(_QWORD *)g_pGlobalInfo + 80LL);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
    CacheKey = v10(g_pGlobalInfo, 0, v28, &v23, v11);
    if ( CacheKey < 0 || (v12 = 0, !v23) )
    {
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
      CacheKey = IIS_LOGON_PROVIDER::IISLogonUser(v13, a2, a3, a5, v27, bInheritHandle, &v23);
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
      if ( CacheKey < 0 )
        goto LABEL_12;
      v14 = *(void (__fastcall **)(struct IHttpServer *, __int64, _BYTE *, struct IHttpTokenEntry **, __int64))(*(_QWORD *)g_pGlobalInfo + 80LL);
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
      v14(g_pGlobalInfo, 1, v28, &v23, v15);
      CurrentProcess = GetCurrentProcess();
      goto LABEL_8;
    }
  }
  else
  {
    if ( (**(unsigned int (__fastcall ***)(struct IHttpServer *))g_pGlobalInfo)(g_pGlobalInfo) )
    {
      v21 = GetCurrentProcess();
      if ( OpenProcessToken(v21, 0xF01FFu, &hObject)
        && DuplicateTokenEx(hObject, 0x2000000u, 0, SecurityDelegation, TokenImpersonation, lpTargetHandle) )
      {
        CacheKey = 0;
        goto LABEL_12;
      }
      goto LABEL_10;
    }
    CacheKey = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(*(_QWORD *)g_pGlobalInfo + 160LL))(
                 g_pGlobalInfo,
                 &v24);
    if ( CacheKey < 0 )
      goto LABEL_12;
    CacheKey = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v24 + 48LL))(v24, 0, &v25);
    if ( CacheKey < 0 )
      goto LABEL_12;
    v12 = 1;
    if ( !v25 )
    {
      CacheKey = -2147024883;
      goto LABEL_12;
    }
  }
  CurrentProcess = GetCurrentProcess();
  if ( !v12 )
  {
LABEL_8:
    v17 = (void *)(*(__int64 (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v23 + 56LL))(v23);
    goto LABEL_9;
  }
  v17 = v25;
LABEL_9:
  v18 = GetCurrentProcess();
  if ( DuplicateHandle(v18, v17, CurrentProcess, lpTargetHandle, 0, 0, 2u) )
    goto LABEL_12;
LABEL_10:
  LastError = GetLastError();
  CacheKey = LastError;
  if ( LastError > 0 )
    CacheKey = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( hObject )
    CloseHandle(hObject);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
    v24 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(struct IHttpTokenEntry *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  TOKEN_KEY::~TOKEN_KEY((TOKEN_KEY *)v28);
  return (unsigned int)CacheKey;
}

```

## disassembly

```asm
0x18000c898  push    rbp
0x18000c89a  push    rbx
0x18000c89b  push    rsi
0x18000c89c  push    rdi
0x18000c89d  push    r12
0x18000c89f  push    r13
0x18000c8a1  push    r14
0x18000c8a3  push    r15
0x18000c8a5  lea     rbp, [rsp-8]
0x18000c8aa  sub     rsp, 108h
0x18000c8b1  mov     rax, cs:__security_cookie
0x18000c8b8  xor     rax, rsp
0x18000c8bb  mov     [rbp+40h+var_50], rax
0x18000c8bf  mov     r12, [rbp+40h+lpTargetHandle]
0x18000c8c3  mov     r13, rcx
0x18000c8c6  lea     rcx, [rsp+140h+var_D0]; this
0x18000c8cb  mov     [rsp+140h+var_E0], r9
0x18000c8d0  mov     r15, r8
0x18000c8d3  mov     [rsp+140h+var_100], 0
0x18000c8dc  mov     r14, rdx
0x18000c8df  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x18000c8e4  lea     rdx, aIusr; "IUSR"
0x18000c8eb  mov     [rsp+140h+var_F8], 0
0x18000c8f4  mov     rcx, r14; String1
0x18000c8f7  mov     [rsp+140h+var_F0], 0
0x18000c900  mov     [rsp+140h+hObject], 0
0x18000c909  call    cs:__imp__wcsicmp
0x18000c90f  test    eax, eax
0x18000c911  jz      loc_18000CB18
0x18000c917  lea     rdx, aNtAuthorityIus; "NT Authority\\IUSR"
0x18000c91e  mov     rcx, r14; String1
0x18000c921  call    cs:__imp__wcsicmp
0x18000c927  test    eax, eax
0x18000c929  jz      loc_18000CB18
0x18000c92f  mov     r9d, [rbp+40h+arg_20]; unsigned int
0x18000c933  lea     rcx, [rsp+140h+var_D0]; this
0x18000c938  mov     r8, r15; unsigned __int16 *
0x18000c93b  mov     rdx, r14; unsigned __int16 *
0x18000c93e  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x18000c943  mov     edi, eax
0x18000c945  test    eax, eax
0x18000c947  js      loc_18000CA9E
0x18000c94d  mov     rax, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c954  mov     rcx, [rax]
0x18000c957  mov     rbx, [rcx+50h]
0x18000c95b  mov     rcx, [r13+18h]
0x18000c95f  mov     rdx, [rcx]
0x18000c962  mov     rax, [rdx+110h]
0x18000c969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c96e  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c975  lea     r9, [rsp+140h+var_100]
0x18000c97a  mov     qword ptr [rsp+140h+dwDesiredAccess], rax
0x18000c97f  lea     r8, [rsp+140h+var_D0]
0x18000c984  mov     rax, rbx
0x18000c987  xor     edx, edx
0x18000c989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98e  mov     edi, eax
0x18000c990  test    eax, eax
0x18000c992  js      short loc_18000C9A1
0x18000c994  xor     esi, esi
0x18000c996  cmp     [rsp+140h+var_100], rsi
0x18000c99b  jnz     loc_18000CBE2
0x18000c9a1  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c9a8  mov     rax, [rcx]
0x18000c9ab  mov     rax, [rax+18h]
0x18000c9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b4  mov     r9d, [rbp+40h+arg_20]; unsigned int
0x18000c9b8  lea     rax, [rsp+140h+var_100]
0x18000c9bd  mov     qword ptr [rsp+140h+dwOptions], rax; struct IHttpTokenEntry **
0x18000c9c2  mov     r8, r15; unsigned __int16 *
0x18000c9c5  mov     rax, [rsp+140h+var_E0]
0x18000c9ca  mov     rdx, r14; unsigned __int16 *
0x18000c9cd  mov     qword ptr [rsp+140h+dwDesiredAccess], rax; unsigned __int16 *
0x18000c9d2  call    ?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z; IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)
0x18000c9d7  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c9de  mov     edi, eax
0x18000c9e0  mov     rax, [rcx]
0x18000c9e3  mov     rax, [rax+20h]
0x18000c9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9ec  test    edi, edi
0x18000c9ee  js      loc_18000CA9E
0x18000c9f4  mov     rax, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000c9fb  mov     rcx, [rax]
0x18000c9fe  mov     rbx, [rcx+50h]
0x18000ca02  mov     rcx, [r13+18h]
0x18000ca06  mov     rdx, [rcx]
0x18000ca09  mov     rax, [rdx+110h]
0x18000ca10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca15  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000ca1c  lea     r9, [rsp+140h+var_100]
0x18000ca21  mov     qword ptr [rsp+140h+dwDesiredAccess], rax
0x18000ca26  lea     r8, [rsp+140h+var_D0]
0x18000ca2b  mov     rax, rbx
0x18000ca2e  mov     edx, 1
0x18000ca33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca38  call    cs:__imp_GetCurrentProcess
0x18000ca3e  mov     r14, rax
0x18000ca41  mov     rcx, [rsp+140h+var_100]
0x18000ca46  mov     rax, [rcx]
0x18000ca49  mov     rax, [rax+38h]
0x18000ca4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca52  mov     rbx, rax
0x18000ca55  call    cs:__imp_GetCurrentProcess
0x18000ca5b  mov     [rsp+140h+dwOptions], 2; dwOptions
0x18000ca63  mov     r9, r12; lpTargetHandle
0x18000ca66  mov     rcx, rax; hSourceProcessHandle
0x18000ca69  mov     [rsp+140h+bInheritHandle], 0; bInheritHandle
0x18000ca71  mov     r8, r14; hTargetProcessHandle
0x18000ca74  mov     [rsp+140h+dwDesiredAccess], 0; dwDesiredAccess
0x18000ca7c  mov     rdx, rbx; hSourceHandle
0x18000ca7f  call    cs:__imp_DuplicateHandle
0x18000ca85  test    eax, eax
0x18000ca87  jnz     short loc_18000CA9E
0x18000ca89  call    cs:__imp_GetLastError
0x18000ca8f  mov     edi, eax
0x18000ca91  test    eax, eax
0x18000ca93  jle     short loc_18000CA9E
0x18000ca95  movzx   edi, ax
0x18000ca98  or      edi, 80070000h
0x18000ca9e  mov     rcx, [rsp+140h+hObject]; hObject
0x18000caa3  test    rcx, rcx
0x18000caa6  jz      short loc_18000CAAE
0x18000caa8  call    cs:__imp_CloseHandle
0x18000caae  mov     rcx, [rsp+140h+var_F8]
0x18000cab3  test    rcx, rcx
0x18000cab6  jz      short loc_18000CACD
0x18000cab8  mov     rax, [rcx]
0x18000cabb  mov     rax, [rax+8]
0x18000cabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac4  mov     [rsp+140h+var_F8], 0
0x18000cacd  mov     rcx, [rsp+140h+var_100]
0x18000cad2  test    rcx, rcx
0x18000cad5  jz      short loc_18000CAEC
0x18000cad7  mov     rax, [rcx]
0x18000cada  mov     rax, [rax+10h]
0x18000cade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cae3  mov     [rsp+140h+var_100], 0
0x18000caec  lea     rcx, [rsp+140h+var_D0]; this
0x18000caf1  call    ??1TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::~TOKEN_KEY(void)
0x18000caf6  mov     eax, edi
0x18000caf8  mov     rcx, [rbp+40h+var_50]
0x18000cafc  xor     rcx, rsp; StackCookie
0x18000caff  call    __security_check_cookie
0x18000cb04  add     rsp, 108h
0x18000cb0b  pop     r15
0x18000cb0d  pop     r14
0x18000cb0f  pop     r13
0x18000cb11  pop     r12
0x18000cb13  pop     rdi
0x18000cb14  pop     rsi
0x18000cb15  pop     rbx
0x18000cb16  pop     rbp
0x18000cb17  retn
0x18000cb18  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000cb1f  mov     rax, [rcx]
0x18000cb22  mov     rax, [rax]
0x18000cb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb2a  test    eax, eax
0x18000cb2c  jz      short loc_18000CB84
0x18000cb2e  call    cs:__imp_GetCurrentProcess
0x18000cb34  lea     r8, [rsp+140h+hObject]; TokenHandle
0x18000cb39  mov     edx, 0F01FFh; DesiredAccess
0x18000cb3e  mov     rcx, rax; ProcessHandle
0x18000cb41  call    cs:__imp_OpenProcessToken
0x18000cb47  test    eax, eax
0x18000cb49  jz      loc_18000CA89
0x18000cb4f  mov     rcx, [rsp+140h+hObject]; hExistingToken
0x18000cb54  mov     r9d, 3; ImpersonationLevel
0x18000cb5a  mov     qword ptr [rsp+140h+bInheritHandle], r12; phNewToken
0x18000cb5f  xor     r8d, r8d; lpTokenAttributes
0x18000cb62  mov     edx, 2000000h; dwDesiredAccess
0x18000cb67  mov     [rsp+140h+dwDesiredAccess], 2; TokenType
0x18000cb6f  call    cs:__imp_DuplicateTokenEx
0x18000cb75  test    eax, eax
0x18000cb77  jz      loc_18000CA89
0x18000cb7d  xor     edi, edi
0x18000cb7f  jmp     loc_18000CA9E
0x18000cb84  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000cb8b  lea     rdx, [rsp+140h+var_F8]
0x18000cb90  mov     rax, [rcx]
0x18000cb93  mov     rax, [rax+0A0h]
0x18000cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9f  mov     edi, eax
0x18000cba1  test    eax, eax
0x18000cba3  js      loc_18000CA9E
0x18000cba9  mov     rcx, [rsp+140h+var_F8]
0x18000cbae  lea     r8, [rsp+140h+var_F0]
0x18000cbb3  xor     edx, edx
0x18000cbb5  mov     rax, [rcx]
0x18000cbb8  mov     rax, [rax+30h]
0x18000cbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbc1  mov     edi, eax
0x18000cbc3  test    eax, eax
0x18000cbc5  js      loc_18000CA9E
0x18000cbcb  cmp     [rsp+140h+var_F0], 0
0x18000cbd1  mov     esi, 1
0x18000cbd6  jnz     short loc_18000CBE2
0x18000cbd8  mov     edi, 8007000Dh
0x18000cbdd  jmp     loc_18000CA9E
0x18000cbe2  call    cs:__imp_GetCurrentProcess
0x18000cbe8  mov     r14, rax
0x18000cbeb  test    esi, esi
0x18000cbed  jz      loc_18000CA41
0x18000cbf3  mov     rbx, [rsp+140h+var_F0]
0x18000cbf8  jmp     loc_18000CA55
```
