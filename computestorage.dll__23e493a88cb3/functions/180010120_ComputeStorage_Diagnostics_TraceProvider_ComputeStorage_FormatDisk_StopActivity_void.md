# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::StopActivity(void)

- ea: `0x180010120`
- end: `0x180010413`
- name: `?StopActivity@ComputeStorage_FormatDisk@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180010120`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010187`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001035d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010187`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001035d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010396`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010396`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk *this)
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
        (int)&byte_1800541FD,
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
        (int)&unk_180054848,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010120  mov     [rsp-8+arg_8], rbx
0x180010125  mov     [rsp-8+arg_10], rdi
0x18001012a  push    rbp
0x18001012b  mov     rbp, rsp
0x18001012e  sub     rsp, 140h
0x180010135  mov     rbx, rcx
0x180010138  mov     rdi, [rcx+110h]
0x18001013f  mov     eax, [rdi+48h]
0x180010142  test    eax, eax
0x180010144  jns     loc_180010336
0x18001014a  add     rdi, 50h ; 'P'
0x18001014e  cmp     eax, [rdi+8]
0x180010151  jnz     loc_180010336
0x180010157  test    rdi, rdi
0x18001015a  jz      loc_180010336
0x180010160  mov     [rbp+SRWLock], 0
0x180010168  lea     rdx, [rbp+SRWLock]
0x18001016c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010171  mov     rax, [rbx+110h]
0x180010178  mov     dword ptr [rax], 2
0x18001017e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010182  test    rcx, rcx
0x180010185  jz      short loc_180010193
0x180010187  call    cs:__imp_ReleaseSRWLockExclusive
0x18001018e  nop     dword ptr [rax+rax+00h]
0x180010193  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180010198  mov     r9, [rax+8]
0x18001019c  mov     eax, [r9]
0x18001019f  cmp     eax, 4
0x1800101a2  jbe     loc_1800103EA
0x1800101a8  mov     rdx, [r9+18h]
0x1800101ac  mov     rax, [r9+10h]
0x1800101b0  mov     ecx, 20040h
0x1800101b5  test    rcx, rax
0x1800101b8  jz      loc_1800103EA
0x1800101be  mov     rax, rdx
0x1800101c1  and     rax, rcx
0x1800101c4  cmp     rax, rdx
0x1800101c7  jnz     loc_1800103EA
0x1800101cd  mov     rax, [rdi+30h]
0x1800101d1  mov     [rbp+var_50], rax
0x1800101d5  mov     eax, [rdi+44h]
0x1800101d8  mov     dword ptr [rbp+var_78+4], eax
0x1800101db  mov     eax, [rdi+10h]
0x1800101de  mov     dword ptr [rbp+var_70], eax
0x1800101e1  mov     rax, [rdi+78h]
0x1800101e5  mov     [rbp+var_48], rax
0x1800101e9  mov     rax, [rdi+70h]
0x1800101ed  mov     [rbp+var_40], rax
0x1800101f1  mov     eax, [rdi+68h]
0x1800101f4  mov     dword ptr [rbp+var_70+4], eax
0x1800101f7  mov     rax, [rdi+60h]
0x1800101fb  mov     [rbp+var_38], rax
0x1800101ff  mov     rax, [rdi+58h]
0x180010203  mov     [rbp+var_30], rax
0x180010207  mov     eax, [rdi+50h]
0x18001020a  mov     dword ptr [rbp+var_68], eax
0x18001020d  mov     rax, [rdi+48h]
0x180010211  mov     [rbp+var_28], rax
0x180010215  mov     eax, [rdi+20h]
0x180010218  mov     dword ptr [rbp+var_68+4], eax
0x18001021b  mov     rax, [rdi+18h]
0x18001021f  mov     [rbp+var_20], rax
0x180010223  mov     eax, [rdi]
0x180010225  mov     [rbp+var_60], eax
0x180010228  mov     rax, [rdi+80h]
0x18001022f  mov     [rbp+var_18], rax
0x180010233  mov     eax, [rdi+40h]
0x180010236  mov     dword ptr [rbp+var_78], eax
0x180010239  mov     rax, [rdi+38h]
0x18001023d  mov     [rbp+var_10], rax
0x180010241  mov     eax, [rdi+8]
0x180010244  mov     dword ptr [rbp+SRWLock], eax
0x180010247  mov     [rbp+var_8], 1000000h
0x18001024f  mov     [rbp+var_58], 0
0x180010257  mov     r8, [rbx+110h]
0x18001025e  add     r8, 8; int
0x180010262  lea     rax, [rbp+var_50]
0x180010266  mov     [rsp+140h+var_90], rax; __int64
0x18001026e  lea     rax, [rbp+var_78+4]
0x180010272  mov     [rsp+140h+var_98], rax; __int64
0x18001027a  lea     rax, [rbp+var_70]
0x18001027e  mov     [rsp+140h+var_A0], rax; __int64
0x180010286  lea     rax, [rbp+var_48]
0x18001028a  mov     [rsp+140h+var_A8], rax; __int64
0x180010292  lea     rax, [rbp+var_40]
0x180010296  mov     [rsp+140h+var_B0], rax; __int64
0x18001029e  lea     rax, [rbp+var_70+4]
0x1800102a2  mov     [rsp+140h+var_B8], rax; __int64
0x1800102aa  lea     rax, [rbp+var_38]
0x1800102ae  mov     [rsp+140h+var_C0], rax; __int64
0x1800102b6  lea     rax, [rbp+var_30]
0x1800102ba  mov     [rsp+140h+var_C8], rax; __int64
0x1800102bf  lea     rax, [rbp+var_68]
0x1800102c3  mov     [rsp+140h+var_D0], rax; __int64
0x1800102c8  lea     rax, [rbp+var_28]
0x1800102cc  mov     [rsp+140h+var_D8], rax; __int64
0x1800102d1  lea     rax, [rbp+var_68+4]
0x1800102d5  mov     [rsp+140h+var_E0], rax; __int64
0x1800102da  lea     rax, [rbp+var_20]
0x1800102de  mov     [rsp+140h+var_E8], rax; __int64
0x1800102e3  lea     rax, [rbp+var_60]
0x1800102e7  mov     [rsp+140h+var_F0], rax; __int64
0x1800102ec  lea     rax, [rbp+var_18]
0x1800102f0  mov     [rsp+140h+var_F8], rax; __int64
0x1800102f5  lea     rax, [rbp+var_78]
0x1800102f9  mov     [rsp+140h+var_100], rax; __int64
0x1800102fe  lea     rax, [rbp+var_10]
0x180010302  mov     [rsp+140h+var_108], rax; __int64
0x180010307  lea     rax, [rbp+SRWLock]
0x18001030b  mov     [rsp+140h+var_110], rax; __int64
0x180010310  lea     rax, [rbp+var_8]
0x180010314  mov     [rsp+140h+var_118], rax; __int64
0x180010319  lea     rax, [rbp+var_58]
0x18001031d  mov     [rsp+140h+var_120], rax; __int64
0x180010322  lea     rdx, byte_1800541FD; int
0x180010329  mov     rcx, r9; int
0x18001032c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010331  jmp     loc_1800103EA
0x180010336  mov     [rbp+SRWLock], 0
0x18001033e  lea     rdx, [rbp+SRWLock]
0x180010342  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010347  mov     rax, [rbx+110h]
0x18001034e  mov     dword ptr [rax], 2
0x180010354  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010358  test    rcx, rcx
0x18001035b  jz      short loc_180010369
0x18001035d  call    cs:__imp_ReleaseSRWLockExclusive
0x180010364  nop     dword ptr [rax+rax+00h]
0x180010369  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18001036e  mov     rdi, [rax+8]
0x180010372  mov     eax, [rdi]
0x180010374  cmp     eax, 4
0x180010377  jbe     short loc_1800103EA
0x180010379  mov     rdx, [rdi+18h]
0x18001037d  mov     rax, [rdi+10h]
0x180010381  mov     ecx, 20040h
0x180010386  test    rcx, rax
0x180010389  jz      short loc_1800103EA
0x18001038b  mov     rax, rdx
0x18001038e  and     rax, rcx
0x180010391  cmp     rax, rdx
0x180010394  jnz     short loc_1800103EA
0x180010396  call    cs:__imp_GetCurrentThreadId
0x18001039d  nop     dword ptr [rax+rax+00h]
0x1800103a2  mov     dword ptr [rbp+SRWLock], eax
0x1800103a5  mov     r8, [rbx+110h]
0x1800103ac  mov     eax, [r8+48h]
0x1800103b0  mov     dword ptr [rbp+var_78], eax
0x1800103b3  mov     [rbp+var_58], 0
0x1800103bb  add     r8, 8
0x1800103bf  lea     rax, [rbp+SRWLock]
0x1800103c3  mov     [rsp+140h+var_110], rax
0x1800103c8  lea     rax, [rbp+var_78]
0x1800103cc  mov     [rsp+140h+var_118], rax
0x1800103d1  lea     rax, [rbp+var_58]
0x1800103d5  mov     [rsp+140h+var_120], rax
0x1800103da  lea     rdx, unk_180054848
0x1800103e1  mov     rcx, rdi
0x1800103e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800103e9  nop
0x1800103ea  lea     rcx, [rbx+120h]; this
0x1800103f1  cmp     dword ptr [rcx+18h], 0
0x1800103f5  jz      short loc_1800103FD
0x1800103f7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800103fc  nop
0x1800103fd  lea     r11, [rsp+140h+var_s0]
0x180010405  mov     rbx, [r11+18h]
0x180010409  mov     rdi, [r11+20h]
0x18001040d  mov     rsp, r11
0x180010410  pop     rbp
0x180010411  retn
```
