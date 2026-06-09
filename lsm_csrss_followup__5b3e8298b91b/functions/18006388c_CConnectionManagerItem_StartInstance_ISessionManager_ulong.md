# CConnectionManagerItem::StartInstance(ISessionManager *,ulong)

- ea: `0x18006388c`
- end: `0x180063b27`
- name: `?StartInstance@CConnectionManagerItem@@QEAAJPEAUISessionManager@@K@Z`
- size: `667`
- prototype: `__int64 __fastcall(CConnectionManagerItem *__hidden this, struct ISessionManager *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180063660`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x18000f260`
- `0x180014ff0`
- `0x18001e3e8`
- `0x180025070`
- `0x180025890`
- `0x1800475ac`
- `0x18004fb2c`
- `0x18006388c`
- `0x180097010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180063954`
- `msvcp_win!_Mtx_unlock` at `0x180063a54`
- `msvcp_win!_Mtx_unlock` at `0x180063954`
- `msvcp_win!_Mtx_unlock` at `0x180063a54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063929`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063929`

## string_xrefs

- `0x1800638f3`: `this->ptrInstance was NULL, so creating com server`
- `0x18006393f`: `CoCreateInstance failed failed: 0x%x in %s`

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
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v27 = (struct ISessionManagerInternal *)"this->ptrInstance was NULL, so creating com server";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)&word_1800C3236,
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
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        LODWORD(v27) = v12;
        v26[0] = "RCM crashed!";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v13,
          (unsigned int)word_1800C31BA,
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
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v27 = (struct ISessionManagerInternal *)"Calling ptrInst->Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v17,
      (unsigned int)&unk_1800C3210,
      v18,
      v19,
      (__int64)&v27);
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 32LL))(v24, a3);
  if ( v12 >= 0 )
  {
    *(_DWORD *)&this[4].Data2 = 0;
  }
  else if ( (unsigned int)dword_1800DA020 > 2 )
  {
    LODWORD(v27) = v12;
    v26[0] = "ConnectionManager->Start() failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)byte_1800C31E5,
      v21,
      v22,
      (__int64)v26,
      (__int64)&v27);
  }
  _Mtx_unlock(Data4);
  if ( v12 < 0 )
    goto LABEL_17;
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v27 = (struct ISessionManagerInternal *)"Starting/Refreshing RCM was successful";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v13,
      (unsigned int)&dword_1800C3194,
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
0x18006388c  mov     [rsp-28h+arg_8], rbx
0x180063891  mov     [rsp-28h+arg_10], rsi
0x180063896  push    rbp
0x180063897  push    rdi
0x180063898  push    r12
0x18006389a  push    r14
0x18006389c  push    r15
0x18006389e  mov     rbp, rsp
0x1800638a1  sub     rsp, 50h
0x1800638a5  mov     r15d, r8d
0x1800638a8  mov     r12, rdx
0x1800638ab  mov     rdi, rcx
0x1800638ae  mov     [rbp+var_20], 0
0x1800638b6  mov     [rbp+var_18], 0
0x1800638be  mov     [rbp+arg_18], 0
0x1800638c6  lea     rsi, [rcx+48h]
0x1800638ca  mov     [rbp+var_10], rsi
0x1800638ce  mov     rcx, rsi; this
0x1800638d1  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800638d6  nop
0x1800638d7  lea     r14, [rdi+98h]
0x1800638de  cmp     qword ptr [r14], 0
0x1800638e2  jnz     loc_1800639C1
0x1800638e8  mov     eax, cs:dword_1800DA020
0x1800638ee  cmp     eax, 5
0x1800638f1  jbe     short loc_180063913
0x1800638f3  lea     rax, aThisPtrinstanc; "this->ptrInstance was NULL, so creating"...
0x1800638fa  mov     [rbp+arg_0], rax
0x1800638fe  lea     rax, [rbp+arg_0]
0x180063902  mov     [rsp+50h+ppv], rax
0x180063907  lea     rdx, word_1800C3236
0x18006390e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063913  lea     rcx, [rdi+30h]; rclsid
0x180063917  mov     [rsp+50h+ppv], r14; ppv
0x18006391c  lea     r9, IID_IConnectionManager; riid
0x180063923  xor     edx, edx; pUnkOuter
0x180063925  lea     r8d, [rdx+4]; dwClsContext
0x180063929  call    cs:__imp_CoCreateInstance
0x18006392f  mov     ebx, eax
0x180063931  test    eax, eax
0x180063933  jns     short loc_18006395F
0x180063935  lea     r9, aCconnectionman_1; "CConnectionManagerItem::StartInstance"
0x18006393c  mov     r8d, eax
0x18006393f  lea     rdx, aCocreateinstan; "CoCreateInstance failed failed: 0x%x in"...
0x180063946  mov     ecx, 8; int
0x18006394b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180063950  nop
0x180063951  mov     rcx, rsi; _Mtx_t
0x180063954  call    cs:__imp__Mtx_unlock
0x18006395a  jmp     loc_180063A5E
0x18006395f  mov     [rbp+arg_0], 0
0x180063967  lea     rcx, [rbp+arg_0]; struct ISessionManagerInternal **
0x18006396b  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x180063970  mov     rcx, [rbp+arg_0]
0x180063974  mov     [rbp+var_18], rcx
0x180063978  mov     rax, [rcx]
0x18006397b  lea     rdx, [rbp+arg_18]
0x18006397f  mov     rax, [rax+20h]
0x180063983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063988  mov     rcx, [r14]
0x18006398b  mov     rax, [rcx]
0x18006398e  mov     r8, [rbp+arg_18]
0x180063992  mov     rdx, r12
0x180063995  mov     rax, [rax+18h]
0x180063999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006399e  mov     ebx, eax
0x1800639a0  test    eax, eax
0x1800639a2  jns     short loc_1800639BA
0x1800639a4  mov     r8d, eax
0x1800639a7  lea     rdx, aConnectionmana_0; "ConnectionManager->Initialize() failed:"...
0x1800639ae  mov     ecx, 8; int
0x1800639b3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800639b8  jmp     short loc_180063951
0x1800639ba  mov     dword ptr [rdi+40h], 1
0x1800639c1  mov     rdx, [r14]
0x1800639c4  lea     rcx, [rbp+var_20]
0x1800639c8  call    ??4?$SmartPtr@VIWinlogonNotify@@@@QEAAAEAV0@PEAVIWinlogonNotify@@@Z; SmartPtr<IWinlogonNotify>::operator=(IWinlogonNotify *)
0x1800639cd  mov     eax, cs:dword_1800DA020
0x1800639d3  cmp     eax, 5
0x1800639d6  jbe     short loc_1800639F8
0x1800639d8  lea     rax, aCallingPtrinst; "Calling ptrInst->Start"
0x1800639df  mov     [rbp+arg_0], rax
0x1800639e3  lea     rax, [rbp+arg_0]
0x1800639e7  mov     [rsp+50h+ppv], rax
0x1800639ec  lea     rdx, unk_1800C3210
0x1800639f3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800639f8  mov     rcx, [rbp+var_20]
0x1800639fc  mov     rax, [rcx]
0x1800639ff  mov     edx, r15d
0x180063a02  mov     rax, [rax+20h]
0x180063a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a0b  mov     ebx, eax
0x180063a0d  test    eax, eax
0x180063a0f  jns     short loc_180063A4A
0x180063a11  mov     eax, cs:dword_1800DA020
0x180063a17  cmp     eax, 2
0x180063a1a  jbe     short loc_180063A51
0x180063a1c  mov     dword ptr [rbp+arg_0], ebx
0x180063a1f  lea     rax, aConnectionmana; "ConnectionManager->Start() failed"
0x180063a26  mov     [rbp+var_10], rax
0x180063a2a  lea     rax, [rbp+arg_0]
0x180063a2e  mov     [rsp+50h+var_28], rax
0x180063a33  lea     rax, [rbp+var_10]
0x180063a37  mov     [rsp+50h+ppv], rax
0x180063a3c  lea     rdx, byte_1800C31E5
0x180063a43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063a48  jmp     short loc_180063A51
0x180063a4a  mov     dword ptr [rdi+44h], 0
0x180063a51  mov     rcx, rsi; _Mtx_t
0x180063a54  call    cs:__imp__Mtx_unlock
0x180063a5a  test    ebx, ebx
0x180063a5c  jns     short loc_180063AC3
0x180063a5e  cmp     dword ptr [rdi+44h], 0
0x180063a62  jnz     short loc_180063A6C
0x180063a64  cmp     ebx, 800700A4h
0x180063a6a  jz      short loc_180063A74
0x180063a6c  mov     rcx, rdi; this
0x180063a6f  call    ?StopInstance@CConnectionManagerItem@@QEAAJXZ; CConnectionManagerItem::StopInstance(void)
0x180063a74  mov     eax, cs:dword_1800DA020
0x180063a7a  cmp     eax, 2
0x180063a7d  jbe     short loc_180063AAB
0x180063a7f  mov     dword ptr [rbp+arg_0], ebx
0x180063a82  lea     rax, aRcmCrashed; "RCM crashed!"
0x180063a89  mov     [rbp+var_10], rax
0x180063a8d  lea     rax, [rbp+arg_0]
0x180063a91  mov     [rsp+50h+var_28], rax
0x180063a96  lea     rax, [rbp+var_10]
0x180063a9a  mov     [rsp+50h+ppv], rax
0x180063a9f  lea     rdx, word_1800C31BA
0x180063aa6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063aab  mov     r8d, ebx
0x180063aae  lea     rdx, EVENT_TS_CONNECTION_MANAGER_START_FAILED
0x180063ab5  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180063abc  call    ??$RaiseEvent@J@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@J@Z; CrimsonHelper::RaiseEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x180063ac1  jmp     short loc_180063AEF
0x180063ac3  mov     eax, cs:dword_1800DA020
0x180063ac9  cmp     eax, 5
0x180063acc  jbe     short loc_180063AEF
0x180063ace  lea     rax, aStartingRefres_0; "Starting/Refreshing RCM was successful"
0x180063ad5  mov     [rbp+arg_0], rax
0x180063ad9  lea     rax, [rbp+arg_0]
0x180063add  mov     [rsp+50h+ppv], rax
0x180063ae2  lea     rdx, dword_1800C3194
0x180063ae9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180063aee  nop
0x180063aef  lea     rcx, [rbp+arg_18]
0x180063af3  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180063af8  nop
0x180063af9  lea     rcx, [rbp+var_18]
0x180063afd  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180063b02  nop
0x180063b03  lea     rcx, [rbp+var_20]
0x180063b07  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180063b0c  mov     eax, ebx
0x180063b0e  lea     r11, [rsp+50h+var_s0]
0x180063b13  mov     rbx, [r11+38h]
0x180063b17  mov     rsi, [r11+40h]
0x180063b1b  mov     rsp, r11
0x180063b1e  pop     r15
0x180063b20  pop     r14
0x180063b22  pop     r12
0x180063b24  pop     rdi
0x180063b25  pop     rbp
0x180063b26  retn
```
