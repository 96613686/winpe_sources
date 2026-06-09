# GuestStateFileTraceProvider::GuestStateFileReopen::StopActivity(void)

- ea: `0x180059fa0`
- end: `0x18005a280`
- name: `?StopActivity@GuestStateFileReopen@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileReopen *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180059fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a007`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a1d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a007`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a1d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a207`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileReopen::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileReopen *this)
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
          (int)&word_1800C9606,
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
          (unsigned int)byte_1800C9755,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileReopen *)((char *)this + 288));
}

```

## disassembly

```asm
0x180059fa0  mov     [rsp-8+arg_8], rbx
0x180059fa5  mov     [rsp-8+arg_10], rdi
0x180059faa  push    rbp
0x180059fab  mov     rbp, rsp
0x180059fae  sub     rsp, 140h
0x180059fb5  mov     rbx, rcx
0x180059fb8  mov     rdi, [rcx+110h]
0x180059fbf  mov     eax, [rdi+48h]
0x180059fc2  test    eax, eax
0x180059fc4  jns     loc_18005A1AE
0x180059fca  add     rdi, 50h ; 'P'
0x180059fce  cmp     eax, [rdi+8]
0x180059fd1  jnz     loc_18005A1AE
0x180059fd7  test    rdi, rdi
0x180059fda  jz      loc_18005A1AE
0x180059fe0  mov     [rbp+SRWLock], 0
0x180059fe8  lea     rdx, [rbp+SRWLock]
0x180059fec  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059ff1  mov     rax, [rbx+110h]
0x180059ff8  mov     dword ptr [rax], 2
0x180059ffe  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a002  test    rcx, rcx
0x18005a005  jz      short loc_18005A00D
0x18005a007  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a00d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a012  mov     r9, rax
0x18005a015  mov     ecx, [rax]
0x18005a017  cmp     ecx, 4
0x18005a01a  jbe     loc_18005A258
0x18005a020  mov     rax, [rax+18h]
0x18005a024  mov     rcx, [r9+10h]
0x18005a028  mov     edx, 1000h
0x18005a02d  test    rdx, rcx
0x18005a030  jz      loc_18005A258
0x18005a036  mov     rcx, rax
0x18005a039  and     rcx, rdx
0x18005a03c  cmp     rcx, rax
0x18005a03f  jnz     loc_18005A258
0x18005a045  mov     rax, [rdi+30h]
0x18005a049  mov     [rbp+var_50], rax
0x18005a04d  mov     eax, [rdi+44h]
0x18005a050  mov     dword ptr [rbp+var_78+4], eax
0x18005a053  mov     eax, [rdi+10h]
0x18005a056  mov     dword ptr [rbp+var_70], eax
0x18005a059  mov     rax, [rdi+78h]
0x18005a05d  mov     [rbp+var_48], rax
0x18005a061  mov     rax, [rdi+70h]
0x18005a065  mov     [rbp+var_40], rax
0x18005a069  mov     eax, [rdi+68h]
0x18005a06c  mov     dword ptr [rbp+var_70+4], eax
0x18005a06f  mov     rax, [rdi+60h]
0x18005a073  mov     [rbp+var_38], rax
0x18005a077  mov     rax, [rdi+58h]
0x18005a07b  mov     [rbp+var_30], rax
0x18005a07f  mov     eax, [rdi+50h]
0x18005a082  mov     dword ptr [rbp+var_68], eax
0x18005a085  mov     rax, [rdi+48h]
0x18005a089  mov     [rbp+var_28], rax
0x18005a08d  mov     eax, [rdi+20h]
0x18005a090  mov     dword ptr [rbp+var_68+4], eax
0x18005a093  mov     rax, [rdi+18h]
0x18005a097  mov     [rbp+var_20], rax
0x18005a09b  mov     eax, [rdi]
0x18005a09d  mov     [rbp+var_60], eax
0x18005a0a0  mov     rax, [rdi+80h]
0x18005a0a7  mov     [rbp+var_18], rax
0x18005a0ab  mov     eax, [rdi+40h]
0x18005a0ae  mov     dword ptr [rbp+var_78], eax
0x18005a0b1  mov     rax, [rdi+38h]
0x18005a0b5  mov     [rbp+var_10], rax
0x18005a0b9  mov     eax, [rdi+8]
0x18005a0bc  mov     dword ptr [rbp+SRWLock], eax
0x18005a0bf  mov     [rbp+var_8], 1000000h
0x18005a0c7  mov     [rbp+var_58], 0
0x18005a0cf  mov     r8, [rbx+110h]
0x18005a0d6  add     r8, 8; int
0x18005a0da  lea     rax, [rbp+var_50]
0x18005a0de  mov     [rsp+140h+var_90], rax; __int64
0x18005a0e6  lea     rax, [rbp+var_78+4]
0x18005a0ea  mov     [rsp+140h+var_98], rax; __int64
0x18005a0f2  lea     rax, [rbp+var_70]
0x18005a0f6  mov     [rsp+140h+var_A0], rax; __int64
0x18005a0fe  lea     rax, [rbp+var_48]
0x18005a102  mov     [rsp+140h+var_A8], rax; __int64
0x18005a10a  lea     rax, [rbp+var_40]
0x18005a10e  mov     [rsp+140h+var_B0], rax; __int64
0x18005a116  lea     rax, [rbp+var_70+4]
0x18005a11a  mov     [rsp+140h+var_B8], rax; __int64
0x18005a122  lea     rax, [rbp+var_38]
0x18005a126  mov     [rsp+140h+var_C0], rax; __int64
0x18005a12e  lea     rax, [rbp+var_30]
0x18005a132  mov     [rsp+140h+var_C8], rax; __int64
0x18005a137  lea     rax, [rbp+var_68]
0x18005a13b  mov     [rsp+140h+var_D0], rax; __int64
0x18005a140  lea     rax, [rbp+var_28]
0x18005a144  mov     [rsp+140h+var_D8], rax; __int64
0x18005a149  lea     rax, [rbp+var_68+4]
0x18005a14d  mov     [rsp+140h+var_E0], rax; __int64
0x18005a152  lea     rax, [rbp+var_20]
0x18005a156  mov     [rsp+140h+var_E8], rax; __int64
0x18005a15b  lea     rax, [rbp+var_60]
0x18005a15f  mov     [rsp+140h+var_F0], rax; __int64
0x18005a164  lea     rax, [rbp+var_18]
0x18005a168  mov     [rsp+140h+var_F8], rax; __int64
0x18005a16d  lea     rax, [rbp+var_78]
0x18005a171  mov     [rsp+140h+var_100], rax; __int64
0x18005a176  lea     rax, [rbp+var_10]
0x18005a17a  mov     [rsp+140h+var_108], rax; __int64
0x18005a17f  lea     rax, [rbp+SRWLock]
0x18005a183  mov     [rsp+140h+var_110], rax; __int64
0x18005a188  lea     rax, [rbp+var_8]
0x18005a18c  mov     [rsp+140h+var_118], rax; __int64
0x18005a191  lea     rax, [rbp+var_58]
0x18005a195  mov     [rsp+140h+var_120], rax; __int64
0x18005a19a  lea     rdx, word_1800C9606; int
0x18005a1a1  mov     rcx, r9; int
0x18005a1a4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005a1a9  jmp     loc_18005A258
0x18005a1ae  mov     [rbp+SRWLock], 0
0x18005a1b6  lea     rdx, [rbp+SRWLock]
0x18005a1ba  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005a1bf  mov     rax, [rbx+110h]
0x18005a1c6  mov     dword ptr [rax], 2
0x18005a1cc  mov     rcx, [rbp+SRWLock]; SRWLock
0x18005a1d0  test    rcx, rcx
0x18005a1d3  jz      short loc_18005A1DB
0x18005a1d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a1db  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x18005a1e0  mov     rdi, rax
0x18005a1e3  mov     ecx, [rax]
0x18005a1e5  cmp     ecx, 4
0x18005a1e8  jbe     short loc_18005A258
0x18005a1ea  mov     rax, [rax+18h]
0x18005a1ee  mov     rcx, [rdi+10h]
0x18005a1f2  mov     edx, 1000h
0x18005a1f7  test    rdx, rcx
0x18005a1fa  jz      short loc_18005A258
0x18005a1fc  mov     rcx, rax
0x18005a1ff  and     rcx, rdx
0x18005a202  cmp     rcx, rax
0x18005a205  jnz     short loc_18005A258
0x18005a207  call    cs:__imp_GetCurrentThreadId
0x18005a20d  mov     dword ptr [rbp+SRWLock], eax
0x18005a210  mov     r8, [rbx+110h]
0x18005a217  mov     eax, [r8+48h]
0x18005a21b  mov     dword ptr [rbp+var_78], eax
0x18005a21e  mov     [rbp+var_58], 0
0x18005a226  add     r8, 8
0x18005a22a  lea     rax, [rbp+SRWLock]
0x18005a22e  mov     [rsp+140h+var_110], rax
0x18005a233  lea     rax, [rbp+var_78]
0x18005a237  mov     [rsp+140h+var_118], rax
0x18005a23c  lea     rax, [rbp+var_58]
0x18005a240  mov     [rsp+140h+var_120], rax
0x18005a245  xor     r9d, r9d
0x18005a248  lea     rdx, byte_1800C9755
0x18005a24f  mov     rcx, rdi
0x18005a252  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005a257  nop
0x18005a258  lea     rcx, [rbx+120h]; this
0x18005a25f  cmp     dword ptr [rcx+18h], 0
0x18005a263  jz      short loc_18005A26B
0x18005a265  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005a26a  nop
0x18005a26b  lea     r11, [rsp+140h+var_s0]
0x18005a273  mov     rbx, [r11+18h]
0x18005a277  mov     rdi, [r11+20h]
0x18005a27b  mov     rsp, r11
0x18005a27e  pop     rbp
0x18005a27f  retn
```
