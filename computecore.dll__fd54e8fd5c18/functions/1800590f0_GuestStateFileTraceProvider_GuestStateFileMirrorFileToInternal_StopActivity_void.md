# GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StopActivity(void)

- ea: `0x1800590f0`
- end: `0x1800593d0`
- name: `?StopActivity@GuestStateFileMirrorFileToInternal@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x1800590f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059157`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059325`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059157`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180059325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059357`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *this)
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
          (int)&byte_1800C9F7B,
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
          (unsigned int)&word_1800C9E06,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileMirrorFileToInternal *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800590f0  mov     [rsp-8+arg_8], rbx
0x1800590f5  mov     [rsp-8+arg_10], rdi
0x1800590fa  push    rbp
0x1800590fb  mov     rbp, rsp
0x1800590fe  sub     rsp, 140h
0x180059105  mov     rbx, rcx
0x180059108  mov     rdi, [rcx+110h]
0x18005910f  mov     eax, [rdi+48h]
0x180059112  test    eax, eax
0x180059114  jns     loc_1800592FE
0x18005911a  add     rdi, 50h ; 'P'
0x18005911e  cmp     eax, [rdi+8]
0x180059121  jnz     loc_1800592FE
0x180059127  test    rdi, rdi
0x18005912a  jz      loc_1800592FE
0x180059130  mov     [rbp+SRWLock], 0
0x180059138  lea     rdx, [rbp+SRWLock]
0x18005913c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180059141  mov     rax, [rbx+110h]
0x180059148  mov     dword ptr [rax], 2
0x18005914e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059152  test    rcx, rcx
0x180059155  jz      short loc_18005915D
0x180059157  call    cs:__imp_ReleaseSRWLockExclusive
0x18005915d  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059162  mov     r9, rax
0x180059165  mov     ecx, [rax]
0x180059167  cmp     ecx, 4
0x18005916a  jbe     loc_1800593A8
0x180059170  mov     rax, [rax+18h]
0x180059174  mov     rcx, [r9+10h]
0x180059178  mov     edx, 1000h
0x18005917d  test    rdx, rcx
0x180059180  jz      loc_1800593A8
0x180059186  mov     rcx, rax
0x180059189  and     rcx, rdx
0x18005918c  cmp     rcx, rax
0x18005918f  jnz     loc_1800593A8
0x180059195  mov     rax, [rdi+30h]
0x180059199  mov     [rbp+var_50], rax
0x18005919d  mov     eax, [rdi+44h]
0x1800591a0  mov     dword ptr [rbp+var_78+4], eax
0x1800591a3  mov     eax, [rdi+10h]
0x1800591a6  mov     dword ptr [rbp+var_70], eax
0x1800591a9  mov     rax, [rdi+78h]
0x1800591ad  mov     [rbp+var_48], rax
0x1800591b1  mov     rax, [rdi+70h]
0x1800591b5  mov     [rbp+var_40], rax
0x1800591b9  mov     eax, [rdi+68h]
0x1800591bc  mov     dword ptr [rbp+var_70+4], eax
0x1800591bf  mov     rax, [rdi+60h]
0x1800591c3  mov     [rbp+var_38], rax
0x1800591c7  mov     rax, [rdi+58h]
0x1800591cb  mov     [rbp+var_30], rax
0x1800591cf  mov     eax, [rdi+50h]
0x1800591d2  mov     dword ptr [rbp+var_68], eax
0x1800591d5  mov     rax, [rdi+48h]
0x1800591d9  mov     [rbp+var_28], rax
0x1800591dd  mov     eax, [rdi+20h]
0x1800591e0  mov     dword ptr [rbp+var_68+4], eax
0x1800591e3  mov     rax, [rdi+18h]
0x1800591e7  mov     [rbp+var_20], rax
0x1800591eb  mov     eax, [rdi]
0x1800591ed  mov     [rbp+var_60], eax
0x1800591f0  mov     rax, [rdi+80h]
0x1800591f7  mov     [rbp+var_18], rax
0x1800591fb  mov     eax, [rdi+40h]
0x1800591fe  mov     dword ptr [rbp+var_78], eax
0x180059201  mov     rax, [rdi+38h]
0x180059205  mov     [rbp+var_10], rax
0x180059209  mov     eax, [rdi+8]
0x18005920c  mov     dword ptr [rbp+SRWLock], eax
0x18005920f  mov     [rbp+var_8], 1000000h
0x180059217  mov     [rbp+var_58], 0
0x18005921f  mov     r8, [rbx+110h]
0x180059226  add     r8, 8; int
0x18005922a  lea     rax, [rbp+var_50]
0x18005922e  mov     [rsp+140h+var_90], rax; __int64
0x180059236  lea     rax, [rbp+var_78+4]
0x18005923a  mov     [rsp+140h+var_98], rax; __int64
0x180059242  lea     rax, [rbp+var_70]
0x180059246  mov     [rsp+140h+var_A0], rax; __int64
0x18005924e  lea     rax, [rbp+var_48]
0x180059252  mov     [rsp+140h+var_A8], rax; __int64
0x18005925a  lea     rax, [rbp+var_40]
0x18005925e  mov     [rsp+140h+var_B0], rax; __int64
0x180059266  lea     rax, [rbp+var_70+4]
0x18005926a  mov     [rsp+140h+var_B8], rax; __int64
0x180059272  lea     rax, [rbp+var_38]
0x180059276  mov     [rsp+140h+var_C0], rax; __int64
0x18005927e  lea     rax, [rbp+var_30]
0x180059282  mov     [rsp+140h+var_C8], rax; __int64
0x180059287  lea     rax, [rbp+var_68]
0x18005928b  mov     [rsp+140h+var_D0], rax; __int64
0x180059290  lea     rax, [rbp+var_28]
0x180059294  mov     [rsp+140h+var_D8], rax; __int64
0x180059299  lea     rax, [rbp+var_68+4]
0x18005929d  mov     [rsp+140h+var_E0], rax; __int64
0x1800592a2  lea     rax, [rbp+var_20]
0x1800592a6  mov     [rsp+140h+var_E8], rax; __int64
0x1800592ab  lea     rax, [rbp+var_60]
0x1800592af  mov     [rsp+140h+var_F0], rax; __int64
0x1800592b4  lea     rax, [rbp+var_18]
0x1800592b8  mov     [rsp+140h+var_F8], rax; __int64
0x1800592bd  lea     rax, [rbp+var_78]
0x1800592c1  mov     [rsp+140h+var_100], rax; __int64
0x1800592c6  lea     rax, [rbp+var_10]
0x1800592ca  mov     [rsp+140h+var_108], rax; __int64
0x1800592cf  lea     rax, [rbp+SRWLock]
0x1800592d3  mov     [rsp+140h+var_110], rax; __int64
0x1800592d8  lea     rax, [rbp+var_8]
0x1800592dc  mov     [rsp+140h+var_118], rax; __int64
0x1800592e1  lea     rax, [rbp+var_58]
0x1800592e5  mov     [rsp+140h+var_120], rax; __int64
0x1800592ea  lea     rdx, byte_1800C9F7B; int
0x1800592f1  mov     rcx, r9; int
0x1800592f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800592f9  jmp     loc_1800593A8
0x1800592fe  mov     [rbp+SRWLock], 0
0x180059306  lea     rdx, [rbp+SRWLock]
0x18005930a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18005930f  mov     rax, [rbx+110h]
0x180059316  mov     dword ptr [rax], 2
0x18005931c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180059320  test    rcx, rcx
0x180059323  jz      short loc_18005932B
0x180059325  call    cs:__imp_ReleaseSRWLockExclusive
0x18005932b  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180059330  mov     rdi, rax
0x180059333  mov     ecx, [rax]
0x180059335  cmp     ecx, 4
0x180059338  jbe     short loc_1800593A8
0x18005933a  mov     rax, [rax+18h]
0x18005933e  mov     rcx, [rdi+10h]
0x180059342  mov     edx, 1000h
0x180059347  test    rdx, rcx
0x18005934a  jz      short loc_1800593A8
0x18005934c  mov     rcx, rax
0x18005934f  and     rcx, rdx
0x180059352  cmp     rcx, rax
0x180059355  jnz     short loc_1800593A8
0x180059357  call    cs:__imp_GetCurrentThreadId
0x18005935d  mov     dword ptr [rbp+SRWLock], eax
0x180059360  mov     r8, [rbx+110h]
0x180059367  mov     eax, [r8+48h]
0x18005936b  mov     dword ptr [rbp+var_78], eax
0x18005936e  mov     [rbp+var_58], 0
0x180059376  add     r8, 8
0x18005937a  lea     rax, [rbp+SRWLock]
0x18005937e  mov     [rsp+140h+var_110], rax
0x180059383  lea     rax, [rbp+var_78]
0x180059387  mov     [rsp+140h+var_118], rax
0x18005938c  lea     rax, [rbp+var_58]
0x180059390  mov     [rsp+140h+var_120], rax
0x180059395  xor     r9d, r9d
0x180059398  lea     rdx, word_1800C9E06
0x18005939f  mov     rcx, rdi
0x1800593a2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800593a7  nop
0x1800593a8  lea     rcx, [rbx+120h]; this
0x1800593af  cmp     dword ptr [rcx+18h], 0
0x1800593b3  jz      short loc_1800593BB
0x1800593b5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800593ba  nop
0x1800593bb  lea     r11, [rsp+140h+var_s0]
0x1800593c3  mov     rbx, [r11+18h]
0x1800593c7  mov     rdi, [r11+20h]
0x1800593cb  mov     rsp, r11
0x1800593ce  pop     rbp
0x1800593cf  retn
```
