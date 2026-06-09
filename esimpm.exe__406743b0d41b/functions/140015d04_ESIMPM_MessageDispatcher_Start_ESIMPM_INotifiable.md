# ESIMPM::MessageDispatcher::_Start(ESIMPM::INotifiable *)

- ea: `0x140015d04`
- end: `0x140015ef1`
- name: `?_Start@MessageDispatcher@ESIMPM@@SAKPEAVINotifiable@2@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct ESIMPM::INotifiable *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140024d88`

## callees

- `0x140002f84`
- `0x140003244`
- `0x140014abc`
- `0x140014f64`
- `0x140015d04`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015ea7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015ea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015e99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015e99`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015ebe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140015ebe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140015d47`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140015d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015e67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140015e55`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x140015e55`

## string_xrefs

- `0x140015e02`: `Thread pool cleanup group already initialized.`
- `0x140015e0b`: `ESIMPM::MessageDispatcher::initializeThreadpoolEnvironment`
- `0x140015e7b`: `ESIMPM::MessageDispatcher::initializeThreadpoolEnvironment`
- `0x140015e72`: `::CreateThreadpoolCleanupGroup failed.%x`

## pseudocode

```c
__int64 __fastcall ESIMPM::MessageDispatcher::_Start(struct ESIMPM::INotifiable *a1)
{
  char *v2; // rbx
  _QWORD *v3; // rax
  _DWORD *v4; // rax
  volatile signed __int32 *v5; // rbx
  char *v6; // rdi
  __int64 LastError; // rsi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  void *v9; // rbx
  __int64 result; // rax
  void *Block; // [rsp+58h] [rbp+10h] BYREF
  char *v12; // [rsp+60h] [rbp+18h]

  try
  {
    v2 = (char *)operator new(0x98u);
    v12 = v2;
    *(_QWORD *)v2 = 0;
    *((_QWORD *)v2 + 1) = 0;
    v3 = operator new(0x20u);
    *v3 = v3;
    v3[1] = v3;
    *(_QWORD *)v2 = v3;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
    v2[56] = 0;
    *((_QWORD *)v2 + 17) = 0;
    *((_QWORD *)v2 + 18) = a1;
    Block = v2;
    v12 = v2;
    v4 = operator new(0x18u);
    v4[2] = 1;
    v4[3] = 1;
    *(_QWORD *)v4 = &std::_Ref_count<ESIMPM::MessageDispatcher>::`vftable';
    *((_QWORD *)v4 + 2) = v2;
    ESIMPM::MessageDispatcher::s_Dispatcher = v2;
    v5 = (volatile signed __int32 *)qword_140075D08;
    qword_140075D08 = (__int64)v4;
    if ( v5 )
    {
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( !_InterlockedDecrement(v5 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
    Block = 0;
    v6 = (char *)ESIMPM::MessageDispatcher::s_Dispatcher;
    if ( *((_QWORD *)ESIMPM::MessageDispatcher::s_Dispatcher + 17) )
    {
      ESIMPM::Log::Error(
        "ESIMPM::MessageDispatcher::initializeThreadpoolEnvironment",
        0,
        L"Thread pool cleanup group already initialized.");
      LODWORD(LastError) = 31;
    }
    else
    {
      *((_DWORD *)ESIMPM::MessageDispatcher::s_Dispatcher + 16) = 3;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 12) = 0;
      *((_QWORD *)v6 + 13) = 0;
      *((_QWORD *)v6 + 14) = 0;
      *((_DWORD *)v6 + 30) = 0;
      *((_DWORD *)v6 + 31) = 1;
      *((_DWORD *)v6 + 32) = 72;
      ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
      *((_QWORD *)v6 + 17) = ThreadpoolCleanupGroup;
      if ( ThreadpoolCleanupGroup )
      {
        *((_QWORD *)v6 + 10) = ThreadpoolCleanupGroup;
        *((_QWORD *)v6 + 11) = 0;
      }
      else
      {
        LastError = GetLastError();
        ESIMPM::Log::Error(
          "ESIMPM::MessageDispatcher::initializeThreadpoolEnvironment",
          0,
          L"::CreateThreadpoolCleanupGroup failed.%x",
          LastError,
          &Block,
          1);
        if ( (_DWORD)LastError )
          goto LABEL_13;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
      v6[56] = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 16));
      LODWORD(LastError) = 0;
    }
LABEL_13:
    v9 = Block;
    if ( Block )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)Block + 16));
      std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(v9);
      operator delete(v9);
    }
    result = (unsigned int)LastError;
  }
  catch ( std::exception )
  {
    ESIMPM::Log::Error("ESIMPM::MessageDispatcher::_Start", 0, L"Memory Allocation Failure");
    SetLastError(8u);
    return 8;
  }
  v2 = (char *)operator new(0x98u);
}

```

## disassembly

```asm
0x140015d04  mov     [rsp+arg_0], rbx
0x140015d09  push    rsi
0x140015d0a  push    rdi
0x140015d0b  push    r14
0x140015d0d  sub     rsp, 30h
0x140015d11  mov     rdi, rcx
0x140015d14  mov     ecx, 98h; Size
0x140015d19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015d1e  mov     rbx, rax
0x140015d21  mov     [rsp+48h+arg_10], rax
0x140015d26  xor     r14d, r14d
0x140015d29  mov     [rax], r14
0x140015d2c  mov     [rax+8], r14
0x140015d30  lea     ecx, [r14+20h]; Size
0x140015d34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015d39  mov     [rax], rax
0x140015d3c  mov     [rax+8], rax
0x140015d40  mov     [rbx], rax
0x140015d43  lea     rcx, [rbx+10h]; lpCriticalSection
0x140015d47  call    cs:__imp_InitializeCriticalSection
0x140015d4d  mov     [rbx+38h], r14b
0x140015d51  mov     [rbx+88h], r14
0x140015d58  mov     [rbx+90h], rdi
0x140015d5f  mov     [rsp+48h+Block], rbx
0x140015d64  lea     rax, [rsp+48h+Block]
0x140015d69  mov     [rsp+48h+var_28], rax
0x140015d6e  mov     [rsp+48h+var_20], 1
0x140015d73  mov     [rsp+48h+arg_10], rbx
0x140015d78  lea     ecx, [r14+18h]; Size
0x140015d7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015d81  mov     dword ptr [rax+8], 1
0x140015d88  mov     dword ptr [rax+0Ch], 1
0x140015d8f  lea     rcx, ??_7?$_Ref_count@VMessageDispatcher@ESIMPM@@@std@@6B@; const std::_Ref_count<ESIMPM::MessageDispatcher>::`vftable'
0x140015d96  mov     [rax], rcx
0x140015d99  mov     [rax+10h], rbx
0x140015d9d  mov     cs:?s_Dispatcher@MessageDispatcher@ESIMPM@@0V?$shared_ptr@VMessageDispatcher@ESIMPM@@@std@@A, rbx; std::shared_ptr<ESIMPM::MessageDispatcher> ESIMPM::MessageDispatcher::s_Dispatcher
0x140015da4  mov     rbx, cs:qword_140075D08
0x140015dab  mov     cs:qword_140075D08, rax
0x140015db2  test    rbx, rbx
0x140015db5  jz      short loc_140015DED
0x140015db7  or      edi, 0FFFFFFFFh
0x140015dba  mov     eax, edi
0x140015dbc  lock xadd [rbx+8], eax
0x140015dc1  add     eax, edi
0x140015dc3  jnz     short loc_140015DED
0x140015dc5  mov     rax, [rbx]
0x140015dc8  mov     rcx, rbx
0x140015dcb  mov     rax, [rax]
0x140015dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015dd3  mov     eax, edi
0x140015dd5  lock xadd [rbx+0Ch], eax
0x140015dda  add     eax, edi
0x140015ddc  jnz     short loc_140015DED
0x140015dde  mov     rax, [rbx]
0x140015de1  mov     rcx, rbx
0x140015de4  mov     rax, [rax+8]
0x140015de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ded  mov     [rsp+48h+Block], r14
0x140015df2  mov     rdi, cs:?s_Dispatcher@MessageDispatcher@ESIMPM@@0V?$shared_ptr@VMessageDispatcher@ESIMPM@@@std@@A; std::shared_ptr<ESIMPM::MessageDispatcher> ESIMPM::MessageDispatcher::s_Dispatcher
0x140015df9  cmp     [rdi+88h], r14
0x140015e00  jz      short loc_140015E21
0x140015e02  lea     r8, aThreadPoolClea; "Thread pool cleanup group already initi"...
0x140015e09  xor     edx, edx; struct _GUID *
0x140015e0b  lea     rcx, aEsimpmMessaged_8; "ESIMPM::MessageDispatcher::initializeTh"...
0x140015e12  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140015e17  mov     esi, 1Fh
0x140015e1c  jmp     loc_140015EB0
0x140015e21  mov     dword ptr [rdi+40h], 3
0x140015e28  mov     [rdi+48h], r14
0x140015e2c  mov     [rdi+50h], r14
0x140015e30  mov     [rdi+58h], r14
0x140015e34  mov     [rdi+60h], r14
0x140015e38  mov     [rdi+68h], r14
0x140015e3c  mov     [rdi+70h], r14
0x140015e40  mov     [rdi+78h], r14d
0x140015e44  mov     dword ptr [rdi+7Ch], 1
0x140015e4b  mov     dword ptr [rdi+80h], 48h ; 'H'
0x140015e55  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140015e5b  mov     [rdi+88h], rax
0x140015e62  test    rax, rax
0x140015e65  jnz     short loc_140015E8D
0x140015e67  call    cs:__imp_GetLastError
0x140015e6d  mov     esi, eax
0x140015e6f  mov     r9d, eax
0x140015e72  lea     r8, aCreatethreadpo; "::CreateThreadpoolCleanupGroup failed.%"...
0x140015e79  xor     edx, edx; struct _GUID *
0x140015e7b  lea     rcx, aEsimpmMessaged_8; "ESIMPM::MessageDispatcher::initializeTh"...
0x140015e82  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x140015e87  test    esi, esi
0x140015e89  jz      short loc_140015E95
0x140015e8b  jmp     short loc_140015EB0
0x140015e8d  mov     [rdi+50h], rax
0x140015e91  mov     [rdi+58h], r14
0x140015e95  lea     rcx, [rdi+10h]; lpCriticalSection
0x140015e99  call    cs:__imp_EnterCriticalSection
0x140015e9f  mov     byte ptr [rdi+38h], 1
0x140015ea3  lea     rcx, [rdi+10h]; lpCriticalSection
0x140015ea7  call    cs:__imp_LeaveCriticalSection
0x140015ead  mov     esi, r14d
0x140015eb0  mov     rbx, [rsp+48h+Block]
0x140015eb5  test    rbx, rbx
0x140015eb8  jz      short loc_140015ED9
0x140015eba  lea     rcx, [rbx+10h]; lpCriticalSection
0x140015ebe  call    cs:__imp_DeleteCriticalSection
0x140015ec4  mov     rcx, rbx
0x140015ec7  call    ??1?$list@V?$shared_ptr@VMessage@ESIMPM@@@std@@V?$allocator@V?$shared_ptr@VMessage@ESIMPM@@@std@@@2@@std@@QEAA@XZ; std::list<std::shared_ptr<ESIMPM::Message>>::~list<std::shared_ptr<ESIMPM::Message>>(void)
0x140015ecc  mov     edx, 98h
0x140015ed1  mov     rcx, rbx; Block
0x140015ed4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015ed9  mov     eax, esi
0x140015edb  jmp     short loc_140015EE2
0x140015edd  mov     eax, 8
0x140015ee2  mov     rbx, [rsp+48h+arg_0]
0x140015ee7  add     rsp, 30h
0x140015eeb  pop     r14
0x140015eed  pop     rdi
0x140015eee  pop     rsi
0x140015eef  retn
```
