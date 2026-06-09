# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StopActivity(void)

- ea: `0x18001a510`
- end: `0x18001a791`
- name: `?StopActivity@ProvOpsPublishDeviceProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `641`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x18001a510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a56a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a56a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a731`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsPublishDeviceProvisioningLogs *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

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
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v18 = *((_QWORD *)v4 + 15);
        v19 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v20 = *((_QWORD *)v4 + 12);
        v21 = *((_QWORD *)v4 + 11);
        v29 = v4[20];
        v22 = *((_QWORD *)v4 + 9);
        LODWORD(v30) = v4[8];
        v23 = *((_QWORD *)v4 + 3);
        v31 = *v4;
        v24 = *((_QWORD *)v4 + 16);
        v16 = v4[16];
        v25 = *((_QWORD *)v4 + 7);
        v17 = v4[2];
        v26 = 0x1000000;
        v27[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&unk_1800400A0,
          v9 + 8,
          v7,
          (__int64)v27,
          (__int64)&v26,
          (__int64)&v17,
          &v25,
          (__int64)&v16,
          &v24,
          (__int64)&v31,
          &v23,
          (__int64)&v30,
          &v22,
          (__int64)&v29,
          &v21,
          &v20,
          (__int64)&SRWLock,
          &v19,
          &v18);
      }
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v29 = *(_DWORD *)(v15 + 72);
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)&dword_180040DDC,
          v15 + 8);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001a510  push    rbp
0x18001a512  push    rbx
0x18001a513  push    rdi
0x18001a514  lea     rbp, [rsp-47h]
0x18001a519  sub     rsp, 100h
0x18001a520  mov     rdi, [rcx+110h]
0x18001a527  mov     rbx, rcx
0x18001a52a  mov     eax, [rdi+48h]
0x18001a52d  test    eax, eax
0x18001a52f  jns     loc_18001A6DB
0x18001a535  add     rdi, 50h ; 'P'
0x18001a539  cmp     eax, [rdi+8]
0x18001a53c  jnz     loc_18001A6DB
0x18001a542  test    rdi, rdi
0x18001a545  jz      loc_18001A6DB
0x18001a54b  lea     rdx, [rbp+57h+SRWLock]
0x18001a54f  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a554  mov     rax, [rbx+110h]
0x18001a55b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a55f  mov     dword ptr [rax], 2
0x18001a565  test    rcx, rcx
0x18001a568  jz      short loc_18001A570
0x18001a56a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a570  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a575  mov     r9, rax
0x18001a578  mov     ecx, [rax]
0x18001a57a  cmp     ecx, 5
0x18001a57d  jbe     loc_18001A77F
0x18001a583  mov     rax, [rax+18h]
0x18001a587  mov     rdx, 400000000000h
0x18001a591  mov     rcx, [r9+10h]
0x18001a595  test    rdx, rcx
0x18001a598  jz      loc_18001A77F
0x18001a59e  mov     rcx, rax
0x18001a5a1  and     rcx, rdx
0x18001a5a4  cmp     rcx, rax
0x18001a5a7  jnz     loc_18001A77F
0x18001a5ad  mov     rax, [rdi+78h]
0x18001a5b1  lea     rdx, unk_1800400A0
0x18001a5b8  mov     r8, [rbx+110h]
0x18001a5bf  mov     rcx, r9
0x18001a5c2  mov     [rbp+57h+var_68], rax
0x18001a5c6  add     r8, 8
0x18001a5ca  mov     rax, [rdi+70h]
0x18001a5ce  mov     [rbp+57h+var_60], rax
0x18001a5d2  mov     eax, [rdi+68h]
0x18001a5d5  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a5d8  mov     rax, [rdi+60h]
0x18001a5dc  mov     [rbp+57h+var_58], rax
0x18001a5e0  mov     rax, [rdi+58h]
0x18001a5e4  mov     [rbp+57h+var_50], rax
0x18001a5e8  mov     eax, [rdi+50h]
0x18001a5eb  mov     [rbp+57h+arg_8], eax
0x18001a5ee  mov     rax, [rdi+48h]
0x18001a5f2  mov     [rbp+57h+var_48], rax
0x18001a5f6  mov     eax, [rdi+20h]
0x18001a5f9  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a5fc  mov     rax, [rdi+18h]
0x18001a600  mov     [rbp+57h+var_40], rax
0x18001a604  mov     eax, [rdi]
0x18001a606  mov     [rbp+57h+arg_18], eax
0x18001a609  mov     rax, [rdi+80h]
0x18001a610  mov     [rbp+57h+var_38], rax
0x18001a614  mov     eax, [rdi+40h]
0x18001a617  mov     [rbp+57h+var_70], eax
0x18001a61a  mov     rax, [rdi+38h]
0x18001a61e  mov     [rbp+57h+var_30], rax
0x18001a622  mov     eax, [rdi+8]
0x18001a625  mov     [rbp+57h+var_6C], eax
0x18001a628  mov     eax, 1000000h
0x18001a62d  mov     [rbp+57h+var_28], rax
0x18001a631  mov     [rbp+57h+var_20], rax
0x18001a635  lea     rax, [rbp+57h+var_68]
0x18001a639  mov     [rsp+110h+var_78], rax
0x18001a641  lea     rax, [rbp+57h+var_60]
0x18001a645  mov     [rsp+110h+var_80], rax
0x18001a64d  lea     rax, [rbp+57h+SRWLock]
0x18001a651  mov     [rsp+110h+var_88], rax
0x18001a659  lea     rax, [rbp+57h+var_58]
0x18001a65d  mov     [rsp+110h+var_90], rax
0x18001a665  lea     rax, [rbp+57h+var_50]
0x18001a669  mov     [rsp+110h+var_98], rax
0x18001a66e  lea     rax, [rbp+57h+arg_8]
0x18001a672  mov     [rsp+110h+var_A0], rax
0x18001a677  lea     rax, [rbp+57h+var_48]
0x18001a67b  mov     [rsp+110h+var_A8], rax
0x18001a680  lea     rax, [rbp+57h+arg_10]
0x18001a684  mov     [rsp+110h+var_B0], rax
0x18001a689  lea     rax, [rbp+57h+var_40]
0x18001a68d  mov     [rsp+110h+var_B8], rax
0x18001a692  lea     rax, [rbp+57h+arg_18]
0x18001a696  mov     [rsp+110h+var_C0], rax
0x18001a69b  lea     rax, [rbp+57h+var_38]
0x18001a69f  mov     [rsp+110h+var_C8], rax
0x18001a6a4  lea     rax, [rbp+57h+var_70]
0x18001a6a8  mov     [rsp+110h+var_D0], rax
0x18001a6ad  lea     rax, [rbp+57h+var_30]
0x18001a6b1  mov     [rsp+110h+var_D8], rax
0x18001a6b6  lea     rax, [rbp+57h+var_6C]
0x18001a6ba  mov     [rsp+110h+var_E0], rax
0x18001a6bf  lea     rax, [rbp+57h+var_28]
0x18001a6c3  mov     [rsp+110h+var_E8], rax
0x18001a6c8  lea     rax, [rbp+57h+var_20]
0x18001a6cc  mov     [rsp+110h+var_F0], rax
0x18001a6d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a6d6  jmp     loc_18001A77F
0x18001a6db  lea     rdx, [rbp+57h+SRWLock]
0x18001a6df  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a6e4  mov     rax, [rbx+110h]
0x18001a6eb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a6ef  mov     dword ptr [rax], 2
0x18001a6f5  test    rcx, rcx
0x18001a6f8  jz      short loc_18001A700
0x18001a6fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a700  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a705  mov     rdi, rax
0x18001a708  mov     ecx, [rax]
0x18001a70a  cmp     ecx, 5
0x18001a70d  jbe     short loc_18001A77F
0x18001a70f  mov     rax, [rax+18h]
0x18001a713  mov     rdx, 400000000000h
0x18001a71d  mov     rcx, [rdi+10h]
0x18001a721  test    rdx, rcx
0x18001a724  jz      short loc_18001A77F
0x18001a726  mov     rcx, rax
0x18001a729  and     rcx, rdx
0x18001a72c  cmp     rcx, rax
0x18001a72f  jnz     short loc_18001A77F
0x18001a731  call    cs:__imp_GetCurrentThreadId
0x18001a737  mov     r8, [rbx+110h]
0x18001a73e  lea     rdx, dword_180040DDC
0x18001a745  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a748  mov     rcx, rdi
0x18001a74b  mov     eax, [r8+48h]
0x18001a74f  add     r8, 8
0x18001a753  mov     [rbp+57h+arg_8], eax
0x18001a756  mov     eax, 1000000h
0x18001a75b  mov     [rbp+57h+arg_10], rax
0x18001a75f  lea     rax, [rbp+57h+SRWLock]
0x18001a763  mov     [rsp+110h+var_E0], rax
0x18001a768  lea     rax, [rbp+57h+arg_8]
0x18001a76c  mov     [rsp+110h+var_E8], rax
0x18001a771  lea     rax, [rbp+57h+arg_10]
0x18001a775  mov     [rsp+110h+var_F0], rax
0x18001a77a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a77f  mov     rcx, rbx
0x18001a782  add     rsp, 100h
0x18001a789  pop     rdi
0x18001a78a  pop     rbx
0x18001a78b  pop     rbp
0x18001a78c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
