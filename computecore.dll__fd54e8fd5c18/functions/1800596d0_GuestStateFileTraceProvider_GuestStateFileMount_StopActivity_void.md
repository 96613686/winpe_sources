# GuestStateFileTraceProvider::GuestStateFileMount::StopActivity(void)

- ea: `0x1800596d0`
- end: `0x1800599b0`
- name: `?StopActivity@GuestStateFileMount@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileMount *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x1800596d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059905`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059937`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileMount::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileMount *this)
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
          (int)&word_1800C98CE,
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
          (unsigned int)word_1800C987A,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileMount *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800596d0  mov     [rsp-8+arg_8], rbx
0x1800596d5  mov     [rsp-8+arg_10], rdi
0x1800596da  push    rbp
0x1800596db  mov     rbp, rsp
0x1800596de  sub     rsp, 140h
0x1800596e5  mov     rbx, rcx
0x1800596e8  mov     rdi, [rcx+110h]
0x1800596ef  mov     eax, [rdi+48h]
0x1800596f2  test    eax, eax
0x1800596f4  jns     loc_1800598DE
0x1800596fa  add     rdi, 50h ; 'P'
0x1800596fe  cmp     eax, [rdi+8]
0x180059701  jnz     loc_1800598DE
0x180059707  test    rdi, rdi
0x18005970a  jz      loc_1800598DE
0x180059710  mov     [rbp+SRWLock], 0
0x180059718  lea     rdx, [rbp+SRWLock]
0x18005971c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059721  mov     rax, [rbx+110h]
0x180059728  mov     dword ptr [rax], 2
0x18005972e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059732  test    rcx, rcx
0x180059735  jz      short loc_18005973D
0x180059737  call    cs:__imp_ReleaseSRWLockExclusive
0x18005973d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059742  mov     r9, rax
0x180059745  mov     ecx, [rax]
0x180059747  cmp     ecx, 4
0x18005974a  jbe     loc_180059988
0x180059750  mov     rax, [rax+18h]
0x180059754  mov     rcx, [r9+10h]
0x180059758  mov     edx, 1000h
0x18005975d  test    rdx, rcx
0x180059760  jz      loc_180059988
0x180059766  mov     rcx, rax
0x180059769  and     rcx, rdx
0x18005976c  cmp     rcx, rax
0x18005976f  jnz     loc_180059988
0x180059775  mov     rax, [rdi+30h]
0x180059779  mov     [rbp+var_50], rax
0x18005977d  mov     eax, [rdi+44h]
0x180059780  mov     dword ptr [rbp+var_78+4], eax
0x180059783  mov     eax, [rdi+10h]
0x180059786  mov     dword ptr [rbp+var_70], eax
0x180059789  mov     rax, [rdi+78h]
0x18005978d  mov     [rbp+var_48], rax
0x180059791  mov     rax, [rdi+70h]
0x180059795  mov     [rbp+var_40], rax
0x180059799  mov     eax, [rdi+68h]
0x18005979c  mov     dword ptr [rbp+var_70+4], eax
0x18005979f  mov     rax, [rdi+60h]
0x1800597a3  mov     [rbp+var_38], rax
0x1800597a7  mov     rax, [rdi+58h]
0x1800597ab  mov     [rbp+var_30], rax
0x1800597af  mov     eax, [rdi+50h]
0x1800597b2  mov     dword ptr [rbp+var_68], eax
0x1800597b5  mov     rax, [rdi+48h]
0x1800597b9  mov     [rbp+var_28], rax
0x1800597bd  mov     eax, [rdi+20h]
0x1800597c0  mov     dword ptr [rbp+var_68+4], eax
0x1800597c3  mov     rax, [rdi+18h]
0x1800597c7  mov     [rbp+var_20], rax
0x1800597cb  mov     eax, [rdi]
0x1800597cd  mov     [rbp+var_60], eax
0x1800597d0  mov     rax, [rdi+80h]
0x1800597d7  mov     [rbp+var_18], rax
0x1800597db  mov     eax, [rdi+40h]
0x1800597de  mov     dword ptr [rbp+var_78], eax
0x1800597e1  mov     rax, [rdi+38h]
0x1800597e5  mov     [rbp+var_10], rax
0x1800597e9  mov     eax, [rdi+8]
0x1800597ec  mov     dword ptr [rbp+SRWLock], eax
0x1800597ef  mov     [rbp+var_8], 1000000h
0x1800597f7  mov     [rbp+var_58], 0
0x1800597ff  mov     r8, [rbx+110h]
0x180059806  add     r8, 8; int
0x18005980a  lea     rax, [rbp+var_50]
0x18005980e  mov     [rsp+140h+var_90], rax; __int64
0x180059816  lea     rax, [rbp+var_78+4]
0x18005981a  mov     [rsp+140h+var_98], rax; __int64
0x180059822  lea     rax, [rbp+var_70]
0x180059826  mov     [rsp+140h+var_A0], rax; __int64
0x18005982e  lea     rax, [rbp+var_48]
0x180059832  mov     [rsp+140h+var_A8], rax; __int64
0x18005983a  lea     rax, [rbp+var_40]
0x18005983e  mov     [rsp+140h+var_B0], rax; __int64
0x180059846  lea     rax, [rbp+var_70+4]
0x18005984a  mov     [rsp+140h+var_B8], rax; __int64
0x180059852  lea     rax, [rbp+var_38]
0x180059856  mov     [rsp+140h+var_C0], rax; __int64
0x18005985e  lea     rax, [rbp+var_30]
0x180059862  mov     [rsp+140h+var_C8], rax; __int64
0x180059867  lea     rax, [rbp+var_68]
0x18005986b  mov     [rsp+140h+var_D0], rax; __int64
0x180059870  lea     rax, [rbp+var_28]
0x180059874  mov     [rsp+140h+var_D8], rax; __int64
0x180059879  lea     rax, [rbp+var_68+4]
0x18005987d  mov     [rsp+140h+var_E0], rax; __int64
0x180059882  lea     rax, [rbp+var_20]
0x180059886  mov     [rsp+140h+var_E8], rax; __int64
0x18005988b  lea     rax, [rbp+var_60]
0x18005988f  mov     [rsp+140h+var_F0], rax; __int64
0x180059894  lea     rax, [rbp+var_18]
0x180059898  mov     [rsp+140h+var_F8], rax; __int64
0x18005989d  lea     rax, [rbp+var_78]
0x1800598a1  mov     [rsp+140h+var_100], rax; __int64
0x1800598a6  lea     rax, [rbp+var_10]
0x1800598aa  mov     [rsp+140h+var_108], rax; __int64
0x1800598af  lea     rax, [rbp+SRWLock]
0x1800598b3  mov     [rsp+140h+var_110], rax; __int64
0x1800598b8  lea     rax, [rbp+var_8]
0x1800598bc  mov     [rsp+140h+var_118], rax; __int64
0x1800598c1  lea     rax, [rbp+var_58]
0x1800598c5  mov     [rsp+140h+var_120], rax; __int64
0x1800598ca  lea     rdx, word_1800C98CE; int
0x1800598d1  mov     rcx, r9; int
0x1800598d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800598d9  jmp     loc_180059988
0x1800598de  mov     [rbp+SRWLock], 0
0x1800598e6  lea     rdx, [rbp+SRWLock]
0x1800598ea  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800598ef  mov     rax, [rbx+110h]
0x1800598f6  mov     dword ptr [rax], 2
0x1800598fc  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059900  test    rcx, rcx
0x180059903  jz      short loc_18005990B
0x180059905  call    cs:__imp_ReleaseSRWLockExclusive
0x18005990b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059910  mov     rdi, rax
0x180059913  mov     ecx, [rax]
0x180059915  cmp     ecx, 4
0x180059918  jbe     short loc_180059988
0x18005991a  mov     rax, [rax+18h]
0x18005991e  mov     rcx, [rdi+10h]
0x180059922  mov     edx, 1000h
0x180059927  test    rdx, rcx
0x18005992a  jz      short loc_180059988
0x18005992c  mov     rcx, rax
0x18005992f  and     rcx, rdx
0x180059932  cmp     rcx, rax
0x180059935  jnz     short loc_180059988
0x180059937  call    cs:__imp_GetCurrentThreadId
0x18005993d  mov     dword ptr [rbp+SRWLock], eax
0x180059940  mov     r8, [rbx+110h]
0x180059947  mov     eax, [r8+48h]
0x18005994b  mov     dword ptr [rbp+var_78], eax
0x18005994e  mov     [rbp+var_58], 0
0x180059956  add     r8, 8
0x18005995a  lea     rax, [rbp+SRWLock]
0x18005995e  mov     [rsp+140h+var_110], rax
0x180059963  lea     rax, [rbp+var_78]
0x180059967  mov     [rsp+140h+var_118], rax
0x18005996c  lea     rax, [rbp+var_58]
0x180059970  mov     [rsp+140h+var_120], rax
0x180059975  xor     r9d, r9d
0x180059978  lea     rdx, word_1800C987A
0x18005997f  mov     rcx, rdi
0x180059982  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180059987  nop
0x180059988  lea     rcx, [rbx+120h]; this
0x18005998f  cmp     dword ptr [rcx+18h], 0
0x180059993  jz      short loc_18005999B
0x180059995  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005999a  nop
0x18005999b  lea     r11, [rsp+140h+var_s0]
0x1800599a3  mov     rbx, [r11+18h]
0x1800599a7  mov     rdi, [r11+20h]
0x1800599ab  mov     rsp, r11
0x1800599ae  pop     rbp
0x1800599af  retn
```
