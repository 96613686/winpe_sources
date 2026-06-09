# HyperVStorageTrace::HyperVFile_OpenAndLock::StopActivity(void)

- ea: `0x18006a750`
- end: `0x18006aa23`
- name: `?StopActivity@HyperVFile_OpenAndLock@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_OpenAndLock *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x18006a750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a97d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a7b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a97d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a9aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a9aa`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_OpenAndLock::StopActivity(
        HyperVStorageTrace::HyperVFile_OpenAndLock *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v9; // [rsp+C8h] [rbp-78h] BYREF
  int v10; // [rsp+CCh] [rbp-74h] BYREF
  int v11; // [rsp+D0h] [rbp-70h] BYREF
  int v12; // [rsp+D4h] [rbp-6Ch] BYREF
  int v13; // [rsp+D8h] [rbp-68h] BYREF
  int v14; // [rsp+DCh] [rbp-64h] BYREF
  int v15; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v17; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v18; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v19; // [rsp+100h] [rbp-40h] BYREF
  __int64 v20; // [rsp+108h] [rbp-38h] BYREF
  __int64 v21; // [rsp+110h] [rbp-30h] BYREF
  __int64 v22; // [rsp+118h] [rbp-28h] BYREF
  __int64 v23; // [rsp+120h] [rbp-20h] BYREF
  __int64 v24; // [rsp+128h] [rbp-18h] BYREF
  __int64 v25; // [rsp+130h] [rbp-10h] BYREF
  __int64 v26; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u && (*(_QWORD *)(v5 + 16) & 2) != 0 && (*(_QWORD *)(v5 + 24) & 2LL) == *(_QWORD *)(v5 + 24) )
    {
      v17 = *((_QWORD *)v4 + 6);
      v10 = v4[17];
      v11 = v4[4];
      v18 = *((_QWORD *)v4 + 15);
      v19 = *((_QWORD *)v4 + 14);
      v12 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v13 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v9 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (int)&word_1800CBB6A,
        *((_QWORD *)this + 34) + 8,
        (__int64)&v16,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v25,
        (__int64)&v9,
        (__int64)&v24,
        (__int64)&v15,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v12,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v11,
        (__int64)&v10,
        (__int64)&v17);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)HyperVStorageTrace::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u && (*(_QWORD *)(v6 + 16) & 2) != 0 && (*(_QWORD *)(v6 + 24) & 2LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_1800CBCBB,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_OpenAndLock *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006a750  mov     [rsp-8+arg_8], rbx
0x18006a755  mov     [rsp-8+arg_10], rdi
0x18006a75a  push    rbp
0x18006a75b  mov     rbp, rsp
0x18006a75e  sub     rsp, 140h
0x18006a765  mov     rbx, rcx
0x18006a768  mov     rdi, [rcx+110h]
0x18006a76f  mov     eax, [rdi+48h]
0x18006a772  test    eax, eax
0x18006a774  jns     loc_18006A956
0x18006a77a  add     rdi, 50h ; 'P'
0x18006a77e  cmp     eax, [rdi+8]
0x18006a781  jnz     loc_18006A956
0x18006a787  test    rdi, rdi
0x18006a78a  jz      loc_18006A956
0x18006a790  mov     [rbp+SRWLock], 0
0x18006a798  lea     rdx, [rbp+SRWLock]
0x18006a79c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006a7a1  mov     rax, [rbx+110h]
0x18006a7a8  mov     dword ptr [rax], 2
0x18006a7ae  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006a7b2  test    rcx, rcx
0x18006a7b5  jz      short loc_18006A7BD
0x18006a7b7  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a7bd  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006a7c2  mov     rcx, [rax+8]; int
0x18006a7c6  mov     eax, [rcx]
0x18006a7c8  cmp     eax, 4
0x18006a7cb  jbe     loc_18006A9FB
0x18006a7d1  mov     rdx, [rcx+18h]
0x18006a7d5  mov     rax, [rcx+10h]
0x18006a7d9  test    al, 2
0x18006a7db  jz      loc_18006A9FB
0x18006a7e1  mov     rax, rdx
0x18006a7e4  and     eax, 2
0x18006a7e7  cmp     rax, rdx
0x18006a7ea  jnz     loc_18006A9FB
0x18006a7f0  mov     rax, [rdi+30h]
0x18006a7f4  mov     [rbp+var_50], rax
0x18006a7f8  mov     eax, [rdi+44h]
0x18006a7fb  mov     dword ptr [rbp+var_78+4], eax
0x18006a7fe  mov     eax, [rdi+10h]
0x18006a801  mov     dword ptr [rbp+var_70], eax
0x18006a804  mov     rax, [rdi+78h]
0x18006a808  mov     [rbp+var_48], rax
0x18006a80c  mov     rax, [rdi+70h]
0x18006a810  mov     [rbp+var_40], rax
0x18006a814  mov     eax, [rdi+68h]
0x18006a817  mov     dword ptr [rbp+var_70+4], eax
0x18006a81a  mov     rax, [rdi+60h]
0x18006a81e  mov     [rbp+var_38], rax
0x18006a822  mov     rax, [rdi+58h]
0x18006a826  mov     [rbp+var_30], rax
0x18006a82a  mov     eax, [rdi+50h]
0x18006a82d  mov     dword ptr [rbp+var_68], eax
0x18006a830  mov     rax, [rdi+48h]
0x18006a834  mov     [rbp+var_28], rax
0x18006a838  mov     eax, [rdi+20h]
0x18006a83b  mov     dword ptr [rbp+var_68+4], eax
0x18006a83e  mov     rax, [rdi+18h]
0x18006a842  mov     [rbp+var_20], rax
0x18006a846  mov     eax, [rdi]
0x18006a848  mov     [rbp+var_60], eax
0x18006a84b  mov     rax, [rdi+80h]
0x18006a852  mov     [rbp+var_18], rax
0x18006a856  mov     eax, [rdi+40h]
0x18006a859  mov     dword ptr [rbp+var_78], eax
0x18006a85c  mov     rax, [rdi+38h]
0x18006a860  mov     [rbp+var_10], rax
0x18006a864  mov     eax, [rdi+8]
0x18006a867  mov     dword ptr [rbp+SRWLock], eax
0x18006a86a  mov     [rbp+var_8], 1000000h
0x18006a872  mov     [rbp+var_58], 0
0x18006a87a  mov     r8, [rbx+110h]
0x18006a881  add     r8, 8; int
0x18006a885  lea     rax, [rbp+var_50]
0x18006a889  mov     [rsp+140h+var_90], rax; __int64
0x18006a891  lea     rax, [rbp+var_78+4]
0x18006a895  mov     [rsp+140h+var_98], rax; __int64
0x18006a89d  lea     rax, [rbp+var_70]
0x18006a8a1  mov     [rsp+140h+var_A0], rax; __int64
0x18006a8a9  lea     rax, [rbp+var_48]
0x18006a8ad  mov     [rsp+140h+var_A8], rax; __int64
0x18006a8b5  lea     rax, [rbp+var_40]
0x18006a8b9  mov     [rsp+140h+var_B0], rax; __int64
0x18006a8c1  lea     rax, [rbp+var_70+4]
0x18006a8c5  mov     [rsp+140h+var_B8], rax; __int64
0x18006a8cd  lea     rax, [rbp+var_38]
0x18006a8d1  mov     [rsp+140h+var_C0], rax; __int64
0x18006a8d9  lea     rax, [rbp+var_30]
0x18006a8dd  mov     [rsp+140h+var_C8], rax; __int64
0x18006a8e2  lea     rax, [rbp+var_68]
0x18006a8e6  mov     [rsp+140h+var_D0], rax; __int64
0x18006a8eb  lea     rax, [rbp+var_28]
0x18006a8ef  mov     [rsp+140h+var_D8], rax; __int64
0x18006a8f4  lea     rax, [rbp+var_68+4]
0x18006a8f8  mov     [rsp+140h+var_E0], rax; __int64
0x18006a8fd  lea     rax, [rbp+var_20]
0x18006a901  mov     [rsp+140h+var_E8], rax; __int64
0x18006a906  lea     rax, [rbp+var_60]
0x18006a90a  mov     [rsp+140h+var_F0], rax; __int64
0x18006a90f  lea     rax, [rbp+var_18]
0x18006a913  mov     [rsp+140h+var_F8], rax; __int64
0x18006a918  lea     rax, [rbp+var_78]
0x18006a91c  mov     [rsp+140h+var_100], rax; __int64
0x18006a921  lea     rax, [rbp+var_10]
0x18006a925  mov     [rsp+140h+var_108], rax; __int64
0x18006a92a  lea     rax, [rbp+SRWLock]
0x18006a92e  mov     [rsp+140h+var_110], rax; __int64
0x18006a933  lea     rax, [rbp+var_8]
0x18006a937  mov     [rsp+140h+var_118], rax; __int64
0x18006a93c  lea     rax, [rbp+var_58]
0x18006a940  mov     [rsp+140h+var_120], rax; __int64
0x18006a945  lea     rdx, word_1800CBB6A; int
0x18006a94c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006a951  jmp     loc_18006A9FB
0x18006a956  mov     [rbp+SRWLock], 0
0x18006a95e  lea     rdx, [rbp+SRWLock]
0x18006a962  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006a967  mov     rax, [rbx+110h]
0x18006a96e  mov     dword ptr [rax], 2
0x18006a974  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006a978  test    rcx, rcx
0x18006a97b  jz      short loc_18006A983
0x18006a97d  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a983  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006a988  mov     rdi, [rax+8]
0x18006a98c  mov     eax, [rdi]
0x18006a98e  cmp     eax, 4
0x18006a991  jbe     short loc_18006A9FB
0x18006a993  mov     rcx, [rdi+18h]
0x18006a997  mov     rax, [rdi+10h]
0x18006a99b  test    al, 2
0x18006a99d  jz      short loc_18006A9FB
0x18006a99f  mov     rax, rcx
0x18006a9a2  and     eax, 2
0x18006a9a5  cmp     rax, rcx
0x18006a9a8  jnz     short loc_18006A9FB
0x18006a9aa  call    cs:__imp_GetCurrentThreadId
0x18006a9b0  mov     dword ptr [rbp+SRWLock], eax
0x18006a9b3  mov     r8, [rbx+110h]
0x18006a9ba  mov     eax, [r8+48h]
0x18006a9be  mov     dword ptr [rbp+var_78], eax
0x18006a9c1  mov     [rbp+var_58], 0
0x18006a9c9  add     r8, 8
0x18006a9cd  lea     rax, [rbp+SRWLock]
0x18006a9d1  mov     [rsp+140h+var_110], rax
0x18006a9d6  lea     rax, [rbp+var_78]
0x18006a9da  mov     [rsp+140h+var_118], rax
0x18006a9df  lea     rax, [rbp+var_58]
0x18006a9e3  mov     [rsp+140h+var_120], rax
0x18006a9e8  xor     r9d, r9d
0x18006a9eb  lea     rdx, byte_1800CBCBB
0x18006a9f2  mov     rcx, rdi
0x18006a9f5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a9fa  nop
0x18006a9fb  lea     rcx, [rbx+120h]; this
0x18006aa02  cmp     dword ptr [rcx+18h], 0
0x18006aa06  jz      short loc_18006AA0E
0x18006aa08  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18006aa0d  nop
0x18006aa0e  lea     r11, [rsp+140h+var_s0]
0x18006aa16  mov     rbx, [r11+18h]
0x18006aa1a  mov     rdi, [r11+20h]
0x18006aa1e  mov     rsp, r11
0x18006aa21  pop     rbp
0x18006aa22  retn
```
