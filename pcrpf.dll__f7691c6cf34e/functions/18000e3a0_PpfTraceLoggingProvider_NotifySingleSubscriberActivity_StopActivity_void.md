# PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StopActivity(void)

- ea: `0x18000e3a0`
- end: `0x18000e633`
- name: `?StopActivity@NotifySingleSubscriberActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::NotifySingleSubscriberActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18000e3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e3fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e3fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StopActivity(
        PpfTraceLoggingProvider::NotifySingleSubscriberActivity *this)
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
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v19; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v20; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v21; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v24; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = PpfTraceLoggingProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = (const wchar_t *)*((_QWORD *)v4 + 15);
        v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = (const wchar_t *)*((_QWORD *)v4 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = (const wchar_t *)*((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_180067FE5,
          v9 + 8,
          v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v32,
          &v24,
          (__int64)&v31,
          &v23,
          (__int64)&v30,
          &v22,
          &v21,
          (__int64)&SRWLock,
          &v20,
          &v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = PpfTraceLoggingProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)word_180067C3A,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000e3a0  push    rbp
0x18000e3a2  push    rbx
0x18000e3a3  push    rdi
0x18000e3a4  lea     rbp, [rsp-47h]
0x18000e3a9  sub     rsp, 100h
0x18000e3b0  mov     rdi, [rcx+110h]
0x18000e3b7  mov     rbx, rcx
0x18000e3ba  mov     eax, [rdi+48h]
0x18000e3bd  test    eax, eax
0x18000e3bf  jns     loc_18000E571
0x18000e3c5  add     rdi, 50h ; 'P'
0x18000e3c9  cmp     eax, [rdi+8]
0x18000e3cc  jnz     loc_18000E571
0x18000e3d2  test    rdi, rdi
0x18000e3d5  jz      loc_18000E571
0x18000e3db  lea     rdx, [rbp+57h+SRWLock]
0x18000e3df  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e3e4  mov     rax, [rbx+110h]
0x18000e3eb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000e3ef  mov     dword ptr [rax], 2
0x18000e3f5  test    rcx, rcx
0x18000e3f8  jz      short loc_18000E406
0x18000e3fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e401  nop     dword ptr [rax+rax+00h]
0x18000e406  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18000e40b  mov     r9, rax
0x18000e40e  mov     ecx, [rax]
0x18000e410  cmp     ecx, 5
0x18000e413  jbe     loc_18000E621
0x18000e419  mov     rax, [rax+18h]
0x18000e41d  mov     rdx, 400000000000h
0x18000e427  mov     rcx, [r9+10h]
0x18000e42b  test    rdx, rcx
0x18000e42e  jz      loc_18000E621
0x18000e434  mov     rcx, rax
0x18000e437  and     rcx, rdx
0x18000e43a  cmp     rcx, rax
0x18000e43d  jnz     loc_18000E621
0x18000e443  mov     rax, [rdi+78h]
0x18000e447  lea     rdx, byte_180067FE5
0x18000e44e  mov     r8, [rbx+110h]
0x18000e455  mov     rcx, r9
0x18000e458  mov     [rbp+57h+var_68], rax
0x18000e45c  add     r8, 8
0x18000e460  mov     rax, [rdi+70h]
0x18000e464  mov     [rbp+57h+var_60], rax
0x18000e468  mov     eax, [rdi+68h]
0x18000e46b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000e46e  mov     rax, [rdi+60h]
0x18000e472  mov     [rbp+57h+var_58], rax
0x18000e476  mov     rax, [rdi+58h]
0x18000e47a  mov     [rbp+57h+var_50], rax
0x18000e47e  mov     eax, [rdi+50h]
0x18000e481  mov     [rbp+57h+arg_8], eax
0x18000e484  mov     rax, [rdi+48h]
0x18000e488  mov     [rbp+57h+var_48], rax
0x18000e48c  mov     eax, [rdi+20h]
0x18000e48f  mov     dword ptr [rbp+57h+arg_10], eax
0x18000e492  mov     rax, [rdi+18h]
0x18000e496  mov     [rbp+57h+var_40], rax
0x18000e49a  mov     eax, [rdi]
0x18000e49c  mov     [rbp+57h+arg_18], eax
0x18000e49f  mov     rax, [rdi+80h]
0x18000e4a6  mov     [rbp+57h+var_38], rax
0x18000e4aa  mov     eax, [rdi+40h]
0x18000e4ad  mov     [rbp+57h+var_70], eax
0x18000e4b0  mov     rax, [rdi+38h]
0x18000e4b4  mov     [rbp+57h+var_30], rax
0x18000e4b8  mov     eax, [rdi+8]
0x18000e4bb  mov     [rbp+57h+var_6C], eax
0x18000e4be  mov     eax, 1000000h
0x18000e4c3  mov     [rbp+57h+var_28], rax
0x18000e4c7  mov     [rbp+57h+var_20], rax
0x18000e4cb  lea     rax, [rbp+57h+var_68]
0x18000e4cf  mov     [rsp+110h+var_78], rax
0x18000e4d7  lea     rax, [rbp+57h+var_60]
0x18000e4db  mov     [rsp+110h+var_80], rax
0x18000e4e3  lea     rax, [rbp+57h+SRWLock]
0x18000e4e7  mov     [rsp+110h+var_88], rax
0x18000e4ef  lea     rax, [rbp+57h+var_58]
0x18000e4f3  mov     [rsp+110h+var_90], rax
0x18000e4fb  lea     rax, [rbp+57h+var_50]
0x18000e4ff  mov     [rsp+110h+var_98], rax
0x18000e504  lea     rax, [rbp+57h+arg_8]
0x18000e508  mov     [rsp+110h+var_A0], rax
0x18000e50d  lea     rax, [rbp+57h+var_48]
0x18000e511  mov     [rsp+110h+var_A8], rax
0x18000e516  lea     rax, [rbp+57h+arg_10]
0x18000e51a  mov     [rsp+110h+var_B0], rax
0x18000e51f  lea     rax, [rbp+57h+var_40]
0x18000e523  mov     [rsp+110h+var_B8], rax
0x18000e528  lea     rax, [rbp+57h+arg_18]
0x18000e52c  mov     [rsp+110h+var_C0], rax
0x18000e531  lea     rax, [rbp+57h+var_38]
0x18000e535  mov     [rsp+110h+var_C8], rax
0x18000e53a  lea     rax, [rbp+57h+var_70]
0x18000e53e  mov     [rsp+110h+var_D0], rax
0x18000e543  lea     rax, [rbp+57h+var_30]
0x18000e547  mov     [rsp+110h+var_D8], rax
0x18000e54c  lea     rax, [rbp+57h+var_6C]
0x18000e550  mov     [rsp+110h+var_E0], rax
0x18000e555  lea     rax, [rbp+57h+var_28]
0x18000e559  mov     [rsp+110h+var_E8], rax
0x18000e55e  lea     rax, [rbp+57h+var_20]
0x18000e562  mov     [rsp+110h+var_F0], rax
0x18000e567  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000e56c  jmp     loc_18000E621
0x18000e571  lea     rdx, [rbp+57h+SRWLock]
0x18000e575  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e57a  mov     rax, [rbx+110h]
0x18000e581  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000e585  mov     dword ptr [rax], 2
0x18000e58b  test    rcx, rcx
0x18000e58e  jz      short loc_18000E59C
0x18000e590  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e597  nop     dword ptr [rax+rax+00h]
0x18000e59c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18000e5a1  mov     rdi, rax
0x18000e5a4  mov     ecx, [rax]
0x18000e5a6  cmp     ecx, 5
0x18000e5a9  jbe     short loc_18000E621
0x18000e5ab  mov     rax, [rax+18h]
0x18000e5af  mov     rdx, 400000000000h
0x18000e5b9  mov     rcx, [rdi+10h]
0x18000e5bd  test    rdx, rcx
0x18000e5c0  jz      short loc_18000E621
0x18000e5c2  mov     rcx, rax
0x18000e5c5  and     rcx, rdx
0x18000e5c8  cmp     rcx, rax
0x18000e5cb  jnz     short loc_18000E621
0x18000e5cd  call    cs:__imp_GetCurrentThreadId
0x18000e5d4  nop     dword ptr [rax+rax+00h]
0x18000e5d9  mov     r8, [rbx+110h]
0x18000e5e0  lea     rdx, word_180067C3A
0x18000e5e7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000e5ea  mov     rcx, rdi
0x18000e5ed  mov     eax, [r8+48h]
0x18000e5f1  add     r8, 8
0x18000e5f5  mov     [rbp+57h+arg_8], eax
0x18000e5f8  mov     eax, 1000000h
0x18000e5fd  mov     [rbp+57h+arg_10], rax
0x18000e601  lea     rax, [rbp+57h+SRWLock]
0x18000e605  mov     [rsp+110h+var_E0], rax
0x18000e60a  lea     rax, [rbp+57h+arg_8]
0x18000e60e  mov     [rsp+110h+var_E8], rax
0x18000e613  lea     rax, [rbp+57h+arg_10]
0x18000e617  mov     [rsp+110h+var_F0], rax
0x18000e61c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e621  mov     rcx, rbx
0x18000e624  add     rsp, 100h
0x18000e62b  pop     rdi
0x18000e62c  pop     rbx
0x18000e62d  pop     rbp
0x18000e62e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
