# WorkerEtwProvider::Deploy::StopActivity(void)

- ea: `0x1400083a0`
- end: `0x140008633`
- name: `?StopActivity@Deploy@WorkerEtwProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(WorkerEtwProvider::Deploy *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001008`
- `0x1400012bc`
- `0x14000547c`
- `0x140005644`
- `0x140006894`
- `0x1400083a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400083fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400083fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008590`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400085cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400085cd`

## pseudocode

```c
void __fastcall WorkerEtwProvider::Deploy::StopActivity(WorkerEtwProvider::Deploy *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  int *v19; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v20; // [rsp+B0h] [rbp-9h] BYREF
  int *v21; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp+Fh] BYREF
  int *v24; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp+27h] BYREF
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
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WorkerEtwProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = (int *)*((_QWORD *)v4 + 15);
        v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = (int *)*((_QWORD *)v4 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = (int *)*((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_14003899B,
          v9 + 8,
          v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v32,
          &v24,
          (__int64)&v31,
          &v23,
          (__int64)&v30,
          &v22,
          &v21,
          (__int64)&SRWLock,
          &v20,
          &v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WorkerEtwProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)&byte_140039057,
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
0x1400083a0  push    rbp
0x1400083a2  push    rbx
0x1400083a3  push    rdi
0x1400083a4  lea     rbp, [rsp-47h]
0x1400083a9  sub     rsp, 100h
0x1400083b0  mov     rdi, [rcx+110h]
0x1400083b7  mov     rbx, rcx
0x1400083ba  mov     eax, [rdi+48h]
0x1400083bd  test    eax, eax
0x1400083bf  jns     loc_140008571
0x1400083c5  add     rdi, 50h ; 'P'
0x1400083c9  cmp     eax, [rdi+8]
0x1400083cc  jnz     loc_140008571
0x1400083d2  test    rdi, rdi
0x1400083d5  jz      loc_140008571
0x1400083db  lea     rdx, [rbp+57h+SRWLock]
0x1400083df  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400083e4  mov     rax, [rbx+110h]
0x1400083eb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400083ef  mov     dword ptr [rax], 2
0x1400083f5  test    rcx, rcx
0x1400083f8  jz      short loc_140008406
0x1400083fa  call    cs:__imp_ReleaseSRWLockExclusive
0x140008401  nop     dword ptr [rax+rax+00h]
0x140008406  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x14000840b  mov     r9, rax
0x14000840e  mov     ecx, [rax]
0x140008410  cmp     ecx, 5
0x140008413  jbe     loc_140008621
0x140008419  mov     rax, [rax+18h]
0x14000841d  mov     rdx, 400000000000h
0x140008427  mov     rcx, [r9+10h]
0x14000842b  test    rdx, rcx
0x14000842e  jz      loc_140008621
0x140008434  mov     rcx, rax
0x140008437  and     rcx, rdx
0x14000843a  cmp     rcx, rax
0x14000843d  jnz     loc_140008621
0x140008443  mov     rax, [rdi+78h]
0x140008447  lea     rdx, byte_14003899B
0x14000844e  mov     r8, [rbx+110h]
0x140008455  mov     rcx, r9
0x140008458  mov     [rbp+57h+var_68], rax
0x14000845c  add     r8, 8
0x140008460  mov     rax, [rdi+70h]
0x140008464  mov     [rbp+57h+var_60], rax
0x140008468  mov     eax, [rdi+68h]
0x14000846b  mov     dword ptr [rbp+57h+SRWLock], eax
0x14000846e  mov     rax, [rdi+60h]
0x140008472  mov     [rbp+57h+var_58], rax
0x140008476  mov     rax, [rdi+58h]
0x14000847a  mov     [rbp+57h+var_50], rax
0x14000847e  mov     eax, [rdi+50h]
0x140008481  mov     [rbp+57h+arg_8], eax
0x140008484  mov     rax, [rdi+48h]
0x140008488  mov     [rbp+57h+var_48], rax
0x14000848c  mov     eax, [rdi+20h]
0x14000848f  mov     dword ptr [rbp+57h+arg_10], eax
0x140008492  mov     rax, [rdi+18h]
0x140008496  mov     [rbp+57h+var_40], rax
0x14000849a  mov     eax, [rdi]
0x14000849c  mov     [rbp+57h+arg_18], eax
0x14000849f  mov     rax, [rdi+80h]
0x1400084a6  mov     [rbp+57h+var_38], rax
0x1400084aa  mov     eax, [rdi+40h]
0x1400084ad  mov     [rbp+57h+var_70], eax
0x1400084b0  mov     rax, [rdi+38h]
0x1400084b4  mov     [rbp+57h+var_30], rax
0x1400084b8  mov     eax, [rdi+8]
0x1400084bb  mov     [rbp+57h+var_6C], eax
0x1400084be  mov     eax, 1000000h
0x1400084c3  mov     [rbp+57h+var_28], rax
0x1400084c7  mov     [rbp+57h+var_20], rax
0x1400084cb  lea     rax, [rbp+57h+var_68]
0x1400084cf  mov     [rsp+110h+var_78], rax
0x1400084d7  lea     rax, [rbp+57h+var_60]
0x1400084db  mov     [rsp+110h+var_80], rax
0x1400084e3  lea     rax, [rbp+57h+SRWLock]
0x1400084e7  mov     [rsp+110h+var_88], rax
0x1400084ef  lea     rax, [rbp+57h+var_58]
0x1400084f3  mov     [rsp+110h+var_90], rax
0x1400084fb  lea     rax, [rbp+57h+var_50]
0x1400084ff  mov     [rsp+110h+var_98], rax
0x140008504  lea     rax, [rbp+57h+arg_8]
0x140008508  mov     [rsp+110h+var_A0], rax
0x14000850d  lea     rax, [rbp+57h+var_48]
0x140008511  mov     [rsp+110h+var_A8], rax
0x140008516  lea     rax, [rbp+57h+arg_10]
0x14000851a  mov     [rsp+110h+var_B0], rax
0x14000851f  lea     rax, [rbp+57h+var_40]
0x140008523  mov     [rsp+110h+var_B8], rax
0x140008528  lea     rax, [rbp+57h+arg_18]
0x14000852c  mov     [rsp+110h+var_C0], rax
0x140008531  lea     rax, [rbp+57h+var_38]
0x140008535  mov     [rsp+110h+var_C8], rax
0x14000853a  lea     rax, [rbp+57h+var_70]
0x14000853e  mov     [rsp+110h+var_D0], rax
0x140008543  lea     rax, [rbp+57h+var_30]
0x140008547  mov     [rsp+110h+var_D8], rax
0x14000854c  lea     rax, [rbp+57h+var_6C]
0x140008550  mov     [rsp+110h+var_E0], rax
0x140008555  lea     rax, [rbp+57h+var_28]
0x140008559  mov     [rsp+110h+var_E8], rax
0x14000855e  lea     rax, [rbp+57h+var_20]
0x140008562  mov     [rsp+110h+var_F0], rax
0x140008567  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000856c  jmp     loc_140008621
0x140008571  lea     rdx, [rbp+57h+SRWLock]
0x140008575  call    ?LockExclusive@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000857a  mov     rax, [rbx+110h]
0x140008581  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140008585  mov     dword ptr [rax], 2
0x14000858b  test    rcx, rcx
0x14000858e  jz      short loc_14000859C
0x140008590  call    cs:__imp_ReleaseSRWLockExclusive
0x140008597  nop     dword ptr [rax+rax+00h]
0x14000859c  call    ?Provider@WorkerEtwProvider@@SAPEBU_tlgProvider_t@@XZ; WorkerEtwProvider::Provider(void)
0x1400085a1  mov     rdi, rax
0x1400085a4  mov     ecx, [rax]
0x1400085a6  cmp     ecx, 5
0x1400085a9  jbe     short loc_140008621
0x1400085ab  mov     rax, [rax+18h]
0x1400085af  mov     rdx, 400000000000h
0x1400085b9  mov     rcx, [rdi+10h]
0x1400085bd  test    rdx, rcx
0x1400085c0  jz      short loc_140008621
0x1400085c2  mov     rcx, rax
0x1400085c5  and     rcx, rdx
0x1400085c8  cmp     rcx, rax
0x1400085cb  jnz     short loc_140008621
0x1400085cd  call    cs:__imp_GetCurrentThreadId
0x1400085d4  nop     dword ptr [rax+rax+00h]
0x1400085d9  mov     r8, [rbx+110h]
0x1400085e0  lea     rdx, byte_140039057
0x1400085e7  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400085ea  mov     rcx, rdi
0x1400085ed  mov     eax, [r8+48h]
0x1400085f1  add     r8, 8
0x1400085f5  mov     [rbp+57h+arg_8], eax
0x1400085f8  mov     eax, 1000000h
0x1400085fd  mov     [rbp+57h+arg_10], rax
0x140008601  lea     rax, [rbp+57h+SRWLock]
0x140008605  mov     [rsp+110h+var_E0], rax
0x14000860a  lea     rax, [rbp+57h+arg_8]
0x14000860e  mov     [rsp+110h+var_E8], rax
0x140008613  lea     rax, [rbp+57h+arg_10]
0x140008617  mov     [rsp+110h+var_F0], rax
0x14000861c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140008621  mov     rcx, rbx
0x140008624  add     rsp, 100h
0x14000862b  pop     rdi
0x14000862c  pop     rbx
0x14000862d  pop     rbp
0x14000862e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
