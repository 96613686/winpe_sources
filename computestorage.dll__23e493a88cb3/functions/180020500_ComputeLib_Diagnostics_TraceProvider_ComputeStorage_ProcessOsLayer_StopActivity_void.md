# ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StopActivity(void)

- ea: `0x180020500`
- end: `0x1800207e6`
- name: `?StopActivity@ComputeStorage_ProcessOsLayer@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `742`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000bc04`
- `0x18001251c`
- `0x18001f068`
- `0x180020500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020567`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020736`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020567`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020769`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020769`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  int v16; // [rsp+D0h] [rbp-70h] BYREF
  int v17; // [rsp+D4h] [rbp-6Ch] BYREF
  int v18; // [rsp+D8h] [rbp-68h] BYREF
  int v19; // [rsp+DCh] [rbp-64h] BYREF
  int v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  __int64 v28; // [rsp+120h] [rbp-20h] BYREF
  __int64 v29; // [rsp+128h] [rbp-18h] BYREF
  __int64 v30; // [rsp+130h] [rbp-10h] BYREF
  __int64 v31; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x40) != 0 && (v7 & 0x40) == v7 )
      {
        v22 = *((_QWORD *)v4 + 6);
        v15 = v4[17];
        v16 = v4[4];
        v23 = *((_QWORD *)v4 + 15);
        v24 = *((_QWORD *)v4 + 14);
        v17 = v4[26];
        v25 = *((_QWORD *)v4 + 12);
        v26 = *((_QWORD *)v4 + 11);
        v18 = v4[20];
        v27 = *((_QWORD *)v4 + 9);
        v19 = v4[8];
        v28 = *((_QWORD *)v4 + 3);
        v20 = *v4;
        v29 = *((_QWORD *)v4 + 16);
        v14 = v4[16];
        v30 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v21 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v6,
          (int)&byte_1800554E9,
          *((_QWORD *)this + 34) + 8,
          v6,
          (__int64)&v21,
          (__int64)&v31,
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v30,
          (__int64)&v14,
          (const unsigned __int16 **)&v29,
          (__int64)&v20,
          (__int64 **)&v28,
          (__int64)&v19,
          (const unsigned __int16 **)&v27,
          (__int64)&v18,
          (const unsigned __int16 **)&v26,
          (__int64 **)&v25,
          (__int64)&v17,
          (const unsigned __int16 **)&v24,
          (__int64 **)&v23,
          (__int64)&v16,
          (__int64)&v15,
          (const unsigned __int16 **)&v22);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v14 = *(_DWORD *)(v11 + 72);
        v21 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v9,
          (int)byte_1800552FB,
          v11 + 8,
          v12,
          (__int64)&v21,
          (__int64)&v14,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ComputeStorage_ProcessOsLayer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180020500  mov     [rsp-8+arg_8], rbx
0x180020505  mov     [rsp-8+arg_10], rdi
0x18002050a  push    rbp
0x18002050b  mov     rbp, rsp
0x18002050e  sub     rsp, 140h
0x180020515  mov     rbx, rcx
0x180020518  mov     rdi, [rcx+110h]
0x18002051f  mov     eax, [rdi+48h]
0x180020522  test    eax, eax
0x180020524  jns     loc_18002070F
0x18002052a  add     rdi, 50h ; 'P'
0x18002052e  cmp     eax, [rdi+8]
0x180020531  jnz     loc_18002070F
0x180020537  test    rdi, rdi
0x18002053a  jz      loc_18002070F
0x180020540  mov     [rbp+SRWLock], 0
0x180020548  lea     rdx, [rbp+SRWLock]
0x18002054c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020551  mov     rax, [rbx+110h]
0x180020558  mov     dword ptr [rax], 2
0x18002055e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180020562  test    rcx, rcx
0x180020565  jz      short loc_180020573
0x180020567  call    cs:__imp_ReleaseSRWLockExclusive
0x18002056e  nop     dword ptr [rax+rax+00h]
0x180020573  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180020578  mov     r9, rax
0x18002057b  mov     ecx, [rax]
0x18002057d  cmp     ecx, 4
0x180020580  jbe     loc_1800207BD
0x180020586  mov     rax, [rax+18h]
0x18002058a  mov     rcx, [r9+10h]
0x18002058e  test    cl, 40h
0x180020591  jz      loc_1800207BD
0x180020597  mov     rcx, rax
0x18002059a  and     ecx, 40h
0x18002059d  cmp     rcx, rax
0x1800205a0  jnz     loc_1800207BD
0x1800205a6  mov     rax, [rdi+30h]
0x1800205aa  mov     [rbp+var_50], rax
0x1800205ae  mov     eax, [rdi+44h]
0x1800205b1  mov     dword ptr [rbp+var_78+4], eax
0x1800205b4  mov     eax, [rdi+10h]
0x1800205b7  mov     dword ptr [rbp+var_70], eax
0x1800205ba  mov     rax, [rdi+78h]
0x1800205be  mov     [rbp+var_48], rax
0x1800205c2  mov     rax, [rdi+70h]
0x1800205c6  mov     [rbp+var_40], rax
0x1800205ca  mov     eax, [rdi+68h]
0x1800205cd  mov     dword ptr [rbp+var_70+4], eax
0x1800205d0  mov     rax, [rdi+60h]
0x1800205d4  mov     [rbp+var_38], rax
0x1800205d8  mov     rax, [rdi+58h]
0x1800205dc  mov     [rbp+var_30], rax
0x1800205e0  mov     eax, [rdi+50h]
0x1800205e3  mov     dword ptr [rbp+var_68], eax
0x1800205e6  mov     rax, [rdi+48h]
0x1800205ea  mov     [rbp+var_28], rax
0x1800205ee  mov     eax, [rdi+20h]
0x1800205f1  mov     dword ptr [rbp+var_68+4], eax
0x1800205f4  mov     rax, [rdi+18h]
0x1800205f8  mov     [rbp+var_20], rax
0x1800205fc  mov     eax, [rdi]
0x1800205fe  mov     [rbp+var_60], eax
0x180020601  mov     rax, [rdi+80h]
0x180020608  mov     [rbp+var_18], rax
0x18002060c  mov     eax, [rdi+40h]
0x18002060f  mov     dword ptr [rbp+var_78], eax
0x180020612  mov     rax, [rdi+38h]
0x180020616  mov     [rbp+var_10], rax
0x18002061a  mov     eax, [rdi+8]
0x18002061d  mov     dword ptr [rbp+SRWLock], eax
0x180020620  mov     [rbp+var_8], 1000000h
0x180020628  mov     [rbp+var_58], 0
0x180020630  mov     r8, [rbx+110h]
0x180020637  add     r8, 8; int
0x18002063b  lea     rax, [rbp+var_50]
0x18002063f  mov     [rsp+140h+var_90], rax; __int64
0x180020647  lea     rax, [rbp+var_78+4]
0x18002064b  mov     [rsp+140h+var_98], rax; __int64
0x180020653  lea     rax, [rbp+var_70]
0x180020657  mov     [rsp+140h+var_A0], rax; __int64
0x18002065f  lea     rax, [rbp+var_48]
0x180020663  mov     [rsp+140h+var_A8], rax; __int64
0x18002066b  lea     rax, [rbp+var_40]
0x18002066f  mov     [rsp+140h+var_B0], rax; __int64
0x180020677  lea     rax, [rbp+var_70+4]
0x18002067b  mov     [rsp+140h+var_B8], rax; __int64
0x180020683  lea     rax, [rbp+var_38]
0x180020687  mov     [rsp+140h+var_C0], rax; __int64
0x18002068f  lea     rax, [rbp+var_30]
0x180020693  mov     [rsp+140h+var_C8], rax; __int64
0x180020698  lea     rax, [rbp+var_68]
0x18002069c  mov     [rsp+140h+var_D0], rax; __int64
0x1800206a1  lea     rax, [rbp+var_28]
0x1800206a5  mov     [rsp+140h+var_D8], rax; __int64
0x1800206aa  lea     rax, [rbp+var_68+4]
0x1800206ae  mov     [rsp+140h+var_E0], rax; __int64
0x1800206b3  lea     rax, [rbp+var_20]
0x1800206b7  mov     [rsp+140h+var_E8], rax; __int64
0x1800206bc  lea     rax, [rbp+var_60]
0x1800206c0  mov     [rsp+140h+var_F0], rax; __int64
0x1800206c5  lea     rax, [rbp+var_18]
0x1800206c9  mov     [rsp+140h+var_F8], rax; __int64
0x1800206ce  lea     rax, [rbp+var_78]
0x1800206d2  mov     [rsp+140h+var_100], rax; __int64
0x1800206d7  lea     rax, [rbp+var_10]
0x1800206db  mov     [rsp+140h+var_108], rax; __int64
0x1800206e0  lea     rax, [rbp+SRWLock]
0x1800206e4  mov     [rsp+140h+var_110], rax; __int64
0x1800206e9  lea     rax, [rbp+var_8]
0x1800206ed  mov     [rsp+140h+var_118], rax; __int64
0x1800206f2  lea     rax, [rbp+var_58]
0x1800206f6  mov     [rsp+140h+var_120], rax; __int64
0x1800206fb  lea     rdx, byte_1800554E9; int
0x180020702  mov     rcx, r9; int
0x180020705  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002070a  jmp     loc_1800207BD
0x18002070f  mov     [rbp+SRWLock], 0
0x180020717  lea     rdx, [rbp+SRWLock]
0x18002071b  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180020720  mov     rax, [rbx+110h]
0x180020727  mov     dword ptr [rax], 2
0x18002072d  mov     rcx, [rbp+SRWLock]; SRWLock
0x180020731  test    rcx, rcx
0x180020734  jz      short loc_180020742
0x180020736  call    cs:__imp_ReleaseSRWLockExclusive
0x18002073d  nop     dword ptr [rax+rax+00h]
0x180020742  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x180020747  mov     rdi, rax
0x18002074a  mov     ecx, [rax]
0x18002074c  cmp     ecx, 4
0x18002074f  jbe     short loc_1800207BD
0x180020751  mov     rax, [rax+18h]
0x180020755  mov     rcx, [rdi+10h]
0x180020759  test    cl, 40h
0x18002075c  jz      short loc_1800207BD
0x18002075e  mov     rcx, rax
0x180020761  and     ecx, 40h
0x180020764  cmp     rcx, rax
0x180020767  jnz     short loc_1800207BD
0x180020769  call    cs:__imp_GetCurrentThreadId
0x180020770  nop     dword ptr [rax+rax+00h]
0x180020775  mov     dword ptr [rbp+SRWLock], eax
0x180020778  mov     r8, [rbx+110h]
0x18002077f  mov     eax, [r8+48h]
0x180020783  mov     dword ptr [rbp+var_78], eax
0x180020786  mov     [rbp+var_58], 0
0x18002078e  add     r8, 8
0x180020792  lea     rax, [rbp+SRWLock]
0x180020796  mov     [rsp+140h+var_110], rax
0x18002079b  lea     rax, [rbp+var_78]
0x18002079f  mov     [rsp+140h+var_118], rax
0x1800207a4  lea     rax, [rbp+var_58]
0x1800207a8  mov     [rsp+140h+var_120], rax
0x1800207ad  lea     rdx, byte_1800552FB
0x1800207b4  mov     rcx, rdi
0x1800207b7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800207bc  nop
0x1800207bd  lea     rcx, [rbx+120h]; this
0x1800207c4  cmp     dword ptr [rcx+18h], 0
0x1800207c8  jz      short loc_1800207D0
0x1800207ca  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800207cf  nop
0x1800207d0  lea     r11, [rsp+140h+var_s0]
0x1800207d8  mov     rbx, [r11+18h]
0x1800207dc  mov     rdi, [r11+20h]
0x1800207e0  mov     rsp, r11
0x1800207e3  pop     rbp
0x1800207e4  retn
```
