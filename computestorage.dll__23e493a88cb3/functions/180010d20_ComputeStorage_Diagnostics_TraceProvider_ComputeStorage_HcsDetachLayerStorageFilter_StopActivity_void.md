# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::StopActivity(void)

- ea: `0x180010d20`
- end: `0x180011013`
- name: `?StopActivity@ComputeStorage_HcsDetachLayerStorageFilter@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180010d20`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010d87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010d87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f96`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter *this)
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
        (int)&byte_1800546E3,
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
        (int)byte_180053D8B,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsDetachLayerStorageFilter *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010d20  mov     [rsp-8+arg_8], rbx
0x180010d25  mov     [rsp-8+arg_10], rdi
0x180010d2a  push    rbp
0x180010d2b  mov     rbp, rsp
0x180010d2e  sub     rsp, 140h
0x180010d35  mov     rbx, rcx
0x180010d38  mov     rdi, [rcx+110h]
0x180010d3f  mov     eax, [rdi+48h]
0x180010d42  test    eax, eax
0x180010d44  jns     loc_180010F36
0x180010d4a  add     rdi, 50h ; 'P'
0x180010d4e  cmp     eax, [rdi+8]
0x180010d51  jnz     loc_180010F36
0x180010d57  test    rdi, rdi
0x180010d5a  jz      loc_180010F36
0x180010d60  mov     [rbp+SRWLock], 0
0x180010d68  lea     rdx, [rbp+SRWLock]
0x180010d6c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010d71  mov     rax, [rbx+110h]
0x180010d78  mov     dword ptr [rax], 2
0x180010d7e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010d82  test    rcx, rcx
0x180010d85  jz      short loc_180010D93
0x180010d87  call    cs:__imp_ReleaseSRWLockExclusive
0x180010d8e  nop     dword ptr [rax+rax+00h]
0x180010d93  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180010d98  mov     r9, [rax+8]
0x180010d9c  mov     eax, [r9]
0x180010d9f  cmp     eax, 4
0x180010da2  jbe     loc_180010FEA
0x180010da8  mov     rdx, [r9+18h]
0x180010dac  mov     rax, [r9+10h]
0x180010db0  mov     ecx, 20040h
0x180010db5  test    rcx, rax
0x180010db8  jz      loc_180010FEA
0x180010dbe  mov     rax, rdx
0x180010dc1  and     rax, rcx
0x180010dc4  cmp     rax, rdx
0x180010dc7  jnz     loc_180010FEA
0x180010dcd  mov     rax, [rdi+30h]
0x180010dd1  mov     [rbp+var_50], rax
0x180010dd5  mov     eax, [rdi+44h]
0x180010dd8  mov     dword ptr [rbp+var_78+4], eax
0x180010ddb  mov     eax, [rdi+10h]
0x180010dde  mov     dword ptr [rbp+var_70], eax
0x180010de1  mov     rax, [rdi+78h]
0x180010de5  mov     [rbp+var_48], rax
0x180010de9  mov     rax, [rdi+70h]
0x180010ded  mov     [rbp+var_40], rax
0x180010df1  mov     eax, [rdi+68h]
0x180010df4  mov     dword ptr [rbp+var_70+4], eax
0x180010df7  mov     rax, [rdi+60h]
0x180010dfb  mov     [rbp+var_38], rax
0x180010dff  mov     rax, [rdi+58h]
0x180010e03  mov     [rbp+var_30], rax
0x180010e07  mov     eax, [rdi+50h]
0x180010e0a  mov     dword ptr [rbp+var_68], eax
0x180010e0d  mov     rax, [rdi+48h]
0x180010e11  mov     [rbp+var_28], rax
0x180010e15  mov     eax, [rdi+20h]
0x180010e18  mov     dword ptr [rbp+var_68+4], eax
0x180010e1b  mov     rax, [rdi+18h]
0x180010e1f  mov     [rbp+var_20], rax
0x180010e23  mov     eax, [rdi]
0x180010e25  mov     [rbp+var_60], eax
0x180010e28  mov     rax, [rdi+80h]
0x180010e2f  mov     [rbp+var_18], rax
0x180010e33  mov     eax, [rdi+40h]
0x180010e36  mov     dword ptr [rbp+var_78], eax
0x180010e39  mov     rax, [rdi+38h]
0x180010e3d  mov     [rbp+var_10], rax
0x180010e41  mov     eax, [rdi+8]
0x180010e44  mov     dword ptr [rbp+SRWLock], eax
0x180010e47  mov     [rbp+var_8], 1000000h
0x180010e4f  mov     [rbp+var_58], 0
0x180010e57  mov     r8, [rbx+110h]
0x180010e5e  add     r8, 8; int
0x180010e62  lea     rax, [rbp+var_50]
0x180010e66  mov     [rsp+140h+var_90], rax; __int64
0x180010e6e  lea     rax, [rbp+var_78+4]
0x180010e72  mov     [rsp+140h+var_98], rax; __int64
0x180010e7a  lea     rax, [rbp+var_70]
0x180010e7e  mov     [rsp+140h+var_A0], rax; __int64
0x180010e86  lea     rax, [rbp+var_48]
0x180010e8a  mov     [rsp+140h+var_A8], rax; __int64
0x180010e92  lea     rax, [rbp+var_40]
0x180010e96  mov     [rsp+140h+var_B0], rax; __int64
0x180010e9e  lea     rax, [rbp+var_70+4]
0x180010ea2  mov     [rsp+140h+var_B8], rax; __int64
0x180010eaa  lea     rax, [rbp+var_38]
0x180010eae  mov     [rsp+140h+var_C0], rax; __int64
0x180010eb6  lea     rax, [rbp+var_30]
0x180010eba  mov     [rsp+140h+var_C8], rax; __int64
0x180010ebf  lea     rax, [rbp+var_68]
0x180010ec3  mov     [rsp+140h+var_D0], rax; __int64
0x180010ec8  lea     rax, [rbp+var_28]
0x180010ecc  mov     [rsp+140h+var_D8], rax; __int64
0x180010ed1  lea     rax, [rbp+var_68+4]
0x180010ed5  mov     [rsp+140h+var_E0], rax; __int64
0x180010eda  lea     rax, [rbp+var_20]
0x180010ede  mov     [rsp+140h+var_E8], rax; __int64
0x180010ee3  lea     rax, [rbp+var_60]
0x180010ee7  mov     [rsp+140h+var_F0], rax; __int64
0x180010eec  lea     rax, [rbp+var_18]
0x180010ef0  mov     [rsp+140h+var_F8], rax; __int64
0x180010ef5  lea     rax, [rbp+var_78]
0x180010ef9  mov     [rsp+140h+var_100], rax; __int64
0x180010efe  lea     rax, [rbp+var_10]
0x180010f02  mov     [rsp+140h+var_108], rax; __int64
0x180010f07  lea     rax, [rbp+SRWLock]
0x180010f0b  mov     [rsp+140h+var_110], rax; __int64
0x180010f10  lea     rax, [rbp+var_8]
0x180010f14  mov     [rsp+140h+var_118], rax; __int64
0x180010f19  lea     rax, [rbp+var_58]
0x180010f1d  mov     [rsp+140h+var_120], rax; __int64
0x180010f22  lea     rdx, byte_1800546E3; int
0x180010f29  mov     rcx, r9; int
0x180010f2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010f31  jmp     loc_180010FEA
0x180010f36  mov     [rbp+SRWLock], 0
0x180010f3e  lea     rdx, [rbp+SRWLock]
0x180010f42  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010f47  mov     rax, [rbx+110h]
0x180010f4e  mov     dword ptr [rax], 2
0x180010f54  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010f58  test    rcx, rcx
0x180010f5b  jz      short loc_180010F69
0x180010f5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180010f64  nop     dword ptr [rax+rax+00h]
0x180010f69  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180010f6e  mov     rdi, [rax+8]
0x180010f72  mov     eax, [rdi]
0x180010f74  cmp     eax, 4
0x180010f77  jbe     short loc_180010FEA
0x180010f79  mov     rdx, [rdi+18h]
0x180010f7d  mov     rax, [rdi+10h]
0x180010f81  mov     ecx, 20040h
0x180010f86  test    rcx, rax
0x180010f89  jz      short loc_180010FEA
0x180010f8b  mov     rax, rdx
0x180010f8e  and     rax, rcx
0x180010f91  cmp     rax, rdx
0x180010f94  jnz     short loc_180010FEA
0x180010f96  call    cs:__imp_GetCurrentThreadId
0x180010f9d  nop     dword ptr [rax+rax+00h]
0x180010fa2  mov     dword ptr [rbp+SRWLock], eax
0x180010fa5  mov     r8, [rbx+110h]
0x180010fac  mov     eax, [r8+48h]
0x180010fb0  mov     dword ptr [rbp+var_78], eax
0x180010fb3  mov     [rbp+var_58], 0
0x180010fbb  add     r8, 8
0x180010fbf  lea     rax, [rbp+SRWLock]
0x180010fc3  mov     [rsp+140h+var_110], rax
0x180010fc8  lea     rax, [rbp+var_78]
0x180010fcc  mov     [rsp+140h+var_118], rax
0x180010fd1  lea     rax, [rbp+var_58]
0x180010fd5  mov     [rsp+140h+var_120], rax
0x180010fda  lea     rdx, byte_180053D8B
0x180010fe1  mov     rcx, rdi
0x180010fe4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010fe9  nop
0x180010fea  lea     rcx, [rbx+120h]; this
0x180010ff1  cmp     dword ptr [rcx+18h], 0
0x180010ff5  jz      short loc_180010FFD
0x180010ff7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010ffc  nop
0x180010ffd  lea     r11, [rsp+140h+var_s0]
0x180011005  mov     rbx, [r11+18h]
0x180011009  mov     rdi, [r11+20h]
0x18001100d  mov     rsp, r11
0x180011010  pop     rbp
0x180011011  retn
```
