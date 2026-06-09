# UpdateJobAttributes

- ea: `0x1800623a0`
- end: `0x180062633`
- name: `UpdateJobAttributes`
- size: `659`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180062db8`
- `0x180063010`
- `0x1800632bc`

## callees

- `0x180008520`
- `0x180008560`
- `0x18000ee90`
- `0x180014dd4`
- `0x180031aa8`
- `0x18003ea2c`
- `0x180041b0c`
- `0x180042a80`
- `0x1800436b8`
- `0x1800436fc`
- `0x180046650`
- `0x1800623a0`
- `0x1800cc910`
- `0x1800d7b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006252b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800624fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006252b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800624d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800624f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800624d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800624f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800624c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800624e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800624c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800624e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006250e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800625ce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006250e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800625ce`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006251d`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006251d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800625b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800625b4`
- `SPOOLSS!DllFreeSplStr` at `0x1800625ff`
- `SPOOLSS!DllFreeSplStr` at `0x180062608`
- `SPOOLSS!DllFreeSplStr` at `0x1800625ff`
- `SPOOLSS!DllFreeSplStr` at `0x180062608`
- `SPOOLSS!AllocSplStr` at `0x18006243c`
- `SPOOLSS!AllocSplStr` at `0x18006244d`
- `SPOOLSS!AllocSplStr` at `0x18006243c`
- `SPOOLSS!AllocSplStr` at `0x18006244d`

## string_xrefs

- `0x18006253a`: `Failed to set the appropriate security context. Printer %ws. Error %d`
- `0x180062544`: `UpdateJobAttributes`

## pseudocode

```c
void __fastcall UpdateJobAttributes(__int64 a1)
{
  const unsigned __int16 *v2; // r14
  __int64 v3; // rax
  __int64 v4; // rcx
  const unsigned __int16 *v5; // rsi
  unsigned int v6; // r15d
  void *v7; // rcx
  DWORD IsRemoteGuest; // edi
  HANDLE CurrentThread; // rax
  HANDLE v10; // rax
  void *v11; // rdx
  DWORD LastError; // eax
  int v13; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-31h] BYREF
  __int128 v15; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-19h] BYREF
  _ATTRIBUTE_INFO_1 v17; // [rsp+60h] [rbp-9h] BYREF

  if ( a1 )
  {
    memset(&v17, 0, sizeof(v17));
    if ( *(_QWORD *)(a1 + 88) )
    {
      if ( !*(_DWORD *)(a1 + 368) && !*(_DWORD *)(a1 + 364) && !(unsigned int)ValidRawDatatype(*(_QWORD *)(a1 + 128)) )
      {
        *(_DWORD *)(a1 + 364) = 1;
        *(_DWORD *)(a1 + 368) = 1;
        v15 = 0;
        EnterSplSem(0);
        v2 = (const unsigned __int16 *)AllocSplStr(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 24LL));
        v3 = AllocSplStr(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 24LL));
        v4 = *(_QWORD *)(a1 + 96);
        v5 = (const unsigned __int16 *)v3;
        v6 = *(_DWORD *)(v4 + 200);
        LeaveSplSem(v4);
        if ( !v2 || !v5 )
        {
LABEL_31:
          DllFreeSplStr(v2);
          DllFreeSplStr(v5);
          sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v15);
          return;
        }
        NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)v16);
        v7 = *(void **)(a1 + 256);
        TokenHandle = (void *)-1LL;
        v13 = 0;
        IsRemoteGuest = PrincipalIsRemoteGuest(v7, &v13);
        if ( IsRemoteGuest )
          goto LABEL_18;
        if ( !v13 || !*(_QWORD *)(a1 + 256) )
          goto LABEL_19;
        CurrentThread = GetCurrentThread();
        if ( !OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
        {
          v10 = GetCurrentThread();
          if ( !OpenThreadToken(v10, 0xCu, 1, &TokenHandle) )
          {
            IsRemoteGuest = GetLastError();
            if ( IsRemoteGuest )
              goto LABEL_18;
          }
        }
        if ( SetThreadToken(0, 0) && ImpersonateSelf(SecurityImpersonation) )
        {
          IsRemoteGuest = 0;
          goto LABEL_19;
        }
        IsRemoteGuest = GetLastError();
        if ( IsRemoteGuest )
LABEL_18:
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "UpdateJobAttributes",
            L"Failed to set the appropriate security context. Printer %ws. Error %d",
            v2,
            IsRemoteGuest);
LABEL_19:
        if ( !sandbox::DriverJobAttributesAdapter::Initialize(
                (sandbox::DriverJobAttributesAdapter *)&v15,
                *(struct sandbox::SandboxManager **)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 280LL) + 368LL),
                v2,
                v5,
                v6)
          && (unsigned int)sandbox::DriverJobAttributesAdapter::QueryAttributes(
                             (sandbox::DriverJobAttributesAdapter *)&v15,
                             *(struct _devicemodeW **)(a1 + 104),
                             &v17) )
        {
          *(_DWORD *)(a1 + 364) = v17.dwJobNumberOfPagesPerSide;
          *(_DWORD *)(a1 + 368) = v17.dwDrvNumberOfPagesPerSide;
        }
        if ( !IsRemoteGuest && TokenHandle != (void *)-1LL && TokenHandle )
        {
          if ( !RevertToSelf() )
            goto LABEL_29;
          v11 = TokenHandle;
          if ( TokenHandle == (void *)-1LL )
            v11 = 0;
          if ( !SetThreadToken(0, v11) )
          {
LABEL_29:
            LastError = GetLastError();
            ForceProcessShutdown(0x68u, LastError);
          }
        }
        NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
        NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)v16);
        goto LABEL_31;
      }
    }
  }
}

```

## disassembly

```asm
0x1800623a0  test    rcx, rcx
0x1800623a3  jz      locret_180062632
0x1800623a9  push    rbp
0x1800623aa  push    rbx
0x1800623ab  push    rsi
0x1800623ac  push    rdi
0x1800623ad  push    r14
0x1800623af  push    r15
0x1800623b1  lea     rbp, [rsp-2Fh]
0x1800623b6  sub     rsp, 98h
0x1800623bd  mov     rax, cs:__security_cookie
0x1800623c4  xor     rax, rsp
0x1800623c7  mov     [rbp+57h+var_40], rax
0x1800623cb  xorps   xmm0, xmm0
0x1800623ce  xor     eax, eax
0x1800623d0  mov     rbx, rcx
0x1800623d3  movups  xmmword ptr [rbp+57h+var_60.dwJobNumberOfPagesPerSide], xmm0
0x1800623d7  movups  xmmword ptr [rbp+57h+var_60.dwJobPageOrderFlags], xmm0
0x1800623db  cmp     [rcx+58h], rax
0x1800623df  jz      loc_180062617
0x1800623e5  cmp     [rcx+170h], eax
0x1800623eb  jnz     loc_180062617
0x1800623f1  cmp     [rcx+16Ch], eax
0x1800623f7  jnz     loc_180062617
0x1800623fd  mov     rcx, [rcx+80h]
0x180062404  call    ValidRawDatatype
0x180062409  test    eax, eax
0x18006240b  jnz     loc_180062617
0x180062411  xorps   xmm0, xmm0
0x180062414  mov     dword ptr [rbx+16Ch], 1
0x18006241e  xor     ecx, ecx
0x180062420  mov     dword ptr [rbx+170h], 1
0x18006242a  movdqu  [rbp+57h+var_80], xmm0
0x18006242f  call    EnterSplSem
0x180062434  mov     rcx, [rbx+58h]
0x180062438  mov     rcx, [rcx+18h]
0x18006243c  call    cs:__imp_AllocSplStr
0x180062442  mov     rcx, [rbx+60h]
0x180062446  mov     r14, rax
0x180062449  mov     rcx, [rcx+18h]
0x18006244d  call    cs:__imp_AllocSplStr
0x180062453  mov     rcx, [rbx+60h]
0x180062457  mov     rsi, rax
0x18006245a  mov     r15d, [rcx+0C8h]
0x180062461  call    LeaveSplSem
0x180062466  test    r14, r14
0x180062469  jz      loc_1800625FC
0x18006246f  test    rsi, rsi
0x180062472  jz      loc_1800625FC
0x180062478  lea     rcx, [rbp+57h+var_70]; this
0x18006247c  call    ??0Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::Low2MediumIntegrity(void)
0x180062481  mov     rcx, [rbx+100h]; TokenHandle
0x180062488  lea     rdx, [rbp+57h+var_90]; int *
0x18006248c  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180062494  mov     [rbp+57h+var_90], 0
0x18006249b  call    ?PrincipalIsRemoteGuest@@YAKPEAXPEAH@Z; PrincipalIsRemoteGuest(void *,int *)
0x1800624a0  mov     edi, eax
0x1800624a2  test    eax, eax
0x1800624a4  jnz     loc_180062537
0x1800624aa  cmp     [rbp+57h+var_90], eax
0x1800624ad  jz      loc_180062550
0x1800624b3  cmp     qword ptr [rbx+100h], 0
0x1800624bb  jz      loc_180062550
0x1800624c1  call    cs:__imp_GetCurrentThread
0x1800624c7  xor     r8d, r8d; OpenAsSelf
0x1800624ca  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800624ce  mov     rcx, rax; ThreadHandle
0x1800624d1  lea     edi, [r8+0Ch]
0x1800624d5  mov     edx, edi; DesiredAccess
0x1800624d7  call    cs:__imp_OpenThreadToken
0x1800624dd  test    eax, eax
0x1800624df  jnz     short loc_18006250A
0x1800624e1  call    cs:__imp_GetCurrentThread
0x1800624e7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800624eb  mov     edx, edi; DesiredAccess
0x1800624ed  mov     rcx, rax; ThreadHandle
0x1800624f0  lea     r8d, [rdi-0Bh]; OpenAsSelf
0x1800624f4  call    cs:__imp_OpenThreadToken
0x1800624fa  test    eax, eax
0x1800624fc  jnz     short loc_18006250A
0x1800624fe  call    cs:__imp_GetLastError
0x180062504  mov     edi, eax
0x180062506  test    eax, eax
0x180062508  jnz     short loc_180062537
0x18006250a  xor     edx, edx; Token
0x18006250c  xor     ecx, ecx; Thread
0x18006250e  call    cs:__imp_SetThreadToken
0x180062514  test    eax, eax
0x180062516  jz      short loc_18006252B
0x180062518  mov     ecx, 2; ImpersonationLevel
0x18006251d  call    cs:__imp_ImpersonateSelf
0x180062523  test    eax, eax
0x180062525  jz      short loc_18006252B
0x180062527  xor     edi, edi
0x180062529  jmp     short loc_180062550
0x18006252b  call    cs:__imp_GetLastError
0x180062531  mov     edi, eax
0x180062533  test    eax, eax
0x180062535  jz      short loc_180062550
0x180062537  mov     r9d, edi
0x18006253a  lea     rdx, aFailedToSetThe_0; "Failed to set the appropriate security "...
0x180062541  mov     r8, r14
0x180062544  lea     rcx, aUpdatejobattri; "UpdateJobAttributes"
0x18006254b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180062550  mov     rax, [rbx+58h]
0x180062554  lea     rcx, [rbp+57h+var_80]; this
0x180062558  mov     r9, rsi; unsigned __int16 *
0x18006255b  mov     [rsp+0C0h+var_A0], r15d; unsigned int
0x180062560  mov     r8, r14; unsigned __int16 *
0x180062563  mov     rdx, [rax+118h]
0x18006256a  mov     rdx, [rdx+170h]; struct sandbox::SandboxManager *
0x180062571  call    ?Initialize@DriverJobAttributesAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG1K@Z; sandbox::DriverJobAttributesAdapter::Initialize(sandbox::SandboxManager *,ushort const *,ushort const *,ulong)
0x180062576  test    eax, eax
0x180062578  jnz     short loc_1800625A1
0x18006257a  mov     rdx, [rbx+68h]; struct _devicemodeW *
0x18006257e  lea     r8, [rbp+57h+var_60]; struct _ATTRIBUTE_INFO_1 *
0x180062582  lea     rcx, [rbp+57h+var_80]; this
0x180062586  call    ?QueryAttributes@DriverJobAttributesAdapter@sandbox@@QEAAHPEAU_devicemodeW@@PEAU_ATTRIBUTE_INFO_1@@@Z; sandbox::DriverJobAttributesAdapter::QueryAttributes(_devicemodeW *,_ATTRIBUTE_INFO_1 *)
0x18006258b  test    eax, eax
0x18006258d  jz      short loc_1800625A1
0x18006258f  mov     eax, [rbp+57h+var_60.dwJobNumberOfPagesPerSide]
0x180062592  mov     [rbx+16Ch], eax
0x180062598  mov     eax, [rbp+57h+var_60.dwDrvNumberOfPagesPerSide]
0x18006259b  mov     [rbx+170h], eax
0x1800625a1  test    edi, edi
0x1800625a3  jnz     short loc_1800625EA
0x1800625a5  mov     rax, [rbp+57h+TokenHandle]
0x1800625a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800625ad  jz      short loc_1800625EA
0x1800625af  test    rax, rax
0x1800625b2  jz      short loc_1800625EA
0x1800625b4  call    cs:__imp_RevertToSelf
0x1800625ba  test    eax, eax
0x1800625bc  jz      short loc_1800625D8
0x1800625be  mov     rdx, [rbp+57h+TokenHandle]
0x1800625c2  xor     eax, eax
0x1800625c4  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800625c8  cmovz   rdx, rax; Token
0x1800625cc  xor     ecx, ecx; Thread
0x1800625ce  call    cs:__imp_SetThreadToken
0x1800625d4  test    eax, eax
0x1800625d6  jnz     short loc_1800625EA
0x1800625d8  call    cs:__imp_GetLastError
0x1800625de  mov     edx, eax; unsigned int
0x1800625e0  mov     ecx, 68h ; 'h'; unsigned int
0x1800625e5  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x1800625ea  lea     rcx, [rbp+57h+TokenHandle]
0x1800625ee  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1800625f3  lea     rcx, [rbp+57h+var_70]; this
0x1800625f7  call    ??1Low2MediumIntegrity@NSecurityLibrary@@QEAA@XZ; NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity(void)
0x1800625fc  mov     rcx, r14
0x1800625ff  call    cs:__imp_DllFreeSplStr
0x180062605  mov     rcx, rsi
0x180062608  call    cs:__imp_DllFreeSplStr
0x18006260e  lea     rcx, [rbp+57h+var_80]; this
0x180062612  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x180062617  mov     rcx, [rbp+57h+var_40]
0x18006261b  xor     rcx, rsp; StackCookie
0x18006261e  call    __security_check_cookie
0x180062623  add     rsp, 98h
0x18006262a  pop     r15
0x18006262c  pop     r14
0x18006262e  pop     rdi
0x18006262f  pop     rsi
0x180062630  pop     rbx
0x180062631  pop     rbp
0x180062632  retn
```
