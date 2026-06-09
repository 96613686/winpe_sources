# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StopActivity(void)

- ea: `0x18001a7a0`
- end: `0x18001aa0f`
- name: `?StopActivity@RemovePackage@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001bf4`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x18001a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a7fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a99b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a7fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9b0`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::RemovePackage *this)
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
    if ( *(_DWORD *)v6 > 5u )
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
        (__int64)&dword_180040314,
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
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v29 = *(_DWORD *)(v12 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&byte_18003FE67,
        v12 + 8);
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001a7a0  push    rbp
0x18001a7a2  push    rbx
0x18001a7a3  push    rdi
0x18001a7a4  lea     rbp, [rsp+10h]
0x18001a7a9  sub     rsp, 130h
0x18001a7b0  mov     rdi, [rcx+110h]
0x18001a7b7  mov     rbx, rcx
0x18001a7ba  mov     eax, [rdi+48h]
0x18001a7bd  test    eax, eax
0x18001a7bf  jns     loc_18001A97C
0x18001a7c5  add     rdi, 50h ; 'P'
0x18001a7c9  cmp     eax, [rdi+8]
0x18001a7cc  jnz     loc_18001A97C
0x18001a7d2  test    rdi, rdi
0x18001a7d5  jz      loc_18001A97C
0x18001a7db  lea     rdx, [rbp+SRWLock]
0x18001a7df  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a7e4  mov     rax, [rbx+110h]
0x18001a7eb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001a7ef  mov     dword ptr [rax], 2
0x18001a7f5  test    rcx, rcx
0x18001a7f8  jz      short loc_18001A800
0x18001a7fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a800  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a805  mov     r9, rax
0x18001a808  mov     ecx, [rax]
0x18001a80a  cmp     ecx, 5
0x18001a80d  jbe     loc_18001A9FD
0x18001a813  mov     rax, [rdi+70h]
0x18001a817  lea     rdx, dword_180040314
0x18001a81e  mov     rcx, [rdi+30h]
0x18001a822  mov     [rbp+var_60], rax
0x18001a826  mov     eax, [rdi+68h]
0x18001a829  mov     r8, [rbx+110h]
0x18001a830  mov     dword ptr [rbp+arg_10], eax
0x18001a833  add     r8, 8
0x18001a837  mov     rax, [rdi+60h]
0x18001a83b  mov     [rbp+var_58], rax
0x18001a83f  mov     rax, [rdi+58h]
0x18001a843  mov     [rbp+var_50], rax
0x18001a847  mov     eax, [rdi+50h]
0x18001a84a  mov     [rbp+arg_18], eax
0x18001a84d  mov     rax, [rdi+48h]
0x18001a851  mov     [rbp+var_48], rax
0x18001a855  mov     eax, [rdi+20h]
0x18001a858  mov     [rbp+var_80], eax
0x18001a85b  mov     rax, [rdi+18h]
0x18001a85f  mov     [rbp+var_40], rax
0x18001a863  mov     eax, [rdi]
0x18001a865  mov     [rbp+var_7C], eax
0x18001a868  mov     rax, [rdi+80h]
0x18001a86f  mov     [rbp+var_38], rax
0x18001a873  mov     eax, [rdi+40h]
0x18001a876  mov     [rbp+var_78], eax
0x18001a879  mov     rax, [rdi+38h]
0x18001a87d  mov     [rbp+var_30], rax
0x18001a881  mov     eax, [rdi+8]
0x18001a884  mov     [rbp+var_74], eax
0x18001a887  lea     rax, [rbp+var_70]
0x18001a88b  mov     [rsp+140h+var_90], rax
0x18001a893  lea     rax, [rbp+SRWLock]
0x18001a897  mov     [rsp+140h+var_98], rax
0x18001a89f  lea     rax, [rbp+arg_8]
0x18001a8a3  mov     [rsp+140h+var_A0], rax
0x18001a8ab  lea     rax, [rbp+var_68]
0x18001a8af  mov     [rsp+140h+var_A8], rax
0x18001a8b7  lea     rax, [rbp+var_60]
0x18001a8bb  mov     [rsp+140h+var_B0], rax
0x18001a8c3  lea     rax, [rbp+arg_10]
0x18001a8c7  mov     [rsp+140h+var_B8], rax
0x18001a8cf  lea     rax, [rbp+var_58]
0x18001a8d3  mov     [rsp+140h+var_C0], rax
0x18001a8db  lea     rax, [rbp+var_50]
0x18001a8df  mov     [rsp+140h+var_C8], rax
0x18001a8e4  lea     rax, [rbp+arg_18]
0x18001a8e8  mov     [rsp+140h+var_D0], rax
0x18001a8ed  lea     rax, [rbp+var_48]
0x18001a8f1  mov     [rsp+140h+var_D8], rax
0x18001a8f6  lea     rax, [rbp+var_80]
0x18001a8fa  mov     [rsp+140h+var_E0], rax
0x18001a8ff  lea     rax, [rbp+var_40]
0x18001a903  mov     [rsp+140h+var_E8], rax
0x18001a908  lea     rax, [rbp+var_7C]
0x18001a90c  mov     [rsp+140h+var_F0], rax
0x18001a911  lea     rax, [rbp+var_38]
0x18001a915  mov     [rsp+140h+var_F8], rax
0x18001a91a  lea     rax, [rbp+var_78]
0x18001a91e  mov     [rsp+140h+var_100], rax
0x18001a923  lea     rax, [rbp+var_30]
0x18001a927  mov     [rsp+140h+var_108], rax
0x18001a92c  lea     rax, [rbp+var_74]
0x18001a930  mov     [rbp+var_70], rcx
0x18001a934  mov     ecx, [rdi+44h]
0x18001a937  mov     [rsp+140h+var_110], rax
0x18001a93c  lea     rax, [rbp+var_28]
0x18001a940  mov     dword ptr [rbp+SRWLock], ecx
0x18001a943  mov     ecx, [rdi+10h]
0x18001a946  mov     [rbp+arg_8], ecx
0x18001a949  mov     rcx, [rdi+78h]
0x18001a94d  mov     [rsp+140h+var_118], rax
0x18001a952  lea     rax, [rbp+var_20]
0x18001a956  mov     [rbp+var_68], rcx
0x18001a95a  mov     rcx, r9
0x18001a95d  mov     [rsp+140h+var_120], rax
0x18001a962  mov     [rbp+var_28], 1000000h
0x18001a96a  mov     [rbp+var_20], 0
0x18001a972  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a977  jmp     loc_18001A9FD
0x18001a97c  lea     rdx, [rbp+SRWLock]
0x18001a980  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a985  mov     rax, [rbx+110h]
0x18001a98c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001a990  mov     dword ptr [rax], 2
0x18001a996  test    rcx, rcx
0x18001a999  jz      short loc_18001A9A1
0x18001a99b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a9a1  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a9a6  mov     rdi, rax
0x18001a9a9  mov     ecx, [rax]
0x18001a9ab  cmp     ecx, 5
0x18001a9ae  jbe     short loc_18001A9FD
0x18001a9b0  call    cs:__imp_GetCurrentThreadId
0x18001a9b6  mov     r8, [rbx+110h]
0x18001a9bd  lea     rdx, byte_18003FE67
0x18001a9c4  mov     dword ptr [rbp+SRWLock], eax
0x18001a9c7  lea     rax, [rbp+SRWLock]
0x18001a9cb  mov     [rsp+140h+var_110], rax
0x18001a9d0  lea     rax, [rbp+arg_8]
0x18001a9d4  mov     [rsp+140h+var_118], rax
0x18001a9d9  lea     rax, [rbp+arg_10]
0x18001a9dd  mov     ecx, [r8+48h]
0x18001a9e1  add     r8, 8
0x18001a9e5  mov     [rbp+arg_8], ecx
0x18001a9e8  mov     rcx, rdi
0x18001a9eb  mov     [rsp+140h+var_120], rax
0x18001a9f0  mov     [rbp+arg_10], 0
0x18001a9f8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a9fd  mov     rcx, rbx
0x18001aa00  add     rsp, 130h
0x18001aa07  pop     rdi
0x18001aa08  pop     rbx
0x18001aa09  pop     rbp
0x18001aa0a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
