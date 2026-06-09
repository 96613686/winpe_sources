# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StopActivity(void)

- ea: `0x1800195e0`
- end: `0x18001984f`
- name: `?StopActivity@CreateProvisioningSession@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001bf4`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x1800195e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001963a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800197db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001963a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800197db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800197f0`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *this)
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
        (__int64)&byte_18004076F,
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
        (__int64)&unk_18003EAE8,
        v12 + 8);
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800195e0  push    rbp
0x1800195e2  push    rbx
0x1800195e3  push    rdi
0x1800195e4  lea     rbp, [rsp+10h]
0x1800195e9  sub     rsp, 130h
0x1800195f0  mov     rdi, [rcx+110h]
0x1800195f7  mov     rbx, rcx
0x1800195fa  mov     eax, [rdi+48h]
0x1800195fd  test    eax, eax
0x1800195ff  jns     loc_1800197BC
0x180019605  add     rdi, 50h ; 'P'
0x180019609  cmp     eax, [rdi+8]
0x18001960c  jnz     loc_1800197BC
0x180019612  test    rdi, rdi
0x180019615  jz      loc_1800197BC
0x18001961b  lea     rdx, [rbp+SRWLock]
0x18001961f  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019624  mov     rax, [rbx+110h]
0x18001962b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001962f  mov     dword ptr [rax], 2
0x180019635  test    rcx, rcx
0x180019638  jz      short loc_180019640
0x18001963a  call    cs:__imp_ReleaseSRWLockExclusive
0x180019640  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019645  mov     r9, rax
0x180019648  mov     ecx, [rax]
0x18001964a  cmp     ecx, 4
0x18001964d  jbe     loc_18001983D
0x180019653  mov     rax, [rdi+70h]
0x180019657  lea     rdx, byte_18004076F
0x18001965e  mov     rcx, [rdi+30h]
0x180019662  mov     [rbp+var_60], rax
0x180019666  mov     eax, [rdi+68h]
0x180019669  mov     r8, [rbx+110h]
0x180019670  mov     dword ptr [rbp+arg_10], eax
0x180019673  add     r8, 8
0x180019677  mov     rax, [rdi+60h]
0x18001967b  mov     [rbp+var_58], rax
0x18001967f  mov     rax, [rdi+58h]
0x180019683  mov     [rbp+var_50], rax
0x180019687  mov     eax, [rdi+50h]
0x18001968a  mov     [rbp+arg_18], eax
0x18001968d  mov     rax, [rdi+48h]
0x180019691  mov     [rbp+var_48], rax
0x180019695  mov     eax, [rdi+20h]
0x180019698  mov     [rbp+var_80], eax
0x18001969b  mov     rax, [rdi+18h]
0x18001969f  mov     [rbp+var_40], rax
0x1800196a3  mov     eax, [rdi]
0x1800196a5  mov     [rbp+var_7C], eax
0x1800196a8  mov     rax, [rdi+80h]
0x1800196af  mov     [rbp+var_38], rax
0x1800196b3  mov     eax, [rdi+40h]
0x1800196b6  mov     [rbp+var_78], eax
0x1800196b9  mov     rax, [rdi+38h]
0x1800196bd  mov     [rbp+var_30], rax
0x1800196c1  mov     eax, [rdi+8]
0x1800196c4  mov     [rbp+var_74], eax
0x1800196c7  lea     rax, [rbp+var_70]
0x1800196cb  mov     [rsp+140h+var_90], rax
0x1800196d3  lea     rax, [rbp+SRWLock]
0x1800196d7  mov     [rsp+140h+var_98], rax
0x1800196df  lea     rax, [rbp+arg_8]
0x1800196e3  mov     [rsp+140h+var_A0], rax
0x1800196eb  lea     rax, [rbp+var_68]
0x1800196ef  mov     [rsp+140h+var_A8], rax
0x1800196f7  lea     rax, [rbp+var_60]
0x1800196fb  mov     [rsp+140h+var_B0], rax
0x180019703  lea     rax, [rbp+arg_10]
0x180019707  mov     [rsp+140h+var_B8], rax
0x18001970f  lea     rax, [rbp+var_58]
0x180019713  mov     [rsp+140h+var_C0], rax
0x18001971b  lea     rax, [rbp+var_50]
0x18001971f  mov     [rsp+140h+var_C8], rax
0x180019724  lea     rax, [rbp+arg_18]
0x180019728  mov     [rsp+140h+var_D0], rax
0x18001972d  lea     rax, [rbp+var_48]
0x180019731  mov     [rsp+140h+var_D8], rax
0x180019736  lea     rax, [rbp+var_80]
0x18001973a  mov     [rsp+140h+var_E0], rax
0x18001973f  lea     rax, [rbp+var_40]
0x180019743  mov     [rsp+140h+var_E8], rax
0x180019748  lea     rax, [rbp+var_7C]
0x18001974c  mov     [rsp+140h+var_F0], rax
0x180019751  lea     rax, [rbp+var_38]
0x180019755  mov     [rsp+140h+var_F8], rax
0x18001975a  lea     rax, [rbp+var_78]
0x18001975e  mov     [rsp+140h+var_100], rax
0x180019763  lea     rax, [rbp+var_30]
0x180019767  mov     [rsp+140h+var_108], rax
0x18001976c  lea     rax, [rbp+var_74]
0x180019770  mov     [rbp+var_70], rcx
0x180019774  mov     ecx, [rdi+44h]
0x180019777  mov     [rsp+140h+var_110], rax
0x18001977c  lea     rax, [rbp+var_28]
0x180019780  mov     dword ptr [rbp+SRWLock], ecx
0x180019783  mov     ecx, [rdi+10h]
0x180019786  mov     [rbp+arg_8], ecx
0x180019789  mov     rcx, [rdi+78h]
0x18001978d  mov     [rsp+140h+var_118], rax
0x180019792  lea     rax, [rbp+var_20]
0x180019796  mov     [rbp+var_68], rcx
0x18001979a  mov     rcx, r9
0x18001979d  mov     [rsp+140h+var_120], rax
0x1800197a2  mov     [rbp+var_28], 1000000h
0x1800197aa  mov     [rbp+var_20], 0
0x1800197b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800197b7  jmp     loc_18001983D
0x1800197bc  lea     rdx, [rbp+SRWLock]
0x1800197c0  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800197c5  mov     rax, [rbx+110h]
0x1800197cc  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800197d0  mov     dword ptr [rax], 2
0x1800197d6  test    rcx, rcx
0x1800197d9  jz      short loc_1800197E1
0x1800197db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800197e1  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800197e6  mov     rdi, rax
0x1800197e9  mov     ecx, [rax]
0x1800197eb  cmp     ecx, 4
0x1800197ee  jbe     short loc_18001983D
0x1800197f0  call    cs:__imp_GetCurrentThreadId
0x1800197f6  mov     r8, [rbx+110h]
0x1800197fd  lea     rdx, unk_18003EAE8
0x180019804  mov     dword ptr [rbp+SRWLock], eax
0x180019807  lea     rax, [rbp+SRWLock]
0x18001980b  mov     [rsp+140h+var_110], rax
0x180019810  lea     rax, [rbp+arg_8]
0x180019814  mov     [rsp+140h+var_118], rax
0x180019819  lea     rax, [rbp+arg_10]
0x18001981d  mov     ecx, [r8+48h]
0x180019821  add     r8, 8
0x180019825  mov     [rbp+arg_8], ecx
0x180019828  mov     rcx, rdi
0x18001982b  mov     [rsp+140h+var_120], rax
0x180019830  mov     [rbp+arg_10], 0
0x180019838  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001983d  mov     rcx, rbx
0x180019840  add     rsp, 130h
0x180019847  pop     rdi
0x180019848  pop     rbx
0x180019849  pop     rbp
0x18001984a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
