# ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StopActivity(void)

- ea: `0x18004c5c0`
- end: `0x18004c8a0`
- name: `?StopActivity@ClientLib_SyncOperationCompletion@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18004c5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c627`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c7f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c627`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c7f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c827`

## pseudocode

```c
void __fastcall ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *this)
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
          (int)&byte_1800C7985,
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
          (unsigned int)&unk_1800C8370,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::ClientLib_SyncOperationCompletion *)((char *)this + 288));
}

```

## disassembly

```asm
0x18004c5c0  mov     [rsp-8+arg_8], rbx
0x18004c5c5  mov     [rsp-8+arg_10], rdi
0x18004c5ca  push    rbp
0x18004c5cb  mov     rbp, rsp
0x18004c5ce  sub     rsp, 140h
0x18004c5d5  mov     rbx, rcx
0x18004c5d8  mov     rdi, [rcx+110h]
0x18004c5df  mov     eax, [rdi+48h]
0x18004c5e2  test    eax, eax
0x18004c5e4  jns     loc_18004C7CE
0x18004c5ea  add     rdi, 50h ; 'P'
0x18004c5ee  cmp     eax, [rdi+8]
0x18004c5f1  jnz     loc_18004C7CE
0x18004c5f7  test    rdi, rdi
0x18004c5fa  jz      loc_18004C7CE
0x18004c600  mov     [rbp+SRWLock], 0
0x18004c608  lea     rdx, [rbp+SRWLock]
0x18004c60c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c611  mov     rax, [rbx+110h]
0x18004c618  mov     dword ptr [rax], 2
0x18004c61e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004c622  test    rcx, rcx
0x18004c625  jz      short loc_18004C62D
0x18004c627  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c62d  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004c632  mov     r9, rax
0x18004c635  mov     ecx, [rax]
0x18004c637  cmp     ecx, 4
0x18004c63a  jbe     loc_18004C878
0x18004c640  mov     rax, [rax+18h]
0x18004c644  mov     rcx, [r9+10h]
0x18004c648  mov     edx, 10000h
0x18004c64d  test    rdx, rcx
0x18004c650  jz      loc_18004C878
0x18004c656  mov     rcx, rax
0x18004c659  and     rcx, rdx
0x18004c65c  cmp     rcx, rax
0x18004c65f  jnz     loc_18004C878
0x18004c665  mov     rax, [rdi+30h]
0x18004c669  mov     [rbp+var_50], rax
0x18004c66d  mov     eax, [rdi+44h]
0x18004c670  mov     dword ptr [rbp+var_78+4], eax
0x18004c673  mov     eax, [rdi+10h]
0x18004c676  mov     dword ptr [rbp+var_70], eax
0x18004c679  mov     rax, [rdi+78h]
0x18004c67d  mov     [rbp+var_48], rax
0x18004c681  mov     rax, [rdi+70h]
0x18004c685  mov     [rbp+var_40], rax
0x18004c689  mov     eax, [rdi+68h]
0x18004c68c  mov     dword ptr [rbp+var_70+4], eax
0x18004c68f  mov     rax, [rdi+60h]
0x18004c693  mov     [rbp+var_38], rax
0x18004c697  mov     rax, [rdi+58h]
0x18004c69b  mov     [rbp+var_30], rax
0x18004c69f  mov     eax, [rdi+50h]
0x18004c6a2  mov     dword ptr [rbp+var_68], eax
0x18004c6a5  mov     rax, [rdi+48h]
0x18004c6a9  mov     [rbp+var_28], rax
0x18004c6ad  mov     eax, [rdi+20h]
0x18004c6b0  mov     dword ptr [rbp+var_68+4], eax
0x18004c6b3  mov     rax, [rdi+18h]
0x18004c6b7  mov     [rbp+var_20], rax
0x18004c6bb  mov     eax, [rdi]
0x18004c6bd  mov     [rbp+var_60], eax
0x18004c6c0  mov     rax, [rdi+80h]
0x18004c6c7  mov     [rbp+var_18], rax
0x18004c6cb  mov     eax, [rdi+40h]
0x18004c6ce  mov     dword ptr [rbp+var_78], eax
0x18004c6d1  mov     rax, [rdi+38h]
0x18004c6d5  mov     [rbp+var_10], rax
0x18004c6d9  mov     eax, [rdi+8]
0x18004c6dc  mov     dword ptr [rbp+SRWLock], eax
0x18004c6df  mov     [rbp+var_8], 1000000h
0x18004c6e7  mov     [rbp+var_58], 0
0x18004c6ef  mov     r8, [rbx+110h]
0x18004c6f6  add     r8, 8; int
0x18004c6fa  lea     rax, [rbp+var_50]
0x18004c6fe  mov     [rsp+140h+var_90], rax; __int64
0x18004c706  lea     rax, [rbp+var_78+4]
0x18004c70a  mov     [rsp+140h+var_98], rax; __int64
0x18004c712  lea     rax, [rbp+var_70]
0x18004c716  mov     [rsp+140h+var_A0], rax; __int64
0x18004c71e  lea     rax, [rbp+var_48]
0x18004c722  mov     [rsp+140h+var_A8], rax; __int64
0x18004c72a  lea     rax, [rbp+var_40]
0x18004c72e  mov     [rsp+140h+var_B0], rax; __int64
0x18004c736  lea     rax, [rbp+var_70+4]
0x18004c73a  mov     [rsp+140h+var_B8], rax; __int64
0x18004c742  lea     rax, [rbp+var_38]
0x18004c746  mov     [rsp+140h+var_C0], rax; __int64
0x18004c74e  lea     rax, [rbp+var_30]
0x18004c752  mov     [rsp+140h+var_C8], rax; __int64
0x18004c757  lea     rax, [rbp+var_68]
0x18004c75b  mov     [rsp+140h+var_D0], rax; __int64
0x18004c760  lea     rax, [rbp+var_28]
0x18004c764  mov     [rsp+140h+var_D8], rax; __int64
0x18004c769  lea     rax, [rbp+var_68+4]
0x18004c76d  mov     [rsp+140h+var_E0], rax; __int64
0x18004c772  lea     rax, [rbp+var_20]
0x18004c776  mov     [rsp+140h+var_E8], rax; __int64
0x18004c77b  lea     rax, [rbp+var_60]
0x18004c77f  mov     [rsp+140h+var_F0], rax; __int64
0x18004c784  lea     rax, [rbp+var_18]
0x18004c788  mov     [rsp+140h+var_F8], rax; __int64
0x18004c78d  lea     rax, [rbp+var_78]
0x18004c791  mov     [rsp+140h+var_100], rax; __int64
0x18004c796  lea     rax, [rbp+var_10]
0x18004c79a  mov     [rsp+140h+var_108], rax; __int64
0x18004c79f  lea     rax, [rbp+SRWLock]
0x18004c7a3  mov     [rsp+140h+var_110], rax; __int64
0x18004c7a8  lea     rax, [rbp+var_8]
0x18004c7ac  mov     [rsp+140h+var_118], rax; __int64
0x18004c7b1  lea     rax, [rbp+var_58]
0x18004c7b5  mov     [rsp+140h+var_120], rax; __int64
0x18004c7ba  lea     rdx, byte_1800C7985; int
0x18004c7c1  mov     rcx, r9; int
0x18004c7c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004c7c9  jmp     loc_18004C878
0x18004c7ce  mov     [rbp+SRWLock], 0
0x18004c7d6  lea     rdx, [rbp+SRWLock]
0x18004c7da  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18004c7df  mov     rax, [rbx+110h]
0x18004c7e6  mov     dword ptr [rax], 2
0x18004c7ec  mov     rcx, [rbp+SRWLock]; SRWLock
0x18004c7f0  test    rcx, rcx
0x18004c7f3  jz      short loc_18004C7FB
0x18004c7f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c7fb  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18004c800  mov     rdi, rax
0x18004c803  mov     ecx, [rax]
0x18004c805  cmp     ecx, 4
0x18004c808  jbe     short loc_18004C878
0x18004c80a  mov     rax, [rax+18h]
0x18004c80e  mov     rcx, [rdi+10h]
0x18004c812  mov     edx, 10000h
0x18004c817  test    rdx, rcx
0x18004c81a  jz      short loc_18004C878
0x18004c81c  mov     rcx, rax
0x18004c81f  and     rcx, rdx
0x18004c822  cmp     rcx, rax
0x18004c825  jnz     short loc_18004C878
0x18004c827  call    cs:__imp_GetCurrentThreadId
0x18004c82d  mov     dword ptr [rbp+SRWLock], eax
0x18004c830  mov     r8, [rbx+110h]
0x18004c837  mov     eax, [r8+48h]
0x18004c83b  mov     dword ptr [rbp+var_78], eax
0x18004c83e  mov     [rbp+var_58], 0
0x18004c846  add     r8, 8
0x18004c84a  lea     rax, [rbp+SRWLock]
0x18004c84e  mov     [rsp+140h+var_110], rax
0x18004c853  lea     rax, [rbp+var_78]
0x18004c857  mov     [rsp+140h+var_118], rax
0x18004c85c  lea     rax, [rbp+var_58]
0x18004c860  mov     [rsp+140h+var_120], rax
0x18004c865  xor     r9d, r9d
0x18004c868  lea     rdx, unk_1800C8370
0x18004c86f  mov     rcx, rdi
0x18004c872  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004c877  nop
0x18004c878  lea     rcx, [rbx+120h]; this
0x18004c87f  cmp     dword ptr [rcx+18h], 0
0x18004c883  jz      short loc_18004C88B
0x18004c885  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18004c88a  nop
0x18004c88b  lea     r11, [rsp+140h+var_s0]
0x18004c893  mov     rbx, [r11+18h]
0x18004c897  mov     rdi, [r11+20h]
0x18004c89b  mov     rsp, r11
0x18004c89e  pop     rbp
0x18004c89f  retn
```
