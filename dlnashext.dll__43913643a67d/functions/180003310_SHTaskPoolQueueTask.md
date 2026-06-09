# SHTaskPoolQueueTask

- ea: `0x180003310`
- end: `0x180003526`
- name: `SHTaskPoolQueueTask`
- size: `534`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, APTTYPE pAptType)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002c00`
- `0x18001e91c`

## callees

- `0x180001710`
- `0x180003310`
- `0x180004950`
- `0x18000c548`
- `0x18000e898`
- `0x18000f198`
- `0x180030c60`
- `0x1800320f8`
- `0x1800329dc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180003409`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180003409`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003399`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800033a2`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800033a2`

## string_xrefs

- `0x180003349`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x180003469`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x1800034c7`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x1800034e2`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall SHTaskPoolQueueTask(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *pAptType)
{
  __int64 v9; // rsi
  unsigned int v11; // eax
  unsigned int v12; // edi
  HANDLE CurrentThread; // rax
  unsigned int ThreadPriority; // eax
  unsigned int OptionsForPriority; // eax
  unsigned int v16; // r14d
  unsigned int v17; // ebx
  HRESULT ApartmentType; // eax
  int v19; // edi
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // esi
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-28h]
  APTTYPEQUALIFIER pAptQualifier; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  if ( pAptType )
    *pAptType = 0;
  v9 = a5;
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x677,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v25);
    return 2147942414LL;
  }
  v27[0] = 0;
  v11 = ResolveApartment();
  v12 = v11;
  if ( v11 == 4 || (a2 & 0x80u) != 0 && (unsigned __int8)OptionsCanRunNested(v11, a2) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
    goto LABEL_39;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  OptionsForPriority = GetOptionsForPriority(ThreadPriority);
  v16 = a2 & 0xF000;
  if ( (a2 & 0xF000) != 0 )
  {
    if ( (a2 & 0x60) == 0 )
      goto LABEL_16;
    v17 = a2 & 0xFFFF0FFF;
    if ( v16 > OptionsForPriority )
      OptionsForPriority = v16;
  }
  else
  {
    v17 = a2 & 0xFFFF0FFF;
    if ( OptionsForPriority < 0x5000 )
      OptionsForPriority = 20480;
  }
  a2 = OptionsForPriority | v17;
LABEL_16:
  if ( v12 == 3 )
  {
    v12 = 0;
    goto LABEL_29;
  }
  if ( v12 == 2 )
  {
    LODWORD(pAptType) = 0;
    pAptQualifier = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType((APTTYPE *)&pAptType, &pAptQualifier);
    v19 = ApartmentType;
    if ( ApartmentType < 0 )
    {
      v20 = (unsigned int)ApartmentType;
      v21 = 1678;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)v20,
        v25);
      goto LABEL_37;
    }
    v12 = 0;
    if ( (_DWORD)pAptType )
    {
      if ( (_DWORD)pAptType == 1 || (_DWORD)pAptType == 2 )
        goto LABEL_29;
      if ( (_DWORD)pAptType != 3 )
      {
        v19 = -2147418113;
        v21 = 1692;
LABEL_35:
        v20 = (unsigned int)v19;
        goto LABEL_36;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v27);
    v22 = Microsoft::WRL::Details::MakeAndInitialize<CRemoteTask,Windows::Internal::IComPoolTask,Windows::Internal::IComPoolTask * &>(
            v27,
            &a5);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x695,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)v22,
        v25);
      v19 = v23;
LABEL_37:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v27);
      return (unsigned int)v19;
    }
    v9 = v27[0];
  }
LABEL_29:
  if ( a4 )
  {
    v25 = v9;
    v19 = WorkThreadManager::s_QueueDelayedTask(v12, a2, a3, a4);
    if ( v19 < 0 )
    {
      v24 = 234;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)v19,
        v25);
      v21 = 1697;
      goto LABEL_35;
    }
  }
  else
  {
    v19 = WorkThreadManager::s_QueuePoolTask(v12, a2, a3, v9);
    if ( v19 < 0 )
    {
      v24 = 238;
      goto LABEL_34;
    }
  }
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v27);
  return 0;
}

```

## disassembly

```asm
0x180003310  push    rbp
0x180003312  push    rbx
0x180003313  push    rsi
0x180003314  push    rdi
0x180003315  push    r12
0x180003317  push    r13
0x180003319  push    r14
0x18000331b  push    r15
0x18000331d  mov     rbp, rsp
0x180003320  sub     rsp, 48h
0x180003324  mov     r15, [rbp+pAptType]
0x180003328  mov     r12d, r9d
0x18000332b  mov     r13d, r8d
0x18000332e  mov     ebx, edx
0x180003330  test    r15, r15
0x180003333  jz      short loc_18000333C
0x180003335  mov     qword ptr [r15], 0
0x18000333c  mov     rsi, [rbp+arg_20]
0x180003340  test    rsi, rsi
0x180003343  jnz     short loc_180003369
0x180003345  mov     rcx, [rbp+40h]; this
0x180003349  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180003350  mov     ebx, 8007000Eh
0x180003355  mov     edx, 677h; void *
0x18000335a  mov     r9d, ebx; char *
0x18000335d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003362  mov     eax, ebx
0x180003364  jmp     loc_180003515
0x180003369  mov     [rbp+var_10], 0
0x180003371  call    ResolveApartment
0x180003376  mov     edi, eax
0x180003378  cmp     eax, 4
0x18000337b  jz      loc_1800034FB
0x180003381  test    bl, bl
0x180003383  jns     short loc_180003396
0x180003385  mov     edx, ebx
0x180003387  mov     ecx, eax
0x180003389  call    OptionsCanRunNested
0x18000338e  test    al, al
0x180003390  jnz     loc_1800034FB
0x180003396  mov     r14d, ebx
0x180003399  call    cs:__imp_GetCurrentThread
0x18000339f  mov     rcx, rax; hThread
0x1800033a2  call    cs:__imp_GetThreadPriority
0x1800033a8  mov     ecx, eax
0x1800033aa  call    ?GetOptionsForPriority@@YA?AW4TaskOptions@Internal@Windows@@H@Z; GetOptionsForPriority(int)
0x1800033af  and     r14d, 0F000h
0x1800033b6  jnz     short loc_1800033CA
0x1800033b8  mov     ecx, 5000h
0x1800033bd  and     ebx, 0FFFF0FFFh
0x1800033c3  cmp     eax, ecx
0x1800033c5  cmovb   eax, ecx
0x1800033c8  jmp     short loc_1800033DC
0x1800033ca  test    bl, 60h
0x1800033cd  jz      short loc_1800033DE
0x1800033cf  and     ebx, 0FFFF0FFFh
0x1800033d5  cmp     r14d, eax
0x1800033d8  cmova   eax, r14d
0x1800033dc  or      ebx, eax
0x1800033de  cmp     edi, 3
0x1800033e1  jnz     short loc_1800033EA
0x1800033e3  xor     edi, edi
0x1800033e5  jmp     loc_180003485
0x1800033ea  cmp     edi, 2
0x1800033ed  jnz     loc_180003485
0x1800033f3  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x1800033f7  mov     dword ptr [rbp+pAptType], 0
0x1800033fe  lea     rcx, [rbp+pAptType]; pAptType
0x180003402  mov     [rbp+pAptQualifier], 0
0x180003409  call    cs:__imp_CoGetApartmentType
0x18000340f  mov     edi, eax
0x180003411  test    eax, eax
0x180003413  jns     short loc_180003422
0x180003415  mov     r9d, eax
0x180003418  mov     edx, 68Eh
0x18000341d  jmp     loc_1800034DE
0x180003422  mov     ecx, dword ptr [rbp+pAptType]
0x180003425  xor     edi, edi
0x180003427  test    ecx, ecx
0x180003429  jz      short loc_180003449
0x18000342b  sub     ecx, 1
0x18000342e  jz      short loc_180003485
0x180003430  sub     ecx, 1
0x180003433  jz      short loc_180003485
0x180003435  cmp     ecx, 1
0x180003438  jz      short loc_180003449
0x18000343a  mov     edi, 8000FFFFh
0x18000343f  mov     edx, 69Ch
0x180003444  jmp     loc_1800034DB
0x180003449  lea     rcx, [rbp+var_10]
0x18000344d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003452  lea     rdx, [rbp+arg_20]
0x180003456  lea     rcx, [rbp+var_10]
0x18000345a  call    ??$MakeAndInitialize@VCRemoteTask@@UIComPoolTask@Internal@Windows@@AEAPEAU234@@Details@WRL@Microsoft@@YAJPEAPEAUIComPoolTask@Internal@Windows@@AEAPEAU345@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRemoteTask,Windows::Internal::IComPoolTask,Windows::Internal::IComPoolTask * &>(Windows::Internal::IComPoolTask * *,Windows::Internal::IComPoolTask * &)
0x18000345f  mov     esi, eax
0x180003461  test    eax, eax
0x180003463  jns     short loc_180003481
0x180003465  mov     rcx, [rbp+40h]; this
0x180003469  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x180003470  mov     r9d, eax; char *
0x180003473  mov     edx, 695h; void *
0x180003478  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000347d  mov     edi, esi
0x18000347f  jmp     short loc_1800034EE
0x180003481  mov     rsi, [rbp+var_10]
0x180003485  mov     r8d, r13d
0x180003488  mov     edx, ebx
0x18000348a  mov     ecx, edi
0x18000348c  test    r12d, r12d
0x18000348f  jz      short loc_1800034B0
0x180003491  mov     [rsp+48h+var_20], r15
0x180003496  mov     r9d, r12d
0x180003499  mov     [rsp+48h+var_28], rsi
0x18000349e  call    ?s_QueueDelayedTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KKPEAUIComPoolTask@34@PEAPEAUIUnknown@@@Z; WorkThreadManager::s_QueueDelayedTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,ulong,Windows::Internal::IComPoolTask *,IUnknown * *)
0x1800034a3  mov     edi, eax
0x1800034a5  test    eax, eax
0x1800034a7  jns     short loc_18000350A
0x1800034a9  mov     edx, 0EAh
0x1800034ae  jmp     short loc_1800034C3
0x1800034b0  mov     r9, rsi
0x1800034b3  call    ?s_QueuePoolTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@@Z; WorkThreadManager::s_QueuePoolTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *)
0x1800034b8  mov     edi, eax
0x1800034ba  test    eax, eax
0x1800034bc  jns     short loc_18000350A
0x1800034be  mov     edx, 0EEh; void *
0x1800034c3  mov     rcx, [rbp+40h]; this
0x1800034c7  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800034ce  mov     r9d, edi; char *
0x1800034d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800034d6  mov     edx, 6A1h; void *
0x1800034db  mov     r9d, edi; char *
0x1800034de  mov     rcx, [rbp+40h]; this
0x1800034e2  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x1800034e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800034ee  lea     rcx, [rbp+var_10]
0x1800034f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800034f7  mov     eax, edi
0x1800034f9  jmp     short loc_180003515
0x1800034fb  mov     rax, [rsi]
0x1800034fe  mov     rcx, rsi
0x180003501  mov     rax, [rax+18h]
0x180003505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350a  lea     rcx, [rbp+var_10]
0x18000350e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003513  xor     eax, eax
0x180003515  add     rsp, 48h
0x180003519  pop     r15
0x18000351b  pop     r14
0x18000351d  pop     r13
0x18000351f  pop     r12
0x180003521  pop     rdi
0x180003522  pop     rsi
0x180003523  pop     rbx
0x180003524  pop     rbp
0x180003525  retn
```
