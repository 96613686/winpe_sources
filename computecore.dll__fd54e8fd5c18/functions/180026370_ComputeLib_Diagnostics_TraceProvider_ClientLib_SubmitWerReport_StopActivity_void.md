# ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport::StopActivity(void)

- ea: `0x180026370`
- end: `0x180026650`
- name: `?StopActivity@ClientLib_SubmitWerReport@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x180026370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800263d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800265a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800263d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800265a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800265d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800265d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x10000LL) != 0 && (v7 & 0x10000) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&byte_1800C5FC1,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = ComputeLib::Diagnostics::TraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x10000LL) != 0 && (v10 & 0x10000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_1800C5F0E,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_SubmitWerReport *)((char *)this + 288));
}

```

## disassembly

```asm
0x180026370  mov     [rsp-8+arg_8], rbx
0x180026375  mov     [rsp-8+arg_10], rdi
0x18002637a  push    rbp
0x18002637b  mov     rbp, rsp
0x18002637e  sub     rsp, 140h
0x180026385  mov     rbx, rcx
0x180026388  mov     rdi, [rcx+110h]
0x18002638f  mov     eax, [rdi+48h]
0x180026392  test    eax, eax
0x180026394  jns     loc_18002657E
0x18002639a  add     rdi, 50h ; 'P'
0x18002639e  cmp     eax, [rdi+8]
0x1800263a1  jnz     loc_18002657E
0x1800263a7  test    rdi, rdi
0x1800263aa  jz      loc_18002657E
0x1800263b0  mov     [rbp+SRWLock], 0
0x1800263b8  lea     rdx, [rbp+SRWLock]
0x1800263bc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800263c1  mov     rax, [rbx+110h]
0x1800263c8  mov     dword ptr [rax], 2
0x1800263ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800263d2  test    rcx, rcx
0x1800263d5  jz      short loc_1800263DD
0x1800263d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800263dd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x1800263e2  mov     r9, rax
0x1800263e5  mov     ecx, [rax]
0x1800263e7  cmp     ecx, 4
0x1800263ea  jbe     loc_180026628
0x1800263f0  mov     rax, [rax+18h]
0x1800263f4  mov     rcx, [r9+10h]
0x1800263f8  mov     edx, 10000h
0x1800263fd  test    rdx, rcx
0x180026400  jz      loc_180026628
0x180026406  mov     rcx, rax
0x180026409  and     rcx, rdx
0x18002640c  cmp     rcx, rax
0x18002640f  jnz     loc_180026628
0x180026415  mov     rax, [rdi+30h]
0x180026419  mov     [rbp+var_50], rax
0x18002641d  mov     eax, [rdi+44h]
0x180026420  mov     dword ptr [rbp+var_78+4], eax
0x180026423  mov     eax, [rdi+10h]
0x180026426  mov     dword ptr [rbp+var_70], eax
0x180026429  mov     rax, [rdi+78h]
0x18002642d  mov     [rbp+var_48], rax
0x180026431  mov     rax, [rdi+70h]
0x180026435  mov     [rbp+var_40], rax
0x180026439  mov     eax, [rdi+68h]
0x18002643c  mov     dword ptr [rbp+var_70+4], eax
0x18002643f  mov     rax, [rdi+60h]
0x180026443  mov     [rbp+var_38], rax
0x180026447  mov     rax, [rdi+58h]
0x18002644b  mov     [rbp+var_30], rax
0x18002644f  mov     eax, [rdi+50h]
0x180026452  mov     dword ptr [rbp+var_68], eax
0x180026455  mov     rax, [rdi+48h]
0x180026459  mov     [rbp+var_28], rax
0x18002645d  mov     eax, [rdi+20h]
0x180026460  mov     dword ptr [rbp+var_68+4], eax
0x180026463  mov     rax, [rdi+18h]
0x180026467  mov     [rbp+var_20], rax
0x18002646b  mov     eax, [rdi]
0x18002646d  mov     [rbp+var_60], eax
0x180026470  mov     rax, [rdi+80h]
0x180026477  mov     [rbp+var_18], rax
0x18002647b  mov     eax, [rdi+40h]
0x18002647e  mov     dword ptr [rbp+var_78], eax
0x180026481  mov     rax, [rdi+38h]
0x180026485  mov     [rbp+var_10], rax
0x180026489  mov     eax, [rdi+8]
0x18002648c  mov     dword ptr [rbp+SRWLock], eax
0x18002648f  mov     [rbp+var_8], 1000000h
0x180026497  mov     [rbp+var_58], 0
0x18002649f  mov     r8, [rbx+110h]
0x1800264a6  add     r8, 8; int
0x1800264aa  lea     rax, [rbp+var_50]
0x1800264ae  mov     [rsp+140h+var_90], rax; __int64
0x1800264b6  lea     rax, [rbp+var_78+4]
0x1800264ba  mov     [rsp+140h+var_98], rax; __int64
0x1800264c2  lea     rax, [rbp+var_70]
0x1800264c6  mov     [rsp+140h+var_A0], rax; __int64
0x1800264ce  lea     rax, [rbp+var_48]
0x1800264d2  mov     [rsp+140h+var_A8], rax; __int64
0x1800264da  lea     rax, [rbp+var_40]
0x1800264de  mov     [rsp+140h+var_B0], rax; __int64
0x1800264e6  lea     rax, [rbp+var_70+4]
0x1800264ea  mov     [rsp+140h+var_B8], rax; __int64
0x1800264f2  lea     rax, [rbp+var_38]
0x1800264f6  mov     [rsp+140h+var_C0], rax; __int64
0x1800264fe  lea     rax, [rbp+var_30]
0x180026502  mov     [rsp+140h+var_C8], rax; __int64
0x180026507  lea     rax, [rbp+var_68]
0x18002650b  mov     [rsp+140h+var_D0], rax; __int64
0x180026510  lea     rax, [rbp+var_28]
0x180026514  mov     [rsp+140h+var_D8], rax; __int64
0x180026519  lea     rax, [rbp+var_68+4]
0x18002651d  mov     [rsp+140h+var_E0], rax; __int64
0x180026522  lea     rax, [rbp+var_20]
0x180026526  mov     [rsp+140h+var_E8], rax; __int64
0x18002652b  lea     rax, [rbp+var_60]
0x18002652f  mov     [rsp+140h+var_F0], rax; __int64
0x180026534  lea     rax, [rbp+var_18]
0x180026538  mov     [rsp+140h+var_F8], rax; __int64
0x18002653d  lea     rax, [rbp+var_78]
0x180026541  mov     [rsp+140h+var_100], rax; __int64
0x180026546  lea     rax, [rbp+var_10]
0x18002654a  mov     [rsp+140h+var_108], rax; __int64
0x18002654f  lea     rax, [rbp+SRWLock]
0x180026553  mov     [rsp+140h+var_110], rax; __int64
0x180026558  lea     rax, [rbp+var_8]
0x18002655c  mov     [rsp+140h+var_118], rax; __int64
0x180026561  lea     rax, [rbp+var_58]
0x180026565  mov     [rsp+140h+var_120], rax; __int64
0x18002656a  lea     rdx, byte_1800C5FC1; int
0x180026571  mov     rcx, r9; int
0x180026574  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026579  jmp     loc_180026628
0x18002657e  mov     [rbp+SRWLock], 0
0x180026586  lea     rdx, [rbp+SRWLock]
0x18002658a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002658f  mov     rax, [rbx+110h]
0x180026596  mov     dword ptr [rax], 2
0x18002659c  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800265a0  test    rcx, rcx
0x1800265a3  jz      short loc_1800265AB
0x1800265a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800265ab  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x1800265b0  mov     rdi, rax
0x1800265b3  mov     ecx, [rax]
0x1800265b5  cmp     ecx, 4
0x1800265b8  jbe     short loc_180026628
0x1800265ba  mov     rax, [rax+18h]
0x1800265be  mov     rcx, [rdi+10h]
0x1800265c2  mov     edx, 10000h
0x1800265c7  test    rdx, rcx
0x1800265ca  jz      short loc_180026628
0x1800265cc  mov     rcx, rax
0x1800265cf  and     rcx, rdx
0x1800265d2  cmp     rcx, rax
0x1800265d5  jnz     short loc_180026628
0x1800265d7  call    cs:__imp_GetCurrentThreadId
0x1800265dd  mov     dword ptr [rbp+SRWLock], eax
0x1800265e0  mov     r8, [rbx+110h]
0x1800265e7  mov     eax, [r8+48h]
0x1800265eb  mov     dword ptr [rbp+var_78], eax
0x1800265ee  mov     [rbp+var_58], 0
0x1800265f6  add     r8, 8
0x1800265fa  lea     rax, [rbp+SRWLock]
0x1800265fe  mov     [rsp+140h+var_110], rax
0x180026603  lea     rax, [rbp+var_78]
0x180026607  mov     [rsp+140h+var_118], rax
0x18002660c  lea     rax, [rbp+var_58]
0x180026610  mov     [rsp+140h+var_120], rax
0x180026615  xor     r9d, r9d
0x180026618  lea     rdx, word_1800C5F0E
0x18002661f  mov     rcx, rdi
0x180026622  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180026627  nop
0x180026628  lea     rcx, [rbx+120h]; this
0x18002662f  cmp     dword ptr [rcx+18h], 0
0x180026633  jz      short loc_18002663B
0x180026635  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002663a  nop
0x18002663b  lea     r11, [rsp+140h+var_s0]
0x180026643  mov     rbx, [r11+18h]
0x180026647  mov     rdi, [r11+20h]
0x18002664b  mov     rsp, r11
0x18002664e  pop     rbp
0x18002664f  retn
```
