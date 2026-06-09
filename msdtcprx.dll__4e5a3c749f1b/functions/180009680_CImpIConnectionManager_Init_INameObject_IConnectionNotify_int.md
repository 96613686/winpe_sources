# CImpIConnectionManager::Init(INameObject *,IConnectionNotify *,int)

- ea: `0x180009680`
- end: `0x180009b81`
- name: `?Init@CImpIConnectionManager@@UEAAJPEAUINameObject@@PEAUIConnectionNotify@@H@Z`
- size: `1281`
- prototype: `__int64 __fastcall(CImpIConnectionManager *__hidden this, struct INameObject *, struct IConnectionNotify *, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009680`
- `0x180009b88`
- `0x18000dff4`
- `0x18000f674`
- `0x180019908`
- `0x18001d138`
- `0x18001d178`
- `0x18002f534`
- `0x180053868`
- `0x180056fbc`
- `0x1800659c0`
- `0x180081d92`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800097eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800097eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000982e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000982e`

## string_xrefs

- `0x1800097bb`: `ServiceNetworkProtocols`
- `0x180009af7`: `com\complus\dtc\dtc\cm\src\ccm.cpp`
- `0x180009a3b`: `ProcID=0x%x Protocols On :%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIConnectionManager::Init(
        CImpIConnectionManager *this,
        struct INameObject *a2,
        struct IConnectionNotify *a3,
        int a4)
{
  __int64 v8; // rcx
  int v9; // ebx
  __int64 v10; // rsi
  CConnectionManagerSettings *v11; // rax
  CConnectionManagerSettings *v12; // rcx
  __int64 v13; // rax
  HANDLE EventA; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  bool v17; // zf
  __int64 v18; // rax
  CClassFactoryDTCUtil *v19; // rax
  CClassFactoryDTCUtil *v20; // rax
  CClassFactoryDTCUtil *v21; // rsi
  int v22; // ebx
  CResourceManager *v23; // rcx
  CConnectionManagerSettings *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 (__fastcall ***v28)(_QWORD, __int64, struct INameObject *, _QWORD, _DWORD); // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned int v32; // [rsp+30h] [rbp-D0h]
  void *v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  struct ITmInstance *v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp-88h] BYREF
  CConnectionManagerSettings *v38; // [rsp+80h] [rbp-80h]
  char v39[256]; // [rsp+90h] [rbp-70h] BYREF

  v35 = 0;
  v36 = 0;
  ThreadId = 0;
  v34 = 0;
  v8 = *((_QWORD *)this + 1);
  if ( !*(_DWORD *)(v8 + 76) )
  {
    v9 = -2147467259;
LABEL_36:
    if ( a2 )
    {
      (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)a2 + 16LL))(a2);
      *(_QWORD *)(*((_QWORD *)this + 1) + 88LL) = 0;
    }
    v30 = *(_QWORD *)(*((_QWORD *)this + 1) + 104LL);
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      *(_QWORD *)(*((_QWORD *)this + 1) + 104LL) = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 1) + 60LL) = 0;
    CConnectionManager::StopTimerProc(*((CConnectionManager **)this + 1));
    DELLog(0, 1u, 0xAu, 0xC0001104, v9, 1, 0, 0, "com\\complus\\dtc\\dtc\\cm\\src\\ccm.cpp", 2118, v33);
    goto LABEL_41;
  }
  v10 = 0;
  (**(void (__fastcall ***)(__int64))(v8 + 288))(v8 + 288);
  *(_QWORD *)(*((_QWORD *)this + 1) + 88LL) = a2;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 88LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1)
                                                                                                 + 88LL));
  *(_QWORD *)(*((_QWORD *)this + 1) + 104LL) = a3;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 8LL))(*(_QWORD *)(*((_QWORD *)this + 1)
                                                                                                  + 104LL));
  v9 = (*(__int64 (__fastcall **)(struct INameObject *, struct ITmInstance **))(*(_QWORD *)a2 + 272LL))(a2, &v35);
  if ( v9 < 0 )
    goto LABEL_34;
  v11 = (CConnectionManagerSettings *)operator new(0x50u);
  v38 = v11;
  if ( v11 )
    v12 = CConnectionManagerSettings::CConnectionManagerSettings(v11, v35);
  else
    v12 = 0;
  *(_QWORD *)(*((_QWORD *)this + 1) + 136LL) = v12;
  v13 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v13 + 136) )
    goto LABEL_8;
  if ( !*(_DWORD *)(v13 + 132) )
  {
    *(_DWORD *)(*((_QWORD *)this + 1) + 124LL) = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)v35 + 344LL))(
                                                   v35,
                                                   L"ServiceNetworkProtocols",
                                                   33);
    *(_DWORD *)(*((_QWORD *)this + 1) + 132LL) = 1;
  }
  EventA = CreateEventA(0, 1, 1, 0);
  v15 = *((_QWORD *)this + 1);
  if ( a4 )
  {
    *(_QWORD *)(v15 + 48) = EventA;
    v16 = *((_QWORD *)this + 1);
    v17 = *(_QWORD *)(v16 + 48) == 0;
  }
  else
  {
    *(_QWORD *)(v15 + 40) = EventA;
    v16 = *((_QWORD *)this + 1);
    v17 = *(_QWORD *)(v16 + 40) == 0;
  }
  if ( v17
    || (*(_DWORD *)(v16 + 80) = a4,
        *(_QWORD *)(*((_QWORD *)this + 1) + 32LL) = CreateThread(
                                                      0,
                                                      0,
                                                      CConnectionManager::TimerProc,
                                                      *((LPVOID *)this + 1),
                                                      0,
                                                      &ThreadId),
        v18 = *((_QWORD *)this + 1),
        !*(_QWORD *)(v18 + 32)) )
  {
LABEL_8:
    v9 = -2147024882;
    goto LABEL_36;
  }
  *(_DWORD *)(v18 + 60) = 1;
  v36 = 0;
  if ( memcmp_0(&CLSID_DTCUtil, &CLSID_DTCUtil, 0x10u)
    || (v19 = (CClassFactoryDTCUtil *)operator new(0x10u), (v38 = v19) == 0)
    || (v20 = CClassFactoryDTCUtil::CClassFactoryDTCUtil(v19), (v21 = v20) == 0) )
  {
LABEL_20:
    v9 = -2147483328;
    goto LABEL_36;
  }
  if ( (**(int (__fastcall ***)(CClassFactoryDTCUtil *, GUID *, __int64 *))v20)(v20, &IID_IClassFactory, &v36) < 0 )
  {
    operator delete(v21);
    goto LABEL_20;
  }
  v22 = (*(__int64 (__fastcall **)(CClassFactoryDTCUtil *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 24LL))(
          v21,
          0,
          &IID_INameService,
          &v36);
  (*(void (__fastcall **)(CClassFactoryDTCUtil *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    goto LABEL_20;
  v10 = v36;
  *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) = v36;
  v23 = *(CResourceManager **)(*((_QWORD *)this + 1) + 240LL);
  if ( !v23 )
    goto LABEL_33;
  v9 = CResourceManager::AcquireResources(v23);
  if ( v9 )
    goto LABEL_34;
  v24 = (CConnectionManagerSettings *)operator new(0x70u);
  v38 = v24;
  if ( v24 )
  {
    v25 = *((_QWORD *)this + 1);
    *(_QWORD *)v24 = &CRpcIOManagerServer::`vftable';
    *((_QWORD *)v24 + 1) = v25;
    *((_DWORD *)v24 + 15) = 1;
    *((_DWORD *)v24 + 14) = 100;
    *((_QWORD *)v24 + 6) = 0;
    *((_DWORD *)v24 + 20) = 0;
    *((_QWORD *)v24 + 12) = 0;
    *((_QWORD *)v24 + 13) = 0;
    v26 = *(_QWORD *)(v25 + 136);
    *((_QWORD *)v24 + 11) = v26;
    _InterlockedAdd((volatile signed __int32 *)(v26 + 72), 1u);
  }
  else
  {
    v24 = 0;
  }
  *(_QWORD *)(*((_QWORD *)this + 1) + 248LL) = v24;
  v27 = *((_QWORD *)this + 1);
  v28 = *(__int64 (__fastcall ****)(_QWORD, __int64, struct INameObject *, _QWORD, _DWORD))(v27 + 248);
  if ( !v28 )
  {
LABEL_33:
    v9 = -2147467259;
    goto LABEL_34;
  }
  v9 = (**v28)(v28, v10, a2, *(unsigned int *)(v27 + 124), *(_DWORD *)(v27 + 128));
  if ( v9 < 0
    || (*(_DWORD *)(*((_QWORD *)this + 1) + 72LL) = 1,
        (v9 = ObtainInProcCOManager((struct IInProcCOManager **)(*((_QWORD *)this + 1) + 112LL))) != 0) )
  {
LABEL_34:
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) = 0;
    }
    goto LABEL_36;
  }
  (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)a2 + 88LL))(a2);
  v29 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(*(_QWORD *)(v29 + 136) + 20LL) )
  {
    (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v29 + 88) + 40LL))(*(_QWORD *)(v29 + 88), &v34);
    StringCchPrintfA(v39, 0xFCu, "ProcID=0x%x Protocols On :%x", **(_DWORD **)(*((_QWORD *)this + 1) + 136LL), v34);
    DtcWriteToEventLoggerA(v9 + 4, v9 + 3, 0x4000103Cu, 0, 0, v39, v32);
  }
LABEL_41:
  if ( v35 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 1) + 288LL) + 8LL))(*((_QWORD *)this + 1) + 288LL);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009680  mov     [rsp-8+arg_10], rbx
0x180009685  push    rbp
0x180009686  push    rsi
0x180009687  push    rdi
0x180009688  push    r12
0x18000968a  push    r13
0x18000968c  push    r14
0x18000968e  push    r15
0x180009690  lea     rbp, [rsp-0A0h]
0x180009698  sub     rsp, 1A0h
0x18000969f  mov     rax, cs:__security_cookie
0x1800096a6  xor     rax, rsp
0x1800096a9  mov     [rbp+0D0h+var_40], rax
0x1800096b0  mov     r15d, r9d
0x1800096b3  mov     rbx, r8
0x1800096b6  mov     r14, rdx
0x1800096b9  mov     rdi, rcx
0x1800096bc  xor     r12d, r12d
0x1800096bf  mov     [rsp+1D0h+var_168], r12
0x1800096c4  mov     [rsp+1D0h+var_160], r12
0x1800096c9  mov     [rsp+1D0h+ThreadId], r12d
0x1800096ce  mov     [rsp+1D0h+var_170], r12d
0x1800096d3  mov     rcx, [rcx+8]
0x1800096d7  lea     r13d, [r12+1]
0x1800096dc  cmp     [rcx+4Ch], r12d
0x1800096e0  jnz     short loc_1800096EC
0x1800096e2  mov     ebx, 80004005h
0x1800096e7  jmp     loc_180009A98
0x1800096ec  mov     rsi, r12
0x1800096ef  add     rcx, 120h
0x1800096f6  mov     rax, [rcx]
0x1800096f9  mov     rax, [rax]
0x1800096fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009701  mov     rax, [rdi+8]
0x180009705  mov     [rax+58h], r14
0x180009709  mov     rax, [rdi+8]
0x18000970d  mov     rcx, [rax+58h]
0x180009711  mov     rax, [rcx]
0x180009714  mov     rax, [rax+8]
0x180009718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971d  mov     rax, [rdi+8]
0x180009721  mov     [rax+68h], rbx
0x180009725  mov     rax, [rdi+8]
0x180009729  mov     rcx, [rax+68h]
0x18000972d  mov     rax, [rcx]
0x180009730  mov     rax, [rax+8]
0x180009734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009739  mov     rax, [r14]
0x18000973c  lea     rdx, [rsp+1D0h+var_168]
0x180009741  mov     rcx, r14
0x180009744  mov     rax, [rax+110h]
0x18000974b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009750  mov     ebx, eax
0x180009752  test    eax, eax
0x180009754  js      loc_180009A7C
0x18000975a  mov     ecx, 50h ; 'P'; Size
0x18000975f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009764  mov     [rbp+0D0h+var_150], rax
0x180009768  test    rax, rax
0x18000976b  jz      short loc_18000977F
0x18000976d  mov     rdx, [rsp+1D0h+var_168]; struct ITmInstance *
0x180009772  mov     rcx, rax; this
0x180009775  call    ??0CConnectionManagerSettings@@QEAA@PEAUITmInstance@@@Z; CConnectionManagerSettings::CConnectionManagerSettings(ITmInstance *)
0x18000977a  mov     rcx, rax
0x18000977d  jmp     short loc_180009782
0x18000977f  mov     rcx, r12
0x180009782  mov     rax, [rdi+8]
0x180009786  mov     [rax+88h], rcx
0x18000978d  mov     rax, [rdi+8]
0x180009791  cmp     [rax+88h], r12
0x180009798  jnz     short loc_1800097A4
0x18000979a  mov     ebx, 8007000Eh
0x18000979f  jmp     loc_180009A98
0x1800097a4  cmp     [rax+84h], r12d
0x1800097ab  jnz     short loc_1800097E0
0x1800097ad  mov     rcx, [rsp+1D0h+var_168]
0x1800097b2  mov     rax, [rcx]
0x1800097b5  mov     r8d, 21h ; '!'
0x1800097bb  lea     rdx, aServicenetwork; "ServiceNetworkProtocols"
0x1800097c2  mov     rax, [rax+158h]
0x1800097c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ce  mov     rcx, [rdi+8]
0x1800097d2  mov     [rcx+7Ch], eax
0x1800097d5  mov     rax, [rdi+8]
0x1800097d9  mov     [rax+84h], r13d
0x1800097e0  xor     r9d, r9d; lpName
0x1800097e3  mov     r8d, r13d; bInitialState
0x1800097e6  mov     edx, r13d; bManualReset
0x1800097e9  xor     ecx, ecx; lpEventAttributes
0x1800097eb  call    cs:__imp_CreateEventA
0x1800097f1  mov     rcx, [rdi+8]
0x1800097f5  test    r15d, r15d
0x1800097f8  jnz     loc_1800098BE
0x1800097fe  mov     [rcx+28h], rax
0x180009802  mov     rax, [rdi+8]
0x180009806  cmp     [rax+28h], r12
0x18000980a  jz      short loc_18000979A
0x18000980c  mov     [rax+50h], r15d
0x180009810  lea     rax, [rsp+1D0h+ThreadId]
0x180009815  mov     [rsp+1D0h+lpThreadId], rax; lpThreadId
0x18000981a  mov     [rsp+1D0h+dwCreationFlags], r12d; dwCreationFlags
0x18000981f  mov     r9, [rdi+8]; lpParameter
0x180009823  lea     r8, ?TimerProc@CConnectionManager@@SAX_K@Z; lpStartAddress
0x18000982a  xor     edx, edx; dwStackSize
0x18000982c  xor     ecx, ecx; lpThreadAttributes
0x18000982e  call    cs:__imp_CreateThread
0x180009834  mov     rcx, [rdi+8]
0x180009838  mov     [rcx+20h], rax
0x18000983c  mov     rax, [rdi+8]
0x180009840  cmp     [rax+20h], r12
0x180009844  jz      loc_18000979A
0x18000984a  mov     [rax+3Ch], r13d
0x18000984e  mov     [rsp+1D0h+var_160], r12
0x180009853  mov     ebx, 10h
0x180009858  mov     r8d, ebx; Size
0x18000985b  lea     rcx, CLSID_DTCUtil; Buf1
0x180009862  mov     rdx, rcx; Buf2
0x180009865  call    memcmp_0
0x18000986a  test    eax, eax
0x18000986c  jnz     short loc_1800098B4
0x18000986e  mov     ecx, ebx; Size
0x180009870  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009875  mov     [rbp+0D0h+var_150], rax
0x180009879  test    rax, rax
0x18000987c  jz      short loc_1800098B4
0x18000987e  mov     rcx, rax; this
0x180009881  call    ??0CClassFactoryDTCUtil@@QEAA@XZ; CClassFactoryDTCUtil::CClassFactoryDTCUtil(void)
0x180009886  mov     rsi, rax
0x180009889  test    rax, rax
0x18000988c  jz      short loc_1800098B4
0x18000988e  mov     rcx, [rax]
0x180009891  mov     rax, [rcx]
0x180009894  lea     r8, [rsp+1D0h+var_160]
0x180009899  lea     rdx, IID_IClassFactory
0x1800098a0  mov     rcx, rsi
0x1800098a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a8  mov     rcx, rsi; Block
0x1800098ab  test    eax, eax
0x1800098ad  jns     short loc_1800098CF
0x1800098af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800098b4  mov     ebx, 80000140h
0x1800098b9  jmp     loc_180009A98
0x1800098be  mov     [rcx+30h], rax
0x1800098c2  mov     rax, [rdi+8]
0x1800098c6  cmp     [rax+30h], r12
0x1800098ca  jmp     loc_18000980A
0x1800098cf  mov     rax, [rsi]
0x1800098d2  lea     r9, [rsp+1D0h+var_160]
0x1800098d7  lea     r8, IID_INameService
0x1800098de  xor     edx, edx
0x1800098e0  mov     rax, [rax+18h]
0x1800098e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e9  mov     ebx, eax
0x1800098eb  mov     rcx, [rsi]
0x1800098ee  mov     rax, [rcx+10h]
0x1800098f2  mov     rcx, rsi
0x1800098f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fa  test    ebx, ebx
0x1800098fc  jnz     short loc_1800098B4
0x1800098fe  mov     rsi, [rsp+1D0h+var_160]
0x180009903  mov     rax, [rdi+8]
0x180009907  mov     [rax+60h], rsi
0x18000990b  mov     rax, [rdi+8]
0x18000990f  mov     rcx, [rax+0F0h]; this
0x180009916  test    rcx, rcx
0x180009919  jz      loc_180009A77
0x18000991f  call    ?AcquireResources@CResourceManager@@QEAAJXZ; CResourceManager::AcquireResources(void)
0x180009924  mov     ebx, eax
0x180009926  test    eax, eax
0x180009928  jnz     loc_180009A7C
0x18000992e  lea     ecx, [rax+70h]; Size
0x180009931  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009936  mov     rcx, rax
0x180009939  mov     [rbp+0D0h+var_150], rax
0x18000993d  test    rax, rax
0x180009940  jz      short loc_180009981
0x180009942  mov     rax, [rdi+8]
0x180009946  lea     rdx, ??_7CRpcIOManagerServer@@6B@; const CRpcIOManagerServer::`vftable'
0x18000994d  mov     [rcx], rdx
0x180009950  mov     [rcx+8], rax
0x180009954  mov     [rcx+3Ch], r13d
0x180009958  mov     dword ptr [rcx+38h], 64h ; 'd'
0x18000995f  mov     [rcx+30h], r12
0x180009963  mov     [rcx+50h], r12d
0x180009967  mov     [rcx+60h], r12
0x18000996b  mov     [rcx+68h], r12
0x18000996f  mov     rax, [rax+88h]
0x180009976  mov     [rcx+58h], rax
0x18000997a  lock add [rax+48h], r13d
0x18000997f  jmp     short loc_180009984
0x180009981  mov     rcx, r12
0x180009984  mov     rax, [rdi+8]
0x180009988  mov     [rax+0F8h], rcx
0x18000998f  mov     r9, [rdi+8]
0x180009993  mov     rcx, [r9+0F8h]
0x18000999a  test    rcx, rcx
0x18000999d  jz      loc_180009A77
0x1800099a3  mov     rax, [rcx]
0x1800099a6  mov     edx, [r9+80h]
0x1800099ad  mov     [rsp+1D0h+dwCreationFlags], edx
0x1800099b1  mov     r9d, [r9+7Ch]
0x1800099b5  mov     r8, r14
0x1800099b8  mov     rdx, rsi
0x1800099bb  mov     rax, [rax]
0x1800099be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c3  mov     ebx, eax
0x1800099c5  test    eax, eax
0x1800099c7  js      loc_180009A7C
0x1800099cd  mov     rax, [rdi+8]
0x1800099d1  mov     [rax+48h], r13d
0x1800099d5  mov     rcx, [rdi+8]
0x1800099d9  add     rcx, 70h ; 'p'; struct IInProcCOManager **
0x1800099dd  call    ?ObtainInProcCOManager@@YAJPEAPEAUIInProcCOManager@@@Z; ObtainInProcCOManager(IInProcCOManager * *)
0x1800099e2  mov     ebx, eax
0x1800099e4  test    eax, eax
0x1800099e6  jnz     loc_180009A7C
0x1800099ec  mov     rax, [r14]
0x1800099ef  mov     rcx, r14
0x1800099f2  mov     rax, [rax+58h]
0x1800099f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fb  mov     rcx, [rdi+8]
0x1800099ff  mov     rax, [rcx+88h]
0x180009a06  cmp     [rax+14h], r12d
0x180009a0a  jz      loc_180009B23
0x180009a10  mov     rcx, [rcx+58h]
0x180009a14  mov     rax, [rcx]
0x180009a17  lea     rdx, [rsp+1D0h+var_170]
0x180009a1c  mov     rax, [rax+28h]
0x180009a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a25  mov     rax, [rdi+8]
0x180009a29  mov     r9, [rax+88h]
0x180009a30  mov     eax, [rsp+1D0h+var_170]
0x180009a34  mov     [rsp+1D0h+dwCreationFlags], eax
0x180009a38  mov     r9d, [r9]
0x180009a3b  lea     r8, aProcid0xXProto; "ProcID=0x%x Protocols On :%x"
0x180009a42  mov     edx, 0FCh; unsigned __int64
0x180009a47  lea     rcx, [rbp+0D0h+var_140]; char *
0x180009a4b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180009a50  lea     rax, [rbp+0D0h+var_140]
0x180009a54  mov     [rsp+1D0h+lpThreadId], rax; char *
0x180009a59  mov     qword ptr [rsp+1D0h+dwCreationFlags], r12; void *
0x180009a5e  xor     r9d, r9d; unsigned int
0x180009a61  lea     edx, [rbx+3]; unsigned int
0x180009a64  lea     ecx, [rbx+4]; unsigned int
0x180009a67  mov     r8d, 4000103Ch; unsigned int
0x180009a6d  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180009a72  jmp     loc_180009B23
0x180009a77  mov     ebx, 80004005h
0x180009a7c  test    rsi, rsi
0x180009a7f  jz      short loc_180009A98
0x180009a81  mov     rax, [rsi]
0x180009a84  mov     rcx, rsi
0x180009a87  mov     rax, [rax+10h]
0x180009a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a90  mov     rax, [rdi+8]
0x180009a94  mov     [rax+60h], r12
0x180009a98  test    r14, r14
0x180009a9b  jz      short loc_180009AB4
0x180009a9d  mov     rax, [r14]
0x180009aa0  mov     rcx, r14
0x180009aa3  mov     rax, [rax+10h]
0x180009aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aac  mov     rax, [rdi+8]
0x180009ab0  mov     [rax+58h], r12
0x180009ab4  mov     rax, [rdi+8]
0x180009ab8  mov     rcx, [rax+68h]
0x180009abc  test    rcx, rcx
0x180009abf  jz      short loc_180009AD5
0x180009ac1  mov     rax, [rcx]
0x180009ac4  mov     rax, [rax+10h]
0x180009ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009acd  mov     rax, [rdi+8]
0x180009ad1  mov     [rax+68h], r12
0x180009ad5  mov     rax, [rdi+8]
0x180009ad9  mov     [rax+3Ch], r12d
0x180009add  mov     rcx, [rdi+8]; this
0x180009ae1  call    ?StopTimerProc@CConnectionManager@@QEAAXXZ; CConnectionManager::StopTimerProc(void)
0x180009ae6  mov     r8d, 0Ah; unsigned __int16
0x180009aec  mov     edx, r13d; unsigned __int16
0x180009aef  mov     [rsp+1D0h+var_188], 846h; int
0x180009af7  lea     rax, aComComplusDtcD_2; "com\\complus\\dtc\\dtc\\cm\\src\\ccm.cp"...
0x180009afe  mov     [rsp+1D0h+var_190], rax; char *
0x180009b03  mov     [rsp+1D0h+var_198], r12; void *
0x180009b08  mov     [rsp+1D0h+var_1A0], r12d; unsigned int
0x180009b0d  mov     dword ptr [rsp+1D0h+lpThreadId], r13d; int
0x180009b12  mov     [rsp+1D0h+dwCreationFlags], ebx; int
0x180009b16  xor     ecx, ecx; struct ITmInstance *
0x180009b18  mov     r9d, 0C0001104h; unsigned int
0x180009b1e  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180009b23  mov     rcx, [rsp+1D0h+var_168]
0x180009b28  test    rcx, rcx
0x180009b2b  jz      short loc_180009B3E
0x180009b2d  mov     rax, [rcx]
0x180009b30  mov     rax, [rax+10h]
0x180009b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b39  mov     [rsp+1D0h+var_168], r12
0x180009b3e  mov     rcx, [rdi+8]
0x180009b42  add     rcx, 120h
0x180009b49  mov     rax, [rcx]
0x180009b4c  mov     rax, [rax+8]
  ... truncated ...
```
