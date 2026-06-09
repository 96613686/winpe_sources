# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::StopActivity(void)

- ea: `0x180011320`
- end: `0x180011613`
- name: `?StopActivity@ComputeStorage_HcsExportLayer@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180011320`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001155d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001155d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011596`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer *this)
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
        (int)&dword_1800544D4,
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
        (int)&dword_18005462C,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLayer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011320  mov     [rsp-8+arg_8], rbx
0x180011325  mov     [rsp-8+arg_10], rdi
0x18001132a  push    rbp
0x18001132b  mov     rbp, rsp
0x18001132e  sub     rsp, 140h
0x180011335  mov     rbx, rcx
0x180011338  mov     rdi, [rcx+110h]
0x18001133f  mov     eax, [rdi+48h]
0x180011342  test    eax, eax
0x180011344  jns     loc_180011536
0x18001134a  add     rdi, 50h ; 'P'
0x18001134e  cmp     eax, [rdi+8]
0x180011351  jnz     loc_180011536
0x180011357  test    rdi, rdi
0x18001135a  jz      loc_180011536
0x180011360  mov     [rbp+SRWLock], 0
0x180011368  lea     rdx, [rbp+SRWLock]
0x18001136c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011371  mov     rax, [rbx+110h]
0x180011378  mov     dword ptr [rax], 2
0x18001137e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011382  test    rcx, rcx
0x180011385  jz      short loc_180011393
0x180011387  call    cs:__imp_ReleaseSRWLockExclusive
0x18001138e  nop     dword ptr [rax+rax+00h]
0x180011393  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180011398  mov     r9, [rax+8]
0x18001139c  mov     eax, [r9]
0x18001139f  cmp     eax, 4
0x1800113a2  jbe     loc_1800115EA
0x1800113a8  mov     rdx, [r9+18h]
0x1800113ac  mov     rax, [r9+10h]
0x1800113b0  mov     ecx, 20040h
0x1800113b5  test    rcx, rax
0x1800113b8  jz      loc_1800115EA
0x1800113be  mov     rax, rdx
0x1800113c1  and     rax, rcx
0x1800113c4  cmp     rax, rdx
0x1800113c7  jnz     loc_1800115EA
0x1800113cd  mov     rax, [rdi+30h]
0x1800113d1  mov     [rbp+var_50], rax
0x1800113d5  mov     eax, [rdi+44h]
0x1800113d8  mov     dword ptr [rbp+var_78+4], eax
0x1800113db  mov     eax, [rdi+10h]
0x1800113de  mov     dword ptr [rbp+var_70], eax
0x1800113e1  mov     rax, [rdi+78h]
0x1800113e5  mov     [rbp+var_48], rax
0x1800113e9  mov     rax, [rdi+70h]
0x1800113ed  mov     [rbp+var_40], rax
0x1800113f1  mov     eax, [rdi+68h]
0x1800113f4  mov     dword ptr [rbp+var_70+4], eax
0x1800113f7  mov     rax, [rdi+60h]
0x1800113fb  mov     [rbp+var_38], rax
0x1800113ff  mov     rax, [rdi+58h]
0x180011403  mov     [rbp+var_30], rax
0x180011407  mov     eax, [rdi+50h]
0x18001140a  mov     dword ptr [rbp+var_68], eax
0x18001140d  mov     rax, [rdi+48h]
0x180011411  mov     [rbp+var_28], rax
0x180011415  mov     eax, [rdi+20h]
0x180011418  mov     dword ptr [rbp+var_68+4], eax
0x18001141b  mov     rax, [rdi+18h]
0x18001141f  mov     [rbp+var_20], rax
0x180011423  mov     eax, [rdi]
0x180011425  mov     [rbp+var_60], eax
0x180011428  mov     rax, [rdi+80h]
0x18001142f  mov     [rbp+var_18], rax
0x180011433  mov     eax, [rdi+40h]
0x180011436  mov     dword ptr [rbp+var_78], eax
0x180011439  mov     rax, [rdi+38h]
0x18001143d  mov     [rbp+var_10], rax
0x180011441  mov     eax, [rdi+8]
0x180011444  mov     dword ptr [rbp+SRWLock], eax
0x180011447  mov     [rbp+var_8], 1000000h
0x18001144f  mov     [rbp+var_58], 0
0x180011457  mov     r8, [rbx+110h]
0x18001145e  add     r8, 8; int
0x180011462  lea     rax, [rbp+var_50]
0x180011466  mov     [rsp+140h+var_90], rax; __int64
0x18001146e  lea     rax, [rbp+var_78+4]
0x180011472  mov     [rsp+140h+var_98], rax; __int64
0x18001147a  lea     rax, [rbp+var_70]
0x18001147e  mov     [rsp+140h+var_A0], rax; __int64
0x180011486  lea     rax, [rbp+var_48]
0x18001148a  mov     [rsp+140h+var_A8], rax; __int64
0x180011492  lea     rax, [rbp+var_40]
0x180011496  mov     [rsp+140h+var_B0], rax; __int64
0x18001149e  lea     rax, [rbp+var_70+4]
0x1800114a2  mov     [rsp+140h+var_B8], rax; __int64
0x1800114aa  lea     rax, [rbp+var_38]
0x1800114ae  mov     [rsp+140h+var_C0], rax; __int64
0x1800114b6  lea     rax, [rbp+var_30]
0x1800114ba  mov     [rsp+140h+var_C8], rax; __int64
0x1800114bf  lea     rax, [rbp+var_68]
0x1800114c3  mov     [rsp+140h+var_D0], rax; __int64
0x1800114c8  lea     rax, [rbp+var_28]
0x1800114cc  mov     [rsp+140h+var_D8], rax; __int64
0x1800114d1  lea     rax, [rbp+var_68+4]
0x1800114d5  mov     [rsp+140h+var_E0], rax; __int64
0x1800114da  lea     rax, [rbp+var_20]
0x1800114de  mov     [rsp+140h+var_E8], rax; __int64
0x1800114e3  lea     rax, [rbp+var_60]
0x1800114e7  mov     [rsp+140h+var_F0], rax; __int64
0x1800114ec  lea     rax, [rbp+var_18]
0x1800114f0  mov     [rsp+140h+var_F8], rax; __int64
0x1800114f5  lea     rax, [rbp+var_78]
0x1800114f9  mov     [rsp+140h+var_100], rax; __int64
0x1800114fe  lea     rax, [rbp+var_10]
0x180011502  mov     [rsp+140h+var_108], rax; __int64
0x180011507  lea     rax, [rbp+SRWLock]
0x18001150b  mov     [rsp+140h+var_110], rax; __int64
0x180011510  lea     rax, [rbp+var_8]
0x180011514  mov     [rsp+140h+var_118], rax; __int64
0x180011519  lea     rax, [rbp+var_58]
0x18001151d  mov     [rsp+140h+var_120], rax; __int64
0x180011522  lea     rdx, dword_1800544D4; int
0x180011529  mov     rcx, r9; int
0x18001152c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011531  jmp     loc_1800115EA
0x180011536  mov     [rbp+SRWLock], 0
0x18001153e  lea     rdx, [rbp+SRWLock]
0x180011542  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011547  mov     rax, [rbx+110h]
0x18001154e  mov     dword ptr [rax], 2
0x180011554  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011558  test    rcx, rcx
0x18001155b  jz      short loc_180011569
0x18001155d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011564  nop     dword ptr [rax+rax+00h]
0x180011569  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18001156e  mov     rdi, [rax+8]
0x180011572  mov     eax, [rdi]
0x180011574  cmp     eax, 4
0x180011577  jbe     short loc_1800115EA
0x180011579  mov     rdx, [rdi+18h]
0x18001157d  mov     rax, [rdi+10h]
0x180011581  mov     ecx, 20040h
0x180011586  test    rcx, rax
0x180011589  jz      short loc_1800115EA
0x18001158b  mov     rax, rdx
0x18001158e  and     rax, rcx
0x180011591  cmp     rax, rdx
0x180011594  jnz     short loc_1800115EA
0x180011596  call    cs:__imp_GetCurrentThreadId
0x18001159d  nop     dword ptr [rax+rax+00h]
0x1800115a2  mov     dword ptr [rbp+SRWLock], eax
0x1800115a5  mov     r8, [rbx+110h]
0x1800115ac  mov     eax, [r8+48h]
0x1800115b0  mov     dword ptr [rbp+var_78], eax
0x1800115b3  mov     [rbp+var_58], 0
0x1800115bb  add     r8, 8
0x1800115bf  lea     rax, [rbp+SRWLock]
0x1800115c3  mov     [rsp+140h+var_110], rax
0x1800115c8  lea     rax, [rbp+var_78]
0x1800115cc  mov     [rsp+140h+var_118], rax
0x1800115d1  lea     rax, [rbp+var_58]
0x1800115d5  mov     [rsp+140h+var_120], rax
0x1800115da  lea     rdx, dword_18005462C
0x1800115e1  mov     rcx, rdi
0x1800115e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800115e9  nop
0x1800115ea  lea     rcx, [rbx+120h]; this
0x1800115f1  cmp     dword ptr [rcx+18h], 0
0x1800115f5  jz      short loc_1800115FD
0x1800115f7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800115fc  nop
0x1800115fd  lea     r11, [rsp+140h+var_s0]
0x180011605  mov     rbx, [r11+18h]
0x180011609  mov     rdi, [r11+20h]
0x18001160d  mov     rsp, r11
0x180011610  pop     rbp
0x180011611  retn
```
