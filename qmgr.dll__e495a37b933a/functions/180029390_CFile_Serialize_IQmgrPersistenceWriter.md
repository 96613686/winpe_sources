# CFile::Serialize(IQmgrPersistenceWriter &)

- ea: `0x180029390`
- end: `0x180029a7b`
- name: `?Serialize@CFile@@AEAAJAEAVIQmgrPersistenceWriter@@@Z`
- size: `1771`
- prototype: `int(CFile *__hidden this, struct IQmgrPersistenceWriter *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002a660`

## callees

- `0x1800231c8`
- `0x180029390`
- `0x1800701a8`
- `0x18007dd84`
- `0x1800a1114`
- `0x1800ab7fc`
- `0x1800cab88`
- `0x18010f010`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180029690`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180029690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029a36`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800298ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800298ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFile::Serialize(CFile *this, struct IQmgrPersistenceWriter *a2)
{
  int v4; // edi
  int v5; // edi
  int v6; // edi
  void *v7; // rax
  int v8; // edi
  int v9; // edi
  ULONG v10; // edi
  void *v11; // rcx
  __int64 v12; // r14
  unsigned int i; // r15d
  struct _RTL_CRITICAL_SECTION *v14; // rsi
  const wchar_t *v15; // r9
  GUID v17; // [rsp+30h] [rbp-20h] BYREF
  __int128 v18; // [rsp+40h] [rbp-10h] BYREF
  HANDLE OwningThread; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+88h] [rbp+38h] BYREF

  *((_BYTE *)this + 408) = 0;
  v17 = (GUID)xmmword_18011A360;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v17, 16);
  if ( *(_DWORD *)(*((_QWORD *)this + 33) + 664LL) )
  {
    OwningThread = (HANDLE)*((_QWORD *)this + 6);
    SafeWritePersistentState(a2, &OwningThread, 8u);
  }
  LODWORD(OwningThread) = **((_DWORD **)this + 2) + 1;
  v4 = (int)OwningThread;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 2) + 12LL,
    (unsigned int)(2 * v4));
  LODWORD(OwningThread) = **((_DWORD **)this + 1) + 1;
  v5 = (int)OwningThread;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 1) + 12LL,
    (unsigned int)(2 * v5));
  LODWORD(OwningThread) = **((_DWORD **)this + 3) + 1;
  v6 = (int)OwningThread;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 3) + 12LL,
    (unsigned int)(2 * v6));
  if ( *((_BYTE *)this + 88) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SI(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        *((_QWORD *)this + 3) + 12,
        *((_QWORD *)this + 10));
    v7 = (void *)*((_QWORD *)this + 10);
  }
  else
  {
    v7 = (void *)*((_QWORD *)this + 9);
  }
  OwningThread = v7;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    8);
  OwningThread = (HANDLE)*((_QWORD *)this + 8);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    8);
  LOBYTE(OwningThread) = *((_BYTE *)this + 256);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  LODWORD(OwningThread) = **((_DWORD **)this + 34) + 1;
  v8 = (int)OwningThread;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 34) + 12LL,
    (unsigned int)(2 * v8));
  LODWORD(OwningThread) = **((_DWORD **)this + 35) + 1;
  v9 = (int)OwningThread;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 35) + 12LL,
    (unsigned int)(2 * v9));
  LODWORD(OwningThread) = *((_DWORD *)this + 72);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  LODWORD(OwningThread) = *((_DWORD *)this + 73);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  OwningThread = (HANDLE)*((_QWORD *)this + 7);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    8);
  LODWORD(OwningThread) = *((_DWORD *)this + 74);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  v10 = 0;
  v11 = (void *)*((_QWORD *)this + 38);
  if ( v11 )
    v10 = RtlLengthSecurityDescriptor(v11);
  LODWORD(OwningThread) = v10;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    4);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, _QWORD, _QWORD))(*(_QWORD *)a2 + 8LL))(
    a2,
    *((_QWORD *)this + 38),
    v10);
  LOBYTE(OwningThread) = *((_BYTE *)this + 257);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  v12 = *((_QWORD *)this + 39);
  if ( v12 )
  {
    LODWORD(OwningThread) = *(_DWORD *)(v12 + 32);
    SafeWritePersistentState(a2, &OwningThread, 4u);
    for ( i = 0; i < *(_DWORD *)(v12 + 32); ++i )
    {
      OwningThread = *(HANDLE *)(*(_QWORD *)(v12 + 40) + 16LL * i);
      SafeWritePersistentState(a2, &OwningThread, 8u);
      v20 = *(_QWORD *)(*(_QWORD *)(v12 + 40) + 16LL * i + 8);
      SafeWritePersistentState(a2, &v20, 8u);
    }
  }
  else
  {
    LODWORD(OwningThread) = 0;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
      a2,
      &OwningThread,
      4);
  }
  if ( !*(_DWORD *)(*((_QWORD *)this + 33) + 664LL) )
  {
    OwningThread = (HANDLE)*((_QWORD *)this + 6);
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
      a2,
      &OwningThread,
      8);
    v17 = GUID_NULL;
    (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, GUID *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v17, 16);
  }
  LOBYTE(OwningThread) = *((_BYTE *)this + 89);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  LOBYTE(OwningThread) = *((_BYTE *)this + 344);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  LOBYTE(OwningThread) = *((_BYTE *)this + 345);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  LOBYTE(OwningThread) = *((_BYTE *)this + 346);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  OwningThread = (HANDLE)*((_QWORD *)this + 41);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    8);
  OwningThread = (HANDLE)*((_QWORD *)this + 42);
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    8);
  GetSystemTimeAsFileTime((LPFILETIME)this + 50);
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 96);
  *(_QWORD *)v17.Data4 = v14;
  if ( LOBYTE(v14[1].DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v14);
  }
  EnterCriticalSection(v14);
  LOBYTE(v17.Data1) = 1;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v15 = L"true";
    if ( !LOBYTE(v14[3].SpinCount) )
      v15 = L"false";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f9d2e0a0012f39e3bbca280c317bc35f_Traceguids, v15);
  }
  v18 = xmmword_18011A350;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v18, 16);
  LOBYTE(OwningThread) = v14[3].SpinCount;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, HANDLE *, __int64))(*(_QWORD *)a2 + 8LL))(
    a2,
    &OwningThread,
    1);
  if ( LOBYTE(v14[3].SpinCount) )
  {
    OwningThread = v14[3].OwningThread;
    SafeWritePersistentState(a2, &OwningThread, 8u);
    LOBYTE(OwningThread) = BYTE3(v14[3].SpinCount);
    SafeWritePersistentState(a2, &OwningThread, 1u);
    RangeTracker::SerializeList(a2, &v14[1].LockSemaphore);
    RangeTracker::SerializeQueue(a2);
  }
  v18 = xmmword_18011A350;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v18, 16);
  if ( LOBYTE(v14[1].DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v14);
  }
  LeaveCriticalSection(v14);
  v18 = xmmword_18011A360;
  (*(void (__fastcall **)(struct IQmgrPersistenceWriter *, __int128 *, __int64))(*(_QWORD *)a2 + 8LL))(a2, &v18, 16);
  return 0;
}

```

## disassembly

```asm
0x180029390  mov     [rsp-28h+arg_10], rbx
0x180029395  mov     [rsp-28h+arg_18], rsi
0x18002939a  push    rbp
0x18002939b  push    rdi
0x18002939c  push    r12
0x18002939e  push    r14
0x1800293a0  push    r15
0x1800293a2  mov     rbp, rsp
0x1800293a5  sub     rsp, 50h
0x1800293a9  mov     rbx, rdx
0x1800293ac  mov     rsi, rcx
0x1800293af  mov     byte ptr [rcx+198h], 0
0x1800293b6  movups  xmm0, cs:xmmword_18011A360
0x1800293bd  movaps  [rbp+var_20], xmm0
0x1800293c1  mov     rax, [rdx]
0x1800293c4  mov     r8d, 10h
0x1800293ca  lea     rdx, [rbp+var_20]
0x1800293ce  mov     rcx, rbx
0x1800293d1  mov     rax, [rax+8]
0x1800293d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293da  mov     rax, [rsi+108h]
0x1800293e1  cmp     dword ptr [rax+298h], 0
0x1800293e8  jz      short loc_180029404
0x1800293ea  mov     rax, [rsi+30h]
0x1800293ee  mov     [rbp+arg_0], rax
0x1800293f2  mov     r8d, 8; unsigned int
0x1800293f8  lea     rdx, [rbp+arg_0]; void *
0x1800293fc  mov     rcx, rbx; struct IQmgrPersistenceWriter *
0x1800293ff  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180029404  mov     rax, [rsi+10h]
0x180029408  mov     edi, [rax]
0x18002940a  inc     edi
0x18002940c  mov     dword ptr [rbp+arg_0], edi
0x18002940f  mov     rax, [rbx]
0x180029412  mov     r8d, 4
0x180029418  lea     rdx, [rbp+arg_0]
0x18002941c  mov     rcx, rbx
0x18002941f  mov     rax, [rax+8]
0x180029423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029428  mov     rax, [rbx]
0x18002942b  lea     r8d, [rdi+rdi]
0x18002942f  mov     rdx, [rsi+10h]
0x180029433  add     rdx, 0Ch
0x180029437  mov     rcx, rbx
0x18002943a  mov     rax, [rax+8]
0x18002943e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029443  mov     rax, [rsi+8]
0x180029447  mov     edi, [rax]
0x180029449  inc     edi
0x18002944b  mov     dword ptr [rbp+arg_0], edi
0x18002944e  mov     rax, [rbx]
0x180029451  mov     r8d, 4
0x180029457  lea     rdx, [rbp+arg_0]
0x18002945b  mov     rcx, rbx
0x18002945e  mov     rax, [rax+8]
0x180029462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029467  mov     rax, [rbx]
0x18002946a  lea     r8d, [rdi+rdi]
0x18002946e  mov     rdx, [rsi+8]
0x180029472  add     rdx, 0Ch
0x180029476  mov     rcx, rbx
0x180029479  mov     rax, [rax+8]
0x18002947d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029482  mov     rax, [rsi+18h]
0x180029486  mov     edi, [rax]
0x180029488  inc     edi
0x18002948a  mov     dword ptr [rbp+arg_0], edi
0x18002948d  mov     rax, [rbx]
0x180029490  mov     r8d, 4
0x180029496  lea     rdx, [rbp+arg_0]
0x18002949a  mov     rcx, rbx
0x18002949d  mov     rax, [rax+8]
0x1800294a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294a6  mov     rax, [rbx]
0x1800294a9  lea     r8d, [rdi+rdi]
0x1800294ad  mov     rdx, [rsi+18h]
0x1800294b1  add     rdx, 0Ch
0x1800294b5  mov     rcx, rbx
0x1800294b8  mov     rax, [rax+8]
0x1800294bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294c1  lea     r12, WPP_GLOBAL_Control
0x1800294c8  cmp     byte ptr [rsi+58h], 0
0x1800294cc  jz      short loc_18002950C
0x1800294ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294d5  cmp     rcx, r12
0x1800294d8  jz      short loc_180029506
0x1800294da  test    byte ptr [rcx+1Ch], 1
0x1800294de  jz      short loc_180029506
0x1800294e0  mov     r9, [rsi+18h]
0x1800294e4  add     r9, 0Ch
0x1800294e8  mov     edx, 1Fh
0x1800294ed  mov     rax, [rsi+50h]
0x1800294f1  mov     [rsp+50h+var_30], rax
0x1800294f6  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x1800294fd  mov     rcx, [rcx+10h]
0x180029501  call    WPP_SF_SI
0x180029506  mov     rax, [rsi+50h]
0x18002950a  jmp     short loc_180029510
0x18002950c  mov     rax, [rsi+48h]
0x180029510  mov     [rbp+arg_0], rax
0x180029514  mov     rax, [rbx]
0x180029517  mov     r8d, 8
0x18002951d  lea     rdx, [rbp+arg_0]
0x180029521  mov     rcx, rbx
0x180029524  mov     rax, [rax+8]
0x180029528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002952d  mov     rax, [rsi+40h]
0x180029531  mov     [rbp+arg_0], rax
0x180029535  mov     rax, [rbx]
0x180029538  mov     r8d, 8
0x18002953e  lea     rdx, [rbp+arg_0]
0x180029542  mov     rcx, rbx
0x180029545  mov     rax, [rax+8]
0x180029549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002954e  movzx   eax, byte ptr [rsi+100h]
0x180029555  mov     byte ptr [rbp+arg_0], al
0x180029558  mov     rax, [rbx]
0x18002955b  mov     r8d, 1
0x180029561  lea     rdx, [rbp+arg_0]
0x180029565  mov     rcx, rbx
0x180029568  mov     rax, [rax+8]
0x18002956c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029571  mov     rax, [rsi+110h]
0x180029578  mov     edi, [rax]
0x18002957a  inc     edi
0x18002957c  mov     dword ptr [rbp+arg_0], edi
0x18002957f  mov     rax, [rbx]
0x180029582  mov     r8d, 4
0x180029588  lea     rdx, [rbp+arg_0]
0x18002958c  mov     rcx, rbx
0x18002958f  mov     rax, [rax+8]
0x180029593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029598  mov     rax, [rbx]
0x18002959b  lea     r8d, [rdi+rdi]
0x18002959f  mov     rdx, [rsi+110h]
0x1800295a6  add     rdx, 0Ch
0x1800295aa  mov     rcx, rbx
0x1800295ad  mov     rax, [rax+8]
0x1800295b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295b6  mov     rax, [rsi+118h]
0x1800295bd  mov     edi, [rax]
0x1800295bf  inc     edi
0x1800295c1  mov     dword ptr [rbp+arg_0], edi
0x1800295c4  mov     rax, [rbx]
0x1800295c7  mov     r8d, 4
0x1800295cd  lea     rdx, [rbp+arg_0]
0x1800295d1  mov     rcx, rbx
0x1800295d4  mov     rax, [rax+8]
0x1800295d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295dd  mov     rax, [rbx]
0x1800295e0  lea     r8d, [rdi+rdi]
0x1800295e4  mov     rdx, [rsi+118h]
0x1800295eb  add     rdx, 0Ch
0x1800295ef  mov     rcx, rbx
0x1800295f2  mov     rax, [rax+8]
0x1800295f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295fb  mov     eax, [rsi+120h]
0x180029601  mov     dword ptr [rbp+arg_0], eax
0x180029604  mov     rax, [rbx]
0x180029607  mov     r8d, 4
0x18002960d  lea     rdx, [rbp+arg_0]
0x180029611  mov     rcx, rbx
0x180029614  mov     rax, [rax+8]
0x180029618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002961d  mov     eax, [rsi+124h]
0x180029623  mov     dword ptr [rbp+arg_0], eax
0x180029626  mov     rax, [rbx]
0x180029629  mov     r8d, 4
0x18002962f  lea     rdx, [rbp+arg_0]
0x180029633  mov     rcx, rbx
0x180029636  mov     rax, [rax+8]
0x18002963a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002963f  mov     rax, [rsi+38h]
0x180029643  mov     [rbp+arg_0], rax
0x180029647  mov     rax, [rbx]
0x18002964a  mov     r8d, 8
0x180029650  lea     rdx, [rbp+arg_0]
0x180029654  mov     rcx, rbx
0x180029657  mov     rax, [rax+8]
0x18002965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029660  mov     eax, [rsi+128h]
0x180029666  mov     dword ptr [rbp+arg_0], eax
0x180029669  mov     rax, [rbx]
0x18002966c  mov     r8d, 4
0x180029672  lea     rdx, [rbp+arg_0]
0x180029676  mov     rcx, rbx
0x180029679  mov     rax, [rax+8]
0x18002967d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029682  xor     edi, edi
0x180029684  mov     rcx, [rsi+130h]; SecurityDescriptor
0x18002968b  test    rcx, rcx
0x18002968e  jz      short loc_180029698
0x180029690  call    cs:__imp_RtlLengthSecurityDescriptor
0x180029696  mov     edi, eax
0x180029698  mov     dword ptr [rbp+arg_0], edi
0x18002969b  mov     rcx, [rbx]
0x18002969e  mov     rax, [rcx+8]
0x1800296a2  mov     r8d, 4
0x1800296a8  lea     rdx, [rbp+arg_0]
0x1800296ac  mov     rcx, rbx
0x1800296af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b4  mov     rcx, [rbx]
0x1800296b7  mov     rax, [rcx+8]
0x1800296bb  mov     r8d, edi
0x1800296be  mov     rdx, [rsi+130h]
0x1800296c5  mov     rcx, rbx
0x1800296c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296cd  movzx   eax, byte ptr [rsi+101h]
0x1800296d4  mov     byte ptr [rbp+arg_0], al
0x1800296d7  mov     rax, [rbx]
0x1800296da  mov     r8d, 1
0x1800296e0  lea     rdx, [rbp+arg_0]
0x1800296e4  mov     rcx, rbx
0x1800296e7  mov     rax, [rax+8]
0x1800296eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296f0  mov     r14, [rsi+138h]
0x1800296f7  mov     r8d, 4; unsigned int
0x1800296fd  lea     rdx, [rbp+arg_0]; void *
0x180029701  mov     rcx, rbx; struct IQmgrPersistenceWriter *
0x180029704  test    r14, r14
0x180029707  jz      short loc_18002976C
0x180029709  mov     eax, [r14+20h]
0x18002970d  mov     dword ptr [rbp+arg_0], eax
0x180029710  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180029715  xor     r15d, r15d
0x180029718  cmp     [r14+20h], r15d
0x18002971c  jbe     short loc_18002977F
0x18002971e  mov     edi, r15d
0x180029721  add     rdi, rdi
0x180029724  mov     rax, [r14+28h]
0x180029728  mov     rcx, [rax+rdi*8]
0x18002972c  mov     [rbp+arg_0], rcx
0x180029730  mov     r8d, 8; unsigned int
0x180029736  lea     rdx, [rbp+arg_0]; void *
0x18002973a  mov     rcx, rbx; struct IQmgrPersistenceWriter *
0x18002973d  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180029742  mov     rax, [r14+28h]
0x180029746  mov     rcx, [rax+rdi*8+8]
0x18002974b  mov     [rbp+arg_8], rcx
0x18002974f  mov     r8d, 8; unsigned int
0x180029755  lea     rdx, [rbp+arg_8]; void *
0x180029759  mov     rcx, rbx; struct IQmgrPersistenceWriter *
0x18002975c  call    ?SafeWritePersistentState@@YAXAEAVIQmgrPersistenceWriter@@PEBXK@Z; SafeWritePersistentState(IQmgrPersistenceWriter &,void const *,ulong)
0x180029761  inc     r15d
0x180029764  cmp     r15d, [r14+20h]
0x180029768  jb      short loc_18002971E
0x18002976a  jmp     short loc_18002977F
0x18002976c  mov     dword ptr [rbp+arg_0], 0
0x180029773  mov     rax, [rbx]
0x180029776  mov     rax, [rax+8]
0x18002977a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002977f  mov     rax, [rsi+108h]
0x180029786  cmp     dword ptr [rax+298h], 0
0x18002978d  jnz     short loc_1800297D4
0x18002978f  mov     rax, [rsi+30h]
0x180029793  mov     [rbp+arg_0], rax
0x180029797  mov     rax, [rbx]
0x18002979a  mov     r8d, 8
0x1800297a0  lea     rdx, [rbp+arg_0]
0x1800297a4  mov     rcx, rbx
0x1800297a7  mov     rax, [rax+8]
0x1800297ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297b0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800297b7  movaps  [rbp+var_20], xmm0
0x1800297bb  mov     rax, [rbx]
0x1800297be  mov     r8d, 10h
0x1800297c4  lea     rdx, [rbp+var_20]
0x1800297c8  mov     rcx, rbx
0x1800297cb  mov     rax, [rax+8]
0x1800297cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d4  movzx   eax, byte ptr [rsi+59h]
0x1800297d8  mov     byte ptr [rbp+arg_0], al
0x1800297db  mov     rax, [rbx]
0x1800297de  mov     r8d, 1
0x1800297e4  lea     rdx, [rbp+arg_0]
0x1800297e8  mov     rcx, rbx
0x1800297eb  mov     rax, [rax+8]
0x1800297ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f4  movzx   eax, byte ptr [rsi+158h]
0x1800297fb  mov     byte ptr [rbp+arg_0], al
0x1800297fe  mov     rax, [rbx]
0x180029801  mov     r8d, 1
0x180029807  lea     rdx, [rbp+arg_0]
0x18002980b  mov     rcx, rbx
0x18002980e  mov     rax, [rax+8]
0x180029812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029817  movzx   eax, byte ptr [rsi+159h]
0x18002981e  mov     byte ptr [rbp+arg_0], al
0x180029821  mov     rax, [rbx]
0x180029824  mov     r8d, 1
0x18002982a  lea     rdx, [rbp+arg_0]
0x18002982e  mov     rcx, rbx
0x180029831  mov     rax, [rax+8]
0x180029835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002983a  movzx   eax, byte ptr [rsi+15Ah]
0x180029841  mov     byte ptr [rbp+arg_0], al
0x180029844  mov     rax, [rbx]
0x180029847  mov     r8d, 1
0x18002984d  lea     rdx, [rbp+arg_0]
0x180029851  mov     rcx, rbx
  ... truncated ...
```
