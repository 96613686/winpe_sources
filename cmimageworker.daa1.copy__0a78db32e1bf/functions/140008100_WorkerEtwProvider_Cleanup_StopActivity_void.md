# WorkerEtwProvider::Cleanup::StopActivity(void)

- ea: `0x140008100`
- end: `0x140008393`
- name: `?StopActivity@Cleanup@WorkerEtwProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(WorkerEtwProvider::Cleanup *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400012bc`
- `0x14000547c`
- `0x140005644`
- `0x140006894`
- `0x140008100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000815a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400082f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000815a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400082f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000832d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000832d`

## pseudocode

```c
void __fastcall WorkerEtwProvider::Cleanup::StopActivity(WorkerEtwProvider::Cleanup *this)
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
          (unsigned int)&dword_14003913C,
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
          (unsigned int)byte_140038953,
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
0x140008100  push    rbp
0x140008102  push    rbx
0x140008103  push    rdi
0x140008104  lea     rbp, [rsp-47h]
0x140008109  sub     rsp, 100h
0x140008110  mov     rdi, [rcx+110h]
0x140008117  mov     rbx, rcx
0x14000811a  mov     eax, [rdi+48h]
0x14000811d  test    eax, eax
0x14000811f  jns     loc_1400082D1
0x140008125  add     rdi, 50h ; 'P'
0x140008129  cmp     eax, [rdi+8]
0x14000812c  jnz     loc_1400082D1
0x140008132  test    rdi, rdi
0x140008135  jz      loc_1400082D1
0x14000813b  lea     rdx, [rbp+57h+SRWLock]
0x14000813f  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008144  mov     rax, [rbx+110h]
0x14000814b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x14000814f  mov     dword ptr [rax], 2
0x140008155  test    rcx, rcx
0x140008158  jz      short loc_140008166
0x14000815a  call    cs:__imp_ReleaseSRWLockExclusive
0x140008161  nop     dword ptr [rax+rax+00h]
0x140008166  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x14000816b  mov     r9, rax
0x14000816e  mov     ecx, [rax]
0x140008170  cmp     ecx, 5
0x140008173  jbe     loc_140008381
0x140008179  mov     rax, [rax+18h]
0x14000817d  mov     rdx, 400000000000h
0x140008187  mov     rcx, [r9+10h]
0x14000818b  test    rdx, rcx
0x14000818e  jz      loc_140008381
0x140008194  mov     rcx, rax
0x140008197  and     rcx, rdx
0x14000819a  cmp     rcx, rax
0x14000819d  jnz     loc_140008381
0x1400081a3  mov     rax, [rdi+78h]
0x1400081a7  lea     rdx, dword_14003913C
0x1400081ae  mov     r8, [rbx+110h]
0x1400081b5  mov     rcx, r9
0x1400081b8  mov     [rbp+57h+var_68], rax
0x1400081bc  add     r8, 8
0x1400081c0  mov     rax, [rdi+70h]
0x1400081c4  mov     [rbp+57h+var_60], rax
0x1400081c8  mov     eax, [rdi+68h]
0x1400081cb  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400081ce  mov     rax, [rdi+60h]
0x1400081d2  mov     [rbp+57h+var_58], rax
0x1400081d6  mov     rax, [rdi+58h]
0x1400081da  mov     [rbp+57h+var_50], rax
0x1400081de  mov     eax, [rdi+50h]
0x1400081e1  mov     [rbp+57h+arg_8], eax
0x1400081e4  mov     rax, [rdi+48h]
0x1400081e8  mov     [rbp+57h+var_48], rax
0x1400081ec  mov     eax, [rdi+20h]
0x1400081ef  mov     dword ptr [rbp+57h+arg_10], eax
0x1400081f2  mov     rax, [rdi+18h]
0x1400081f6  mov     [rbp+57h+var_40], rax
0x1400081fa  mov     eax, [rdi]
0x1400081fc  mov     [rbp+57h+arg_18], eax
0x1400081ff  mov     rax, [rdi+80h]
0x140008206  mov     [rbp+57h+var_38], rax
0x14000820a  mov     eax, [rdi+40h]
0x14000820d  mov     [rbp+57h+var_70], eax
0x140008210  mov     rax, [rdi+38h]
0x140008214  mov     [rbp+57h+var_30], rax
0x140008218  mov     eax, [rdi+8]
0x14000821b  mov     [rbp+57h+var_6C], eax
0x14000821e  mov     eax, 1000000h
0x140008223  mov     [rbp+57h+var_28], rax
0x140008227  mov     [rbp+57h+var_20], rax
0x14000822b  lea     rax, [rbp+57h+var_68]
0x14000822f  mov     [rsp+110h+var_78], rax
0x140008237  lea     rax, [rbp+57h+var_60]
0x14000823b  mov     [rsp+110h+var_80], rax
0x140008243  lea     rax, [rbp+57h+SRWLock]
0x140008247  mov     [rsp+110h+var_88], rax
0x14000824f  lea     rax, [rbp+57h+var_58]
0x140008253  mov     [rsp+110h+var_90], rax
0x14000825b  lea     rax, [rbp+57h+var_50]
0x14000825f  mov     [rsp+110h+var_98], rax
0x140008264  lea     rax, [rbp+57h+arg_8]
0x140008268  mov     [rsp+110h+var_A0], rax
0x14000826d  lea     rax, [rbp+57h+var_48]
0x140008271  mov     [rsp+110h+var_A8], rax
0x140008276  lea     rax, [rbp+57h+arg_10]
0x14000827a  mov     [rsp+110h+var_B0], rax
0x14000827f  lea     rax, [rbp+57h+var_40]
0x140008283  mov     [rsp+110h+var_B8], rax
0x140008288  lea     rax, [rbp+57h+arg_18]
0x14000828c  mov     [rsp+110h+var_C0], rax
0x140008291  lea     rax, [rbp+57h+var_38]
0x140008295  mov     [rsp+110h+var_C8], rax
0x14000829a  lea     rax, [rbp+57h+var_70]
0x14000829e  mov     [rsp+110h+var_D0], rax
0x1400082a3  lea     rax, [rbp+57h+var_30]
0x1400082a7  mov     [rsp+110h+var_D8], rax
0x1400082ac  lea     rax, [rbp+57h+var_6C]
0x1400082b0  mov     [rsp+110h+var_E0], rax
0x1400082b5  lea     rax, [rbp+57h+var_28]
0x1400082b9  mov     [rsp+110h+var_E8], rax
0x1400082be  lea     rax, [rbp+57h+var_20]
0x1400082c2  mov     [rsp+110h+var_F0], rax
0x1400082c7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400082cc  jmp     loc_140008381
0x1400082d1  lea     rdx, [rbp+57h+SRWLock]
0x1400082d5  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400082da  mov     rax, [rbx+110h]
0x1400082e1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400082e5  mov     dword ptr [rax], 2
0x1400082eb  test    rcx, rcx
0x1400082ee  jz      short loc_1400082FC
0x1400082f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400082f7  nop     dword ptr [rax+rax+00h]
0x1400082fc  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x140008301  mov     rdi, rax
0x140008304  mov     ecx, [rax]
0x140008306  cmp     ecx, 5
0x140008309  jbe     short loc_140008381
0x14000830b  mov     rax, [rax+18h]
0x14000830f  mov     rdx, 400000000000h
0x140008319  mov     rcx, [rdi+10h]
0x14000831d  test    rdx, rcx
0x140008320  jz      short loc_140008381
0x140008322  mov     rcx, rax
0x140008325  and     rcx, rdx
0x140008328  cmp     rcx, rax
0x14000832b  jnz     short loc_140008381
0x14000832d  call    cs:__imp_GetCurrentThreadId
0x140008334  nop     dword ptr [rax+rax+00h]
0x140008339  mov     r8, [rbx+110h]
0x140008340  lea     rdx, byte_140038953
0x140008347  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000834a  mov     rcx, rdi
0x14000834d  mov     eax, [r8+48h]
0x140008351  add     r8, 8
0x140008355  mov     [rbp+57h+arg_8], eax
0x140008358  mov     eax, 1000000h
0x14000835d  mov     [rbp+57h+arg_10], rax
0x140008361  lea     rax, [rbp+57h+SRWLock]
0x140008365  mov     [rsp+110h+var_E0], rax
0x14000836a  lea     rax, [rbp+57h+arg_8]
0x14000836e  mov     [rsp+110h+var_E8], rax
0x140008373  lea     rax, [rbp+57h+arg_10]
0x140008377  mov     [rsp+110h+var_F0], rax
0x14000837c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140008381  mov     rcx, rbx
0x140008384  add     rsp, 100h
0x14000838b  pop     rdi
0x14000838c  pop     rbx
0x14000838d  pop     rbp
0x14000838e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
