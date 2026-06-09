# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StopActivity(void)

- ea: `0x18001a000`
- end: `0x18001a281`
- name: `?StopActivity@ProvOpsCleanupOOBEProvisioningLogs@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `641`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x18001a000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a1ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a05a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a1ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a221`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsCleanupOOBEProvisioningLogs *this)
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
          (__int64)&dword_18003F4FC,
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
          (__int64)&dword_18003FE04,
          v15 + 8);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001a000  push    rbp
0x18001a002  push    rbx
0x18001a003  push    rdi
0x18001a004  lea     rbp, [rsp-47h]
0x18001a009  sub     rsp, 100h
0x18001a010  mov     rdi, [rcx+110h]
0x18001a017  mov     rbx, rcx
0x18001a01a  mov     eax, [rdi+48h]
0x18001a01d  test    eax, eax
0x18001a01f  jns     loc_18001A1CB
0x18001a025  add     rdi, 50h ; 'P'
0x18001a029  cmp     eax, [rdi+8]
0x18001a02c  jnz     loc_18001A1CB
0x18001a032  test    rdi, rdi
0x18001a035  jz      loc_18001A1CB
0x18001a03b  lea     rdx, [rbp+57h+SRWLock]
0x18001a03f  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a044  mov     rax, [rbx+110h]
0x18001a04b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a04f  mov     dword ptr [rax], 2
0x18001a055  test    rcx, rcx
0x18001a058  jz      short loc_18001A060
0x18001a05a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a060  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a065  mov     r9, rax
0x18001a068  mov     ecx, [rax]
0x18001a06a  cmp     ecx, 5
0x18001a06d  jbe     loc_18001A26F
0x18001a073  mov     rax, [rax+18h]
0x18001a077  mov     rdx, 400000000000h
0x18001a081  mov     rcx, [r9+10h]
0x18001a085  test    rdx, rcx
0x18001a088  jz      loc_18001A26F
0x18001a08e  mov     rcx, rax
0x18001a091  and     rcx, rdx
0x18001a094  cmp     rcx, rax
0x18001a097  jnz     loc_18001A26F
0x18001a09d  mov     rax, [rdi+78h]
0x18001a0a1  lea     rdx, dword_18003F4FC
0x18001a0a8  mov     r8, [rbx+110h]
0x18001a0af  mov     rcx, r9
0x18001a0b2  mov     [rbp+57h+var_68], rax
0x18001a0b6  add     r8, 8
0x18001a0ba  mov     rax, [rdi+70h]
0x18001a0be  mov     [rbp+57h+var_60], rax
0x18001a0c2  mov     eax, [rdi+68h]
0x18001a0c5  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a0c8  mov     rax, [rdi+60h]
0x18001a0cc  mov     [rbp+57h+var_58], rax
0x18001a0d0  mov     rax, [rdi+58h]
0x18001a0d4  mov     [rbp+57h+var_50], rax
0x18001a0d8  mov     eax, [rdi+50h]
0x18001a0db  mov     [rbp+57h+arg_8], eax
0x18001a0de  mov     rax, [rdi+48h]
0x18001a0e2  mov     [rbp+57h+var_48], rax
0x18001a0e6  mov     eax, [rdi+20h]
0x18001a0e9  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a0ec  mov     rax, [rdi+18h]
0x18001a0f0  mov     [rbp+57h+var_40], rax
0x18001a0f4  mov     eax, [rdi]
0x18001a0f6  mov     [rbp+57h+arg_18], eax
0x18001a0f9  mov     rax, [rdi+80h]
0x18001a100  mov     [rbp+57h+var_38], rax
0x18001a104  mov     eax, [rdi+40h]
0x18001a107  mov     [rbp+57h+var_70], eax
0x18001a10a  mov     rax, [rdi+38h]
0x18001a10e  mov     [rbp+57h+var_30], rax
0x18001a112  mov     eax, [rdi+8]
0x18001a115  mov     [rbp+57h+var_6C], eax
0x18001a118  mov     eax, 1000000h
0x18001a11d  mov     [rbp+57h+var_28], rax
0x18001a121  mov     [rbp+57h+var_20], rax
0x18001a125  lea     rax, [rbp+57h+var_68]
0x18001a129  mov     [rsp+110h+var_78], rax
0x18001a131  lea     rax, [rbp+57h+var_60]
0x18001a135  mov     [rsp+110h+var_80], rax
0x18001a13d  lea     rax, [rbp+57h+SRWLock]
0x18001a141  mov     [rsp+110h+var_88], rax
0x18001a149  lea     rax, [rbp+57h+var_58]
0x18001a14d  mov     [rsp+110h+var_90], rax
0x18001a155  lea     rax, [rbp+57h+var_50]
0x18001a159  mov     [rsp+110h+var_98], rax
0x18001a15e  lea     rax, [rbp+57h+arg_8]
0x18001a162  mov     [rsp+110h+var_A0], rax
0x18001a167  lea     rax, [rbp+57h+var_48]
0x18001a16b  mov     [rsp+110h+var_A8], rax
0x18001a170  lea     rax, [rbp+57h+arg_10]
0x18001a174  mov     [rsp+110h+var_B0], rax
0x18001a179  lea     rax, [rbp+57h+var_40]
0x18001a17d  mov     [rsp+110h+var_B8], rax
0x18001a182  lea     rax, [rbp+57h+arg_18]
0x18001a186  mov     [rsp+110h+var_C0], rax
0x18001a18b  lea     rax, [rbp+57h+var_38]
0x18001a18f  mov     [rsp+110h+var_C8], rax
0x18001a194  lea     rax, [rbp+57h+var_70]
0x18001a198  mov     [rsp+110h+var_D0], rax
0x18001a19d  lea     rax, [rbp+57h+var_30]
0x18001a1a1  mov     [rsp+110h+var_D8], rax
0x18001a1a6  lea     rax, [rbp+57h+var_6C]
0x18001a1aa  mov     [rsp+110h+var_E0], rax
0x18001a1af  lea     rax, [rbp+57h+var_28]
0x18001a1b3  mov     [rsp+110h+var_E8], rax
0x18001a1b8  lea     rax, [rbp+57h+var_20]
0x18001a1bc  mov     [rsp+110h+var_F0], rax
0x18001a1c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a1c6  jmp     loc_18001A26F
0x18001a1cb  lea     rdx, [rbp+57h+SRWLock]
0x18001a1cf  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a1d4  mov     rax, [rbx+110h]
0x18001a1db  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a1df  mov     dword ptr [rax], 2
0x18001a1e5  test    rcx, rcx
0x18001a1e8  jz      short loc_18001A1F0
0x18001a1ea  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a1f0  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001a1f5  mov     rdi, rax
0x18001a1f8  mov     ecx, [rax]
0x18001a1fa  cmp     ecx, 5
0x18001a1fd  jbe     short loc_18001A26F
0x18001a1ff  mov     rax, [rax+18h]
0x18001a203  mov     rdx, 400000000000h
0x18001a20d  mov     rcx, [rdi+10h]
0x18001a211  test    rdx, rcx
0x18001a214  jz      short loc_18001A26F
0x18001a216  mov     rcx, rax
0x18001a219  and     rcx, rdx
0x18001a21c  cmp     rcx, rax
0x18001a21f  jnz     short loc_18001A26F
0x18001a221  call    cs:__imp_GetCurrentThreadId
0x18001a227  mov     r8, [rbx+110h]
0x18001a22e  lea     rdx, dword_18003FE04
0x18001a235  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a238  mov     rcx, rdi
0x18001a23b  mov     eax, [r8+48h]
0x18001a23f  add     r8, 8
0x18001a243  mov     [rbp+57h+arg_8], eax
0x18001a246  mov     eax, 1000000h
0x18001a24b  mov     [rbp+57h+arg_10], rax
0x18001a24f  lea     rax, [rbp+57h+SRWLock]
0x18001a253  mov     [rsp+110h+var_E0], rax
0x18001a258  lea     rax, [rbp+57h+arg_8]
0x18001a25c  mov     [rsp+110h+var_E8], rax
0x18001a261  lea     rax, [rbp+57h+arg_10]
0x18001a265  mov     [rsp+110h+var_F0], rax
0x18001a26a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a26f  mov     rcx, rbx
0x18001a272  add     rsp, 100h
0x18001a279  pop     rdi
0x18001a27a  pop     rbx
0x18001a27b  pop     rbp
0x18001a27c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
