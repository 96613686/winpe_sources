# PpfTraceLoggingProvider::PpfStageTransformActivity::StopActivity(void)

- ea: `0x18001a6a0`
- end: `0x18001a933`
- name: `?StopActivity@PpfStageTransformActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfStageTransformActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18001a6a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a890`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a6fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a8cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a8cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfStageTransformActivity::StopActivity(
        PpfTraceLoggingProvider::PpfStageTransformActivity *this)
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
          (__int64)byte_18006922D,
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
          (__int64)byte_180069455,
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
0x18001a6a0  push    rbp
0x18001a6a2  push    rbx
0x18001a6a3  push    rdi
0x18001a6a4  lea     rbp, [rsp-47h]
0x18001a6a9  sub     rsp, 100h
0x18001a6b0  mov     rdi, [rcx+110h]
0x18001a6b7  mov     rbx, rcx
0x18001a6ba  mov     eax, [rdi+48h]
0x18001a6bd  test    eax, eax
0x18001a6bf  jns     loc_18001A871
0x18001a6c5  add     rdi, 50h ; 'P'
0x18001a6c9  cmp     eax, [rdi+8]
0x18001a6cc  jnz     loc_18001A871
0x18001a6d2  test    rdi, rdi
0x18001a6d5  jz      loc_18001A871
0x18001a6db  lea     rdx, [rbp+57h+SRWLock]
0x18001a6df  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a6e4  mov     rax, [rbx+110h]
0x18001a6eb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a6ef  mov     dword ptr [rax], 2
0x18001a6f5  test    rcx, rcx
0x18001a6f8  jz      short loc_18001A706
0x18001a6fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a701  nop     dword ptr [rax+rax+00h]
0x18001a706  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001a70b  mov     r9, rax
0x18001a70e  mov     ecx, [rax]
0x18001a710  cmp     ecx, 5
0x18001a713  jbe     loc_18001A921
0x18001a719  mov     rax, [rax+18h]
0x18001a71d  mov     rdx, 400000000000h
0x18001a727  mov     rcx, [r9+10h]
0x18001a72b  test    rdx, rcx
0x18001a72e  jz      loc_18001A921
0x18001a734  mov     rcx, rax
0x18001a737  and     rcx, rdx
0x18001a73a  cmp     rcx, rax
0x18001a73d  jnz     loc_18001A921
0x18001a743  mov     rax, [rdi+78h]
0x18001a747  lea     rdx, byte_18006922D
0x18001a74e  mov     r8, [rbx+110h]
0x18001a755  mov     rcx, r9
0x18001a758  mov     [rbp+57h+var_68], rax
0x18001a75c  add     r8, 8
0x18001a760  mov     rax, [rdi+70h]
0x18001a764  mov     [rbp+57h+var_60], rax
0x18001a768  mov     eax, [rdi+68h]
0x18001a76b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a76e  mov     rax, [rdi+60h]
0x18001a772  mov     [rbp+57h+var_58], rax
0x18001a776  mov     rax, [rdi+58h]
0x18001a77a  mov     [rbp+57h+var_50], rax
0x18001a77e  mov     eax, [rdi+50h]
0x18001a781  mov     [rbp+57h+arg_8], eax
0x18001a784  mov     rax, [rdi+48h]
0x18001a788  mov     [rbp+57h+var_48], rax
0x18001a78c  mov     eax, [rdi+20h]
0x18001a78f  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a792  mov     rax, [rdi+18h]
0x18001a796  mov     [rbp+57h+var_40], rax
0x18001a79a  mov     eax, [rdi]
0x18001a79c  mov     [rbp+57h+arg_18], eax
0x18001a79f  mov     rax, [rdi+80h]
0x18001a7a6  mov     [rbp+57h+var_38], rax
0x18001a7aa  mov     eax, [rdi+40h]
0x18001a7ad  mov     [rbp+57h+var_70], eax
0x18001a7b0  mov     rax, [rdi+38h]
0x18001a7b4  mov     [rbp+57h+var_30], rax
0x18001a7b8  mov     eax, [rdi+8]
0x18001a7bb  mov     [rbp+57h+var_6C], eax
0x18001a7be  mov     eax, 1000000h
0x18001a7c3  mov     [rbp+57h+var_28], rax
0x18001a7c7  mov     [rbp+57h+var_20], rax
0x18001a7cb  lea     rax, [rbp+57h+var_68]
0x18001a7cf  mov     [rsp+110h+var_78], rax
0x18001a7d7  lea     rax, [rbp+57h+var_60]
0x18001a7db  mov     [rsp+110h+var_80], rax
0x18001a7e3  lea     rax, [rbp+57h+SRWLock]
0x18001a7e7  mov     [rsp+110h+var_88], rax
0x18001a7ef  lea     rax, [rbp+57h+var_58]
0x18001a7f3  mov     [rsp+110h+var_90], rax
0x18001a7fb  lea     rax, [rbp+57h+var_50]
0x18001a7ff  mov     [rsp+110h+var_98], rax
0x18001a804  lea     rax, [rbp+57h+arg_8]
0x18001a808  mov     [rsp+110h+var_A0], rax
0x18001a80d  lea     rax, [rbp+57h+var_48]
0x18001a811  mov     [rsp+110h+var_A8], rax
0x18001a816  lea     rax, [rbp+57h+arg_10]
0x18001a81a  mov     [rsp+110h+var_B0], rax
0x18001a81f  lea     rax, [rbp+57h+var_40]
0x18001a823  mov     [rsp+110h+var_B8], rax
0x18001a828  lea     rax, [rbp+57h+arg_18]
0x18001a82c  mov     [rsp+110h+var_C0], rax
0x18001a831  lea     rax, [rbp+57h+var_38]
0x18001a835  mov     [rsp+110h+var_C8], rax
0x18001a83a  lea     rax, [rbp+57h+var_70]
0x18001a83e  mov     [rsp+110h+var_D0], rax
0x18001a843  lea     rax, [rbp+57h+var_30]
0x18001a847  mov     [rsp+110h+var_D8], rax
0x18001a84c  lea     rax, [rbp+57h+var_6C]
0x18001a850  mov     [rsp+110h+var_E0], rax
0x18001a855  lea     rax, [rbp+57h+var_28]
0x18001a859  mov     [rsp+110h+var_E8], rax
0x18001a85e  lea     rax, [rbp+57h+var_20]
0x18001a862  mov     [rsp+110h+var_F0], rax
0x18001a867  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a86c  jmp     loc_18001A921
0x18001a871  lea     rdx, [rbp+57h+SRWLock]
0x18001a875  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a87a  mov     rax, [rbx+110h]
0x18001a881  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a885  mov     dword ptr [rax], 2
0x18001a88b  test    rcx, rcx
0x18001a88e  jz      short loc_18001A89C
0x18001a890  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a897  nop     dword ptr [rax+rax+00h]
0x18001a89c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001a8a1  mov     rdi, rax
0x18001a8a4  mov     ecx, [rax]
0x18001a8a6  cmp     ecx, 5
0x18001a8a9  jbe     short loc_18001A921
0x18001a8ab  mov     rax, [rax+18h]
0x18001a8af  mov     rdx, 400000000000h
0x18001a8b9  mov     rcx, [rdi+10h]
0x18001a8bd  test    rdx, rcx
0x18001a8c0  jz      short loc_18001A921
0x18001a8c2  mov     rcx, rax
0x18001a8c5  and     rcx, rdx
0x18001a8c8  cmp     rcx, rax
0x18001a8cb  jnz     short loc_18001A921
0x18001a8cd  call    cs:__imp_GetCurrentThreadId
0x18001a8d4  nop     dword ptr [rax+rax+00h]
0x18001a8d9  mov     r8, [rbx+110h]
0x18001a8e0  lea     rdx, byte_180069455
0x18001a8e7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a8ea  mov     rcx, rdi
0x18001a8ed  mov     eax, [r8+48h]
0x18001a8f1  add     r8, 8
0x18001a8f5  mov     [rbp+57h+arg_8], eax
0x18001a8f8  mov     eax, 1000000h
0x18001a8fd  mov     [rbp+57h+arg_10], rax
0x18001a901  lea     rax, [rbp+57h+SRWLock]
0x18001a905  mov     [rsp+110h+var_E0], rax
0x18001a90a  lea     rax, [rbp+57h+arg_8]
0x18001a90e  mov     [rsp+110h+var_E8], rax
0x18001a913  lea     rax, [rbp+57h+arg_10]
0x18001a917  mov     [rsp+110h+var_F0], rax
0x18001a91c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a921  mov     rcx, rbx
0x18001a924  add     rsp, 100h
0x18001a92b  pop     rdi
0x18001a92c  pop     rbx
0x18001a92d  pop     rbp
0x18001a92e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
