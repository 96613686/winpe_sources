# ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StopActivity(void)

- ea: `0x1800152a0`
- end: `0x180015583`
- name: `?StopActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@MEAAXXZ`
- size: `739`
- prototype: `void __fastcall(ComputeCore::Diagnostics::TraceProvider::HcsClientApi *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x18000d0fc`
- `0x180014a2c`
- `0x1800152a0`
- `0x18001558c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015307`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800154d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015307`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800154d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001550a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001550a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StopActivity(
        ComputeCore::Diagnostics::TraceProvider::HcsClientApi *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
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
    v5 = *((_QWORD *)ComputeCore::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 4u
      && (*(_QWORD *)(v5 + 16) & 0x20000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x20000LL) == *(_QWORD *)(v5 + 24) )
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
        (int)&word_1800C5ADA,
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
    v6 = *((_QWORD *)ComputeCore::Diagnostics::TraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 4u
      && (*(_QWORD *)(v6 + 16) & 0x20000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x20000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v9 = *(_DWORD *)(v7 + 72);
      v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_1800C5E0B,
        v7 + 8,
        0,
        (__int64)&v16,
        (__int64)&v9,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800152a0  mov     [rsp-8+arg_8], rbx
0x1800152a5  mov     [rsp-8+arg_10], rdi
0x1800152aa  push    rbp
0x1800152ab  mov     rbp, rsp
0x1800152ae  sub     rsp, 140h
0x1800152b5  mov     rbx, rcx
0x1800152b8  mov     rdi, [rcx+110h]
0x1800152bf  mov     eax, [rdi+48h]
0x1800152c2  test    eax, eax
0x1800152c4  jns     loc_1800154B0
0x1800152ca  add     rdi, 50h ; 'P'
0x1800152ce  cmp     eax, [rdi+8]
0x1800152d1  jnz     loc_1800154B0
0x1800152d7  test    rdi, rdi
0x1800152da  jz      loc_1800154B0
0x1800152e0  mov     [rbp+SRWLock], 0
0x1800152e8  lea     rdx, [rbp+SRWLock]
0x1800152ec  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800152f1  mov     rax, [rbx+110h]
0x1800152f8  mov     dword ptr [rax], 2
0x1800152fe  mov     rcx, [rbp+SRWLock]; SRWLock
0x180015302  test    rcx, rcx
0x180015305  jz      short loc_18001530D
0x180015307  call    cs:__imp_ReleaseSRWLockExclusive
0x18001530d  call    ?Instance@TraceProvider@Diagnostics@ComputeCore@@KAPEAV123@XZ; ComputeCore::Diagnostics::TraceProvider::Instance(void)
0x180015312  mov     r9, [rax+8]
0x180015316  mov     eax, [r9]
0x180015319  cmp     eax, 4
0x18001531c  jbe     loc_18001555B
0x180015322  mov     rdx, [r9+18h]
0x180015326  mov     rax, [r9+10h]
0x18001532a  mov     ecx, 20000h
0x18001532f  test    rcx, rax
0x180015332  jz      loc_18001555B
0x180015338  mov     rax, rdx
0x18001533b  and     rax, rcx
0x18001533e  cmp     rax, rdx
0x180015341  jnz     loc_18001555B
0x180015347  mov     rax, [rdi+30h]
0x18001534b  mov     [rbp+var_50], rax
0x18001534f  mov     eax, [rdi+44h]
0x180015352  mov     dword ptr [rbp+var_78+4], eax
0x180015355  mov     eax, [rdi+10h]
0x180015358  mov     dword ptr [rbp+var_70], eax
0x18001535b  mov     rax, [rdi+78h]
0x18001535f  mov     [rbp+var_48], rax
0x180015363  mov     rax, [rdi+70h]
0x180015367  mov     [rbp+var_40], rax
0x18001536b  mov     eax, [rdi+68h]
0x18001536e  mov     dword ptr [rbp+var_70+4], eax
0x180015371  mov     rax, [rdi+60h]
0x180015375  mov     [rbp+var_38], rax
0x180015379  mov     rax, [rdi+58h]
0x18001537d  mov     [rbp+var_30], rax
0x180015381  mov     eax, [rdi+50h]
0x180015384  mov     dword ptr [rbp+var_68], eax
0x180015387  mov     rax, [rdi+48h]
0x18001538b  mov     [rbp+var_28], rax
0x18001538f  mov     eax, [rdi+20h]
0x180015392  mov     dword ptr [rbp+var_68+4], eax
0x180015395  mov     rax, [rdi+18h]
0x180015399  mov     [rbp+var_20], rax
0x18001539d  mov     eax, [rdi]
0x18001539f  mov     [rbp+var_60], eax
0x1800153a2  mov     rax, [rdi+80h]
0x1800153a9  mov     [rbp+var_18], rax
0x1800153ad  mov     eax, [rdi+40h]
0x1800153b0  mov     dword ptr [rbp+var_78], eax
0x1800153b3  mov     rax, [rdi+38h]
0x1800153b7  mov     [rbp+var_10], rax
0x1800153bb  mov     eax, [rdi+8]
0x1800153be  mov     dword ptr [rbp+SRWLock], eax
0x1800153c1  mov     [rbp+var_8], 1000000h
0x1800153c9  mov     [rbp+var_58], 0
0x1800153d1  mov     r8, [rbx+110h]
0x1800153d8  add     r8, 8; int
0x1800153dc  lea     rax, [rbp+var_50]
0x1800153e0  mov     [rsp+140h+var_90], rax; __int64
0x1800153e8  lea     rax, [rbp+var_78+4]
0x1800153ec  mov     [rsp+140h+var_98], rax; __int64
0x1800153f4  lea     rax, [rbp+var_70]
0x1800153f8  mov     [rsp+140h+var_A0], rax; __int64
0x180015400  lea     rax, [rbp+var_48]
0x180015404  mov     [rsp+140h+var_A8], rax; __int64
0x18001540c  lea     rax, [rbp+var_40]
0x180015410  mov     [rsp+140h+var_B0], rax; __int64
0x180015418  lea     rax, [rbp+var_70+4]
0x18001541c  mov     [rsp+140h+var_B8], rax; __int64
0x180015424  lea     rax, [rbp+var_38]
0x180015428  mov     [rsp+140h+var_C0], rax; __int64
0x180015430  lea     rax, [rbp+var_30]
0x180015434  mov     [rsp+140h+var_C8], rax; __int64
0x180015439  lea     rax, [rbp+var_68]
0x18001543d  mov     [rsp+140h+var_D0], rax; __int64
0x180015442  lea     rax, [rbp+var_28]
0x180015446  mov     [rsp+140h+var_D8], rax; __int64
0x18001544b  lea     rax, [rbp+var_68+4]
0x18001544f  mov     [rsp+140h+var_E0], rax; __int64
0x180015454  lea     rax, [rbp+var_20]
0x180015458  mov     [rsp+140h+var_E8], rax; __int64
0x18001545d  lea     rax, [rbp+var_60]
0x180015461  mov     [rsp+140h+var_F0], rax; __int64
0x180015466  lea     rax, [rbp+var_18]
0x18001546a  mov     [rsp+140h+var_F8], rax; __int64
0x18001546f  lea     rax, [rbp+var_78]
0x180015473  mov     [rsp+140h+var_100], rax; __int64
0x180015478  lea     rax, [rbp+var_10]
0x18001547c  mov     [rsp+140h+var_108], rax; __int64
0x180015481  lea     rax, [rbp+SRWLock]
0x180015485  mov     [rsp+140h+var_110], rax; __int64
0x18001548a  lea     rax, [rbp+var_8]
0x18001548e  mov     [rsp+140h+var_118], rax; __int64
0x180015493  lea     rax, [rbp+var_58]
0x180015497  mov     [rsp+140h+var_120], rax; __int64
0x18001549c  lea     rdx, word_1800C5ADA; int
0x1800154a3  mov     rcx, r9; int
0x1800154a6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800154ab  jmp     loc_18001555B
0x1800154b0  mov     [rbp+SRWLock], 0
0x1800154b8  lea     rdx, [rbp+SRWLock]
0x1800154bc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800154c1  mov     rax, [rbx+110h]
0x1800154c8  mov     dword ptr [rax], 2
0x1800154ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800154d2  test    rcx, rcx
0x1800154d5  jz      short loc_1800154DD
0x1800154d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800154dd  call    ?Instance@TraceProvider@Diagnostics@ComputeCore@@KAPEAV123@XZ; ComputeCore::Diagnostics::TraceProvider::Instance(void)
0x1800154e2  mov     rdi, [rax+8]
0x1800154e6  mov     eax, [rdi]
0x1800154e8  cmp     eax, 4
0x1800154eb  jbe     short loc_18001555B
0x1800154ed  mov     rdx, [rdi+18h]
0x1800154f1  mov     rax, [rdi+10h]
0x1800154f5  mov     ecx, 20000h
0x1800154fa  test    rcx, rax
0x1800154fd  jz      short loc_18001555B
0x1800154ff  mov     rax, rdx
0x180015502  and     rax, rcx
0x180015505  cmp     rax, rdx
0x180015508  jnz     short loc_18001555B
0x18001550a  call    cs:__imp_GetCurrentThreadId
0x180015510  mov     dword ptr [rbp+SRWLock], eax
0x180015513  mov     r8, [rbx+110h]
0x18001551a  mov     eax, [r8+48h]
0x18001551e  mov     dword ptr [rbp+var_78], eax
0x180015521  mov     [rbp+var_58], 0
0x180015529  add     r8, 8
0x18001552d  lea     rax, [rbp+SRWLock]
0x180015531  mov     [rsp+140h+var_110], rax
0x180015536  lea     rax, [rbp+var_78]
0x18001553a  mov     [rsp+140h+var_118], rax
0x18001553f  lea     rax, [rbp+var_58]
0x180015543  mov     [rsp+140h+var_120], rax
0x180015548  xor     r9d, r9d
0x18001554b  lea     rdx, byte_1800C5E0B
0x180015552  mov     rcx, rdi
0x180015555  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001555a  nop
0x18001555b  lea     rcx, [rbx+120h]; this
0x180015562  cmp     dword ptr [rcx+18h], 0
0x180015566  jz      short loc_18001556E
0x180015568  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001556d  nop
0x18001556e  lea     r11, [rsp+140h+var_s0]
0x180015576  mov     rbx, [r11+18h]
0x18001557a  mov     rdi, [r11+20h]
0x18001557e  mov     rsp, r11
0x180015581  pop     rbp
0x180015582  retn
```
