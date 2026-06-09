# CflApiTraceProvider::CflGetScenarioDataActivity::StopActivity(void)

- ea: `0x18000e180`
- end: `0x18000e3ee`
- name: `?StopActivity@CflGetScenarioDataActivity@CflApiTraceProvider@@MEAAXXZ`
- size: `622`
- prototype: `void __fastcall(CflApiTraceProvider::CflGetScenarioDataActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x18000a290`
- `0x18000a31c`
- `0x18000a4b8`
- `0x18000e180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e1da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e1da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e379`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e38f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e38f`

## pseudocode

```c
void __fastcall CflApiTraceProvider::CflGetScenarioDataActivity::StopActivity(
        CflApiTraceProvider::CflGetScenarioDataActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  _DWORD *v6; // rcx
  int v7; // r9d
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  _DWORD *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *v6 > 5u )
    {
      v18 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v20 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v6,
        (unsigned int)&byte_180036AC7,
        v8 + 8,
        v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = (_DWORD *)*((_QWORD *)CflApiTraceProvider::Instance() + 1);
    if ( *v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&dword_180036A6C,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000e180  push    rbp
0x18000e182  push    rbx
0x18000e183  push    rdi
0x18000e184  lea     rbp, [rsp+10h]
0x18000e189  sub     rsp, 130h
0x18000e190  mov     rdi, [rcx+110h]
0x18000e197  mov     rbx, rcx
0x18000e19a  mov     eax, [rdi+48h]
0x18000e19d  test    eax, eax
0x18000e19f  jns     loc_18000E35A
0x18000e1a5  add     rdi, 50h ; 'P'
0x18000e1a9  cmp     eax, [rdi+8]
0x18000e1ac  jnz     loc_18000E35A
0x18000e1b2  test    rdi, rdi
0x18000e1b5  jz      loc_18000E35A
0x18000e1bb  lea     rdx, [rbp+SRWLock]
0x18000e1bf  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e1c4  mov     rax, [rbx+110h]
0x18000e1cb  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000e1cf  mov     dword ptr [rax], 2
0x18000e1d5  test    rcx, rcx
0x18000e1d8  jz      short loc_18000E1E0
0x18000e1da  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e1e0  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000e1e5  mov     rcx, [rax+8]
0x18000e1e9  mov     eax, [rcx]
0x18000e1eb  cmp     eax, 5
0x18000e1ee  jbe     loc_18000E3DC
0x18000e1f4  mov     rax, [rdi+30h]
0x18000e1f8  lea     rdx, byte_180036AC7
0x18000e1ff  mov     [rbp+var_70], rax
0x18000e203  mov     eax, [rdi+44h]
0x18000e206  mov     dword ptr [rbp+SRWLock], eax
0x18000e209  mov     eax, [rdi+10h]
0x18000e20c  mov     [rbp+arg_8], eax
0x18000e20f  mov     rax, [rdi+78h]
0x18000e213  mov     [rbp+var_68], rax
0x18000e217  mov     rax, [rdi+70h]
0x18000e21b  mov     [rbp+var_60], rax
0x18000e21f  mov     eax, [rdi+68h]
0x18000e222  mov     r8, [rbx+110h]
0x18000e229  mov     dword ptr [rbp+arg_10], eax
0x18000e22c  add     r8, 8
0x18000e230  mov     rax, [rdi+60h]
0x18000e234  mov     [rbp+var_58], rax
0x18000e238  mov     rax, [rdi+58h]
0x18000e23c  mov     [rbp+var_50], rax
0x18000e240  mov     eax, [rdi+50h]
0x18000e243  mov     [rbp+arg_18], eax
0x18000e246  mov     rax, [rdi+48h]
0x18000e24a  mov     [rbp+var_48], rax
0x18000e24e  mov     eax, [rdi+20h]
0x18000e251  mov     [rbp+var_80], eax
0x18000e254  mov     rax, [rdi+18h]
0x18000e258  mov     [rbp+var_40], rax
0x18000e25c  mov     eax, [rdi]
0x18000e25e  mov     [rbp+var_7C], eax
0x18000e261  mov     rax, [rdi+80h]
0x18000e268  mov     [rbp+var_38], rax
0x18000e26c  mov     eax, [rdi+40h]
0x18000e26f  mov     [rbp+var_78], eax
0x18000e272  mov     rax, [rdi+38h]
0x18000e276  mov     [rbp+var_30], rax
0x18000e27a  mov     eax, [rdi+8]
0x18000e27d  mov     [rbp+var_74], eax
0x18000e280  lea     rax, [rbp+var_70]
0x18000e284  mov     [rsp+140h+var_90], rax
0x18000e28c  lea     rax, [rbp+SRWLock]
0x18000e290  mov     [rsp+140h+var_98], rax
0x18000e298  lea     rax, [rbp+arg_8]
0x18000e29c  mov     [rsp+140h+var_A0], rax
0x18000e2a4  lea     rax, [rbp+var_68]
0x18000e2a8  mov     [rsp+140h+var_A8], rax
0x18000e2b0  lea     rax, [rbp+var_60]
0x18000e2b4  mov     [rsp+140h+var_B0], rax
0x18000e2bc  lea     rax, [rbp+arg_10]
0x18000e2c0  mov     [rsp+140h+var_B8], rax
0x18000e2c8  lea     rax, [rbp+var_58]
0x18000e2cc  mov     [rsp+140h+var_C0], rax
0x18000e2d4  lea     rax, [rbp+var_50]
0x18000e2d8  mov     [rsp+140h+var_C8], rax
0x18000e2dd  lea     rax, [rbp+arg_18]
0x18000e2e1  mov     [rsp+140h+var_D0], rax
0x18000e2e6  lea     rax, [rbp+var_48]
0x18000e2ea  mov     [rsp+140h+var_D8], rax
0x18000e2ef  lea     rax, [rbp+var_80]
0x18000e2f3  mov     [rsp+140h+var_E0], rax
0x18000e2f8  lea     rax, [rbp+var_40]
0x18000e2fc  mov     [rsp+140h+var_E8], rax
0x18000e301  lea     rax, [rbp+var_7C]
0x18000e305  mov     [rsp+140h+var_F0], rax
0x18000e30a  lea     rax, [rbp+var_38]
0x18000e30e  mov     [rsp+140h+var_F8], rax
0x18000e313  lea     rax, [rbp+var_78]
0x18000e317  mov     [rsp+140h+var_100], rax
0x18000e31c  lea     rax, [rbp+var_30]
0x18000e320  mov     [rsp+140h+var_108], rax
0x18000e325  lea     rax, [rbp+var_74]
0x18000e329  mov     [rsp+140h+var_110], rax
0x18000e32e  lea     rax, [rbp+var_28]
0x18000e332  mov     [rsp+140h+var_118], rax
0x18000e337  lea     rax, [rbp+var_20]
0x18000e33b  mov     [rsp+140h+var_120], rax
0x18000e340  mov     [rbp+var_28], 1000000h
0x18000e348  mov     [rbp+var_20], 0
0x18000e350  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e355  jmp     loc_18000E3DC
0x18000e35a  lea     rdx, [rbp+SRWLock]
0x18000e35e  call    ?LockExclusive@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e363  mov     rax, [rbx+110h]
0x18000e36a  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000e36e  mov     dword ptr [rax], 2
0x18000e374  test    rcx, rcx
0x18000e377  jz      short loc_18000E37F
0x18000e379  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e37f  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18000e384  mov     rdi, [rax+8]
0x18000e388  mov     eax, [rdi]
0x18000e38a  cmp     eax, 5
0x18000e38d  jbe     short loc_18000E3DC
0x18000e38f  call    cs:__imp_GetCurrentThreadId
0x18000e395  mov     r8, [rbx+110h]
0x18000e39c  lea     rdx, dword_180036A6C
0x18000e3a3  mov     dword ptr [rbp+SRWLock], eax
0x18000e3a6  mov     rcx, rdi
0x18000e3a9  mov     eax, [r8+48h]
0x18000e3ad  add     r8, 8
0x18000e3b1  mov     [rbp+arg_8], eax
0x18000e3b4  lea     rax, [rbp+SRWLock]
0x18000e3b8  mov     [rsp+140h+var_110], rax
0x18000e3bd  lea     rax, [rbp+arg_8]
0x18000e3c1  mov     [rsp+140h+var_118], rax
0x18000e3c6  lea     rax, [rbp+arg_10]
0x18000e3ca  mov     [rsp+140h+var_120], rax
0x18000e3cf  mov     [rbp+arg_10], 0
0x18000e3d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e3dc  mov     rcx, rbx
0x18000e3df  add     rsp, 130h
0x18000e3e6  pop     rdi
0x18000e3e7  pop     rbx
0x18000e3e8  pop     rbp
0x18000e3e9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
