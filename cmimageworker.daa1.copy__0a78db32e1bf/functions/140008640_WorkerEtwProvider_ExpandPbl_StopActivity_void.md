# WorkerEtwProvider::ExpandPbl::StopActivity(void)

- ea: `0x140008640`
- end: `0x1400088d3`
- name: `?StopActivity@ExpandPbl@WorkerEtwProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(WorkerEtwProvider::ExpandPbl *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400012bc`
- `0x14000547c`
- `0x140005644`
- `0x140006894`
- `0x140008640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000869a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008830`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000869a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000886d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000886d`

## pseudocode

```c
void __fastcall WorkerEtwProvider::ExpandPbl::StopActivity(WorkerEtwProvider::ExpandPbl *this)
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
          (unsigned int)&unk_140038EE0,
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
          (unsigned int)&word_140038E96,
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
0x140008640  push    rbp
0x140008642  push    rbx
0x140008643  push    rdi
0x140008644  lea     rbp, [rsp-47h]
0x140008649  sub     rsp, 100h
0x140008650  mov     rdi, [rcx+110h]
0x140008657  mov     rbx, rcx
0x14000865a  mov     eax, [rdi+48h]
0x14000865d  test    eax, eax
0x14000865f  jns     loc_140008811
0x140008665  add     rdi, 50h ; 'P'
0x140008669  cmp     eax, [rdi+8]
0x14000866c  jnz     loc_140008811
0x140008672  test    rdi, rdi
0x140008675  jz      loc_140008811
0x14000867b  lea     rdx, [rbp+57h+SRWLock]
0x14000867f  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008684  mov     rax, [rbx+110h]
0x14000868b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000868f  mov     dword ptr [rax], 2
0x140008695  test    rcx, rcx
0x140008698  jz      short loc_1400086A6
0x14000869a  call    cs:__imp_ReleaseSRWLockExclusive
0x1400086a1  nop     dword ptr [rax+rax+00h]
0x1400086a6  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x1400086ab  mov     r9, rax
0x1400086ae  mov     ecx, [rax]
0x1400086b0  cmp     ecx, 5
0x1400086b3  jbe     loc_1400088C1
0x1400086b9  mov     rax, [rax+18h]
0x1400086bd  mov     rdx, 400000000000h
0x1400086c7  mov     rcx, [r9+10h]
0x1400086cb  test    rdx, rcx
0x1400086ce  jz      loc_1400088C1
0x1400086d4  mov     rcx, rax
0x1400086d7  and     rcx, rdx
0x1400086da  cmp     rcx, rax
0x1400086dd  jnz     loc_1400088C1
0x1400086e3  mov     rax, [rdi+78h]
0x1400086e7  lea     rdx, unk_140038EE0
0x1400086ee  mov     r8, [rbx+110h]
0x1400086f5  mov     rcx, r9
0x1400086f8  mov     [rbp+57h+var_68], rax
0x1400086fc  add     r8, 8
0x140008700  mov     rax, [rdi+70h]
0x140008704  mov     [rbp+57h+var_60], rax
0x140008708  mov     eax, [rdi+68h]
0x14000870b  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000870e  mov     rax, [rdi+60h]
0x140008712  mov     [rbp+57h+var_58], rax
0x140008716  mov     rax, [rdi+58h]
0x14000871a  mov     [rbp+57h+var_50], rax
0x14000871e  mov     eax, [rdi+50h]
0x140008721  mov     [rbp+57h+arg_8], eax
0x140008724  mov     rax, [rdi+48h]
0x140008728  mov     [rbp+57h+var_48], rax
0x14000872c  mov     eax, [rdi+20h]
0x14000872f  mov     dword ptr [rbp+57h+arg_10], eax
0x140008732  mov     rax, [rdi+18h]
0x140008736  mov     [rbp+57h+var_40], rax
0x14000873a  mov     eax, [rdi]
0x14000873c  mov     [rbp+57h+arg_18], eax
0x14000873f  mov     rax, [rdi+80h]
0x140008746  mov     [rbp+57h+var_38], rax
0x14000874a  mov     eax, [rdi+40h]
0x14000874d  mov     [rbp+57h+var_70], eax
0x140008750  mov     rax, [rdi+38h]
0x140008754  mov     [rbp+57h+var_30], rax
0x140008758  mov     eax, [rdi+8]
0x14000875b  mov     [rbp+57h+var_6C], eax
0x14000875e  mov     eax, 1000000h
0x140008763  mov     [rbp+57h+var_28], rax
0x140008767  mov     [rbp+57h+var_20], rax
0x14000876b  lea     rax, [rbp+57h+var_68]
0x14000876f  mov     [rsp+110h+var_78], rax
0x140008777  lea     rax, [rbp+57h+var_60]
0x14000877b  mov     [rsp+110h+var_80], rax
0x140008783  lea     rax, [rbp+57h+SRWLock]
0x140008787  mov     [rsp+110h+var_88], rax
0x14000878f  lea     rax, [rbp+57h+var_58]
0x140008793  mov     [rsp+110h+var_90], rax
0x14000879b  lea     rax, [rbp+57h+var_50]
0x14000879f  mov     [rsp+110h+var_98], rax
0x1400087a4  lea     rax, [rbp+57h+arg_8]
0x1400087a8  mov     [rsp+110h+var_A0], rax
0x1400087ad  lea     rax, [rbp+57h+var_48]
0x1400087b1  mov     [rsp+110h+var_A8], rax
0x1400087b6  lea     rax, [rbp+57h+arg_10]
0x1400087ba  mov     [rsp+110h+var_B0], rax
0x1400087bf  lea     rax, [rbp+57h+var_40]
0x1400087c3  mov     [rsp+110h+var_B8], rax
0x1400087c8  lea     rax, [rbp+57h+arg_18]
0x1400087cc  mov     [rsp+110h+var_C0], rax
0x1400087d1  lea     rax, [rbp+57h+var_38]
0x1400087d5  mov     [rsp+110h+var_C8], rax
0x1400087da  lea     rax, [rbp+57h+var_70]
0x1400087de  mov     [rsp+110h+var_D0], rax
0x1400087e3  lea     rax, [rbp+57h+var_30]
0x1400087e7  mov     [rsp+110h+var_D8], rax
0x1400087ec  lea     rax, [rbp+57h+var_6C]
0x1400087f0  mov     [rsp+110h+var_E0], rax
0x1400087f5  lea     rax, [rbp+57h+var_28]
0x1400087f9  mov     [rsp+110h+var_E8], rax
0x1400087fe  lea     rax, [rbp+57h+var_20]
0x140008802  mov     [rsp+110h+var_F0], rax
0x140008807  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000880c  jmp     loc_1400088C1
0x140008811  lea     rdx, [rbp+57h+SRWLock]
0x140008815  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000881a  mov     rax, [rbx+110h]
0x140008821  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140008825  mov     dword ptr [rax], 2
0x14000882b  test    rcx, rcx
0x14000882e  jz      short loc_14000883C
0x140008830  call    cs:__imp_ReleaseSRWLockExclusive
0x140008837  nop     dword ptr [rax+rax+00h]
0x14000883c  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140008841  mov     rdi, rax
0x140008844  mov     ecx, [rax]
0x140008846  cmp     ecx, 5
0x140008849  jbe     short loc_1400088C1
0x14000884b  mov     rax, [rax+18h]
0x14000884f  mov     rdx, 400000000000h
0x140008859  mov     rcx, [rdi+10h]
0x14000885d  test    rdx, rcx
0x140008860  jz      short loc_1400088C1
0x140008862  mov     rcx, rax
0x140008865  and     rcx, rdx
0x140008868  cmp     rcx, rax
0x14000886b  jnz     short loc_1400088C1
0x14000886d  call    cs:__imp_GetCurrentThreadId
0x140008874  nop     dword ptr [rax+rax+00h]
0x140008879  mov     r8, [rbx+110h]
0x140008880  lea     rdx, word_140038E96
0x140008887  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000888a  mov     rcx, rdi
0x14000888d  mov     eax, [r8+48h]
0x140008891  add     r8, 8
0x140008895  mov     [rbp+57h+arg_8], eax
0x140008898  mov     eax, 1000000h
0x14000889d  mov     [rbp+57h+arg_10], rax
0x1400088a1  lea     rax, [rbp+57h+SRWLock]
0x1400088a5  mov     [rsp+110h+var_E0], rax
0x1400088aa  lea     rax, [rbp+57h+arg_8]
0x1400088ae  mov     [rsp+110h+var_E8], rax
0x1400088b3  lea     rax, [rbp+57h+arg_10]
0x1400088b7  mov     [rsp+110h+var_F0], rax
0x1400088bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400088c1  mov     rcx, rbx
0x1400088c4  add     rsp, 100h
0x1400088cb  pop     rdi
0x1400088cc  pop     rbx
0x1400088cd  pop     rbp
0x1400088ce  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
