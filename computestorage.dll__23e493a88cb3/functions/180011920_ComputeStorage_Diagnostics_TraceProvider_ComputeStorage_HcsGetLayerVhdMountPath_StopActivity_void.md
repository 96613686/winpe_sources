# ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StopActivity(void)

- ea: `0x180011920`
- end: `0x180011c13`
- name: `?StopActivity@ComputeStorage_HcsGetLayerVhdMountPath@TraceProvider@Diagnostics@ComputeStorage@@MEAAXXZ`
- size: `755`
- prototype: `void __fastcall(ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180001350`
- `0x180001664`
- `0x18000b9b4`
- `0x18000bc04`
- `0x180011920`
- `0x18001251c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011b5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011987`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011b5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b96`

## pseudocode

```c
void __fastcall ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath::StopActivity(
        ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *this)
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
        (int)&byte_180054A1B,
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
        (int)byte_1800548F3,
        v7 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v10,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_HcsGetLayerVhdMountPath *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011920  mov     [rsp-8+arg_8], rbx
0x180011925  mov     [rsp-8+arg_10], rdi
0x18001192a  push    rbp
0x18001192b  mov     rbp, rsp
0x18001192e  sub     rsp, 140h
0x180011935  mov     rbx, rcx
0x180011938  mov     rdi, [rcx+110h]
0x18001193f  mov     eax, [rdi+48h]
0x180011942  test    eax, eax
0x180011944  jns     loc_180011B36
0x18001194a  add     rdi, 50h ; 'P'
0x18001194e  cmp     eax, [rdi+8]
0x180011951  jnz     loc_180011B36
0x180011957  test    rdi, rdi
0x18001195a  jz      loc_180011B36
0x180011960  mov     [rbp+SRWLock], 0
0x180011968  lea     rdx, [rbp+SRWLock]
0x18001196c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011971  mov     rax, [rbx+110h]
0x180011978  mov     dword ptr [rax], 2
0x18001197e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011982  test    rcx, rcx
0x180011985  jz      short loc_180011993
0x180011987  call    cs:__imp_ReleaseSRWLockExclusive
0x18001198e  nop     dword ptr [rax+rax+00h]
0x180011993  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180011998  mov     r9, [rax+8]
0x18001199c  mov     eax, [r9]
0x18001199f  cmp     eax, 4
0x1800119a2  jbe     loc_180011BEA
0x1800119a8  mov     rdx, [r9+18h]
0x1800119ac  mov     rax, [r9+10h]
0x1800119b0  mov     ecx, 20040h
0x1800119b5  test    rcx, rax
0x1800119b8  jz      loc_180011BEA
0x1800119be  mov     rax, rdx
0x1800119c1  and     rax, rcx
0x1800119c4  cmp     rax, rdx
0x1800119c7  jnz     loc_180011BEA
0x1800119cd  mov     rax, [rdi+30h]
0x1800119d1  mov     [rbp+var_50], rax
0x1800119d5  mov     eax, [rdi+44h]
0x1800119d8  mov     dword ptr [rbp+var_78+4], eax
0x1800119db  mov     eax, [rdi+10h]
0x1800119de  mov     dword ptr [rbp+var_70], eax
0x1800119e1  mov     rax, [rdi+78h]
0x1800119e5  mov     [rbp+var_48], rax
0x1800119e9  mov     rax, [rdi+70h]
0x1800119ed  mov     [rbp+var_40], rax
0x1800119f1  mov     eax, [rdi+68h]
0x1800119f4  mov     dword ptr [rbp+var_70+4], eax
0x1800119f7  mov     rax, [rdi+60h]
0x1800119fb  mov     [rbp+var_38], rax
0x1800119ff  mov     rax, [rdi+58h]
0x180011a03  mov     [rbp+var_30], rax
0x180011a07  mov     eax, [rdi+50h]
0x180011a0a  mov     dword ptr [rbp+var_68], eax
0x180011a0d  mov     rax, [rdi+48h]
0x180011a11  mov     [rbp+var_28], rax
0x180011a15  mov     eax, [rdi+20h]
0x180011a18  mov     dword ptr [rbp+var_68+4], eax
0x180011a1b  mov     rax, [rdi+18h]
0x180011a1f  mov     [rbp+var_20], rax
0x180011a23  mov     eax, [rdi]
0x180011a25  mov     [rbp+var_60], eax
0x180011a28  mov     rax, [rdi+80h]
0x180011a2f  mov     [rbp+var_18], rax
0x180011a33  mov     eax, [rdi+40h]
0x180011a36  mov     dword ptr [rbp+var_78], eax
0x180011a39  mov     rax, [rdi+38h]
0x180011a3d  mov     [rbp+var_10], rax
0x180011a41  mov     eax, [rdi+8]
0x180011a44  mov     dword ptr [rbp+SRWLock], eax
0x180011a47  mov     [rbp+var_8], 1000000h
0x180011a4f  mov     [rbp+var_58], 0
0x180011a57  mov     r8, [rbx+110h]
0x180011a5e  add     r8, 8; int
0x180011a62  lea     rax, [rbp+var_50]
0x180011a66  mov     [rsp+140h+var_90], rax; __int64
0x180011a6e  lea     rax, [rbp+var_78+4]
0x180011a72  mov     [rsp+140h+var_98], rax; __int64
0x180011a7a  lea     rax, [rbp+var_70]
0x180011a7e  mov     [rsp+140h+var_A0], rax; __int64
0x180011a86  lea     rax, [rbp+var_48]
0x180011a8a  mov     [rsp+140h+var_A8], rax; __int64
0x180011a92  lea     rax, [rbp+var_40]
0x180011a96  mov     [rsp+140h+var_B0], rax; __int64
0x180011a9e  lea     rax, [rbp+var_70+4]
0x180011aa2  mov     [rsp+140h+var_B8], rax; __int64
0x180011aaa  lea     rax, [rbp+var_38]
0x180011aae  mov     [rsp+140h+var_C0], rax; __int64
0x180011ab6  lea     rax, [rbp+var_30]
0x180011aba  mov     [rsp+140h+var_C8], rax; __int64
0x180011abf  lea     rax, [rbp+var_68]
0x180011ac3  mov     [rsp+140h+var_D0], rax; __int64
0x180011ac8  lea     rax, [rbp+var_28]
0x180011acc  mov     [rsp+140h+var_D8], rax; __int64
0x180011ad1  lea     rax, [rbp+var_68+4]
0x180011ad5  mov     [rsp+140h+var_E0], rax; __int64
0x180011ada  lea     rax, [rbp+var_20]
0x180011ade  mov     [rsp+140h+var_E8], rax; __int64
0x180011ae3  lea     rax, [rbp+var_60]
0x180011ae7  mov     [rsp+140h+var_F0], rax; __int64
0x180011aec  lea     rax, [rbp+var_18]
0x180011af0  mov     [rsp+140h+var_F8], rax; __int64
0x180011af5  lea     rax, [rbp+var_78]
0x180011af9  mov     [rsp+140h+var_100], rax; __int64
0x180011afe  lea     rax, [rbp+var_10]
0x180011b02  mov     [rsp+140h+var_108], rax; __int64
0x180011b07  lea     rax, [rbp+SRWLock]
0x180011b0b  mov     [rsp+140h+var_110], rax; __int64
0x180011b10  lea     rax, [rbp+var_8]
0x180011b14  mov     [rsp+140h+var_118], rax; __int64
0x180011b19  lea     rax, [rbp+var_58]
0x180011b1d  mov     [rsp+140h+var_120], rax; __int64
0x180011b22  lea     rdx, byte_180054A1B; int
0x180011b29  mov     rcx, r9; int
0x180011b2c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011b31  jmp     loc_180011BEA
0x180011b36  mov     [rbp+SRWLock], 0
0x180011b3e  lea     rdx, [rbp+SRWLock]
0x180011b42  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011b47  mov     rax, [rbx+110h]
0x180011b4e  mov     dword ptr [rax], 2
0x180011b54  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011b58  test    rcx, rcx
0x180011b5b  jz      short loc_180011B69
0x180011b5d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011b64  nop     dword ptr [rax+rax+00h]
0x180011b69  call    ?Instance@TraceProvider@Diagnostics@ComputeStorage@@KAPEAV123@XZ; ComputeStorage::Diagnostics::TraceProvider::Instance(void)
0x180011b6e  mov     rdi, [rax+8]
0x180011b72  mov     eax, [rdi]
0x180011b74  cmp     eax, 4
0x180011b77  jbe     short loc_180011BEA
0x180011b79  mov     rdx, [rdi+18h]
0x180011b7d  mov     rax, [rdi+10h]
0x180011b81  mov     ecx, 20040h
0x180011b86  test    rcx, rax
0x180011b89  jz      short loc_180011BEA
0x180011b8b  mov     rax, rdx
0x180011b8e  and     rax, rcx
0x180011b91  cmp     rax, rdx
0x180011b94  jnz     short loc_180011BEA
0x180011b96  call    cs:__imp_GetCurrentThreadId
0x180011b9d  nop     dword ptr [rax+rax+00h]
0x180011ba2  mov     dword ptr [rbp+SRWLock], eax
0x180011ba5  mov     r8, [rbx+110h]
0x180011bac  mov     eax, [r8+48h]
0x180011bb0  mov     dword ptr [rbp+var_78], eax
0x180011bb3  mov     [rbp+var_58], 0
0x180011bbb  add     r8, 8
0x180011bbf  lea     rax, [rbp+SRWLock]
0x180011bc3  mov     [rsp+140h+var_110], rax
0x180011bc8  lea     rax, [rbp+var_78]
0x180011bcc  mov     [rsp+140h+var_118], rax
0x180011bd1  lea     rax, [rbp+var_58]
0x180011bd5  mov     [rsp+140h+var_120], rax
0x180011bda  lea     rdx, byte_1800548F3
0x180011be1  mov     rcx, rdi
0x180011be4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011be9  nop
0x180011bea  lea     rcx, [rbx+120h]; this
0x180011bf1  cmp     dword ptr [rcx+18h], 0
0x180011bf5  jz      short loc_180011BFD
0x180011bf7  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180011bfc  nop
0x180011bfd  lea     r11, [rsp+140h+var_s0]
0x180011c05  mov     rbx, [r11+18h]
0x180011c09  mov     rdi, [r11+20h]
0x180011c0d  mov     rsp, r11
0x180011c10  pop     rbp
0x180011c11  retn
```
