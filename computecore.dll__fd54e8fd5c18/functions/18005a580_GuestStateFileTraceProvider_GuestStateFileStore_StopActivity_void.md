# GuestStateFileTraceProvider::GuestStateFileStore::StopActivity(void)

- ea: `0x18005a580`
- end: `0x18005a860`
- name: `?StopActivity@GuestStateFileStore@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileStore *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x18005a580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a5e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a5e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a7b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a7e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a7e7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileStore::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileStore *this)
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
    v5 = GuestStateFileTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x1000LL) != 0 && (v7 & 0x1000) == v7 )
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
          (int)&unk_1800CA978,
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
    v8 = GuestStateFileTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x1000LL) != 0 && (v10 & 0x1000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&dword_1800CA924,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileStore *)((char *)this + 288));
}

```

## disassembly

```asm
0x18005a580  mov     [rsp-8+arg_8], rbx
0x18005a585  mov     [rsp-8+arg_10], rdi
0x18005a58a  push    rbp
0x18005a58b  mov     rbp, rsp
0x18005a58e  sub     rsp, 140h
0x18005a595  mov     rbx, rcx
0x18005a598  mov     rdi, [rcx+110h]
0x18005a59f  mov     eax, [rdi+48h]
0x18005a5a2  test    eax, eax
0x18005a5a4  jns     loc_18005A78E
0x18005a5aa  add     rdi, 50h ; 'P'
0x18005a5ae  cmp     eax, [rdi+8]
0x18005a5b1  jnz     loc_18005A78E
0x18005a5b7  test    rdi, rdi
0x18005a5ba  jz      loc_18005A78E
0x18005a5c0  mov     [rbp+SRWLock], 0
0x18005a5c8  lea     rdx, [rbp+SRWLock]
0x18005a5cc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005a5d1  mov     rax, [rbx+110h]
0x18005a5d8  mov     dword ptr [rax], 2
0x18005a5de  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a5e2  test    rcx, rcx
0x18005a5e5  jz      short loc_18005A5ED
0x18005a5e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a5ed  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a5f2  mov     r9, rax
0x18005a5f5  mov     ecx, [rax]
0x18005a5f7  cmp     ecx, 4
0x18005a5fa  jbe     loc_18005A838
0x18005a600  mov     rax, [rax+18h]
0x18005a604  mov     rcx, [r9+10h]
0x18005a608  mov     edx, 1000h
0x18005a60d  test    rdx, rcx
0x18005a610  jz      loc_18005A838
0x18005a616  mov     rcx, rax
0x18005a619  and     rcx, rdx
0x18005a61c  cmp     rcx, rax
0x18005a61f  jnz     loc_18005A838
0x18005a625  mov     rax, [rdi+30h]
0x18005a629  mov     [rbp+var_50], rax
0x18005a62d  mov     eax, [rdi+44h]
0x18005a630  mov     dword ptr [rbp+var_78+4], eax
0x18005a633  mov     eax, [rdi+10h]
0x18005a636  mov     dword ptr [rbp+var_70], eax
0x18005a639  mov     rax, [rdi+78h]
0x18005a63d  mov     [rbp+var_48], rax
0x18005a641  mov     rax, [rdi+70h]
0x18005a645  mov     [rbp+var_40], rax
0x18005a649  mov     eax, [rdi+68h]
0x18005a64c  mov     dword ptr [rbp+var_70+4], eax
0x18005a64f  mov     rax, [rdi+60h]
0x18005a653  mov     [rbp+var_38], rax
0x18005a657  mov     rax, [rdi+58h]
0x18005a65b  mov     [rbp+var_30], rax
0x18005a65f  mov     eax, [rdi+50h]
0x18005a662  mov     dword ptr [rbp+var_68], eax
0x18005a665  mov     rax, [rdi+48h]
0x18005a669  mov     [rbp+var_28], rax
0x18005a66d  mov     eax, [rdi+20h]
0x18005a670  mov     dword ptr [rbp+var_68+4], eax
0x18005a673  mov     rax, [rdi+18h]
0x18005a677  mov     [rbp+var_20], rax
0x18005a67b  mov     eax, [rdi]
0x18005a67d  mov     [rbp+var_60], eax
0x18005a680  mov     rax, [rdi+80h]
0x18005a687  mov     [rbp+var_18], rax
0x18005a68b  mov     eax, [rdi+40h]
0x18005a68e  mov     dword ptr [rbp+var_78], eax
0x18005a691  mov     rax, [rdi+38h]
0x18005a695  mov     [rbp+var_10], rax
0x18005a699  mov     eax, [rdi+8]
0x18005a69c  mov     dword ptr [rbp+SRWLock], eax
0x18005a69f  mov     [rbp+var_8], 1000000h
0x18005a6a7  mov     [rbp+var_58], 0
0x18005a6af  mov     r8, [rbx+110h]
0x18005a6b6  add     r8, 8; int
0x18005a6ba  lea     rax, [rbp+var_50]
0x18005a6be  mov     [rsp+140h+var_90], rax; __int64
0x18005a6c6  lea     rax, [rbp+var_78+4]
0x18005a6ca  mov     [rsp+140h+var_98], rax; __int64
0x18005a6d2  lea     rax, [rbp+var_70]
0x18005a6d6  mov     [rsp+140h+var_A0], rax; __int64
0x18005a6de  lea     rax, [rbp+var_48]
0x18005a6e2  mov     [rsp+140h+var_A8], rax; __int64
0x18005a6ea  lea     rax, [rbp+var_40]
0x18005a6ee  mov     [rsp+140h+var_B0], rax; __int64
0x18005a6f6  lea     rax, [rbp+var_70+4]
0x18005a6fa  mov     [rsp+140h+var_B8], rax; __int64
0x18005a702  lea     rax, [rbp+var_38]
0x18005a706  mov     [rsp+140h+var_C0], rax; __int64
0x18005a70e  lea     rax, [rbp+var_30]
0x18005a712  mov     [rsp+140h+var_C8], rax; __int64
0x18005a717  lea     rax, [rbp+var_68]
0x18005a71b  mov     [rsp+140h+var_D0], rax; __int64
0x18005a720  lea     rax, [rbp+var_28]
0x18005a724  mov     [rsp+140h+var_D8], rax; __int64
0x18005a729  lea     rax, [rbp+var_68+4]
0x18005a72d  mov     [rsp+140h+var_E0], rax; __int64
0x18005a732  lea     rax, [rbp+var_20]
0x18005a736  mov     [rsp+140h+var_E8], rax; __int64
0x18005a73b  lea     rax, [rbp+var_60]
0x18005a73f  mov     [rsp+140h+var_F0], rax; __int64
0x18005a744  lea     rax, [rbp+var_18]
0x18005a748  mov     [rsp+140h+var_F8], rax; __int64
0x18005a74d  lea     rax, [rbp+var_78]
0x18005a751  mov     [rsp+140h+var_100], rax; __int64
0x18005a756  lea     rax, [rbp+var_10]
0x18005a75a  mov     [rsp+140h+var_108], rax; __int64
0x18005a75f  lea     rax, [rbp+SRWLock]
0x18005a763  mov     [rsp+140h+var_110], rax; __int64
0x18005a768  lea     rax, [rbp+var_8]
0x18005a76c  mov     [rsp+140h+var_118], rax; __int64
0x18005a771  lea     rax, [rbp+var_58]
0x18005a775  mov     [rsp+140h+var_120], rax; __int64
0x18005a77a  lea     rdx, unk_1800CA978; int
0x18005a781  mov     rcx, r9; int
0x18005a784  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005a789  jmp     loc_18005A838
0x18005a78e  mov     [rbp+SRWLock], 0
0x18005a796  lea     rdx, [rbp+SRWLock]
0x18005a79a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005a79f  mov     rax, [rbx+110h]
0x18005a7a6  mov     dword ptr [rax], 2
0x18005a7ac  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a7b0  test    rcx, rcx
0x18005a7b3  jz      short loc_18005A7BB
0x18005a7b5  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a7bb  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a7c0  mov     rdi, rax
0x18005a7c3  mov     ecx, [rax]
0x18005a7c5  cmp     ecx, 4
0x18005a7c8  jbe     short loc_18005A838
0x18005a7ca  mov     rax, [rax+18h]
0x18005a7ce  mov     rcx, [rdi+10h]
0x18005a7d2  mov     edx, 1000h
0x18005a7d7  test    rdx, rcx
0x18005a7da  jz      short loc_18005A838
0x18005a7dc  mov     rcx, rax
0x18005a7df  and     rcx, rdx
0x18005a7e2  cmp     rcx, rax
0x18005a7e5  jnz     short loc_18005A838
0x18005a7e7  call    cs:__imp_GetCurrentThreadId
0x18005a7ed  mov     dword ptr [rbp+SRWLock], eax
0x18005a7f0  mov     r8, [rbx+110h]
0x18005a7f7  mov     eax, [r8+48h]
0x18005a7fb  mov     dword ptr [rbp+var_78], eax
0x18005a7fe  mov     [rbp+var_58], 0
0x18005a806  add     r8, 8
0x18005a80a  lea     rax, [rbp+SRWLock]
0x18005a80e  mov     [rsp+140h+var_110], rax
0x18005a813  lea     rax, [rbp+var_78]
0x18005a817  mov     [rsp+140h+var_118], rax
0x18005a81c  lea     rax, [rbp+var_58]
0x18005a820  mov     [rsp+140h+var_120], rax
0x18005a825  xor     r9d, r9d
0x18005a828  lea     rdx, dword_1800CA924
0x18005a82f  mov     rcx, rdi
0x18005a832  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005a837  nop
0x18005a838  lea     rcx, [rbx+120h]; this
0x18005a83f  cmp     dword ptr [rcx+18h], 0
0x18005a843  jz      short loc_18005A84B
0x18005a845  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005a84a  nop
0x18005a84b  lea     r11, [rsp+140h+var_s0]
0x18005a853  mov     rbx, [r11+18h]
0x18005a857  mov     rdi, [r11+20h]
0x18005a85b  mov     rsp, r11
0x18005a85e  pop     rbp
0x18005a85f  retn
```
