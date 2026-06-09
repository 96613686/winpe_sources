# EnergyWizardImpl::TelemetryAnalysis(int)

- ea: `0x18005e770`
- end: `0x18005e9d4`
- name: `?TelemetryAnalysis@EnergyWizardImpl@@QEAAJH@Z`
- size: `612`
- prototype: `__int64 __fastcall(EnergyWizardImpl *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18005e250`

## callees

- `0x180001e48`
- `0x1800021e8`
- `0x180008740`
- `0x180023560`
- `0x180033c4c`
- `0x18003742c`
- `0x18004ca90`
- `0x18004fddc`
- `0x18005e464`
- `0x18005e770`
- `0x180096010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005e7b6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005e7d8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005e7b6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005e7d8`
- `msvcp_win!_Mtx_unlock` at `0x18005e80a`
- `msvcp_win!_Mtx_unlock` at `0x18005e80a`
- `msvcp_win!_Mtx_lock` at `0x18005e7a7`
- `msvcp_win!_Mtx_lock` at `0x18005e7a7`
- `RPCRT4!UuidCreate` at `0x18005e82f`
- `RPCRT4!UuidCreate` at `0x18005e82f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnergyWizardImpl::TelemetryAnalysis(EnergyWizardImpl *this, int a2)
{
  int v2; // r14d
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  Troubleshooter *v9; // rcx
  __int64 v10; // r9
  Troubleshooter **v11; // rbx
  unsigned int v13; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v14[4]; // [rsp+44h] [rbp-74h] BYREF
  int v15; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-68h] BYREF
  struct _GUID v17; // [rsp+60h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-48h] BYREF

  v2 = a2;
  Uuid = 0;
  if ( _Mtx_lock((_Mtx_t)`ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>::GetProviderContext'::`2'::Context) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800C80EC == 0x7FFFFFFF )
  {
    dword_1800C80EC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v4 = dword_1800C80F0;
  if ( !dword_1800C80F0 )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1800C60E0);
    v4 = dword_1800C80F0;
  }
  dword_1800C80F0 = v4 + 1;
  _Mtx_unlock((_Mtx_t)`ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>::GetProviderContext'::`2'::Context);
  if ( *((_QWORD *)this + 1) == *(_QWORD *)this || *((_DWORD *)this + 28) != 2 || UuidCreate(&Uuid) )
  {
    v5 = -2147467259;
  }
  else
  {
    v5 = 0;
    v9 = (Troubleshooter *)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9));
    if ( (unsigned __int64)v9 <= 0x98967FFECED300LL && (unsigned int)dword_1800C60E0 > 5 )
    {
      v13 = ((int)v9 + 5000000) / 0x989680u;
      v16[0] = &Uuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800C60E0,
        (__int64)&dword_1800B36B4,
        v7,
        v8,
        v16,
        (__int64)&v13);
    }
    CommonBitmask = v2 != 0;
    if ( (unsigned int)dword_1800C60E0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C60E0, 0x400000000000LL) )
    {
      v13 = *((_DWORD *)this + 23);
      v15 = *((_DWORD *)this + 24);
      LODWORD(v16[0]) = *((_DWORD *)this + 25);
      *(_QWORD *)&v17.Data1 = &Uuid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800C60E0,
        (__int64)byte_1800B36E3,
        v7,
        v10,
        (__int64 *)&v17,
        (__int64)v16,
        (__int64)&v15,
        (__int64)&v13);
    }
    v11 = *(Troubleshooter ***)this;
    while ( v11 != *((Troubleshooter ***)this + 1) )
    {
      try
      {
        if ( !*v11 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v9, v6, v7);
        Troubleshooter::ValidateSelf(*v11);
        v9 = *v11;
        if ( (unsigned int)(*((_DWORD *)*v11 + 2) - 1) <= 1 )
        {
          v17 = Uuid;
          (*(void (__fastcall **)(Troubleshooter *, struct _GUID *))(*(_QWORD *)v9 + 56LL))(v9, &v17);
        }
        ++v11;
      }
      catch ( std::bad_alloc )
      {
        v13 = -2147024882;
        v5 = -2147024882;
        v2 = a2;
        break;
      }
      catch ( ... )
      {
        v13 = -2147467259;
        v5 = -2147467259;
        v2 = a2;
        break;
      }
    }
    if ( v2 )
    {
      v17 = Uuid;
      SendBatteryAnalysisTelemetry(&v17);
    }
  }
  ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>(v14);
  return v5;
}

```

## disassembly

```asm
0x18005e770  mov     [rsp+arg_8], edx
0x18005e774  push    rbx
0x18005e775  push    rsi
0x18005e776  push    rdi
0x18005e777  push    r14
0x18005e779  sub     rsp, 98h
0x18005e780  mov     rax, cs:__security_cookie
0x18005e787  xor     rax, rsp
0x18005e78a  mov     [rsp+0B8h+var_38], rax
0x18005e792  mov     r14d, edx
0x18005e795  mov     rsi, rcx
0x18005e798  xorps   xmm0, xmm0
0x18005e79b  movups  xmmword ptr [rsp+0B8h+Uuid.Data1], xmm0
0x18005e7a0  lea     rcx, ?Context@?1??GetProviderContext@?$ProviderRegistrationGuard@$1?EnergyWizardCommonLoggingProvider@@3QEBU_tlgProvider_t@@EB@@CAAEAU?$ProviderContext@$1?EnergyWizardCommonLoggingProvider@@3QEBU_tlgProvider_t@@EB@2@XZ@4U32@A; _Mtx_t
0x18005e7a7  call    cs:__imp__Mtx_lock
0x18005e7ad  test    eax, eax
0x18005e7af  jz      short loc_18005E7BD
0x18005e7b1  mov     ecx, 5
0x18005e7b6  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005e7bc  int     3; Trap to Debugger
0x18005e7bd  cmp     cs:dword_1800C80EC, 7FFFFFFFh
0x18005e7c7  jnz     short loc_18005E7DF
0x18005e7c9  mov     cs:dword_1800C80EC, 7FFFFFFEh
0x18005e7d3  mov     ecx, 6
0x18005e7d8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005e7de  int     3; Trap to Debugger
0x18005e7df  mov     eax, cs:dword_1800C80F0
0x18005e7e5  test    eax, eax
0x18005e7e7  jnz     short loc_18005E7FB
0x18005e7e9  lea     rcx, dword_1800C60E0; CallbackContext
0x18005e7f0  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18005e7f5  mov     eax, cs:dword_1800C80F0
0x18005e7fb  inc     eax
0x18005e7fd  mov     cs:dword_1800C80F0, eax
0x18005e803  lea     rcx, ?Context@?1??GetProviderContext@?$ProviderRegistrationGuard@$1?EnergyWizardCommonLoggingProvider@@3QEBU_tlgProvider_t@@EB@@CAAEAU?$ProviderContext@$1?EnergyWizardCommonLoggingProvider@@3QEBU_tlgProvider_t@@EB@2@XZ@4U32@A; _Mtx_t
0x18005e80a  call    cs:__imp__Mtx_unlock
0x18005e810  nop
0x18005e811  mov     rax, [rsi+8]
0x18005e815  cmp     rax, [rsi]
0x18005e818  jnz     short loc_18005E824
0x18005e81a  mov     edi, 80004005h
0x18005e81f  jmp     loc_18005E9AB
0x18005e824  cmp     dword ptr [rsi+70h], 2
0x18005e828  jnz     short loc_18005E81A
0x18005e82a  lea     rcx, [rsp+0B8h+Uuid]; Uuid
0x18005e82f  call    cs:__imp_UuidCreate
0x18005e835  test    eax, eax
0x18005e837  jnz     short loc_18005E81A
0x18005e839  xor     edi, edi
0x18005e83b  mov     rcx, [rsi+50h]
0x18005e83f  sub     rcx, [rsi+48h]
0x18005e843  mov     rax, 98967FFECED300h
0x18005e84d  cmp     rcx, rax
0x18005e850  ja      short loc_18005E8A2
0x18005e852  mov     eax, cs:dword_1800C60E0
0x18005e858  cmp     eax, 5
0x18005e85b  jbe     short loc_18005E8A2
0x18005e85d  add     ecx, 4C4B40h
0x18005e863  mov     eax, 6B5FCA6Bh
0x18005e868  mul     ecx
0x18005e86a  shr     edx, 16h
0x18005e86d  mov     [rsp+0B8h+var_78], edx
0x18005e871  lea     rax, [rsp+0B8h+Uuid]
0x18005e876  mov     [rsp+0B8h+var_68], rax
0x18005e87b  lea     rax, [rsp+0B8h+var_78]
0x18005e880  mov     [rsp+0B8h+var_90], rax
0x18005e885  lea     rax, [rsp+0B8h+var_68]
0x18005e88a  mov     [rsp+0B8h+var_98], rax
0x18005e88f  lea     rdx, dword_1800B36B4
0x18005e896  lea     rcx, dword_1800C60E0
0x18005e89d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18005e8a2  mov     cs:?CommonBitmask@@3KA, edi; ulong CommonBitmask
0x18005e8a8  test    r14d, r14d
0x18005e8ab  jz      short loc_18005E8B7
0x18005e8ad  mov     cs:?CommonBitmask@@3KA, 1; ulong CommonBitmask
0x18005e8b7  mov     eax, cs:dword_1800C60E0
0x18005e8bd  cmp     eax, 5
0x18005e8c0  jbe     short loc_18005E937
0x18005e8c2  mov     rdx, 400000000000h
0x18005e8cc  lea     rcx, dword_1800C60E0
0x18005e8d3  call    _tlgKeywordOn
0x18005e8d8  test    al, al
0x18005e8da  jz      short loc_18005E937
0x18005e8dc  mov     eax, [rsi+5Ch]
0x18005e8df  mov     [rsp+0B8h+var_78], eax
0x18005e8e3  mov     eax, [rsi+60h]
0x18005e8e6  mov     [rsp+0B8h+var_70], eax
0x18005e8ea  mov     eax, [rsi+64h]
0x18005e8ed  mov     dword ptr [rsp+0B8h+var_68], eax
0x18005e8f1  lea     rax, [rsp+0B8h+Uuid]
0x18005e8f6  mov     qword ptr [rsp+0B8h+var_58.Data1], rax
0x18005e8fb  lea     rax, [rsp+0B8h+var_78]
0x18005e900  mov     [rsp+0B8h+var_80], rax
0x18005e905  lea     rax, [rsp+0B8h+var_70]
0x18005e90a  mov     [rsp+0B8h+var_88], rax
0x18005e90f  lea     rax, [rsp+0B8h+var_68]
0x18005e914  mov     [rsp+0B8h+var_90], rax
0x18005e919  lea     rax, [rsp+0B8h+var_58]
0x18005e91e  mov     [rsp+0B8h+var_98], rax
0x18005e923  lea     rdx, byte_1800B36E3
0x18005e92a  lea     rcx, dword_1800C60E0
0x18005e931  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005e936  nop
0x18005e937  mov     rbx, [rsi]
0x18005e93a  cmp     rbx, [rsi+8]
0x18005e93e  jnz     short loc_18005E942
0x18005e940  jmp     short loc_18005E990
0x18005e942  cmp     qword ptr [rbx], 0
0x18005e946  jnz     short loc_18005E94D
0x18005e948  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005e94d  mov     rcx, [rbx]; this
0x18005e950  call    ?ValidateSelf@Troubleshooter@@QEAAKXZ; Troubleshooter::ValidateSelf(void)
0x18005e955  mov     rcx, [rbx]
0x18005e958  mov     eax, [rcx+8]
0x18005e95b  dec     eax
0x18005e95d  cmp     eax, 1
0x18005e960  ja      short loc_18005E97E
0x18005e962  movaps  xmm0, xmmword ptr [rsp+0B8h+Uuid.Data1]
0x18005e967  movdqa  xmmword ptr [rsp+0B8h+var_58.Data1], xmm0
0x18005e96d  mov     rax, [rcx]
0x18005e970  lea     rdx, [rsp+0B8h+var_58]
0x18005e975  mov     rax, [rax+38h]
0x18005e979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e97e  add     rbx, 8
0x18005e982  jmp     short loc_18005E93A
0x18005e984  mov     edi, [rsp+0B8h+var_78]
0x18005e988  mov     r14d, [rsp+0B8h+arg_8]
0x18005e990  test    r14d, r14d
0x18005e993  jz      short loc_18005E9AB
0x18005e995  movaps  xmm0, xmmword ptr [rsp+0B8h+Uuid.Data1]
0x18005e99a  movdqa  xmmword ptr [rsp+0B8h+var_58.Data1], xmm0
0x18005e9a0  lea     rcx, [rsp+0B8h+var_58]; struct _GUID
0x18005e9a5  call    ?SendBatteryAnalysisTelemetry@@YAXU_GUID@@@Z; SendBatteryAnalysisTelemetry(_GUID)
0x18005e9aa  nop
0x18005e9ab  lea     rcx, [rsp+0B8h+var_74]
0x18005e9b0  call    ??1?$ProviderRegistrationGuard@$1?EnergyWizardCommonLoggingProvider@@3QEBU_tlgProvider_t@@EB@@QEAA@XZ; ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>::~ProviderRegistrationGuard<&_tlgProvider_t const * const EnergyWizardCommonLoggingProvider>(void)
0x18005e9b5  mov     eax, edi
0x18005e9b7  mov     rcx, [rsp+0B8h+var_38]
0x18005e9bf  xor     rcx, rsp; StackCookie
0x18005e9c2  call    __security_check_cookie
0x18005e9c7  add     rsp, 98h
0x18005e9ce  pop     r14
0x18005e9d0  pop     rdi
0x18005e9d1  pop     rsi
0x18005e9d2  pop     rbx
0x18005e9d3  retn
```
