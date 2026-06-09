# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::StopActivity(void)

- ea: `0x180011620`
- end: `0x180011913`
- name: `?StopActivity@ComputeStorage_HcsExportLegacyWritableLayer@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180011620`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001185d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001185d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011896`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer *this)
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
        (int)&dword_180053FD4,
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
        (int)&byte_1800549AF,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsExportLegacyWritableLayer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011620  mov     [rsp-8+arg_8], rbx
0x180011625  mov     [rsp-8+arg_10], rdi
0x18001162a  push    rbp
0x18001162b  mov     rbp, rsp
0x18001162e  sub     rsp, 140h
0x180011635  mov     rbx, rcx
0x180011638  mov     rdi, [rcx+110h]
0x18001163f  mov     eax, [rdi+48h]
0x180011642  test    eax, eax
0x180011644  jns     loc_180011836
0x18001164a  add     rdi, 50h ; 'P'
0x18001164e  cmp     eax, [rdi+8]
0x180011651  jnz     loc_180011836
0x180011657  test    rdi, rdi
0x18001165a  jz      loc_180011836
0x180011660  mov     [rbp+SRWLock], 0
0x180011668  lea     rdx, [rbp+SRWLock]
0x18001166c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011671  mov     rax, [rbx+110h]
0x180011678  mov     dword ptr [rax], 2
0x18001167e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011682  test    rcx, rcx
0x180011685  jz      short loc_180011693
0x180011687  call    cs:__imp_ReleaseSRWLockExclusive
0x18001168e  nop     dword ptr [rax+rax+00h]
0x180011693  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180011698  mov     r9, [rax+8]
0x18001169c  mov     eax, [r9]
0x18001169f  cmp     eax, 4
0x1800116a2  jbe     loc_1800118EA
0x1800116a8  mov     rdx, [r9+18h]
0x1800116ac  mov     rax, [r9+10h]
0x1800116b0  mov     ecx, 20040h
0x1800116b5  test    rcx, rax
0x1800116b8  jz      loc_1800118EA
0x1800116be  mov     rax, rdx
0x1800116c1  and     rax, rcx
0x1800116c4  cmp     rax, rdx
0x1800116c7  jnz     loc_1800118EA
0x1800116cd  mov     rax, [rdi+30h]
0x1800116d1  mov     [rbp+var_50], rax
0x1800116d5  mov     eax, [rdi+44h]
0x1800116d8  mov     dword ptr [rbp+var_78+4], eax
0x1800116db  mov     eax, [rdi+10h]
0x1800116de  mov     dword ptr [rbp+var_70], eax
0x1800116e1  mov     rax, [rdi+78h]
0x1800116e5  mov     [rbp+var_48], rax
0x1800116e9  mov     rax, [rdi+70h]
0x1800116ed  mov     [rbp+var_40], rax
0x1800116f1  mov     eax, [rdi+68h]
0x1800116f4  mov     dword ptr [rbp+var_70+4], eax
0x1800116f7  mov     rax, [rdi+60h]
0x1800116fb  mov     [rbp+var_38], rax
0x1800116ff  mov     rax, [rdi+58h]
0x180011703  mov     [rbp+var_30], rax
0x180011707  mov     eax, [rdi+50h]
0x18001170a  mov     dword ptr [rbp+var_68], eax
0x18001170d  mov     rax, [rdi+48h]
0x180011711  mov     [rbp+var_28], rax
0x180011715  mov     eax, [rdi+20h]
0x180011718  mov     dword ptr [rbp+var_68+4], eax
0x18001171b  mov     rax, [rdi+18h]
0x18001171f  mov     [rbp+var_20], rax
0x180011723  mov     eax, [rdi]
0x180011725  mov     [rbp+var_60], eax
0x180011728  mov     rax, [rdi+80h]
0x18001172f  mov     [rbp+var_18], rax
0x180011733  mov     eax, [rdi+40h]
0x180011736  mov     dword ptr [rbp+var_78], eax
0x180011739  mov     rax, [rdi+38h]
0x18001173d  mov     [rbp+var_10], rax
0x180011741  mov     eax, [rdi+8]
0x180011744  mov     dword ptr [rbp+SRWLock], eax
0x180011747  mov     [rbp+var_8], 1000000h
0x18001174f  mov     [rbp+var_58], 0
0x180011757  mov     r8, [rbx+110h]
0x18001175e  add     r8, 8; int
0x180011762  lea     rax, [rbp+var_50]
0x180011766  mov     [rsp+140h+var_90], rax; __int64
0x18001176e  lea     rax, [rbp+var_78+4]
0x180011772  mov     [rsp+140h+var_98], rax; __int64
0x18001177a  lea     rax, [rbp+var_70]
0x18001177e  mov     [rsp+140h+var_A0], rax; __int64
0x180011786  lea     rax, [rbp+var_48]
0x18001178a  mov     [rsp+140h+var_A8], rax; __int64
0x180011792  lea     rax, [rbp+var_40]
0x180011796  mov     [rsp+140h+var_B0], rax; __int64
0x18001179e  lea     rax, [rbp+var_70+4]
0x1800117a2  mov     [rsp+140h+var_B8], rax; __int64
0x1800117aa  lea     rax, [rbp+var_38]
0x1800117ae  mov     [rsp+140h+var_C0], rax; __int64
0x1800117b6  lea     rax, [rbp+var_30]
0x1800117ba  mov     [rsp+140h+var_C8], rax; __int64
0x1800117bf  lea     rax, [rbp+var_68]
0x1800117c3  mov     [rsp+140h+var_D0], rax; __int64
0x1800117c8  lea     rax, [rbp+var_28]
0x1800117cc  mov     [rsp+140h+var_D8], rax; __int64
0x1800117d1  lea     rax, [rbp+var_68+4]
0x1800117d5  mov     [rsp+140h+var_E0], rax; __int64
0x1800117da  lea     rax, [rbp+var_20]
0x1800117de  mov     [rsp+140h+var_E8], rax; __int64
0x1800117e3  lea     rax, [rbp+var_60]
0x1800117e7  mov     [rsp+140h+var_F0], rax; __int64
0x1800117ec  lea     rax, [rbp+var_18]
0x1800117f0  mov     [rsp+140h+var_F8], rax; __int64
0x1800117f5  lea     rax, [rbp+var_78]
0x1800117f9  mov     [rsp+140h+var_100], rax; __int64
0x1800117fe  lea     rax, [rbp+var_10]
0x180011802  mov     [rsp+140h+var_108], rax; __int64
0x180011807  lea     rax, [rbp+SRWLock]
0x18001180b  mov     [rsp+140h+var_110], rax; __int64
0x180011810  lea     rax, [rbp+var_8]
0x180011814  mov     [rsp+140h+var_118], rax; __int64
0x180011819  lea     rax, [rbp+var_58]
0x18001181d  mov     [rsp+140h+var_120], rax; __int64
0x180011822  lea     rdx, dword_180053FD4; int
0x180011829  mov     rcx, r9; int
0x18001182c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011831  jmp     loc_1800118EA
0x180011836  mov     [rbp+SRWLock], 0
0x18001183e  lea     rdx, [rbp+SRWLock]
0x180011842  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011847  mov     rax, [rbx+110h]
0x18001184e  mov     dword ptr [rax], 2
0x180011854  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011858  test    rcx, rcx
0x18001185b  jz      short loc_180011869
0x18001185d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011864  nop     dword ptr [rax+rax+00h]
0x180011869  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x18001186e  mov     rdi, [rax+8]
0x180011872  mov     eax, [rdi]
0x180011874  cmp     eax, 4
0x180011877  jbe     short loc_1800118EA
0x180011879  mov     rdx, [rdi+18h]
0x18001187d  mov     rax, [rdi+10h]
0x180011881  mov     ecx, 20040h
0x180011886  test    rcx, rax
0x180011889  jz      short loc_1800118EA
0x18001188b  mov     rax, rdx
0x18001188e  and     rax, rcx
0x180011891  cmp     rax, rdx
0x180011894  jnz     short loc_1800118EA
0x180011896  call    cs:__imp_GetCurrentThreadId
0x18001189d  nop     dword ptr [rax+rax+00h]
0x1800118a2  mov     dword ptr [rbp+SRWLock], eax
0x1800118a5  mov     r8, [rbx+110h]
0x1800118ac  mov     eax, [r8+48h]
0x1800118b0  mov     dword ptr [rbp+var_78], eax
0x1800118b3  mov     [rbp+var_58], 0
0x1800118bb  add     r8, 8
0x1800118bf  lea     rax, [rbp+SRWLock]
0x1800118c3  mov     [rsp+140h+var_110], rax
0x1800118c8  lea     rax, [rbp+var_78]
0x1800118cc  mov     [rsp+140h+var_118], rax
0x1800118d1  lea     rax, [rbp+var_58]
0x1800118d5  mov     [rsp+140h+var_120], rax
0x1800118da  lea     rdx, byte_1800549AF
0x1800118e1  mov     rcx, rdi
0x1800118e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800118e9  nop
0x1800118ea  lea     rcx, [rbx+120h]; this
0x1800118f1  cmp     dword ptr [rcx+18h], 0
0x1800118f5  jz      short loc_1800118FD
0x1800118f7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800118fc  nop
0x1800118fd  lea     r11, [rsp+140h+var_s0]
0x180011905  mov     rbx, [r11+18h]
0x180011909  mov     rdi, [r11+20h]
0x18001190d  mov     rsp, r11
0x180011910  pop     rbp
0x180011911  retn
```
