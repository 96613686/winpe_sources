# HyperVStorageTrace::HyperVFile_Close::StopActivity(void)

- ea: `0x1800698f0`
- end: `0x180069bc3`
- name: `?StopActivity@HyperVFile_Close@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Close *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x1800698f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069957`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069957`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180069b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180069b4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HyperVStorageTrace::HyperVFile_Close::StopActivity(HyperVStorageTrace::HyperVFile_Close *this)
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
        (int)&byte_1800CBD63,
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
        (unsigned int)word_1800CBD12,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Close *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800698f0  mov     [rsp-8+arg_8], rbx
0x1800698f5  mov     [rsp-8+arg_10], rdi
0x1800698fa  push    rbp
0x1800698fb  mov     rbp, rsp
0x1800698fe  sub     rsp, 140h
0x180069905  mov     rbx, rcx
0x180069908  mov     rdi, [rcx+110h]
0x18006990f  mov     eax, [rdi+48h]
0x180069912  test    eax, eax
0x180069914  jns     loc_180069AF6
0x18006991a  add     rdi, 50h ; 'P'
0x18006991e  cmp     eax, [rdi+8]
0x180069921  jnz     loc_180069AF6
0x180069927  test    rdi, rdi
0x18006992a  jz      loc_180069AF6
0x180069930  mov     [rbp+SRWLock], 0
0x180069938  lea     rdx, [rbp+SRWLock]
0x18006993c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069941  mov     rax, [rbx+110h]
0x180069948  mov     dword ptr [rax], 2
0x18006994e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180069952  test    rcx, rcx
0x180069955  jz      short loc_18006995D
0x180069957  call    cs:__imp_ReleaseSRWLockExclusive
0x18006995d  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180069962  mov     rcx, [rax+8]; int
0x180069966  mov     eax, [rcx]
0x180069968  cmp     eax, 4
0x18006996b  jbe     loc_180069B9B
0x180069971  mov     rdx, [rcx+18h]
0x180069975  mov     rax, [rcx+10h]
0x180069979  test    al, 2
0x18006997b  jz      loc_180069B9B
0x180069981  mov     rax, rdx
0x180069984  and     eax, 2
0x180069987  cmp     rax, rdx
0x18006998a  jnz     loc_180069B9B
0x180069990  mov     rax, [rdi+30h]
0x180069994  mov     [rbp+var_50], rax
0x180069998  mov     eax, [rdi+44h]
0x18006999b  mov     dword ptr [rbp+var_78+4], eax
0x18006999e  mov     eax, [rdi+10h]
0x1800699a1  mov     dword ptr [rbp+var_70], eax
0x1800699a4  mov     rax, [rdi+78h]
0x1800699a8  mov     [rbp+var_48], rax
0x1800699ac  mov     rax, [rdi+70h]
0x1800699b0  mov     [rbp+var_40], rax
0x1800699b4  mov     eax, [rdi+68h]
0x1800699b7  mov     dword ptr [rbp+var_70+4], eax
0x1800699ba  mov     rax, [rdi+60h]
0x1800699be  mov     [rbp+var_38], rax
0x1800699c2  mov     rax, [rdi+58h]
0x1800699c6  mov     [rbp+var_30], rax
0x1800699ca  mov     eax, [rdi+50h]
0x1800699cd  mov     dword ptr [rbp+var_68], eax
0x1800699d0  mov     rax, [rdi+48h]
0x1800699d4  mov     [rbp+var_28], rax
0x1800699d8  mov     eax, [rdi+20h]
0x1800699db  mov     dword ptr [rbp+var_68+4], eax
0x1800699de  mov     rax, [rdi+18h]
0x1800699e2  mov     [rbp+var_20], rax
0x1800699e6  mov     eax, [rdi]
0x1800699e8  mov     [rbp+var_60], eax
0x1800699eb  mov     rax, [rdi+80h]
0x1800699f2  mov     [rbp+var_18], rax
0x1800699f6  mov     eax, [rdi+40h]
0x1800699f9  mov     dword ptr [rbp+var_78], eax
0x1800699fc  mov     rax, [rdi+38h]
0x180069a00  mov     [rbp+var_10], rax
0x180069a04  mov     eax, [rdi+8]
0x180069a07  mov     dword ptr [rbp+SRWLock], eax
0x180069a0a  mov     [rbp+var_8], 1000000h
0x180069a12  mov     [rbp+var_58], 0
0x180069a1a  mov     r8, [rbx+110h]
0x180069a21  add     r8, 8; int
0x180069a25  lea     rax, [rbp+var_50]
0x180069a29  mov     [rsp+140h+var_90], rax; __int64
0x180069a31  lea     rax, [rbp+var_78+4]
0x180069a35  mov     [rsp+140h+var_98], rax; __int64
0x180069a3d  lea     rax, [rbp+var_70]
0x180069a41  mov     [rsp+140h+var_A0], rax; __int64
0x180069a49  lea     rax, [rbp+var_48]
0x180069a4d  mov     [rsp+140h+var_A8], rax; __int64
0x180069a55  lea     rax, [rbp+var_40]
0x180069a59  mov     [rsp+140h+var_B0], rax; __int64
0x180069a61  lea     rax, [rbp+var_70+4]
0x180069a65  mov     [rsp+140h+var_B8], rax; __int64
0x180069a6d  lea     rax, [rbp+var_38]
0x180069a71  mov     [rsp+140h+var_C0], rax; __int64
0x180069a79  lea     rax, [rbp+var_30]
0x180069a7d  mov     [rsp+140h+var_C8], rax; __int64
0x180069a82  lea     rax, [rbp+var_68]
0x180069a86  mov     [rsp+140h+var_D0], rax; __int64
0x180069a8b  lea     rax, [rbp+var_28]
0x180069a8f  mov     [rsp+140h+var_D8], rax; __int64
0x180069a94  lea     rax, [rbp+var_68+4]
0x180069a98  mov     [rsp+140h+var_E0], rax; __int64
0x180069a9d  lea     rax, [rbp+var_20]
0x180069aa1  mov     [rsp+140h+var_E8], rax; __int64
0x180069aa6  lea     rax, [rbp+var_60]
0x180069aaa  mov     [rsp+140h+var_F0], rax; __int64
0x180069aaf  lea     rax, [rbp+var_18]
0x180069ab3  mov     [rsp+140h+var_F8], rax; __int64
0x180069ab8  lea     rax, [rbp+var_78]
0x180069abc  mov     [rsp+140h+var_100], rax; __int64
0x180069ac1  lea     rax, [rbp+var_10]
0x180069ac5  mov     [rsp+140h+var_108], rax; __int64
0x180069aca  lea     rax, [rbp+SRWLock]
0x180069ace  mov     [rsp+140h+var_110], rax; __int64
0x180069ad3  lea     rax, [rbp+var_8]
0x180069ad7  mov     [rsp+140h+var_118], rax; __int64
0x180069adc  lea     rax, [rbp+var_58]
0x180069ae0  mov     [rsp+140h+var_120], rax; __int64
0x180069ae5  lea     rdx, byte_1800CBD63; int
0x180069aec  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180069af1  jmp     loc_180069B9B
0x180069af6  mov     [rbp+SRWLock], 0
0x180069afe  lea     rdx, [rbp+SRWLock]
0x180069b02  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180069b07  mov     rax, [rbx+110h]
0x180069b0e  mov     dword ptr [rax], 2
0x180069b14  mov     rcx, [rbp+SRWLock]; SRWLock
0x180069b18  test    rcx, rcx
0x180069b1b  jz      short loc_180069B23
0x180069b1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180069b23  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180069b28  mov     rdi, [rax+8]
0x180069b2c  mov     eax, [rdi]
0x180069b2e  cmp     eax, 4
0x180069b31  jbe     short loc_180069B9B
0x180069b33  mov     rcx, [rdi+18h]
0x180069b37  mov     rax, [rdi+10h]
0x180069b3b  test    al, 2
0x180069b3d  jz      short loc_180069B9B
0x180069b3f  mov     rax, rcx
0x180069b42  and     eax, 2
0x180069b45  cmp     rax, rcx
0x180069b48  jnz     short loc_180069B9B
0x180069b4a  call    cs:__imp_GetCurrentThreadId
0x180069b50  mov     dword ptr [rbp+SRWLock], eax
0x180069b53  mov     r8, [rbx+110h]
0x180069b5a  mov     eax, [r8+48h]
0x180069b5e  mov     dword ptr [rbp+var_78], eax
0x180069b61  mov     [rbp+var_58], 0
0x180069b69  add     r8, 8
0x180069b6d  lea     rax, [rbp+SRWLock]
0x180069b71  mov     [rsp+140h+var_110], rax
0x180069b76  lea     rax, [rbp+var_78]
0x180069b7a  mov     [rsp+140h+var_118], rax
0x180069b7f  lea     rax, [rbp+var_58]
0x180069b83  mov     [rsp+140h+var_120], rax
0x180069b88  xor     r9d, r9d
0x180069b8b  lea     rdx, word_1800CBD12
0x180069b92  mov     rcx, rdi
0x180069b95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069b9a  nop
0x180069b9b  lea     rcx, [rbx+120h]; this
0x180069ba2  cmp     dword ptr [rcx+18h], 0
0x180069ba6  jz      short loc_180069BAE
0x180069ba8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180069bad  nop
0x180069bae  lea     r11, [rsp+140h+var_s0]
0x180069bb6  mov     rbx, [r11+18h]
0x180069bba  mov     rdi, [r11+20h]
0x180069bbe  mov     rsp, r11
0x180069bc1  pop     rbp
0x180069bc2  retn
```
