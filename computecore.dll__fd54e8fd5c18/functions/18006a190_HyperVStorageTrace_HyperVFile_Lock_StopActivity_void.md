# HyperVStorageTrace::HyperVFile_Lock::StopActivity(void)

- ea: `0x18006a190`
- end: `0x18006a463`
- name: `?StopActivity@HyperVFile_Lock@HyperVStorageTrace@@MEAAXXZ`
- size: `723`
- prototype: `void __fastcall(HyperVStorageTrace::HyperVFile_Lock *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180066284`
- `0x18006a190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a1f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a3bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a1f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006a3bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a3ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a3ea`

## pseudocode

```c
void __fastcall HyperVStorageTrace::HyperVFile_Lock::StopActivity(HyperVStorageTrace::HyperVFile_Lock *this)
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
        (int)&word_1800CB156,
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
        (unsigned int)qword_1800CB2A0,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((HyperVStorageTrace::HyperVFile_Lock *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006a190  mov     [rsp-8+arg_8], rbx
0x18006a195  mov     [rsp-8+arg_10], rdi
0x18006a19a  push    rbp
0x18006a19b  mov     rbp, rsp
0x18006a19e  sub     rsp, 140h
0x18006a1a5  mov     rbx, rcx
0x18006a1a8  mov     rdi, [rcx+110h]
0x18006a1af  mov     eax, [rdi+48h]
0x18006a1b2  test    eax, eax
0x18006a1b4  jns     loc_18006A396
0x18006a1ba  add     rdi, 50h ; 'P'
0x18006a1be  cmp     eax, [rdi+8]
0x18006a1c1  jnz     loc_18006A396
0x18006a1c7  test    rdi, rdi
0x18006a1ca  jz      loc_18006A396
0x18006a1d0  mov     [rbp+SRWLock], 0
0x18006a1d8  lea     rdx, [rbp+SRWLock]
0x18006a1dc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006a1e1  mov     rax, [rbx+110h]
0x18006a1e8  mov     dword ptr [rax], 2
0x18006a1ee  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006a1f2  test    rcx, rcx
0x18006a1f5  jz      short loc_18006A1FD
0x18006a1f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a1fd  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006a202  mov     rcx, [rax+8]; int
0x18006a206  mov     eax, [rcx]
0x18006a208  cmp     eax, 4
0x18006a20b  jbe     loc_18006A43B
0x18006a211  mov     rdx, [rcx+18h]
0x18006a215  mov     rax, [rcx+10h]
0x18006a219  test    al, 2
0x18006a21b  jz      loc_18006A43B
0x18006a221  mov     rax, rdx
0x18006a224  and     eax, 2
0x18006a227  cmp     rax, rdx
0x18006a22a  jnz     loc_18006A43B
0x18006a230  mov     rax, [rdi+30h]
0x18006a234  mov     [rbp+var_50], rax
0x18006a238  mov     eax, [rdi+44h]
0x18006a23b  mov     dword ptr [rbp+var_78+4], eax
0x18006a23e  mov     eax, [rdi+10h]
0x18006a241  mov     dword ptr [rbp+var_70], eax
0x18006a244  mov     rax, [rdi+78h]
0x18006a248  mov     [rbp+var_48], rax
0x18006a24c  mov     rax, [rdi+70h]
0x18006a250  mov     [rbp+var_40], rax
0x18006a254  mov     eax, [rdi+68h]
0x18006a257  mov     dword ptr [rbp+var_70+4], eax
0x18006a25a  mov     rax, [rdi+60h]
0x18006a25e  mov     [rbp+var_38], rax
0x18006a262  mov     rax, [rdi+58h]
0x18006a266  mov     [rbp+var_30], rax
0x18006a26a  mov     eax, [rdi+50h]
0x18006a26d  mov     dword ptr [rbp+var_68], eax
0x18006a270  mov     rax, [rdi+48h]
0x18006a274  mov     [rbp+var_28], rax
0x18006a278  mov     eax, [rdi+20h]
0x18006a27b  mov     dword ptr [rbp+var_68+4], eax
0x18006a27e  mov     rax, [rdi+18h]
0x18006a282  mov     [rbp+var_20], rax
0x18006a286  mov     eax, [rdi]
0x18006a288  mov     [rbp+var_60], eax
0x18006a28b  mov     rax, [rdi+80h]
0x18006a292  mov     [rbp+var_18], rax
0x18006a296  mov     eax, [rdi+40h]
0x18006a299  mov     dword ptr [rbp+var_78], eax
0x18006a29c  mov     rax, [rdi+38h]
0x18006a2a0  mov     [rbp+var_10], rax
0x18006a2a4  mov     eax, [rdi+8]
0x18006a2a7  mov     dword ptr [rbp+SRWLock], eax
0x18006a2aa  mov     [rbp+var_8], 1000000h
0x18006a2b2  mov     [rbp+var_58], 0
0x18006a2ba  mov     r8, [rbx+110h]
0x18006a2c1  add     r8, 8; int
0x18006a2c5  lea     rax, [rbp+var_50]
0x18006a2c9  mov     [rsp+140h+var_90], rax; __int64
0x18006a2d1  lea     rax, [rbp+var_78+4]
0x18006a2d5  mov     [rsp+140h+var_98], rax; __int64
0x18006a2dd  lea     rax, [rbp+var_70]
0x18006a2e1  mov     [rsp+140h+var_A0], rax; __int64
0x18006a2e9  lea     rax, [rbp+var_48]
0x18006a2ed  mov     [rsp+140h+var_A8], rax; __int64
0x18006a2f5  lea     rax, [rbp+var_40]
0x18006a2f9  mov     [rsp+140h+var_B0], rax; __int64
0x18006a301  lea     rax, [rbp+var_70+4]
0x18006a305  mov     [rsp+140h+var_B8], rax; __int64
0x18006a30d  lea     rax, [rbp+var_38]
0x18006a311  mov     [rsp+140h+var_C0], rax; __int64
0x18006a319  lea     rax, [rbp+var_30]
0x18006a31d  mov     [rsp+140h+var_C8], rax; __int64
0x18006a322  lea     rax, [rbp+var_68]
0x18006a326  mov     [rsp+140h+var_D0], rax; __int64
0x18006a32b  lea     rax, [rbp+var_28]
0x18006a32f  mov     [rsp+140h+var_D8], rax; __int64
0x18006a334  lea     rax, [rbp+var_68+4]
0x18006a338  mov     [rsp+140h+var_E0], rax; __int64
0x18006a33d  lea     rax, [rbp+var_20]
0x18006a341  mov     [rsp+140h+var_E8], rax; __int64
0x18006a346  lea     rax, [rbp+var_60]
0x18006a34a  mov     [rsp+140h+var_F0], rax; __int64
0x18006a34f  lea     rax, [rbp+var_18]
0x18006a353  mov     [rsp+140h+var_F8], rax; __int64
0x18006a358  lea     rax, [rbp+var_78]
0x18006a35c  mov     [rsp+140h+var_100], rax; __int64
0x18006a361  lea     rax, [rbp+var_10]
0x18006a365  mov     [rsp+140h+var_108], rax; __int64
0x18006a36a  lea     rax, [rbp+SRWLock]
0x18006a36e  mov     [rsp+140h+var_110], rax; __int64
0x18006a373  lea     rax, [rbp+var_8]
0x18006a377  mov     [rsp+140h+var_118], rax; __int64
0x18006a37c  lea     rax, [rbp+var_58]
0x18006a380  mov     [rsp+140h+var_120], rax; __int64
0x18006a385  lea     rdx, word_1800CB156; int
0x18006a38c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006a391  jmp     loc_18006A43B
0x18006a396  mov     [rbp+SRWLock], 0
0x18006a39e  lea     rdx, [rbp+SRWLock]
0x18006a3a2  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006a3a7  mov     rax, [rbx+110h]
0x18006a3ae  mov     dword ptr [rax], 2
0x18006a3b4  mov     rcx, [rbp+SRWLock]; SRWLock
0x18006a3b8  test    rcx, rcx
0x18006a3bb  jz      short loc_18006A3C3
0x18006a3bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18006a3c3  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x18006a3c8  mov     rdi, [rax+8]
0x18006a3cc  mov     eax, [rdi]
0x18006a3ce  cmp     eax, 4
0x18006a3d1  jbe     short loc_18006A43B
0x18006a3d3  mov     rcx, [rdi+18h]
0x18006a3d7  mov     rax, [rdi+10h]
0x18006a3db  test    al, 2
0x18006a3dd  jz      short loc_18006A43B
0x18006a3df  mov     rax, rcx
0x18006a3e2  and     eax, 2
0x18006a3e5  cmp     rax, rcx
0x18006a3e8  jnz     short loc_18006A43B
0x18006a3ea  call    cs:__imp_GetCurrentThreadId
0x18006a3f0  mov     dword ptr [rbp+SRWLock], eax
0x18006a3f3  mov     r8, [rbx+110h]
0x18006a3fa  mov     eax, [r8+48h]
0x18006a3fe  mov     dword ptr [rbp+var_78], eax
0x18006a401  mov     [rbp+var_58], 0
0x18006a409  add     r8, 8
0x18006a40d  lea     rax, [rbp+SRWLock]
0x18006a411  mov     [rsp+140h+var_110], rax
0x18006a416  lea     rax, [rbp+var_78]
0x18006a41a  mov     [rsp+140h+var_118], rax
0x18006a41f  lea     rax, [rbp+var_58]
0x18006a423  mov     [rsp+140h+var_120], rax
0x18006a428  xor     r9d, r9d
0x18006a42b  lea     rdx, qword_1800CB2A0
0x18006a432  mov     rcx, rdi
0x18006a435  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a43a  nop
0x18006a43b  lea     rcx, [rbx+120h]; this
0x18006a442  cmp     dword ptr [rcx+18h], 0
0x18006a446  jz      short loc_18006A44E
0x18006a448  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18006a44d  nop
0x18006a44e  lea     r11, [rsp+140h+var_s0]
0x18006a456  mov     rbx, [r11+18h]
0x18006a45a  mov     rdi, [r11+20h]
0x18006a45e  mov     rsp, r11
0x18006a461  pop     rbp
0x18006a462  retn
```
