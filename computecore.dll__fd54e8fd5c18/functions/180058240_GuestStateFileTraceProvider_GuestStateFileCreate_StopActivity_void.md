# GuestStateFileTraceProvider::GuestStateFileCreate::StopActivity(void)

- ea: `0x180058240`
- end: `0x180058520`
- name: `?StopActivity@GuestStateFileCreate@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileCreate *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180058240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800582a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058475`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800582a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180058475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800584a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800584a7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileCreate::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileCreate *this)
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
          (int)&byte_1800CA71B,
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
          (unsigned int)word_1800CA86A,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileCreate *)((char *)this + 288));
}

```

## disassembly

```asm
0x180058240  mov     [rsp-8+arg_8], rbx
0x180058245  mov     [rsp-8+arg_10], rdi
0x18005824a  push    rbp
0x18005824b  mov     rbp, rsp
0x18005824e  sub     rsp, 140h
0x180058255  mov     rbx, rcx
0x180058258  mov     rdi, [rcx+110h]
0x18005825f  mov     eax, [rdi+48h]
0x180058262  test    eax, eax
0x180058264  jns     loc_18005844E
0x18005826a  add     rdi, 50h ; 'P'
0x18005826e  cmp     eax, [rdi+8]
0x180058271  jnz     loc_18005844E
0x180058277  test    rdi, rdi
0x18005827a  jz      loc_18005844E
0x180058280  mov     [rbp+SRWLock], 0
0x180058288  lea     rdx, [rbp+SRWLock]
0x18005828c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180058291  mov     rax, [rbx+110h]
0x180058298  mov     dword ptr [rax], 2
0x18005829e  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800582a2  test    rcx, rcx
0x1800582a5  jz      short loc_1800582AD
0x1800582a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800582ad  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x1800582b2  mov     r9, rax
0x1800582b5  mov     ecx, [rax]
0x1800582b7  cmp     ecx, 4
0x1800582ba  jbe     loc_1800584F8
0x1800582c0  mov     rax, [rax+18h]
0x1800582c4  mov     rcx, [r9+10h]
0x1800582c8  mov     edx, 1000h
0x1800582cd  test    rdx, rcx
0x1800582d0  jz      loc_1800584F8
0x1800582d6  mov     rcx, rax
0x1800582d9  and     rcx, rdx
0x1800582dc  cmp     rcx, rax
0x1800582df  jnz     loc_1800584F8
0x1800582e5  mov     rax, [rdi+30h]
0x1800582e9  mov     [rbp+var_50], rax
0x1800582ed  mov     eax, [rdi+44h]
0x1800582f0  mov     dword ptr [rbp+var_78+4], eax
0x1800582f3  mov     eax, [rdi+10h]
0x1800582f6  mov     dword ptr [rbp+var_70], eax
0x1800582f9  mov     rax, [rdi+78h]
0x1800582fd  mov     [rbp+var_48], rax
0x180058301  mov     rax, [rdi+70h]
0x180058305  mov     [rbp+var_40], rax
0x180058309  mov     eax, [rdi+68h]
0x18005830c  mov     dword ptr [rbp+var_70+4], eax
0x18005830f  mov     rax, [rdi+60h]
0x180058313  mov     [rbp+var_38], rax
0x180058317  mov     rax, [rdi+58h]
0x18005831b  mov     [rbp+var_30], rax
0x18005831f  mov     eax, [rdi+50h]
0x180058322  mov     dword ptr [rbp+var_68], eax
0x180058325  mov     rax, [rdi+48h]
0x180058329  mov     [rbp+var_28], rax
0x18005832d  mov     eax, [rdi+20h]
0x180058330  mov     dword ptr [rbp+var_68+4], eax
0x180058333  mov     rax, [rdi+18h]
0x180058337  mov     [rbp+var_20], rax
0x18005833b  mov     eax, [rdi]
0x18005833d  mov     [rbp+var_60], eax
0x180058340  mov     rax, [rdi+80h]
0x180058347  mov     [rbp+var_18], rax
0x18005834b  mov     eax, [rdi+40h]
0x18005834e  mov     dword ptr [rbp+var_78], eax
0x180058351  mov     rax, [rdi+38h]
0x180058355  mov     [rbp+var_10], rax
0x180058359  mov     eax, [rdi+8]
0x18005835c  mov     dword ptr [rbp+SRWLock], eax
0x18005835f  mov     [rbp+var_8], 1000000h
0x180058367  mov     [rbp+var_58], 0
0x18005836f  mov     r8, [rbx+110h]
0x180058376  add     r8, 8; int
0x18005837a  lea     rax, [rbp+var_50]
0x18005837e  mov     [rsp+140h+var_90], rax; __int64
0x180058386  lea     rax, [rbp+var_78+4]
0x18005838a  mov     [rsp+140h+var_98], rax; __int64
0x180058392  lea     rax, [rbp+var_70]
0x180058396  mov     [rsp+140h+var_A0], rax; __int64
0x18005839e  lea     rax, [rbp+var_48]
0x1800583a2  mov     [rsp+140h+var_A8], rax; __int64
0x1800583aa  lea     rax, [rbp+var_40]
0x1800583ae  mov     [rsp+140h+var_B0], rax; __int64
0x1800583b6  lea     rax, [rbp+var_70+4]
0x1800583ba  mov     [rsp+140h+var_B8], rax; __int64
0x1800583c2  lea     rax, [rbp+var_38]
0x1800583c6  mov     [rsp+140h+var_C0], rax; __int64
0x1800583ce  lea     rax, [rbp+var_30]
0x1800583d2  mov     [rsp+140h+var_C8], rax; __int64
0x1800583d7  lea     rax, [rbp+var_68]
0x1800583db  mov     [rsp+140h+var_D0], rax; __int64
0x1800583e0  lea     rax, [rbp+var_28]
0x1800583e4  mov     [rsp+140h+var_D8], rax; __int64
0x1800583e9  lea     rax, [rbp+var_68+4]
0x1800583ed  mov     [rsp+140h+var_E0], rax; __int64
0x1800583f2  lea     rax, [rbp+var_20]
0x1800583f6  mov     [rsp+140h+var_E8], rax; __int64
0x1800583fb  lea     rax, [rbp+var_60]
0x1800583ff  mov     [rsp+140h+var_F0], rax; __int64
0x180058404  lea     rax, [rbp+var_18]
0x180058408  mov     [rsp+140h+var_F8], rax; __int64
0x18005840d  lea     rax, [rbp+var_78]
0x180058411  mov     [rsp+140h+var_100], rax; __int64
0x180058416  lea     rax, [rbp+var_10]
0x18005841a  mov     [rsp+140h+var_108], rax; __int64
0x18005841f  lea     rax, [rbp+SRWLock]
0x180058423  mov     [rsp+140h+var_110], rax; __int64
0x180058428  lea     rax, [rbp+var_8]
0x18005842c  mov     [rsp+140h+var_118], rax; __int64
0x180058431  lea     rax, [rbp+var_58]
0x180058435  mov     [rsp+140h+var_120], rax; __int64
0x18005843a  lea     rdx, byte_1800CA71B; int
0x180058441  mov     rcx, r9; int
0x180058444  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180058449  jmp     loc_1800584F8
0x18005844e  mov     [rbp+SRWLock], 0
0x180058456  lea     rdx, [rbp+SRWLock]
0x18005845a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005845f  mov     rax, [rbx+110h]
0x180058466  mov     dword ptr [rax], 2
0x18005846c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180058470  test    rcx, rcx
0x180058473  jz      short loc_18005847B
0x180058475  call    cs:__imp_ReleaseSRWLockExclusive
0x18005847b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180058480  mov     rdi, rax
0x180058483  mov     ecx, [rax]
0x180058485  cmp     ecx, 4
0x180058488  jbe     short loc_1800584F8
0x18005848a  mov     rax, [rax+18h]
0x18005848e  mov     rcx, [rdi+10h]
0x180058492  mov     edx, 1000h
0x180058497  test    rdx, rcx
0x18005849a  jz      short loc_1800584F8
0x18005849c  mov     rcx, rax
0x18005849f  and     rcx, rdx
0x1800584a2  cmp     rcx, rax
0x1800584a5  jnz     short loc_1800584F8
0x1800584a7  call    cs:__imp_GetCurrentThreadId
0x1800584ad  mov     dword ptr [rbp+SRWLock], eax
0x1800584b0  mov     r8, [rbx+110h]
0x1800584b7  mov     eax, [r8+48h]
0x1800584bb  mov     dword ptr [rbp+var_78], eax
0x1800584be  mov     [rbp+var_58], 0
0x1800584c6  add     r8, 8
0x1800584ca  lea     rax, [rbp+SRWLock]
0x1800584ce  mov     [rsp+140h+var_110], rax
0x1800584d3  lea     rax, [rbp+var_78]
0x1800584d7  mov     [rsp+140h+var_118], rax
0x1800584dc  lea     rax, [rbp+var_58]
0x1800584e0  mov     [rsp+140h+var_120], rax
0x1800584e5  xor     r9d, r9d
0x1800584e8  lea     rdx, word_1800CA86A
0x1800584ef  mov     rcx, rdi
0x1800584f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800584f7  nop
0x1800584f8  lea     rcx, [rbx+120h]; this
0x1800584ff  cmp     dword ptr [rcx+18h], 0
0x180058503  jz      short loc_18005850B
0x180058505  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005850a  nop
0x18005850b  lea     r11, [rsp+140h+var_s0]
0x180058513  mov     rbx, [r11+18h]
0x180058517  mov     rdi, [r11+20h]
0x18005851b  mov     rsp, r11
0x18005851e  pop     rbp
0x18005851f  retn
```
