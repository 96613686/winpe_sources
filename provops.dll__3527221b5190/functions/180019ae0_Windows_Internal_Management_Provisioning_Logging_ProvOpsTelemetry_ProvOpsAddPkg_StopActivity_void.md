# Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StopActivity(void)

- ea: `0x180019ae0`
- end: `0x180019d63`
- name: `?StopActivity@ProvOpsAddPkg@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001f08`
- `0x180006f50`
- `0x180013034`
- `0x180013200`
- `0x180019ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019d04`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg::StopActivity(
        Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsAddPkg *this)
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
          (__int64)byte_18003FB09,
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
          (__int64)byte_180040BD3,
          v15 + 8);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019ae0  push    rbp
0x180019ae2  push    rbx
0x180019ae3  push    rdi
0x180019ae4  lea     rbp, [rsp-47h]
0x180019ae9  sub     rsp, 100h
0x180019af0  mov     rdi, [rcx+110h]
0x180019af7  mov     rbx, rcx
0x180019afa  mov     eax, [rdi+48h]
0x180019afd  test    eax, eax
0x180019aff  jns     loc_180019CAE
0x180019b05  add     rdi, 50h ; 'P'
0x180019b09  cmp     eax, [rdi+8]
0x180019b0c  jnz     loc_180019CAE
0x180019b12  test    rdi, rdi
0x180019b15  jz      loc_180019CAE
0x180019b1b  lea     rdx, [rbp+57h+SRWLock]
0x180019b1f  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019b24  mov     rax, [rbx+110h]
0x180019b2b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019b2f  mov     dword ptr [rax], 2
0x180019b35  test    rcx, rcx
0x180019b38  jz      short loc_180019B40
0x180019b3a  call    cs:__imp_ReleaseSRWLockExclusive
0x180019b40  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019b45  mov     r9, rax
0x180019b48  mov     ecx, [rax]
0x180019b4a  cmp     ecx, 5
0x180019b4d  jbe     loc_180019D51
0x180019b53  mov     rax, [rax+18h]
0x180019b57  mov     rdx, 400000000000h
0x180019b61  mov     rcx, [r9+10h]
0x180019b65  test    rdx, rcx
0x180019b68  jz      loc_180019D51
0x180019b6e  mov     rcx, rax
0x180019b71  and     rcx, rdx
0x180019b74  cmp     rcx, rax
0x180019b77  jnz     loc_180019D51
0x180019b7d  mov     rax, [rdi+78h]
0x180019b81  lea     rdx, byte_18003FB09
0x180019b88  mov     r8, [rbx+110h]
0x180019b8f  mov     rcx, r9
0x180019b92  mov     [rbp+57h+var_68], rax
0x180019b96  add     r8, 8
0x180019b9a  mov     rax, [rdi+70h]
0x180019b9e  mov     [rbp+57h+var_60], rax
0x180019ba2  mov     eax, [rdi+68h]
0x180019ba5  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019ba8  mov     rax, [rdi+60h]
0x180019bac  mov     [rbp+57h+var_58], rax
0x180019bb0  mov     rax, [rdi+58h]
0x180019bb4  mov     [rbp+57h+var_50], rax
0x180019bb8  mov     eax, [rdi+50h]
0x180019bbb  mov     [rbp+57h+arg_8], eax
0x180019bbe  mov     rax, [rdi+48h]
0x180019bc2  mov     [rbp+57h+var_48], rax
0x180019bc6  mov     eax, [rdi+20h]
0x180019bc9  mov     dword ptr [rbp+57h+arg_10], eax
0x180019bcc  mov     rax, [rdi+18h]
0x180019bd0  mov     [rbp+57h+var_40], rax
0x180019bd4  mov     eax, [rdi]
0x180019bd6  mov     [rbp+57h+arg_18], eax
0x180019bd9  mov     rax, [rdi+80h]
0x180019be0  mov     [rbp+57h+var_38], rax
0x180019be4  mov     eax, [rdi+40h]
0x180019be7  mov     [rbp+57h+var_70], eax
0x180019bea  mov     rax, [rdi+38h]
0x180019bee  mov     [rbp+57h+var_30], rax
0x180019bf2  mov     eax, [rdi+8]
0x180019bf5  mov     [rbp+57h+var_6C], eax
0x180019bf8  lea     rax, [rbp+57h+var_68]
0x180019bfc  mov     [rsp+110h+var_78], rax
0x180019c04  lea     rax, [rbp+57h+var_60]
0x180019c08  mov     [rsp+110h+var_80], rax
0x180019c10  lea     rax, [rbp+57h+SRWLock]
0x180019c14  mov     [rsp+110h+var_88], rax
0x180019c1c  lea     rax, [rbp+57h+var_58]
0x180019c20  mov     [rsp+110h+var_90], rax
0x180019c28  lea     rax, [rbp+57h+var_50]
0x180019c2c  mov     [rsp+110h+var_98], rax
0x180019c31  lea     rax, [rbp+57h+arg_8]
0x180019c35  mov     [rsp+110h+var_A0], rax
0x180019c3a  lea     rax, [rbp+57h+var_48]
0x180019c3e  mov     [rsp+110h+var_A8], rax
0x180019c43  lea     rax, [rbp+57h+arg_10]
0x180019c47  mov     [rsp+110h+var_B0], rax
0x180019c4c  lea     rax, [rbp+57h+var_40]
0x180019c50  mov     [rsp+110h+var_B8], rax
0x180019c55  lea     rax, [rbp+57h+arg_18]
0x180019c59  mov     [rsp+110h+var_C0], rax
0x180019c5e  lea     rax, [rbp+57h+var_38]
0x180019c62  mov     [rsp+110h+var_C8], rax
0x180019c67  lea     rax, [rbp+57h+var_70]
0x180019c6b  mov     [rsp+110h+var_D0], rax
0x180019c70  lea     rax, [rbp+57h+var_30]
0x180019c74  mov     [rsp+110h+var_D8], rax
0x180019c79  lea     rax, [rbp+57h+var_6C]
0x180019c7d  mov     [rsp+110h+var_E0], rax
0x180019c82  lea     rax, [rbp+57h+var_28]
0x180019c86  mov     [rsp+110h+var_E8], rax
0x180019c8b  lea     rax, [rbp+57h+var_20]
0x180019c8f  mov     [rsp+110h+var_F0], rax
0x180019c94  mov     [rbp+57h+var_28], 1000000h
0x180019c9c  mov     [rbp+57h+var_20], 0
0x180019ca4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019ca9  jmp     loc_180019D51
0x180019cae  lea     rdx, [rbp+57h+SRWLock]
0x180019cb2  call    ?LockExclusive@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019cb7  mov     rax, [rbx+110h]
0x180019cbe  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019cc2  mov     dword ptr [rax], 2
0x180019cc8  test    rcx, rcx
0x180019ccb  jz      short loc_180019CD3
0x180019ccd  call    cs:__imp_ReleaseSRWLockExclusive
0x180019cd3  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180019cd8  mov     rdi, rax
0x180019cdb  mov     ecx, [rax]
0x180019cdd  cmp     ecx, 5
0x180019ce0  jbe     short loc_180019D51
0x180019ce2  mov     rax, [rax+18h]
0x180019ce6  mov     rdx, 400000000000h
0x180019cf0  mov     rcx, [rdi+10h]
0x180019cf4  test    rdx, rcx
0x180019cf7  jz      short loc_180019D51
0x180019cf9  mov     rcx, rax
0x180019cfc  and     rcx, rdx
0x180019cff  cmp     rcx, rax
0x180019d02  jnz     short loc_180019D51
0x180019d04  call    cs:__imp_GetCurrentThreadId
0x180019d0a  mov     r8, [rbx+110h]
0x180019d11  lea     rdx, byte_180040BD3
0x180019d18  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019d1b  mov     rcx, rdi
0x180019d1e  mov     eax, [r8+48h]
0x180019d22  add     r8, 8
0x180019d26  mov     [rbp+57h+arg_8], eax
0x180019d29  lea     rax, [rbp+57h+SRWLock]
0x180019d2d  mov     [rsp+110h+var_E0], rax
0x180019d32  lea     rax, [rbp+57h+arg_8]
0x180019d36  mov     [rsp+110h+var_E8], rax
0x180019d3b  lea     rax, [rbp+57h+arg_10]
0x180019d3f  mov     [rsp+110h+var_F0], rax
0x180019d44  mov     [rbp+57h+arg_10], 0
0x180019d4c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019d51  mov     rcx, rbx
0x180019d54  add     rsp, 100h
0x180019d5b  pop     rdi
0x180019d5c  pop     rbx
0x180019d5d  pop     rbp
0x180019d5e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
