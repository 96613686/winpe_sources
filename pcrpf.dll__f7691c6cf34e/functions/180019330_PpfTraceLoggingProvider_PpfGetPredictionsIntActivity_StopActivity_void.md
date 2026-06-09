# PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StopActivity(void)

- ea: `0x180019330`
- end: `0x1800195c3`
- name: `?StopActivity@PpfGetPredictionsIntActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180019330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001938a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019520`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001938a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001955d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001955d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfGetPredictionsIntActivity::StopActivity(
        PpfTraceLoggingProvider::PpfGetPredictionsIntActivity *this)
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
          (__int64)&word_1800688BE,
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
          (__int64)byte_1800685E3,
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
0x180019330  push    rbp
0x180019332  push    rbx
0x180019333  push    rdi
0x180019334  lea     rbp, [rsp-47h]
0x180019339  sub     rsp, 100h
0x180019340  mov     rdi, [rcx+110h]
0x180019347  mov     rbx, rcx
0x18001934a  mov     eax, [rdi+48h]
0x18001934d  test    eax, eax
0x18001934f  jns     loc_180019501
0x180019355  add     rdi, 50h ; 'P'
0x180019359  cmp     eax, [rdi+8]
0x18001935c  jnz     loc_180019501
0x180019362  test    rdi, rdi
0x180019365  jz      loc_180019501
0x18001936b  lea     rdx, [rbp+57h+SRWLock]
0x18001936f  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019374  mov     rax, [rbx+110h]
0x18001937b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001937f  mov     dword ptr [rax], 2
0x180019385  test    rcx, rcx
0x180019388  jz      short loc_180019396
0x18001938a  call    cs:__imp_ReleaseSRWLockExclusive
0x180019391  nop     dword ptr [rax+rax+00h]
0x180019396  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001939b  mov     r9, rax
0x18001939e  mov     ecx, [rax]
0x1800193a0  cmp     ecx, 5
0x1800193a3  jbe     loc_1800195B1
0x1800193a9  mov     rax, [rax+18h]
0x1800193ad  mov     rdx, 400000000000h
0x1800193b7  mov     rcx, [r9+10h]
0x1800193bb  test    rdx, rcx
0x1800193be  jz      loc_1800195B1
0x1800193c4  mov     rcx, rax
0x1800193c7  and     rcx, rdx
0x1800193ca  cmp     rcx, rax
0x1800193cd  jnz     loc_1800195B1
0x1800193d3  mov     rax, [rdi+78h]
0x1800193d7  lea     rdx, word_1800688BE
0x1800193de  mov     r8, [rbx+110h]
0x1800193e5  mov     rcx, r9
0x1800193e8  mov     [rbp+57h+var_68], rax
0x1800193ec  add     r8, 8
0x1800193f0  mov     rax, [rdi+70h]
0x1800193f4  mov     [rbp+57h+var_60], rax
0x1800193f8  mov     eax, [rdi+68h]
0x1800193fb  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800193fe  mov     rax, [rdi+60h]
0x180019402  mov     [rbp+57h+var_58], rax
0x180019406  mov     rax, [rdi+58h]
0x18001940a  mov     [rbp+57h+var_50], rax
0x18001940e  mov     eax, [rdi+50h]
0x180019411  mov     [rbp+57h+arg_8], eax
0x180019414  mov     rax, [rdi+48h]
0x180019418  mov     [rbp+57h+var_48], rax
0x18001941c  mov     eax, [rdi+20h]
0x18001941f  mov     dword ptr [rbp+57h+arg_10], eax
0x180019422  mov     rax, [rdi+18h]
0x180019426  mov     [rbp+57h+var_40], rax
0x18001942a  mov     eax, [rdi]
0x18001942c  mov     [rbp+57h+arg_18], eax
0x18001942f  mov     rax, [rdi+80h]
0x180019436  mov     [rbp+57h+var_38], rax
0x18001943a  mov     eax, [rdi+40h]
0x18001943d  mov     [rbp+57h+var_70], eax
0x180019440  mov     rax, [rdi+38h]
0x180019444  mov     [rbp+57h+var_30], rax
0x180019448  mov     eax, [rdi+8]
0x18001944b  mov     [rbp+57h+var_6C], eax
0x18001944e  mov     eax, 1000000h
0x180019453  mov     [rbp+57h+var_28], rax
0x180019457  mov     [rbp+57h+var_20], rax
0x18001945b  lea     rax, [rbp+57h+var_68]
0x18001945f  mov     [rsp+110h+var_78], rax
0x180019467  lea     rax, [rbp+57h+var_60]
0x18001946b  mov     [rsp+110h+var_80], rax
0x180019473  lea     rax, [rbp+57h+SRWLock]
0x180019477  mov     [rsp+110h+var_88], rax
0x18001947f  lea     rax, [rbp+57h+var_58]
0x180019483  mov     [rsp+110h+var_90], rax
0x18001948b  lea     rax, [rbp+57h+var_50]
0x18001948f  mov     [rsp+110h+var_98], rax
0x180019494  lea     rax, [rbp+57h+arg_8]
0x180019498  mov     [rsp+110h+var_A0], rax
0x18001949d  lea     rax, [rbp+57h+var_48]
0x1800194a1  mov     [rsp+110h+var_A8], rax
0x1800194a6  lea     rax, [rbp+57h+arg_10]
0x1800194aa  mov     [rsp+110h+var_B0], rax
0x1800194af  lea     rax, [rbp+57h+var_40]
0x1800194b3  mov     [rsp+110h+var_B8], rax
0x1800194b8  lea     rax, [rbp+57h+arg_18]
0x1800194bc  mov     [rsp+110h+var_C0], rax
0x1800194c1  lea     rax, [rbp+57h+var_38]
0x1800194c5  mov     [rsp+110h+var_C8], rax
0x1800194ca  lea     rax, [rbp+57h+var_70]
0x1800194ce  mov     [rsp+110h+var_D0], rax
0x1800194d3  lea     rax, [rbp+57h+var_30]
0x1800194d7  mov     [rsp+110h+var_D8], rax
0x1800194dc  lea     rax, [rbp+57h+var_6C]
0x1800194e0  mov     [rsp+110h+var_E0], rax
0x1800194e5  lea     rax, [rbp+57h+var_28]
0x1800194e9  mov     [rsp+110h+var_E8], rax
0x1800194ee  lea     rax, [rbp+57h+var_20]
0x1800194f2  mov     [rsp+110h+var_F0], rax
0x1800194f7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800194fc  jmp     loc_1800195B1
0x180019501  lea     rdx, [rbp+57h+SRWLock]
0x180019505  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001950a  mov     rax, [rbx+110h]
0x180019511  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019515  mov     dword ptr [rax], 2
0x18001951b  test    rcx, rcx
0x18001951e  jz      short loc_18001952C
0x180019520  call    cs:__imp_ReleaseSRWLockExclusive
0x180019527  nop     dword ptr [rax+rax+00h]
0x18001952c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019531  mov     rdi, rax
0x180019534  mov     ecx, [rax]
0x180019536  cmp     ecx, 5
0x180019539  jbe     short loc_1800195B1
0x18001953b  mov     rax, [rax+18h]
0x18001953f  mov     rdx, 400000000000h
0x180019549  mov     rcx, [rdi+10h]
0x18001954d  test    rdx, rcx
0x180019550  jz      short loc_1800195B1
0x180019552  mov     rcx, rax
0x180019555  and     rcx, rdx
0x180019558  cmp     rcx, rax
0x18001955b  jnz     short loc_1800195B1
0x18001955d  call    cs:__imp_GetCurrentThreadId
0x180019564  nop     dword ptr [rax+rax+00h]
0x180019569  mov     r8, [rbx+110h]
0x180019570  lea     rdx, byte_1800685E3
0x180019577  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001957a  mov     rcx, rdi
0x18001957d  mov     eax, [r8+48h]
0x180019581  add     r8, 8
0x180019585  mov     [rbp+57h+arg_8], eax
0x180019588  mov     eax, 1000000h
0x18001958d  mov     [rbp+57h+arg_10], rax
0x180019591  lea     rax, [rbp+57h+SRWLock]
0x180019595  mov     [rsp+110h+var_E0], rax
0x18001959a  lea     rax, [rbp+57h+arg_8]
0x18001959e  mov     [rsp+110h+var_E8], rax
0x1800195a3  lea     rax, [rbp+57h+arg_10]
0x1800195a7  mov     [rsp+110h+var_F0], rax
0x1800195ac  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800195b1  mov     rcx, rbx
0x1800195b4  add     rsp, 100h
0x1800195bb  pop     rdi
0x1800195bc  pop     rbx
0x1800195bd  pop     rbp
0x1800195be  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
