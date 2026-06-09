# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StopActivity(void)

- ea: `0x180019d70`
- end: `0x180019ff3`
- name: `?StopActivity@ProvOpsApplyKnownPackages@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x180019d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f94`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsApplyKnownPackages *this)
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
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
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
        v27[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&dword_18003F284,
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
        v30 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)byte_18003FC55,
          v15 + 8);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019d70  push    rbp
0x180019d72  push    rbx
0x180019d73  push    rdi
0x180019d74  lea     rbp, [rsp-47h]
0x180019d79  sub     rsp, 100h
0x180019d80  mov     rdi, [rcx+110h]
0x180019d87  mov     rbx, rcx
0x180019d8a  mov     eax, [rdi+48h]
0x180019d8d  test    eax, eax
0x180019d8f  jns     loc_180019F3E
0x180019d95  add     rdi, 50h ; 'P'
0x180019d99  cmp     eax, [rdi+8]
0x180019d9c  jnz     loc_180019F3E
0x180019da2  test    rdi, rdi
0x180019da5  jz      loc_180019F3E
0x180019dab  lea     rdx, [rbp+57h+SRWLock]
0x180019daf  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019db4  mov     rax, [rbx+110h]
0x180019dbb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019dbf  mov     dword ptr [rax], 2
0x180019dc5  test    rcx, rcx
0x180019dc8  jz      short loc_180019DD0
0x180019dca  call    cs:__imp_ReleaseSRWLockExclusive
0x180019dd0  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019dd5  mov     r9, rax
0x180019dd8  mov     ecx, [rax]
0x180019dda  cmp     ecx, 5
0x180019ddd  jbe     loc_180019FE1
0x180019de3  mov     rax, [rax+18h]
0x180019de7  mov     rdx, 400000000000h
0x180019df1  mov     rcx, [r9+10h]
0x180019df5  test    rdx, rcx
0x180019df8  jz      loc_180019FE1
0x180019dfe  mov     rcx, rax
0x180019e01  and     rcx, rdx
0x180019e04  cmp     rcx, rax
0x180019e07  jnz     loc_180019FE1
0x180019e0d  mov     rax, [rdi+78h]
0x180019e11  lea     rdx, dword_18003F284
0x180019e18  mov     r8, [rbx+110h]
0x180019e1f  mov     rcx, r9
0x180019e22  mov     [rbp+57h+var_68], rax
0x180019e26  add     r8, 8
0x180019e2a  mov     rax, [rdi+70h]
0x180019e2e  mov     [rbp+57h+var_60], rax
0x180019e32  mov     eax, [rdi+68h]
0x180019e35  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019e38  mov     rax, [rdi+60h]
0x180019e3c  mov     [rbp+57h+var_58], rax
0x180019e40  mov     rax, [rdi+58h]
0x180019e44  mov     [rbp+57h+var_50], rax
0x180019e48  mov     eax, [rdi+50h]
0x180019e4b  mov     [rbp+57h+arg_8], eax
0x180019e4e  mov     rax, [rdi+48h]
0x180019e52  mov     [rbp+57h+var_48], rax
0x180019e56  mov     eax, [rdi+20h]
0x180019e59  mov     dword ptr [rbp+57h+arg_10], eax
0x180019e5c  mov     rax, [rdi+18h]
0x180019e60  mov     [rbp+57h+var_40], rax
0x180019e64  mov     eax, [rdi]
0x180019e66  mov     [rbp+57h+arg_18], eax
0x180019e69  mov     rax, [rdi+80h]
0x180019e70  mov     [rbp+57h+var_38], rax
0x180019e74  mov     eax, [rdi+40h]
0x180019e77  mov     [rbp+57h+var_70], eax
0x180019e7a  mov     rax, [rdi+38h]
0x180019e7e  mov     [rbp+57h+var_30], rax
0x180019e82  mov     eax, [rdi+8]
0x180019e85  mov     [rbp+57h+var_6C], eax
0x180019e88  lea     rax, [rbp+57h+var_68]
0x180019e8c  mov     [rsp+110h+var_78], rax
0x180019e94  lea     rax, [rbp+57h+var_60]
0x180019e98  mov     [rsp+110h+var_80], rax
0x180019ea0  lea     rax, [rbp+57h+SRWLock]
0x180019ea4  mov     [rsp+110h+var_88], rax
0x180019eac  lea     rax, [rbp+57h+var_58]
0x180019eb0  mov     [rsp+110h+var_90], rax
0x180019eb8  lea     rax, [rbp+57h+var_50]
0x180019ebc  mov     [rsp+110h+var_98], rax
0x180019ec1  lea     rax, [rbp+57h+arg_8]
0x180019ec5  mov     [rsp+110h+var_A0], rax
0x180019eca  lea     rax, [rbp+57h+var_48]
0x180019ece  mov     [rsp+110h+var_A8], rax
0x180019ed3  lea     rax, [rbp+57h+arg_10]
0x180019ed7  mov     [rsp+110h+var_B0], rax
0x180019edc  lea     rax, [rbp+57h+var_40]
0x180019ee0  mov     [rsp+110h+var_B8], rax
0x180019ee5  lea     rax, [rbp+57h+arg_18]
0x180019ee9  mov     [rsp+110h+var_C0], rax
0x180019eee  lea     rax, [rbp+57h+var_38]
0x180019ef2  mov     [rsp+110h+var_C8], rax
0x180019ef7  lea     rax, [rbp+57h+var_70]
0x180019efb  mov     [rsp+110h+var_D0], rax
0x180019f00  lea     rax, [rbp+57h+var_30]
0x180019f04  mov     [rsp+110h+var_D8], rax
0x180019f09  lea     rax, [rbp+57h+var_6C]
0x180019f0d  mov     [rsp+110h+var_E0], rax
0x180019f12  lea     rax, [rbp+57h+var_28]
0x180019f16  mov     [rsp+110h+var_E8], rax
0x180019f1b  lea     rax, [rbp+57h+var_20]
0x180019f1f  mov     [rsp+110h+var_F0], rax
0x180019f24  mov     [rbp+57h+var_28], 1000000h
0x180019f2c  mov     [rbp+57h+var_20], 0
0x180019f34  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019f39  jmp     loc_180019FE1
0x180019f3e  lea     rdx, [rbp+57h+SRWLock]
0x180019f42  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019f47  mov     rax, [rbx+110h]
0x180019f4e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019f52  mov     dword ptr [rax], 2
0x180019f58  test    rcx, rcx
0x180019f5b  jz      short loc_180019F63
0x180019f5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180019f63  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019f68  mov     rdi, rax
0x180019f6b  mov     ecx, [rax]
0x180019f6d  cmp     ecx, 5
0x180019f70  jbe     short loc_180019FE1
0x180019f72  mov     rax, [rax+18h]
0x180019f76  mov     rdx, 400000000000h
0x180019f80  mov     rcx, [rdi+10h]
0x180019f84  test    rdx, rcx
0x180019f87  jz      short loc_180019FE1
0x180019f89  mov     rcx, rax
0x180019f8c  and     rcx, rdx
0x180019f8f  cmp     rcx, rax
0x180019f92  jnz     short loc_180019FE1
0x180019f94  call    cs:__imp_GetCurrentThreadId
0x180019f9a  mov     r8, [rbx+110h]
0x180019fa1  lea     rdx, byte_18003FC55
0x180019fa8  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019fab  mov     rcx, rdi
0x180019fae  mov     eax, [r8+48h]
0x180019fb2  add     r8, 8
0x180019fb6  mov     [rbp+57h+arg_8], eax
0x180019fb9  lea     rax, [rbp+57h+SRWLock]
0x180019fbd  mov     [rsp+110h+var_E0], rax
0x180019fc2  lea     rax, [rbp+57h+arg_8]
0x180019fc6  mov     [rsp+110h+var_E8], rax
0x180019fcb  lea     rax, [rbp+57h+arg_10]
0x180019fcf  mov     [rsp+110h+var_F0], rax
0x180019fd4  mov     [rbp+57h+arg_10], 0
0x180019fdc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019fe1  mov     rcx, rbx
0x180019fe4  add     rsp, 100h
0x180019feb  pop     rdi
0x180019fec  pop     rbx
0x180019fed  pop     rbp
0x180019fee  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
