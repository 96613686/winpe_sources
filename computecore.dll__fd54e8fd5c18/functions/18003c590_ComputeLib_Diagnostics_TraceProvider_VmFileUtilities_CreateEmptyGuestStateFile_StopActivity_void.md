# ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyGuestStateFile::StopActivity(void)

- ea: `0x18003c590`
- end: `0x18003c866`
- name: `?StopActivity@VmFileUtilities_CreateEmptyGuestStateFile@TraceProvider@Diagnostics@ComputeLib@@MEAAXXZ`
- size: `726`
- prototype: `void __fastcall(ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyGuestStateFile *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x180014de4`
- `0x18001558c`
- `0x18003c590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c5f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c7c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c5f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c7c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c7ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c7ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyGuestStateFile::StopActivity(
        ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyGuestStateFile *this)
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
      if ( (*((_QWORD *)v6 + 2) & 0x40) != 0 && (v7 & 0x40) == v7 )
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
          (int)&word_1800C7476,
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
      if ( (*((_QWORD *)v9 + 2) & 0x40) != 0 && (v10 & 0x40) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800C6731,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeLib::Diagnostics::TraceProvider::VmFileUtilities_CreateEmptyGuestStateFile *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003c590  mov     [rsp-8+arg_8], rbx
0x18003c595  mov     [rsp-8+arg_10], rdi
0x18003c59a  push    rbp
0x18003c59b  mov     rbp, rsp
0x18003c59e  sub     rsp, 140h
0x18003c5a5  mov     rbx, rcx
0x18003c5a8  mov     rdi, [rcx+110h]
0x18003c5af  mov     eax, [rdi+48h]
0x18003c5b2  test    eax, eax
0x18003c5b4  jns     loc_18003C799
0x18003c5ba  add     rdi, 50h ; 'P'
0x18003c5be  cmp     eax, [rdi+8]
0x18003c5c1  jnz     loc_18003C799
0x18003c5c7  test    rdi, rdi
0x18003c5ca  jz      loc_18003C799
0x18003c5d0  mov     [rbp+SRWLock], 0
0x18003c5d8  lea     rdx, [rbp+SRWLock]
0x18003c5dc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003c5e1  mov     rax, [rbx+110h]
0x18003c5e8  mov     dword ptr [rax], 2
0x18003c5ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003c5f2  test    rcx, rcx
0x18003c5f5  jz      short loc_18003C5FD
0x18003c5f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c5fd  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003c602  mov     r9, rax
0x18003c605  mov     ecx, [rax]
0x18003c607  cmp     ecx, 4
0x18003c60a  jbe     loc_18003C83E
0x18003c610  mov     rax, [rax+18h]
0x18003c614  mov     rcx, [r9+10h]
0x18003c618  test    cl, 40h
0x18003c61b  jz      loc_18003C83E
0x18003c621  mov     rcx, rax
0x18003c624  and     ecx, 40h
0x18003c627  cmp     rcx, rax
0x18003c62a  jnz     loc_18003C83E
0x18003c630  mov     rax, [rdi+30h]
0x18003c634  mov     [rbp+var_50], rax
0x18003c638  mov     eax, [rdi+44h]
0x18003c63b  mov     dword ptr [rbp+var_78+4], eax
0x18003c63e  mov     eax, [rdi+10h]
0x18003c641  mov     dword ptr [rbp+var_70], eax
0x18003c644  mov     rax, [rdi+78h]
0x18003c648  mov     [rbp+var_48], rax
0x18003c64c  mov     rax, [rdi+70h]
0x18003c650  mov     [rbp+var_40], rax
0x18003c654  mov     eax, [rdi+68h]
0x18003c657  mov     dword ptr [rbp+var_70+4], eax
0x18003c65a  mov     rax, [rdi+60h]
0x18003c65e  mov     [rbp+var_38], rax
0x18003c662  mov     rax, [rdi+58h]
0x18003c666  mov     [rbp+var_30], rax
0x18003c66a  mov     eax, [rdi+50h]
0x18003c66d  mov     dword ptr [rbp+var_68], eax
0x18003c670  mov     rax, [rdi+48h]
0x18003c674  mov     [rbp+var_28], rax
0x18003c678  mov     eax, [rdi+20h]
0x18003c67b  mov     dword ptr [rbp+var_68+4], eax
0x18003c67e  mov     rax, [rdi+18h]
0x18003c682  mov     [rbp+var_20], rax
0x18003c686  mov     eax, [rdi]
0x18003c688  mov     [rbp+var_60], eax
0x18003c68b  mov     rax, [rdi+80h]
0x18003c692  mov     [rbp+var_18], rax
0x18003c696  mov     eax, [rdi+40h]
0x18003c699  mov     dword ptr [rbp+var_78], eax
0x18003c69c  mov     rax, [rdi+38h]
0x18003c6a0  mov     [rbp+var_10], rax
0x18003c6a4  mov     eax, [rdi+8]
0x18003c6a7  mov     dword ptr [rbp+SRWLock], eax
0x18003c6aa  mov     [rbp+var_8], 1000000h
0x18003c6b2  mov     [rbp+var_58], 0
0x18003c6ba  mov     r8, [rbx+110h]
0x18003c6c1  add     r8, 8; int
0x18003c6c5  lea     rax, [rbp+var_50]
0x18003c6c9  mov     [rsp+140h+var_90], rax; __int64
0x18003c6d1  lea     rax, [rbp+var_78+4]
0x18003c6d5  mov     [rsp+140h+var_98], rax; __int64
0x18003c6dd  lea     rax, [rbp+var_70]
0x18003c6e1  mov     [rsp+140h+var_A0], rax; __int64
0x18003c6e9  lea     rax, [rbp+var_48]
0x18003c6ed  mov     [rsp+140h+var_A8], rax; __int64
0x18003c6f5  lea     rax, [rbp+var_40]
0x18003c6f9  mov     [rsp+140h+var_B0], rax; __int64
0x18003c701  lea     rax, [rbp+var_70+4]
0x18003c705  mov     [rsp+140h+var_B8], rax; __int64
0x18003c70d  lea     rax, [rbp+var_38]
0x18003c711  mov     [rsp+140h+var_C0], rax; __int64
0x18003c719  lea     rax, [rbp+var_30]
0x18003c71d  mov     [rsp+140h+var_C8], rax; __int64
0x18003c722  lea     rax, [rbp+var_68]
0x18003c726  mov     [rsp+140h+var_D0], rax; __int64
0x18003c72b  lea     rax, [rbp+var_28]
0x18003c72f  mov     [rsp+140h+var_D8], rax; __int64
0x18003c734  lea     rax, [rbp+var_68+4]
0x18003c738  mov     [rsp+140h+var_E0], rax; __int64
0x18003c73d  lea     rax, [rbp+var_20]
0x18003c741  mov     [rsp+140h+var_E8], rax; __int64
0x18003c746  lea     rax, [rbp+var_60]
0x18003c74a  mov     [rsp+140h+var_F0], rax; __int64
0x18003c74f  lea     rax, [rbp+var_18]
0x18003c753  mov     [rsp+140h+var_F8], rax; __int64
0x18003c758  lea     rax, [rbp+var_78]
0x18003c75c  mov     [rsp+140h+var_100], rax; __int64
0x18003c761  lea     rax, [rbp+var_10]
0x18003c765  mov     [rsp+140h+var_108], rax; __int64
0x18003c76a  lea     rax, [rbp+SRWLock]
0x18003c76e  mov     [rsp+140h+var_110], rax; __int64
0x18003c773  lea     rax, [rbp+var_8]
0x18003c777  mov     [rsp+140h+var_118], rax; __int64
0x18003c77c  lea     rax, [rbp+var_58]
0x18003c780  mov     [rsp+140h+var_120], rax; __int64
0x18003c785  lea     rdx, word_1800C7476; int
0x18003c78c  mov     rcx, r9; int
0x18003c78f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003c794  jmp     loc_18003C83E
0x18003c799  mov     [rbp+SRWLock], 0
0x18003c7a1  lea     rdx, [rbp+SRWLock]
0x18003c7a5  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003c7aa  mov     rax, [rbx+110h]
0x18003c7b1  mov     dword ptr [rax], 2
0x18003c7b7  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003c7bb  test    rcx, rcx
0x18003c7be  jz      short loc_18003C7C6
0x18003c7c0  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c7c6  call    ?Provider@TraceProvider@Diagnostics@ComputeLib@@SAPEBU_tlgProvider_t@@XZ; ComputeLib::Diagnostics::TraceProvider::Provider(void)
0x18003c7cb  mov     rdi, rax
0x18003c7ce  mov     ecx, [rax]
0x18003c7d0  cmp     ecx, 4
0x18003c7d3  jbe     short loc_18003C83E
0x18003c7d5  mov     rax, [rax+18h]
0x18003c7d9  mov     rcx, [rdi+10h]
0x18003c7dd  test    cl, 40h
0x18003c7e0  jz      short loc_18003C83E
0x18003c7e2  mov     rcx, rax
0x18003c7e5  and     ecx, 40h
0x18003c7e8  cmp     rcx, rax
0x18003c7eb  jnz     short loc_18003C83E
0x18003c7ed  call    cs:__imp_GetCurrentThreadId
0x18003c7f3  mov     dword ptr [rbp+SRWLock], eax
0x18003c7f6  mov     r8, [rbx+110h]
0x18003c7fd  mov     eax, [r8+48h]
0x18003c801  mov     dword ptr [rbp+var_78], eax
0x18003c804  mov     [rbp+var_58], 0
0x18003c80c  add     r8, 8
0x18003c810  lea     rax, [rbp+SRWLock]
0x18003c814  mov     [rsp+140h+var_110], rax
0x18003c819  lea     rax, [rbp+var_78]
0x18003c81d  mov     [rsp+140h+var_118], rax
0x18003c822  lea     rax, [rbp+var_58]
0x18003c826  mov     [rsp+140h+var_120], rax
0x18003c82b  xor     r9d, r9d
0x18003c82e  lea     rdx, byte_1800C6731
0x18003c835  mov     rcx, rdi
0x18003c838  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003c83d  nop
0x18003c83e  lea     rcx, [rbx+120h]; this
0x18003c845  cmp     dword ptr [rcx+18h], 0
0x18003c849  jz      short loc_18003C851
0x18003c84b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003c850  nop
0x18003c851  lea     r11, [rsp+140h+var_s0]
0x18003c859  mov     rbx, [r11+18h]
0x18003c85d  mov     rdi, [r11+20h]
0x18003c861  mov     rsp, r11
0x18003c864  pop     rbp
0x18003c865  retn
```
