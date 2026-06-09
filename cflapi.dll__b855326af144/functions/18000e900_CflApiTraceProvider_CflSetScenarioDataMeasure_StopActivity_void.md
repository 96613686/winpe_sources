# CflApiTraceProvider::CflSetScenarioDataMeasure::StopActivity(void)

- ea: `0x18000e900`
- end: `0x18000eb86`
- name: `?StopActivity@CflSetScenarioDataMeasure@CflApiTraceProvider@@MEAAXXZ`
- size: `646`
- prototype: `void __fastcall(CflApiTraceProvider::CflSetScenarioDataMeasure *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800015d0`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000e900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e95a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eaef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e95a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000eaef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eb27`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflSetScenarioDataMeasure::StopActivity(
        CflApiTraceProvider::CflSetScenarioDataMeasure *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)&byte_180036F2F,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_180036ED5,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000e900  push    rbp
0x18000e902  push    rbx
0x18000e903  push    rdi
0x18000e904  lea     rbp, [rsp-47h]
0x18000e909  sub     rsp, 100h
0x18000e910  mov     rdi, [rcx+110h]
0x18000e917  mov     rbx, rcx
0x18000e91a  mov     eax, [rdi+48h]
0x18000e91d  test    eax, eax
0x18000e91f  jns     loc_18000EAD0
0x18000e925  add     rdi, 50h ; 'P'
0x18000e929  cmp     eax, [rdi+8]
0x18000e92c  jnz     loc_18000EAD0
0x18000e932  test    rdi, rdi
0x18000e935  jz      loc_18000EAD0
0x18000e93b  lea     rdx, [rbp+57h+SRWLock]
0x18000e93f  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e944  mov     rax, [rbx+110h]
0x18000e94b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000e94f  mov     dword ptr [rax], 2
0x18000e955  test    rcx, rcx
0x18000e958  jz      short loc_18000E960
0x18000e95a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e960  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000e965  mov     r9, [rax+8]
0x18000e969  mov     eax, [r9]
0x18000e96c  cmp     eax, 5
0x18000e96f  jbe     loc_18000EB74
0x18000e975  mov     rdx, [r9+18h]
0x18000e979  mov     rcx, 400000000000h
0x18000e983  mov     rax, [r9+10h]
0x18000e987  test    rcx, rax
0x18000e98a  jz      loc_18000EB74
0x18000e990  mov     rax, rdx
0x18000e993  and     rax, rcx
0x18000e996  cmp     rax, rdx
0x18000e999  jnz     loc_18000EB74
0x18000e99f  mov     rax, [rdi+78h]
0x18000e9a3  lea     rdx, byte_180036F2F
0x18000e9aa  mov     r8, [rbx+110h]
0x18000e9b1  mov     rcx, r9
0x18000e9b4  mov     [rbp+57h+var_68], rax
0x18000e9b8  add     r8, 8
0x18000e9bc  mov     rax, [rdi+70h]
0x18000e9c0  mov     [rbp+57h+var_60], rax
0x18000e9c4  mov     eax, [rdi+68h]
0x18000e9c7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000e9ca  mov     rax, [rdi+60h]
0x18000e9ce  mov     [rbp+57h+var_58], rax
0x18000e9d2  mov     rax, [rdi+58h]
0x18000e9d6  mov     [rbp+57h+var_50], rax
0x18000e9da  mov     eax, [rdi+50h]
0x18000e9dd  mov     [rbp+57h+arg_8], eax
0x18000e9e0  mov     rax, [rdi+48h]
0x18000e9e4  mov     [rbp+57h+var_48], rax
0x18000e9e8  mov     eax, [rdi+20h]
0x18000e9eb  mov     dword ptr [rbp+57h+arg_10], eax
0x18000e9ee  mov     rax, [rdi+18h]
0x18000e9f2  mov     [rbp+57h+var_40], rax
0x18000e9f6  mov     eax, [rdi]
0x18000e9f8  mov     [rbp+57h+arg_18], eax
0x18000e9fb  mov     rax, [rdi+80h]
0x18000ea02  mov     [rbp+57h+var_38], rax
0x18000ea06  mov     eax, [rdi+40h]
0x18000ea09  mov     [rbp+57h+var_70], eax
0x18000ea0c  mov     rax, [rdi+38h]
0x18000ea10  mov     [rbp+57h+var_30], rax
0x18000ea14  mov     eax, [rdi+8]
0x18000ea17  mov     [rbp+57h+var_6C], eax
0x18000ea1a  lea     rax, [rbp+57h+var_68]
0x18000ea1e  mov     [rsp+110h+var_78], rax
0x18000ea26  lea     rax, [rbp+57h+var_60]
0x18000ea2a  mov     [rsp+110h+var_80], rax
0x18000ea32  lea     rax, [rbp+57h+SRWLock]
0x18000ea36  mov     [rsp+110h+var_88], rax
0x18000ea3e  lea     rax, [rbp+57h+var_58]
0x18000ea42  mov     [rsp+110h+var_90], rax
0x18000ea4a  lea     rax, [rbp+57h+var_50]
0x18000ea4e  mov     [rsp+110h+var_98], rax
0x18000ea53  lea     rax, [rbp+57h+arg_8]
0x18000ea57  mov     [rsp+110h+var_A0], rax
0x18000ea5c  lea     rax, [rbp+57h+var_48]
0x18000ea60  mov     [rsp+110h+var_A8], rax
0x18000ea65  lea     rax, [rbp+57h+arg_10]
0x18000ea69  mov     [rsp+110h+var_B0], rax
0x18000ea6e  lea     rax, [rbp+57h+var_40]
0x18000ea72  mov     [rsp+110h+var_B8], rax
0x18000ea77  lea     rax, [rbp+57h+arg_18]
0x18000ea7b  mov     [rsp+110h+var_C0], rax
0x18000ea80  lea     rax, [rbp+57h+var_38]
0x18000ea84  mov     [rsp+110h+var_C8], rax
0x18000ea89  lea     rax, [rbp+57h+var_70]
0x18000ea8d  mov     [rsp+110h+var_D0], rax
0x18000ea92  lea     rax, [rbp+57h+var_30]
0x18000ea96  mov     [rsp+110h+var_D8], rax
0x18000ea9b  lea     rax, [rbp+57h+var_6C]
0x18000ea9f  mov     [rsp+110h+var_E0], rax
0x18000eaa4  lea     rax, [rbp+57h+var_28]
0x18000eaa8  mov     [rsp+110h+var_E8], rax
0x18000eaad  lea     rax, [rbp+57h+var_20]
0x18000eab1  mov     [rsp+110h+var_F0], rax
0x18000eab6  mov     [rbp+57h+var_28], 1000000h
0x18000eabe  mov     [rbp+57h+var_20], 0
0x18000eac6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000eacb  jmp     loc_18000EB74
0x18000ead0  lea     rdx, [rbp+57h+SRWLock]
0x18000ead4  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ead9  mov     rax, [rbx+110h]
0x18000eae0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000eae4  mov     dword ptr [rax], 2
0x18000eaea  test    rcx, rcx
0x18000eaed  jz      short loc_18000EAF5
0x18000eaef  call    cs:__imp_ReleaseSRWLockExclusive
0x18000eaf5  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000eafa  mov     rdi, [rax+8]
0x18000eafe  mov     eax, [rdi]
0x18000eb00  cmp     eax, 5
0x18000eb03  jbe     short loc_18000EB74
0x18000eb05  mov     rdx, [rdi+18h]
0x18000eb09  mov     rcx, 400000000000h
0x18000eb13  mov     rax, [rdi+10h]
0x18000eb17  test    rcx, rax
0x18000eb1a  jz      short loc_18000EB74
0x18000eb1c  mov     rax, rdx
0x18000eb1f  and     rax, rcx
0x18000eb22  cmp     rax, rdx
0x18000eb25  jnz     short loc_18000EB74
0x18000eb27  call    cs:__imp_GetCurrentThreadId
0x18000eb2d  mov     r8, [rbx+110h]
0x18000eb34  lea     rdx, byte_180036ED5
0x18000eb3b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000eb3e  mov     rcx, rdi
0x18000eb41  mov     eax, [r8+48h]
0x18000eb45  add     r8, 8
0x18000eb49  mov     [rbp+57h+arg_8], eax
0x18000eb4c  lea     rax, [rbp+57h+SRWLock]
0x18000eb50  mov     [rsp+110h+var_E0], rax
0x18000eb55  lea     rax, [rbp+57h+arg_8]
0x18000eb59  mov     [rsp+110h+var_E8], rax
0x18000eb5e  lea     rax, [rbp+57h+arg_10]
0x18000eb62  mov     [rsp+110h+var_F0], rax
0x18000eb67  mov     [rbp+57h+arg_10], 0
0x18000eb6f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000eb74  mov     rcx, rbx
0x18000eb77  add     rsp, 100h
0x18000eb7e  pop     rdi
0x18000eb7f  pop     rbx
0x18000eb80  pop     rbp
0x18000eb81  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
