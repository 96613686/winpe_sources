# WorkerEtwProvider::ApplyAdjustments::StopActivity(void)

- ea: `0x140007e60`
- end: `0x1400080f3`
- name: `?StopActivity@ApplyAdjustments@WorkerEtwProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(WorkerEtwProvider::ApplyAdjustments *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400012bc`
- `0x14000547c`
- `0x140005644`
- `0x140006894`
- `0x140007e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007eba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008050`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000808d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000808d`

## pseudocode

```c
void __fastcall WorkerEtwProvider::ApplyAdjustments::StopActivity(WorkerEtwProvider::ApplyAdjustments *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WorkerEtwProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = *((_QWORD *)v4 + 15);
        v20 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = *((_QWORD *)v4 + 12);
        v22 = *((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = *((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = *((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = *((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = *((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&word_140038D6E,
          v9 + 8,
          (_DWORD)v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v31,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&SRWLock,
          (__int64)&v20,
          (__int64)&v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WorkerEtwProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v12,
          (unsigned int)word_140038902,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140007e60  push    rbp
0x140007e62  push    rbx
0x140007e63  push    rdi
0x140007e64  lea     rbp, [rsp-47h]
0x140007e69  sub     rsp, 100h
0x140007e70  mov     rdi, [rcx+110h]
0x140007e77  mov     rbx, rcx
0x140007e7a  mov     eax, [rdi+48h]
0x140007e7d  test    eax, eax
0x140007e7f  jns     loc_140008031
0x140007e85  add     rdi, 50h ; 'P'
0x140007e89  cmp     eax, [rdi+8]
0x140007e8c  jnz     loc_140008031
0x140007e92  test    rdi, rdi
0x140007e95  jz      loc_140008031
0x140007e9b  lea     rdx, [rbp+57h+SRWLock]
0x140007e9f  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140007ea4  mov     rax, [rbx+110h]
0x140007eab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140007eaf  mov     dword ptr [rax], 2
0x140007eb5  test    rcx, rcx
0x140007eb8  jz      short loc_140007EC6
0x140007eba  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ec1  nop     dword ptr [rax+rax+00h]
0x140007ec6  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140007ecb  mov     r9, rax
0x140007ece  mov     ecx, [rax]
0x140007ed0  cmp     ecx, 5
0x140007ed3  jbe     loc_1400080E1
0x140007ed9  mov     rax, [rax+18h]
0x140007edd  mov     rdx, 400000000000h
0x140007ee7  mov     rcx, [r9+10h]
0x140007eeb  test    rdx, rcx
0x140007eee  jz      loc_1400080E1
0x140007ef4  mov     rcx, rax
0x140007ef7  and     rcx, rdx
0x140007efa  cmp     rcx, rax
0x140007efd  jnz     loc_1400080E1
0x140007f03  mov     rax, [rdi+78h]
0x140007f07  lea     rdx, word_140038D6E
0x140007f0e  mov     r8, [rbx+110h]
0x140007f15  mov     rcx, r9
0x140007f18  mov     [rbp+57h+var_68], rax
0x140007f1c  add     r8, 8
0x140007f20  mov     rax, [rdi+70h]
0x140007f24  mov     [rbp+57h+var_60], rax
0x140007f28  mov     eax, [rdi+68h]
0x140007f2b  mov     dword ptr [rbp+57h+SRWLock], eax
0x140007f2e  mov     rax, [rdi+60h]
0x140007f32  mov     [rbp+57h+var_58], rax
0x140007f36  mov     rax, [rdi+58h]
0x140007f3a  mov     [rbp+57h+var_50], rax
0x140007f3e  mov     eax, [rdi+50h]
0x140007f41  mov     [rbp+57h+arg_8], eax
0x140007f44  mov     rax, [rdi+48h]
0x140007f48  mov     [rbp+57h+var_48], rax
0x140007f4c  mov     eax, [rdi+20h]
0x140007f4f  mov     dword ptr [rbp+57h+arg_10], eax
0x140007f52  mov     rax, [rdi+18h]
0x140007f56  mov     [rbp+57h+var_40], rax
0x140007f5a  mov     eax, [rdi]
0x140007f5c  mov     [rbp+57h+arg_18], eax
0x140007f5f  mov     rax, [rdi+80h]
0x140007f66  mov     [rbp+57h+var_38], rax
0x140007f6a  mov     eax, [rdi+40h]
0x140007f6d  mov     [rbp+57h+var_70], eax
0x140007f70  mov     rax, [rdi+38h]
0x140007f74  mov     [rbp+57h+var_30], rax
0x140007f78  mov     eax, [rdi+8]
0x140007f7b  mov     [rbp+57h+var_6C], eax
0x140007f7e  mov     eax, 1000000h
0x140007f83  mov     [rbp+57h+var_28], rax
0x140007f87  mov     [rbp+57h+var_20], rax
0x140007f8b  lea     rax, [rbp+57h+var_68]
0x140007f8f  mov     [rsp+110h+var_78], rax
0x140007f97  lea     rax, [rbp+57h+var_60]
0x140007f9b  mov     [rsp+110h+var_80], rax
0x140007fa3  lea     rax, [rbp+57h+SRWLock]
0x140007fa7  mov     [rsp+110h+var_88], rax
0x140007faf  lea     rax, [rbp+57h+var_58]
0x140007fb3  mov     [rsp+110h+var_90], rax
0x140007fbb  lea     rax, [rbp+57h+var_50]
0x140007fbf  mov     [rsp+110h+var_98], rax
0x140007fc4  lea     rax, [rbp+57h+arg_8]
0x140007fc8  mov     [rsp+110h+var_A0], rax
0x140007fcd  lea     rax, [rbp+57h+var_48]
0x140007fd1  mov     [rsp+110h+var_A8], rax
0x140007fd6  lea     rax, [rbp+57h+arg_10]
0x140007fda  mov     [rsp+110h+var_B0], rax
0x140007fdf  lea     rax, [rbp+57h+var_40]
0x140007fe3  mov     [rsp+110h+var_B8], rax
0x140007fe8  lea     rax, [rbp+57h+arg_18]
0x140007fec  mov     [rsp+110h+var_C0], rax
0x140007ff1  lea     rax, [rbp+57h+var_38]
0x140007ff5  mov     [rsp+110h+var_C8], rax
0x140007ffa  lea     rax, [rbp+57h+var_70]
0x140007ffe  mov     [rsp+110h+var_D0], rax
0x140008003  lea     rax, [rbp+57h+var_30]
0x140008007  mov     [rsp+110h+var_D8], rax
0x14000800c  lea     rax, [rbp+57h+var_6C]
0x140008010  mov     [rsp+110h+var_E0], rax
0x140008015  lea     rax, [rbp+57h+var_28]
0x140008019  mov     [rsp+110h+var_E8], rax
0x14000801e  lea     rax, [rbp+57h+var_20]
0x140008022  mov     [rsp+110h+var_F0], rax
0x140008027  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000802c  jmp     loc_1400080E1
0x140008031  lea     rdx, [rbp+57h+SRWLock]
0x140008035  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000803a  mov     rax, [rbx+110h]
0x140008041  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140008045  mov     dword ptr [rax], 2
0x14000804b  test    rcx, rcx
0x14000804e  jz      short loc_14000805C
0x140008050  call    cs:__imp_ReleaseSRWLockExclusive
0x140008057  nop     dword ptr [rax+rax+00h]
0x14000805c  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140008061  mov     rdi, rax
0x140008064  mov     ecx, [rax]
0x140008066  cmp     ecx, 5
0x140008069  jbe     short loc_1400080E1
0x14000806b  mov     rax, [rax+18h]
0x14000806f  mov     rdx, 400000000000h
0x140008079  mov     rcx, [rdi+10h]
0x14000807d  test    rdx, rcx
0x140008080  jz      short loc_1400080E1
0x140008082  mov     rcx, rax
0x140008085  and     rcx, rdx
0x140008088  cmp     rcx, rax
0x14000808b  jnz     short loc_1400080E1
0x14000808d  call    cs:__imp_GetCurrentThreadId
0x140008094  nop     dword ptr [rax+rax+00h]
0x140008099  mov     r8, [rbx+110h]
0x1400080a0  lea     rdx, word_140038902
0x1400080a7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400080aa  mov     rcx, rdi
0x1400080ad  mov     eax, [r8+48h]
0x1400080b1  add     r8, 8
0x1400080b5  mov     [rbp+57h+arg_8], eax
0x1400080b8  mov     eax, 1000000h
0x1400080bd  mov     [rbp+57h+arg_10], rax
0x1400080c1  lea     rax, [rbp+57h+SRWLock]
0x1400080c5  mov     [rsp+110h+var_E0], rax
0x1400080ca  lea     rax, [rbp+57h+arg_8]
0x1400080ce  mov     [rsp+110h+var_E8], rax
0x1400080d3  lea     rax, [rbp+57h+arg_10]
0x1400080d7  mov     [rsp+110h+var_F0], rax
0x1400080dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400080e1  mov     rcx, rbx
0x1400080e4  add     rsp, 100h
0x1400080eb  pop     rdi
0x1400080ec  pop     rbx
0x1400080ed  pop     rbp
0x1400080ee  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
