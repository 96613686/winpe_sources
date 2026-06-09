# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StopActivity(void)

- ea: `0x180019860`
- end: `0x180019acf`
- name: `?StopActivity@PostProvisioningActivities@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001bf4`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x180019860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800198ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800198ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a70`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v17; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v18; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v27[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v7 = *((_QWORD *)v4 + 6);
      v19 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v30) = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v31 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v17 = v7;
      LODWORD(SRWLock) = v4[17];
      v29 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)&byte_18003FCAF,
        v8 + 8,
        (__int64)v6,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v31,
        &v21,
        &v20,
        (__int64)&v30,
        &v19,
        &v18,
        (__int64)&v29,
        (__int64)&SRWLock,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v29 = *(_DWORD *)(v12 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)word_180040D42,
        v12 + 8);
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019860  push    rbp
0x180019862  push    rbx
0x180019863  push    rdi
0x180019864  lea     rbp, [rsp+10h]
0x180019869  sub     rsp, 130h
0x180019870  mov     rdi, [rcx+110h]
0x180019877  mov     rbx, rcx
0x18001987a  mov     eax, [rdi+48h]
0x18001987d  test    eax, eax
0x18001987f  jns     loc_180019A3C
0x180019885  add     rdi, 50h ; 'P'
0x180019889  cmp     eax, [rdi+8]
0x18001988c  jnz     loc_180019A3C
0x180019892  test    rdi, rdi
0x180019895  jz      loc_180019A3C
0x18001989b  lea     rdx, [rbp+SRWLock]
0x18001989f  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800198a4  mov     rax, [rbx+110h]
0x1800198ab  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800198af  mov     dword ptr [rax], 2
0x1800198b5  test    rcx, rcx
0x1800198b8  jz      short loc_1800198C0
0x1800198ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800198c0  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800198c5  mov     r9, rax
0x1800198c8  mov     ecx, [rax]
0x1800198ca  cmp     ecx, 4
0x1800198cd  jbe     loc_180019ABD
0x1800198d3  mov     rax, [rdi+70h]
0x1800198d7  lea     rdx, byte_18003FCAF
0x1800198de  mov     rcx, [rdi+30h]
0x1800198e2  mov     [rbp+var_60], rax
0x1800198e6  mov     eax, [rdi+68h]
0x1800198e9  mov     r8, [rbx+110h]
0x1800198f0  mov     dword ptr [rbp+arg_10], eax
0x1800198f3  add     r8, 8
0x1800198f7  mov     rax, [rdi+60h]
0x1800198fb  mov     [rbp+var_58], rax
0x1800198ff  mov     rax, [rdi+58h]
0x180019903  mov     [rbp+var_50], rax
0x180019907  mov     eax, [rdi+50h]
0x18001990a  mov     [rbp+arg_18], eax
0x18001990d  mov     rax, [rdi+48h]
0x180019911  mov     [rbp+var_48], rax
0x180019915  mov     eax, [rdi+20h]
0x180019918  mov     [rbp+var_80], eax
0x18001991b  mov     rax, [rdi+18h]
0x18001991f  mov     [rbp+var_40], rax
0x180019923  mov     eax, [rdi]
0x180019925  mov     [rbp+var_7C], eax
0x180019928  mov     rax, [rdi+80h]
0x18001992f  mov     [rbp+var_38], rax
0x180019933  mov     eax, [rdi+40h]
0x180019936  mov     [rbp+var_78], eax
0x180019939  mov     rax, [rdi+38h]
0x18001993d  mov     [rbp+var_30], rax
0x180019941  mov     eax, [rdi+8]
0x180019944  mov     [rbp+var_74], eax
0x180019947  lea     rax, [rbp+var_70]
0x18001994b  mov     [rsp+140h+var_90], rax
0x180019953  lea     rax, [rbp+SRWLock]
0x180019957  mov     [rsp+140h+var_98], rax
0x18001995f  lea     rax, [rbp+arg_8]
0x180019963  mov     [rsp+140h+var_A0], rax
0x18001996b  lea     rax, [rbp+var_68]
0x18001996f  mov     [rsp+140h+var_A8], rax
0x180019977  lea     rax, [rbp+var_60]
0x18001997b  mov     [rsp+140h+var_B0], rax
0x180019983  lea     rax, [rbp+arg_10]
0x180019987  mov     [rsp+140h+var_B8], rax
0x18001998f  lea     rax, [rbp+var_58]
0x180019993  mov     [rsp+140h+var_C0], rax
0x18001999b  lea     rax, [rbp+var_50]
0x18001999f  mov     [rsp+140h+var_C8], rax
0x1800199a4  lea     rax, [rbp+arg_18]
0x1800199a8  mov     [rsp+140h+var_D0], rax
0x1800199ad  lea     rax, [rbp+var_48]
0x1800199b1  mov     [rsp+140h+var_D8], rax
0x1800199b6  lea     rax, [rbp+var_80]
0x1800199ba  mov     [rsp+140h+var_E0], rax
0x1800199bf  lea     rax, [rbp+var_40]
0x1800199c3  mov     [rsp+140h+var_E8], rax
0x1800199c8  lea     rax, [rbp+var_7C]
0x1800199cc  mov     [rsp+140h+var_F0], rax
0x1800199d1  lea     rax, [rbp+var_38]
0x1800199d5  mov     [rsp+140h+var_F8], rax
0x1800199da  lea     rax, [rbp+var_78]
0x1800199de  mov     [rsp+140h+var_100], rax
0x1800199e3  lea     rax, [rbp+var_30]
0x1800199e7  mov     [rsp+140h+var_108], rax
0x1800199ec  lea     rax, [rbp+var_74]
0x1800199f0  mov     [rbp+var_70], rcx
0x1800199f4  mov     ecx, [rdi+44h]
0x1800199f7  mov     [rsp+140h+var_110], rax
0x1800199fc  lea     rax, [rbp+var_28]
0x180019a00  mov     dword ptr [rbp+SRWLock], ecx
0x180019a03  mov     ecx, [rdi+10h]
0x180019a06  mov     [rbp+arg_8], ecx
0x180019a09  mov     rcx, [rdi+78h]
0x180019a0d  mov     [rsp+140h+var_118], rax
0x180019a12  lea     rax, [rbp+var_20]
0x180019a16  mov     [rbp+var_68], rcx
0x180019a1a  mov     rcx, r9
0x180019a1d  mov     [rsp+140h+var_120], rax
0x180019a22  mov     [rbp+var_28], 1000000h
0x180019a2a  mov     [rbp+var_20], 0
0x180019a32  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019a37  jmp     loc_180019ABD
0x180019a3c  lea     rdx, [rbp+SRWLock]
0x180019a40  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019a45  mov     rax, [rbx+110h]
0x180019a4c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180019a50  mov     dword ptr [rax], 2
0x180019a56  test    rcx, rcx
0x180019a59  jz      short loc_180019A61
0x180019a5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180019a61  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019a66  mov     rdi, rax
0x180019a69  mov     ecx, [rax]
0x180019a6b  cmp     ecx, 4
0x180019a6e  jbe     short loc_180019ABD
0x180019a70  call    cs:__imp_GetCurrentThreadId
0x180019a76  mov     r8, [rbx+110h]
0x180019a7d  lea     rdx, word_180040D42
0x180019a84  mov     dword ptr [rbp+SRWLock], eax
0x180019a87  lea     rax, [rbp+SRWLock]
0x180019a8b  mov     [rsp+140h+var_110], rax
0x180019a90  lea     rax, [rbp+arg_8]
0x180019a94  mov     [rsp+140h+var_118], rax
0x180019a99  lea     rax, [rbp+arg_10]
0x180019a9d  mov     ecx, [r8+48h]
0x180019aa1  add     r8, 8
0x180019aa5  mov     [rbp+arg_8], ecx
0x180019aa8  mov     rcx, rdi
0x180019aab  mov     [rsp+140h+var_120], rax
0x180019ab0  mov     [rbp+arg_10], 0
0x180019ab8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019abd  mov     rcx, rbx
0x180019ac0  add     rsp, 130h
0x180019ac7  pop     rdi
0x180019ac8  pop     rbx
0x180019ac9  pop     rbp
0x180019aca  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
