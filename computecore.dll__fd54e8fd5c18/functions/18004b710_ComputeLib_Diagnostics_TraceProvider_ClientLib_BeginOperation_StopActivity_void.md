# ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation::StopActivity(void)

- ea: `0x18004b710`
- end: `0x18004b9f0`
- name: `?StopActivity@ClientLib_BeginOperation@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18004b710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b945`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b777`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004b945`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b977`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *this)
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
          (int)&byte_1800C8547,
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
          (unsigned int)word_1800C8482,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_BeginOperation *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004b710  mov     [rsp-8+arg_8], rbx
0x18004b715  mov     [rsp-8+arg_10], rdi
0x18004b71a  push    rbp
0x18004b71b  mov     rbp, rsp
0x18004b71e  sub     rsp, 140h
0x18004b725  mov     rbx, rcx
0x18004b728  mov     rdi, [rcx+110h]
0x18004b72f  mov     eax, [rdi+48h]
0x18004b732  test    eax, eax
0x18004b734  jns     loc_18004B91E
0x18004b73a  add     rdi, 50h ; 'P'
0x18004b73e  cmp     eax, [rdi+8]
0x18004b741  jnz     loc_18004B91E
0x18004b747  test    rdi, rdi
0x18004b74a  jz      loc_18004B91E
0x18004b750  mov     [rbp+SRWLock], 0
0x18004b758  lea     rdx, [rbp+SRWLock]
0x18004b75c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b761  mov     rax, [rbx+110h]
0x18004b768  mov     dword ptr [rax], 2
0x18004b76e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b772  test    rcx, rcx
0x18004b775  jz      short loc_18004B77D
0x18004b777  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b77d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b782  mov     r9, rax
0x18004b785  mov     ecx, [rax]
0x18004b787  cmp     ecx, 4
0x18004b78a  jbe     loc_18004B9C8
0x18004b790  mov     rax, [rax+18h]
0x18004b794  mov     rcx, [r9+10h]
0x18004b798  mov     edx, 10000h
0x18004b79d  test    rdx, rcx
0x18004b7a0  jz      loc_18004B9C8
0x18004b7a6  mov     rcx, rax
0x18004b7a9  and     rcx, rdx
0x18004b7ac  cmp     rcx, rax
0x18004b7af  jnz     loc_18004B9C8
0x18004b7b5  mov     rax, [rdi+30h]
0x18004b7b9  mov     [rbp+var_50], rax
0x18004b7bd  mov     eax, [rdi+44h]
0x18004b7c0  mov     dword ptr [rbp+var_78+4], eax
0x18004b7c3  mov     eax, [rdi+10h]
0x18004b7c6  mov     dword ptr [rbp+var_70], eax
0x18004b7c9  mov     rax, [rdi+78h]
0x18004b7cd  mov     [rbp+var_48], rax
0x18004b7d1  mov     rax, [rdi+70h]
0x18004b7d5  mov     [rbp+var_40], rax
0x18004b7d9  mov     eax, [rdi+68h]
0x18004b7dc  mov     dword ptr [rbp+var_70+4], eax
0x18004b7df  mov     rax, [rdi+60h]
0x18004b7e3  mov     [rbp+var_38], rax
0x18004b7e7  mov     rax, [rdi+58h]
0x18004b7eb  mov     [rbp+var_30], rax
0x18004b7ef  mov     eax, [rdi+50h]
0x18004b7f2  mov     dword ptr [rbp+var_68], eax
0x18004b7f5  mov     rax, [rdi+48h]
0x18004b7f9  mov     [rbp+var_28], rax
0x18004b7fd  mov     eax, [rdi+20h]
0x18004b800  mov     dword ptr [rbp+var_68+4], eax
0x18004b803  mov     rax, [rdi+18h]
0x18004b807  mov     [rbp+var_20], rax
0x18004b80b  mov     eax, [rdi]
0x18004b80d  mov     [rbp+var_60], eax
0x18004b810  mov     rax, [rdi+80h]
0x18004b817  mov     [rbp+var_18], rax
0x18004b81b  mov     eax, [rdi+40h]
0x18004b81e  mov     dword ptr [rbp+var_78], eax
0x18004b821  mov     rax, [rdi+38h]
0x18004b825  mov     [rbp+var_10], rax
0x18004b829  mov     eax, [rdi+8]
0x18004b82c  mov     dword ptr [rbp+SRWLock], eax
0x18004b82f  mov     [rbp+var_8], 1000000h
0x18004b837  mov     [rbp+var_58], 0
0x18004b83f  mov     r8, [rbx+110h]
0x18004b846  add     r8, 8; int
0x18004b84a  lea     rax, [rbp+var_50]
0x18004b84e  mov     [rsp+140h+var_90], rax; __int64
0x18004b856  lea     rax, [rbp+var_78+4]
0x18004b85a  mov     [rsp+140h+var_98], rax; __int64
0x18004b862  lea     rax, [rbp+var_70]
0x18004b866  mov     [rsp+140h+var_A0], rax; __int64
0x18004b86e  lea     rax, [rbp+var_48]
0x18004b872  mov     [rsp+140h+var_A8], rax; __int64
0x18004b87a  lea     rax, [rbp+var_40]
0x18004b87e  mov     [rsp+140h+var_B0], rax; __int64
0x18004b886  lea     rax, [rbp+var_70+4]
0x18004b88a  mov     [rsp+140h+var_B8], rax; __int64
0x18004b892  lea     rax, [rbp+var_38]
0x18004b896  mov     [rsp+140h+var_C0], rax; __int64
0x18004b89e  lea     rax, [rbp+var_30]
0x18004b8a2  mov     [rsp+140h+var_C8], rax; __int64
0x18004b8a7  lea     rax, [rbp+var_68]
0x18004b8ab  mov     [rsp+140h+var_D0], rax; __int64
0x18004b8b0  lea     rax, [rbp+var_28]
0x18004b8b4  mov     [rsp+140h+var_D8], rax; __int64
0x18004b8b9  lea     rax, [rbp+var_68+4]
0x18004b8bd  mov     [rsp+140h+var_E0], rax; __int64
0x18004b8c2  lea     rax, [rbp+var_20]
0x18004b8c6  mov     [rsp+140h+var_E8], rax; __int64
0x18004b8cb  lea     rax, [rbp+var_60]
0x18004b8cf  mov     [rsp+140h+var_F0], rax; __int64
0x18004b8d4  lea     rax, [rbp+var_18]
0x18004b8d8  mov     [rsp+140h+var_F8], rax; __int64
0x18004b8dd  lea     rax, [rbp+var_78]
0x18004b8e1  mov     [rsp+140h+var_100], rax; __int64
0x18004b8e6  lea     rax, [rbp+var_10]
0x18004b8ea  mov     [rsp+140h+var_108], rax; __int64
0x18004b8ef  lea     rax, [rbp+SRWLock]
0x18004b8f3  mov     [rsp+140h+var_110], rax; __int64
0x18004b8f8  lea     rax, [rbp+var_8]
0x18004b8fc  mov     [rsp+140h+var_118], rax; __int64
0x18004b901  lea     rax, [rbp+var_58]
0x18004b905  mov     [rsp+140h+var_120], rax; __int64
0x18004b90a  lea     rdx, byte_1800C8547; int
0x18004b911  mov     rcx, r9; int
0x18004b914  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004b919  jmp     loc_18004B9C8
0x18004b91e  mov     [rbp+SRWLock], 0
0x18004b926  lea     rdx, [rbp+SRWLock]
0x18004b92a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004b92f  mov     rax, [rbx+110h]
0x18004b936  mov     dword ptr [rax], 2
0x18004b93c  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004b940  test    rcx, rcx
0x18004b943  jz      short loc_18004B94B
0x18004b945  call    cs:__imp_ReleaseSRWLockExclusive
0x18004b94b  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004b950  mov     rdi, rax
0x18004b953  mov     ecx, [rax]
0x18004b955  cmp     ecx, 4
0x18004b958  jbe     short loc_18004B9C8
0x18004b95a  mov     rax, [rax+18h]
0x18004b95e  mov     rcx, [rdi+10h]
0x18004b962  mov     edx, 10000h
0x18004b967  test    rdx, rcx
0x18004b96a  jz      short loc_18004B9C8
0x18004b96c  mov     rcx, rax
0x18004b96f  and     rcx, rdx
0x18004b972  cmp     rcx, rax
0x18004b975  jnz     short loc_18004B9C8
0x18004b977  call    cs:__imp_GetCurrentThreadId
0x18004b97d  mov     dword ptr [rbp+SRWLock], eax
0x18004b980  mov     r8, [rbx+110h]
0x18004b987  mov     eax, [r8+48h]
0x18004b98b  mov     dword ptr [rbp+var_78], eax
0x18004b98e  mov     [rbp+var_58], 0
0x18004b996  add     r8, 8
0x18004b99a  lea     rax, [rbp+SRWLock]
0x18004b99e  mov     [rsp+140h+var_110], rax
0x18004b9a3  lea     rax, [rbp+var_78]
0x18004b9a7  mov     [rsp+140h+var_118], rax
0x18004b9ac  lea     rax, [rbp+var_58]
0x18004b9b0  mov     [rsp+140h+var_120], rax
0x18004b9b5  xor     r9d, r9d
0x18004b9b8  lea     rdx, word_1800C8482
0x18004b9bf  mov     rcx, rdi
0x18004b9c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004b9c7  nop
0x18004b9c8  lea     rcx, [rbx+120h]; this
0x18004b9cf  cmp     dword ptr [rcx+18h], 0
0x18004b9d3  jz      short loc_18004B9DB
0x18004b9d5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004b9da  nop
0x18004b9db  lea     r11, [rsp+140h+var_s0]
0x18004b9e3  mov     rbx, [r11+18h]
0x18004b9e7  mov     rdi, [r11+20h]
0x18004b9eb  mov     rsp, r11
0x18004b9ee  pop     rbp
0x18004b9ef  retn
```
