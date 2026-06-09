# PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StopActivity(void)

- ea: `0x180019090`
- end: `0x180019323`
- name: `?StopActivity@PpfGenerateFinalPcrValuesForPpfEventLogActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180019090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800190ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019280`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800190ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019280`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800192bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800192bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity::StopActivity(
        PpfTraceLoggingProvider::PpfGenerateFinalPcrValuesForPpfEventLogActivity *this)
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
          (__int64)&byte_180068147,
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
          (__int64)word_1800689F2,
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
0x180019090  push    rbp
0x180019092  push    rbx
0x180019093  push    rdi
0x180019094  lea     rbp, [rsp-47h]
0x180019099  sub     rsp, 100h
0x1800190a0  mov     rdi, [rcx+110h]
0x1800190a7  mov     rbx, rcx
0x1800190aa  mov     eax, [rdi+48h]
0x1800190ad  test    eax, eax
0x1800190af  jns     loc_180019261
0x1800190b5  add     rdi, 50h ; 'P'
0x1800190b9  cmp     eax, [rdi+8]
0x1800190bc  jnz     loc_180019261
0x1800190c2  test    rdi, rdi
0x1800190c5  jz      loc_180019261
0x1800190cb  lea     rdx, [rbp+57h+SRWLock]
0x1800190cf  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800190d4  mov     rax, [rbx+110h]
0x1800190db  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800190df  mov     dword ptr [rax], 2
0x1800190e5  test    rcx, rcx
0x1800190e8  jz      short loc_1800190F6
0x1800190ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800190f1  nop     dword ptr [rax+rax+00h]
0x1800190f6  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x1800190fb  mov     r9, rax
0x1800190fe  mov     ecx, [rax]
0x180019100  cmp     ecx, 5
0x180019103  jbe     loc_180019311
0x180019109  mov     rax, [rax+18h]
0x18001910d  mov     rdx, 400000000000h
0x180019117  mov     rcx, [r9+10h]
0x18001911b  test    rdx, rcx
0x18001911e  jz      loc_180019311
0x180019124  mov     rcx, rax
0x180019127  and     rcx, rdx
0x18001912a  cmp     rcx, rax
0x18001912d  jnz     loc_180019311
0x180019133  mov     rax, [rdi+78h]
0x180019137  lea     rdx, byte_180068147
0x18001913e  mov     r8, [rbx+110h]
0x180019145  mov     rcx, r9
0x180019148  mov     [rbp+57h+var_68], rax
0x18001914c  add     r8, 8
0x180019150  mov     rax, [rdi+70h]
0x180019154  mov     [rbp+57h+var_60], rax
0x180019158  mov     eax, [rdi+68h]
0x18001915b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001915e  mov     rax, [rdi+60h]
0x180019162  mov     [rbp+57h+var_58], rax
0x180019166  mov     rax, [rdi+58h]
0x18001916a  mov     [rbp+57h+var_50], rax
0x18001916e  mov     eax, [rdi+50h]
0x180019171  mov     [rbp+57h+arg_8], eax
0x180019174  mov     rax, [rdi+48h]
0x180019178  mov     [rbp+57h+var_48], rax
0x18001917c  mov     eax, [rdi+20h]
0x18001917f  mov     dword ptr [rbp+57h+arg_10], eax
0x180019182  mov     rax, [rdi+18h]
0x180019186  mov     [rbp+57h+var_40], rax
0x18001918a  mov     eax, [rdi]
0x18001918c  mov     [rbp+57h+arg_18], eax
0x18001918f  mov     rax, [rdi+80h]
0x180019196  mov     [rbp+57h+var_38], rax
0x18001919a  mov     eax, [rdi+40h]
0x18001919d  mov     [rbp+57h+var_70], eax
0x1800191a0  mov     rax, [rdi+38h]
0x1800191a4  mov     [rbp+57h+var_30], rax
0x1800191a8  mov     eax, [rdi+8]
0x1800191ab  mov     [rbp+57h+var_6C], eax
0x1800191ae  mov     eax, 1000000h
0x1800191b3  mov     [rbp+57h+var_28], rax
0x1800191b7  mov     [rbp+57h+var_20], rax
0x1800191bb  lea     rax, [rbp+57h+var_68]
0x1800191bf  mov     [rsp+110h+var_78], rax
0x1800191c7  lea     rax, [rbp+57h+var_60]
0x1800191cb  mov     [rsp+110h+var_80], rax
0x1800191d3  lea     rax, [rbp+57h+SRWLock]
0x1800191d7  mov     [rsp+110h+var_88], rax
0x1800191df  lea     rax, [rbp+57h+var_58]
0x1800191e3  mov     [rsp+110h+var_90], rax
0x1800191eb  lea     rax, [rbp+57h+var_50]
0x1800191ef  mov     [rsp+110h+var_98], rax
0x1800191f4  lea     rax, [rbp+57h+arg_8]
0x1800191f8  mov     [rsp+110h+var_A0], rax
0x1800191fd  lea     rax, [rbp+57h+var_48]
0x180019201  mov     [rsp+110h+var_A8], rax
0x180019206  lea     rax, [rbp+57h+arg_10]
0x18001920a  mov     [rsp+110h+var_B0], rax
0x18001920f  lea     rax, [rbp+57h+var_40]
0x180019213  mov     [rsp+110h+var_B8], rax
0x180019218  lea     rax, [rbp+57h+arg_18]
0x18001921c  mov     [rsp+110h+var_C0], rax
0x180019221  lea     rax, [rbp+57h+var_38]
0x180019225  mov     [rsp+110h+var_C8], rax
0x18001922a  lea     rax, [rbp+57h+var_70]
0x18001922e  mov     [rsp+110h+var_D0], rax
0x180019233  lea     rax, [rbp+57h+var_30]
0x180019237  mov     [rsp+110h+var_D8], rax
0x18001923c  lea     rax, [rbp+57h+var_6C]
0x180019240  mov     [rsp+110h+var_E0], rax
0x180019245  lea     rax, [rbp+57h+var_28]
0x180019249  mov     [rsp+110h+var_E8], rax
0x18001924e  lea     rax, [rbp+57h+var_20]
0x180019252  mov     [rsp+110h+var_F0], rax
0x180019257  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001925c  jmp     loc_180019311
0x180019261  lea     rdx, [rbp+57h+SRWLock]
0x180019265  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001926a  mov     rax, [rbx+110h]
0x180019271  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019275  mov     dword ptr [rax], 2
0x18001927b  test    rcx, rcx
0x18001927e  jz      short loc_18001928C
0x180019280  call    cs:__imp_ReleaseSRWLockExclusive
0x180019287  nop     dword ptr [rax+rax+00h]
0x18001928c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019291  mov     rdi, rax
0x180019294  mov     ecx, [rax]
0x180019296  cmp     ecx, 5
0x180019299  jbe     short loc_180019311
0x18001929b  mov     rax, [rax+18h]
0x18001929f  mov     rdx, 400000000000h
0x1800192a9  mov     rcx, [rdi+10h]
0x1800192ad  test    rdx, rcx
0x1800192b0  jz      short loc_180019311
0x1800192b2  mov     rcx, rax
0x1800192b5  and     rcx, rdx
0x1800192b8  cmp     rcx, rax
0x1800192bb  jnz     short loc_180019311
0x1800192bd  call    cs:__imp_GetCurrentThreadId
0x1800192c4  nop     dword ptr [rax+rax+00h]
0x1800192c9  mov     r8, [rbx+110h]
0x1800192d0  lea     rdx, word_1800689F2
0x1800192d7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800192da  mov     rcx, rdi
0x1800192dd  mov     eax, [r8+48h]
0x1800192e1  add     r8, 8
0x1800192e5  mov     [rbp+57h+arg_8], eax
0x1800192e8  mov     eax, 1000000h
0x1800192ed  mov     [rbp+57h+arg_10], rax
0x1800192f1  lea     rax, [rbp+57h+SRWLock]
0x1800192f5  mov     [rsp+110h+var_E0], rax
0x1800192fa  lea     rax, [rbp+57h+arg_8]
0x1800192fe  mov     [rsp+110h+var_E8], rax
0x180019303  lea     rax, [rbp+57h+arg_10]
0x180019307  mov     [rsp+110h+var_F0], rax
0x18001930c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019311  mov     rcx, rbx
0x180019314  add     rsp, 100h
0x18001931b  pop     rdi
0x18001931c  pop     rbx
0x18001931d  pop     rbp
0x18001931e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
