# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsAttachLayerStorageFilter::StopActivity(void)

- ea: `0x180010420`
- end: `0x180010713`
- name: `?StopActivity@ComputeStorage_HcsAttachLayerStorageFilter@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsAttachLayerStorageFilter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180010420`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010487`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001065d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010487`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001065d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010696`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsAttachLayerStorageFilter::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsAttachLayerStorageFilter *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v10; // [rsp+C8h] [rbp-78h] BYREF
  int v11; // [rsp+CCh] [rbp-74h] BYREF
  int v12; // [rsp+D0h] [rbp-70h] BYREF
  int v13; // [rsp+D4h] [rbp-6Ch] BYREF
  int v14; // [rsp+D8h] [rbp-68h] BYREF
  int v15; // [rsp+DCh] [rbp-64h] BYREF
  int v16; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+100h] [rbp-40h] BYREF
  __int64 v21; // [rsp+108h] [rbp-38h] BYREF
  __int64 v22; // [rsp+110h] [rbp-30h] BYREF
  __int64 v23; // [rsp+118h] [rbp-28h] BYREF
  __int64 v24; // [rsp+120h] [rbp-20h] BYREF
  __int64 v25; // [rsp+128h] [rbp-18h] BYREF
  __int64 v26; // [rsp+130h] [rbp-10h] BYREF
  __int64 v27; // [rsp+138h] [rbp-8h] BYREF

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
    v5 = *((_QWORD *)ComputeStorage::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x20040LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x20040LL) == *(_QWORD *)(v5 + 24) )
    {
      v18 = *((_QWORD *)v4 + 6);
      v11 = v4[17];
      v12 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v13 = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v14 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v10 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v27 = 0x1000000;
      v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&byte_180053BBB,
        *((_QWORD *)this + 34) + 8,
        v5,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&SRWLock,
        (const unsigned __int16 **)&v26,
        (__int64)&v10,
        (const unsigned __int16 **)&v25,
        (__int64)&v16,
        (__int64 **)&v24,
        (__int64)&v15,
        (const unsigned __int16 **)&v23,
        (__int64)&v14,
        (const unsigned __int16 **)&v22,
        (__int64 **)&v21,
        (__int64)&v13,
        (const unsigned __int16 **)&v20,
        (__int64 **)&v19,
        (__int64)&v12,
        (__int64)&v11,
        (const unsigned __int16 **)&v18);
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
    v6 = *((_QWORD *)ComputeStorage::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x20040LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x20040LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v10 = *(_DWORD *)(v7 + 72);
      v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (int)&unk_180053D20,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsAttachLayerStorageFilter *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010420  mov     [rsp-8+arg_8], rbx
0x180010425  mov     [rsp-8+arg_10], rdi
0x18001042a  push    rbp
0x18001042b  mov     rbp, rsp
0x18001042e  sub     rsp, 140h
0x180010435  mov     rbx, rcx
0x180010438  mov     rdi, [rcx+110h]
0x18001043f  mov     eax, [rdi+48h]
0x180010442  test    eax, eax
0x180010444  jns     loc_180010636
0x18001044a  add     rdi, 50h ; 'P'
0x18001044e  cmp     eax, [rdi+8]
0x180010451  jnz     loc_180010636
0x180010457  test    rdi, rdi
0x18001045a  jz      loc_180010636
0x180010460  mov     [rbp+SRWLock], 0
0x180010468  lea     rdx, [rbp+SRWLock]
0x18001046c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010471  mov     rax, [rbx+110h]
0x180010478  mov     dword ptr [rax], 2
0x18001047e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010482  test    rcx, rcx
0x180010485  jz      short loc_180010493
0x180010487  call    cs:__imp_ReleaseSRWLockExclusive
0x18001048e  nop     dword ptr [rax+rax+00h]
0x180010493  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180010498  mov     r9, [rax+8]
0x18001049c  mov     eax, [r9]
0x18001049f  cmp     eax, 4
0x1800104a2  jbe     loc_1800106EA
0x1800104a8  mov     rdx, [r9+18h]
0x1800104ac  mov     rax, [r9+10h]
0x1800104b0  mov     ecx, 20040h
0x1800104b5  test    rcx, rax
0x1800104b8  jz      loc_1800106EA
0x1800104be  mov     rax, rdx
0x1800104c1  and     rax, rcx
0x1800104c4  cmp     rax, rdx
0x1800104c7  jnz     loc_1800106EA
0x1800104cd  mov     rax, [rdi+30h]
0x1800104d1  mov     [rbp+var_50], rax
0x1800104d5  mov     eax, [rdi+44h]
0x1800104d8  mov     dword ptr [rbp+var_78+4], eax
0x1800104db  mov     eax, [rdi+10h]
0x1800104de  mov     dword ptr [rbp+var_70], eax
0x1800104e1  mov     rax, [rdi+78h]
0x1800104e5  mov     [rbp+var_48], rax
0x1800104e9  mov     rax, [rdi+70h]
0x1800104ed  mov     [rbp+var_40], rax
0x1800104f1  mov     eax, [rdi+68h]
0x1800104f4  mov     dword ptr [rbp+var_70+4], eax
0x1800104f7  mov     rax, [rdi+60h]
0x1800104fb  mov     [rbp+var_38], rax
0x1800104ff  mov     rax, [rdi+58h]
0x180010503  mov     [rbp+var_30], rax
0x180010507  mov     eax, [rdi+50h]
0x18001050a  mov     dword ptr [rbp+var_68], eax
0x18001050d  mov     rax, [rdi+48h]
0x180010511  mov     [rbp+var_28], rax
0x180010515  mov     eax, [rdi+20h]
0x180010518  mov     dword ptr [rbp+var_68+4], eax
0x18001051b  mov     rax, [rdi+18h]
0x18001051f  mov     [rbp+var_20], rax
0x180010523  mov     eax, [rdi]
0x180010525  mov     [rbp+var_60], eax
0x180010528  mov     rax, [rdi+80h]
0x18001052f  mov     [rbp+var_18], rax
0x180010533  mov     eax, [rdi+40h]
0x180010536  mov     dword ptr [rbp+var_78], eax
0x180010539  mov     rax, [rdi+38h]
0x18001053d  mov     [rbp+var_10], rax
0x180010541  mov     eax, [rdi+8]
0x180010544  mov     dword ptr [rbp+SRWLock], eax
0x180010547  mov     [rbp+var_8], 1000000h
0x18001054f  mov     [rbp+var_58], 0
0x180010557  mov     r8, [rbx+110h]
0x18001055e  add     r8, 8; int
0x180010562  lea     rax, [rbp+var_50]
0x180010566  mov     [rsp+140h+var_90], rax; __int64
0x18001056e  lea     rax, [rbp+var_78+4]
0x180010572  mov     [rsp+140h+var_98], rax; __int64
0x18001057a  lea     rax, [rbp+var_70]
0x18001057e  mov     [rsp+140h+var_A0], rax; __int64
0x180010586  lea     rax, [rbp+var_48]
0x18001058a  mov     [rsp+140h+var_A8], rax; __int64
0x180010592  lea     rax, [rbp+var_40]
0x180010596  mov     [rsp+140h+var_B0], rax; __int64
0x18001059e  lea     rax, [rbp+var_70+4]
0x1800105a2  mov     [rsp+140h+var_B8], rax; __int64
0x1800105aa  lea     rax, [rbp+var_38]
0x1800105ae  mov     [rsp+140h+var_C0], rax; __int64
0x1800105b6  lea     rax, [rbp+var_30]
0x1800105ba  mov     [rsp+140h+var_C8], rax; __int64
0x1800105bf  lea     rax, [rbp+var_68]
0x1800105c3  mov     [rsp+140h+var_D0], rax; __int64
0x1800105c8  lea     rax, [rbp+var_28]
0x1800105cc  mov     [rsp+140h+var_D8], rax; __int64
0x1800105d1  lea     rax, [rbp+var_68+4]
0x1800105d5  mov     [rsp+140h+var_E0], rax; __int64
0x1800105da  lea     rax, [rbp+var_20]
0x1800105de  mov     [rsp+140h+var_E8], rax; __int64
0x1800105e3  lea     rax, [rbp+var_60]
0x1800105e7  mov     [rsp+140h+var_F0], rax; __int64
0x1800105ec  lea     rax, [rbp+var_18]
0x1800105f0  mov     [rsp+140h+var_F8], rax; __int64
0x1800105f5  lea     rax, [rbp+var_78]
0x1800105f9  mov     [rsp+140h+var_100], rax; __int64
0x1800105fe  lea     rax, [rbp+var_10]
0x180010602  mov     [rsp+140h+var_108], rax; __int64
0x180010607  lea     rax, [rbp+SRWLock]
0x18001060b  mov     [rsp+140h+var_110], rax; __int64
0x180010610  lea     rax, [rbp+var_8]
0x180010614  mov     [rsp+140h+var_118], rax; __int64
0x180010619  lea     rax, [rbp+var_58]
0x18001061d  mov     [rsp+140h+var_120], rax; __int64
0x180010622  lea     rdx, byte_180053BBB; int
0x180010629  mov     rcx, r9; int
0x18001062c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010631  jmp     loc_1800106EA
0x180010636  mov     [rbp+SRWLock], 0
0x18001063e  lea     rdx, [rbp+SRWLock]
0x180010642  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010647  mov     rax, [rbx+110h]
0x18001064e  mov     dword ptr [rax], 2
0x180010654  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010658  test    rcx, rcx
0x18001065b  jz      short loc_180010669
0x18001065d  call    cs:__imp_ReleaseSRWLockExclusive
0x180010664  nop     dword ptr [rax+rax+00h]
0x180010669  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18001066e  mov     rdi, [rax+8]
0x180010672  mov     eax, [rdi]
0x180010674  cmp     eax, 4
0x180010677  jbe     short loc_1800106EA
0x180010679  mov     rdx, [rdi+18h]
0x18001067d  mov     rax, [rdi+10h]
0x180010681  mov     ecx, 20040h
0x180010686  test    rcx, rax
0x180010689  jz      short loc_1800106EA
0x18001068b  mov     rax, rdx
0x18001068e  and     rax, rcx
0x180010691  cmp     rax, rdx
0x180010694  jnz     short loc_1800106EA
0x180010696  call    cs:__imp_GetCurrentThreadId
0x18001069d  nop     dword ptr [rax+rax+00h]
0x1800106a2  mov     dword ptr [rbp+SRWLock], eax
0x1800106a5  mov     r8, [rbx+110h]
0x1800106ac  mov     eax, [r8+48h]
0x1800106b0  mov     dword ptr [rbp+var_78], eax
0x1800106b3  mov     [rbp+var_58], 0
0x1800106bb  add     r8, 8
0x1800106bf  lea     rax, [rbp+SRWLock]
0x1800106c3  mov     [rsp+140h+var_110], rax
0x1800106c8  lea     rax, [rbp+var_78]
0x1800106cc  mov     [rsp+140h+var_118], rax
0x1800106d1  lea     rax, [rbp+var_58]
0x1800106d5  mov     [rsp+140h+var_120], rax
0x1800106da  lea     rdx, unk_180053D20
0x1800106e1  mov     rcx, rdi
0x1800106e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800106e9  nop
0x1800106ea  lea     rcx, [rbx+120h]; this
0x1800106f1  cmp     dword ptr [rcx+18h], 0
0x1800106f5  jz      short loc_1800106FD
0x1800106f7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800106fc  nop
0x1800106fd  lea     r11, [rsp+140h+var_s0]
0x180010705  mov     rbx, [r11+18h]
0x180010709  mov     rdi, [r11+20h]
0x18001070d  mov     rsp, r11
0x180010710  pop     rbp
0x180010711  retn
```
