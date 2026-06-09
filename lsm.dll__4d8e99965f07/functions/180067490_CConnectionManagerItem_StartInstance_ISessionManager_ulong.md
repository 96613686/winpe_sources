# CConnectionManagerItem::StartInstance(ISessionManager *,ulong)

- ea: `0x180067490`
- end: `0x18006773e`
- name: `?StartInstance@CConnectionManagerItem@@QEAAJPEAUISessionManager@@K@Z`
- size: `686`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this, struct ISessionManager *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180067260`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x18000f320`
- `0x180012e04`
- `0x18001fb7c`
- `0x18002701c`
- `0x18002772c`
- `0x18004a6a8`
- `0x1800530d8`
- `0x180067490`
- `0x18009c010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18006755e`
- `msvcp_win!_Mtx_unlock` at `0x180067664`
- `msvcp_win!_Mtx_unlock` at `0x18006755e`
- `msvcp_win!_Mtx_unlock` at `0x180067664`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006752d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006752d`

## string_xrefs

- `0x1800674f7`: `this->ptrInstance was NULL, so creating com server`
- `0x180067549`: `CoCreateInstance failed failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CConnectionManagerItem::StartInstance(IID *this, struct ISessionManager *a2, unsigned int a3)
{
  struct _Mtx_internal_imp_t *Data4; // rsi
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned __int8 *v10; // r14
  HRESULT Instance; // eax
  int v12; // ebx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v24; // [rsp+30h] [rbp-20h] BYREF
  struct ISessionManagerInternal *v25; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-10h] BYREF
  struct ISessionManagerInternal *v27; // [rsp+80h] [rbp+30h] BYREF
  __int64 v28; // [rsp+98h] [rbp+48h] BYREF

  v24 = 0;
  v25 = 0;
  v28 = 0;
  Data4 = (struct _Mtx_internal_imp_t *)this[4].Data4;
  v26[0] = (char *)this + 72;
  std::_Mutex_base::lock((std::_Mutex_base *)this[4].Data4);
  v10 = this[9].Data4;
  if ( !*(_QWORD *)this[9].Data4 )
  {
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v27 = (struct ISessionManagerInternal *)"this->ptrInstance was NULL, so creating com server";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)&word_1800C83BE,
        v8,
        v9,
        (__int64)&v27);
    }
    Instance = CoCreateInstance(this + 3, 0, 4u, &IID_IConnectionManager, (LPVOID *)this[9].Data4);
    v12 = Instance;
    if ( Instance < 0 )
    {
      _DbgPrintMessage(
        8,
        "CoCreateInstance failed failed: 0x%x in %s",
        Instance,
        "CConnectionManagerItem::StartInstance");
LABEL_6:
      _Mtx_unlock(Data4);
LABEL_17:
      if ( *(_DWORD *)&this[4].Data2 || v12 != -2147024732 )
        CConnectionManagerItem::StopInstance((CConnectionManagerItem *)this);
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        LODWORD(v27) = v12;
        v26[0] = "RCM crashed!";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)word_1800C8342,
          v14,
          v15,
          (__int64)v26,
          (__int64)&v27);
      }
      CrimsonHelper::RaiseEvent<long>(
        &CrimsonHelper::s_instance,
        EVENT_TS_CONNECTION_MANAGER_START_FAILED,
        (unsigned int)v12);
      goto LABEL_25;
    }
    v27 = 0;
    ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v27);
    v25 = v27;
    (*(void (__fastcall **)(struct ISessionManagerInternal *, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, &v28);
    v16 = (*(__int64 (__fastcall **)(_QWORD, struct ISessionManager *, __int64))(**(_QWORD **)v10 + 24LL))(
            *(_QWORD *)v10,
            a2,
            v28);
    v12 = v16;
    if ( v16 < 0 )
    {
      _DbgPrintMessage(8, "ConnectionManager->Initialize() failed: 0x%x", v16);
      goto LABEL_6;
    }
    this[4].Data1 = 1;
  }
  SmartPtr<IWinlogonNotify>::operator=(&v24, *(_QWORD *)v10);
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v27 = (struct ISessionManagerInternal *)"Calling ptrInst->Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v17,
      (unsigned int)&unk_1800C8398,
      v18,
      v19,
      (__int64)&v27);
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 32LL))(v24, a3);
  if ( v12 >= 0 )
  {
    *(_DWORD *)&this[4].Data2 = 0;
  }
  else if ( (unsigned int)dword_1800DF020 > 2 )
  {
    LODWORD(v27) = v12;
    v26[0] = "ConnectionManager->Start() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)byte_1800C836D,
      v21,
      v22,
      (__int64)v26,
      (__int64)&v27);
  }
  _Mtx_unlock(Data4);
  if ( v12 < 0 )
    goto LABEL_17;
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v27 = (struct ISessionManagerInternal *)"Starting/Refreshing RCM was successful";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v13,
      (unsigned int)&dword_1800C831C,
      v14,
      v15,
      (__int64)&v27);
  }
LABEL_25:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v28);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v25);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v24);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180067490  mov     [rsp-28h+arg_8], rbx
0x180067495  mov     [rsp-28h+arg_10], rsi
0x18006749a  push    rbp
0x18006749b  push    rdi
0x18006749c  push    r12
0x18006749e  push    r14
0x1800674a0  push    r15
0x1800674a2  mov     rbp, rsp
0x1800674a5  sub     rsp, 50h
0x1800674a9  mov     r15d, r8d
0x1800674ac  mov     r12, rdx
0x1800674af  mov     rdi, rcx
0x1800674b2  mov     [rbp+var_20], 0
0x1800674ba  mov     [rbp+var_18], 0
0x1800674c2  mov     [rbp+arg_18], 0
0x1800674ca  lea     rsi, [rcx+48h]
0x1800674ce  mov     [rbp+var_10], rsi
0x1800674d2  mov     rcx, rsi; this
0x1800674d5  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800674da  nop
0x1800674db  lea     r14, [rdi+98h]
0x1800674e2  cmp     qword ptr [r14], 0
0x1800674e6  jnz     loc_1800675D1
0x1800674ec  mov     eax, cs:dword_1800DF020
0x1800674f2  cmp     eax, 5
0x1800674f5  jbe     short loc_180067517
0x1800674f7  lea     rax, aThisPtrinstanc; "this->ptrInstance was NULL, so creating"...
0x1800674fe  mov     [rbp+arg_0], rax
0x180067502  lea     rax, [rbp+arg_0]
0x180067506  mov     [rsp+50h+ppv], rax
0x18006750b  lea     rdx, word_1800C83BE
0x180067512  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067517  lea     rcx, [rdi+30h]; rclsid
0x18006751b  mov     [rsp+50h+ppv], r14; ppv
0x180067520  lea     r9, IID_IConnectionManager; riid
0x180067527  xor     edx, edx; pUnkOuter
0x180067529  lea     r8d, [rdx+4]; dwClsContext
0x18006752d  call    cs:__imp_CoCreateInstance
0x180067534  nop     dword ptr [rax+rax+00h]
0x180067539  mov     ebx, eax
0x18006753b  test    eax, eax
0x18006753d  jns     short loc_18006756F
0x18006753f  lea     r9, aCconnectionman_1; "CConnectionManagerItem::StartInstance"
0x180067546  mov     r8d, eax
0x180067549  lea     rdx, aCocreateinstan; "CoCreateInstance failed failed: 0x%x in"...
0x180067550  mov     ecx, 8; int
0x180067555  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006755a  nop
0x18006755b  mov     rcx, rsi; _Mtx_t
0x18006755e  call    cs:__imp__Mtx_unlock
0x180067565  nop     dword ptr [rax+rax+00h]
0x18006756a  jmp     loc_180067674
0x18006756f  mov     [rbp+arg_0], 0
0x180067577  lea     rcx, [rbp+arg_0]; struct ISessionManagerInternal **
0x18006757b  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180067580  mov     rcx, [rbp+arg_0]
0x180067584  mov     [rbp+var_18], rcx
0x180067588  mov     rax, [rcx]
0x18006758b  lea     rdx, [rbp+arg_18]
0x18006758f  mov     rax, [rax+20h]
0x180067593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067598  mov     rcx, [r14]
0x18006759b  mov     rax, [rcx]
0x18006759e  mov     r8, [rbp+arg_18]
0x1800675a2  mov     rdx, r12
0x1800675a5  mov     rax, [rax+18h]
0x1800675a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675ae  mov     ebx, eax
0x1800675b0  test    eax, eax
0x1800675b2  jns     short loc_1800675CA
0x1800675b4  mov     r8d, eax
0x1800675b7  lea     rdx, aConnectionmana_0; "ConnectionManager->Initialize() failed:"...
0x1800675be  mov     ecx, 8; int
0x1800675c3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800675c8  jmp     short loc_18006755B
0x1800675ca  mov     dword ptr [rdi+40h], 1
0x1800675d1  mov     rdx, [r14]
0x1800675d4  lea     rcx, [rbp+var_20]
0x1800675d8  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x1800675dd  mov     eax, cs:dword_1800DF020
0x1800675e3  cmp     eax, 5
0x1800675e6  jbe     short loc_180067608
0x1800675e8  lea     rax, aCallingPtrinst; "Calling ptrInst->Start"
0x1800675ef  mov     [rbp+arg_0], rax
0x1800675f3  lea     rax, [rbp+arg_0]
0x1800675f7  mov     [rsp+50h+ppv], rax
0x1800675fc  lea     rdx, unk_1800C8398
0x180067603  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067608  mov     rcx, [rbp+var_20]
0x18006760c  mov     rax, [rcx]
0x18006760f  mov     edx, r15d
0x180067612  mov     rax, [rax+20h]
0x180067616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006761b  mov     ebx, eax
0x18006761d  test    eax, eax
0x18006761f  jns     short loc_18006765A
0x180067621  mov     eax, cs:dword_1800DF020
0x180067627  cmp     eax, 2
0x18006762a  jbe     short loc_180067661
0x18006762c  mov     dword ptr [rbp+arg_0], ebx
0x18006762f  lea     rax, aConnectionmana; "ConnectionManager->Start() failed"
0x180067636  mov     [rbp+var_10], rax
0x18006763a  lea     rax, [rbp+arg_0]
0x18006763e  mov     [rsp+50h+var_28], rax
0x180067643  lea     rax, [rbp+var_10]
0x180067647  mov     [rsp+50h+ppv], rax
0x18006764c  lea     rdx, byte_1800C836D
0x180067653  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180067658  jmp     short loc_180067661
0x18006765a  mov     dword ptr [rdi+44h], 0
0x180067661  mov     rcx, rsi; _Mtx_t
0x180067664  call    cs:__imp__Mtx_unlock
0x18006766b  nop     dword ptr [rax+rax+00h]
0x180067670  test    ebx, ebx
0x180067672  jns     short loc_1800676D9
0x180067674  cmp     dword ptr [rdi+44h], 0
0x180067678  jnz     short loc_180067682
0x18006767a  cmp     ebx, 800700A4h
0x180067680  jz      short loc_18006768A
0x180067682  mov     rcx, rdi; this
0x180067685  call    ?StopInstance@CConnectionManagerItem@@QEAAJXZ; CConnectionManagerItem::StopInstance(void)
0x18006768a  mov     eax, cs:dword_1800DF020
0x180067690  cmp     eax, 2
0x180067693  jbe     short loc_1800676C1
0x180067695  mov     dword ptr [rbp+arg_0], ebx
0x180067698  lea     rax, aRcmCrashed; "RCM crashed!"
0x18006769f  mov     [rbp+var_10], rax
0x1800676a3  lea     rax, [rbp+arg_0]
0x1800676a7  mov     [rsp+50h+var_28], rax
0x1800676ac  lea     rax, [rbp+var_10]
0x1800676b0  mov     [rsp+50h+ppv], rax
0x1800676b5  lea     rdx, word_1800C8342
0x1800676bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800676c1  mov     r8d, ebx
0x1800676c4  lea     rdx, EVENT_TS_CONNECTION_MANAGER_START_FAILED
0x1800676cb  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x1800676d2  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x1800676d7  jmp     short loc_180067705
0x1800676d9  mov     eax, cs:dword_1800DF020
0x1800676df  cmp     eax, 5
0x1800676e2  jbe     short loc_180067705
0x1800676e4  lea     rax, aStartingRefres_0; "Starting/Refreshing RCM was successful"
0x1800676eb  mov     [rbp+arg_0], rax
0x1800676ef  lea     rax, [rbp+arg_0]
0x1800676f3  mov     [rsp+50h+ppv], rax
0x1800676f8  lea     rdx, dword_1800C831C
0x1800676ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180067704  nop
0x180067705  lea     rcx, [rbp+arg_18]
0x180067709  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006770e  nop
0x18006770f  lea     rcx, [rbp+var_18]
0x180067713  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180067718  nop
0x180067719  lea     rcx, [rbp+var_20]
0x18006771d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180067722  mov     eax, ebx
0x180067724  lea     r11, [rsp+50h+var_s0]
0x180067729  mov     rbx, [r11+38h]
0x18006772d  mov     rsi, [r11+40h]
0x180067731  mov     rsp, r11
0x180067734  pop     r15
0x180067736  pop     r14
0x180067738  pop     r12
0x18006773a  pop     rdi
0x18006773b  pop     rbp
0x18006773c  retn
```
