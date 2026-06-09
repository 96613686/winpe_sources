# ContainerProvider::ConvertToServerSilo::StopActivity(void)

- ea: `0x180011010`
- end: `0x1800112b3`
- name: `?StopActivity@ConvertToServerSilo@ContainerProvider@@MEAAXXZ`
- size: `675`
- prototype: `void __fastcall(ContainerProvider::ConvertToServerSilo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001098`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001106a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011203`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001106a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011203`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011240`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011240`

## pseudocode

```c
void __fastcall ContainerProvider::ConvertToServerSilo::StopActivity(ContainerProvider::ConvertToServerSilo *this)
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
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = ContainerProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v15 = *((_QWORD *)v4 + 15);
        v16 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = *((_QWORD *)v4 + 12);
        v18 = *((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = *((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = *((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = *((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0x2000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)byte_18003B0E5,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          (__int64)&v22,
          (__int64)&v13,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v20,
          (__int64)&v27,
          (__int64)&v19,
          (__int64)&v26,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&SRWLock,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = ContainerProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0x2000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&dword_18003BC2C,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::ConvertToServerSilo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011010  push    rbp
0x180011012  push    rbx
0x180011013  push    rdi
0x180011014  lea     rbp, [rsp-47h]
0x180011019  sub     rsp, 100h
0x180011020  mov     rbx, rcx
0x180011023  mov     rdi, [rcx+110h]
0x18001102a  mov     eax, [rdi+48h]
0x18001102d  test    eax, eax
0x18001102f  jns     loc_1800111E4
0x180011035  add     rdi, 50h ; 'P'
0x180011039  cmp     eax, [rdi+8]
0x18001103c  jnz     loc_1800111E4
0x180011042  test    rdi, rdi
0x180011045  jz      loc_1800111E4
0x18001104b  lea     rdx, [rbp+57h+SRWLock]
0x18001104f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011054  mov     rax, [rbx+110h]
0x18001105b  mov     dword ptr [rax], 2
0x180011061  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180011065  test    rcx, rcx
0x180011068  jz      short loc_180011076
0x18001106a  call    cs:__imp_ReleaseSRWLockExclusive
0x180011071  nop     dword ptr [rax+rax+00h]
0x180011076  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001107b  mov     r9, rax
0x18001107e  mov     ecx, [rax]
0x180011080  cmp     ecx, 5
0x180011083  jbe     loc_180011294
0x180011089  mov     rax, [rax+18h]
0x18001108d  mov     rcx, [r9+10h]
0x180011091  mov     rdx, 400000000000h
0x18001109b  test    rdx, rcx
0x18001109e  jz      loc_180011294
0x1800110a4  mov     rcx, rax
0x1800110a7  and     rcx, rdx
0x1800110aa  cmp     rcx, rax
0x1800110ad  jnz     loc_180011294
0x1800110b3  mov     rax, [rdi+78h]
0x1800110b7  mov     [rbp+57h+var_68], rax
0x1800110bb  mov     rax, [rdi+70h]
0x1800110bf  mov     [rbp+57h+var_60], rax
0x1800110c3  mov     eax, [rdi+68h]
0x1800110c6  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800110c9  mov     rax, [rdi+60h]
0x1800110cd  mov     [rbp+57h+var_58], rax
0x1800110d1  mov     rax, [rdi+58h]
0x1800110d5  mov     [rbp+57h+var_50], rax
0x1800110d9  mov     eax, [rdi+50h]
0x1800110dc  mov     [rbp+57h+arg_8], eax
0x1800110df  mov     rax, [rdi+48h]
0x1800110e3  mov     [rbp+57h+var_48], rax
0x1800110e7  mov     eax, [rdi+20h]
0x1800110ea  mov     dword ptr [rbp+57h+arg_10], eax
0x1800110ed  mov     rax, [rdi+18h]
0x1800110f1  mov     [rbp+57h+var_40], rax
0x1800110f5  mov     eax, [rdi]
0x1800110f7  mov     [rbp+57h+arg_18], eax
0x1800110fa  mov     rax, [rdi+80h]
0x180011101  mov     [rbp+57h+var_38], rax
0x180011105  mov     eax, [rdi+40h]
0x180011108  mov     [rbp+57h+var_70], eax
0x18001110b  mov     rax, [rdi+38h]
0x18001110f  mov     [rbp+57h+var_30], rax
0x180011113  mov     eax, [rdi+8]
0x180011116  mov     [rbp+57h+var_6C], eax
0x180011119  mov     [rbp+57h+var_28], 1000000h
0x180011121  mov     [rbp+57h+var_20], 2000000h
0x180011129  mov     r8, [rbx+110h]
0x180011130  add     r8, 8
0x180011134  lea     rax, [rbp+57h+var_68]
0x180011138  mov     [rsp+110h+var_78], rax
0x180011140  lea     rax, [rbp+57h+var_60]
0x180011144  mov     [rsp+110h+var_80], rax
0x18001114c  lea     rax, [rbp+57h+SRWLock]
0x180011150  mov     [rsp+110h+var_88], rax
0x180011158  lea     rax, [rbp+57h+var_58]
0x18001115c  mov     [rsp+110h+var_90], rax
0x180011164  lea     rax, [rbp+57h+var_50]
0x180011168  mov     [rsp+110h+var_98], rax
0x18001116d  lea     rax, [rbp+57h+arg_8]
0x180011171  mov     [rsp+110h+var_A0], rax
0x180011176  lea     rax, [rbp+57h+var_48]
0x18001117a  mov     [rsp+110h+var_A8], rax
0x18001117f  lea     rax, [rbp+57h+arg_10]
0x180011183  mov     [rsp+110h+var_B0], rax
0x180011188  lea     rax, [rbp+57h+var_40]
0x18001118c  mov     [rsp+110h+var_B8], rax
0x180011191  lea     rax, [rbp+57h+arg_18]
0x180011195  mov     [rsp+110h+var_C0], rax
0x18001119a  lea     rax, [rbp+57h+var_38]
0x18001119e  mov     [rsp+110h+var_C8], rax
0x1800111a3  lea     rax, [rbp+57h+var_70]
0x1800111a7  mov     [rsp+110h+var_D0], rax
0x1800111ac  lea     rax, [rbp+57h+var_30]
0x1800111b0  mov     [rsp+110h+var_D8], rax
0x1800111b5  lea     rax, [rbp+57h+var_6C]
0x1800111b9  mov     [rsp+110h+var_E0], rax
0x1800111be  lea     rax, [rbp+57h+var_28]
0x1800111c2  mov     [rsp+110h+var_E8], rax
0x1800111c7  lea     rax, [rbp+57h+var_20]
0x1800111cb  mov     [rsp+110h+var_F0], rax
0x1800111d0  lea     rdx, byte_18003B0E5
0x1800111d7  mov     rcx, r9
0x1800111da  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800111df  jmp     loc_180011294
0x1800111e4  lea     rdx, [rbp+57h+SRWLock]
0x1800111e8  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800111ed  mov     rax, [rbx+110h]
0x1800111f4  mov     dword ptr [rax], 2
0x1800111fa  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800111fe  test    rcx, rcx
0x180011201  jz      short loc_18001120F
0x180011203  call    cs:__imp_ReleaseSRWLockExclusive
0x18001120a  nop     dword ptr [rax+rax+00h]
0x18001120f  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011214  mov     rdi, rax
0x180011217  mov     ecx, [rax]
0x180011219  cmp     ecx, 5
0x18001121c  jbe     short loc_180011294
0x18001121e  mov     rax, [rax+18h]
0x180011222  mov     rcx, [rdi+10h]
0x180011226  mov     rdx, 400000000000h
0x180011230  test    rdx, rcx
0x180011233  jz      short loc_180011294
0x180011235  mov     rcx, rax
0x180011238  and     rcx, rdx
0x18001123b  cmp     rcx, rax
0x18001123e  jnz     short loc_180011294
0x180011240  call    cs:__imp_GetCurrentThreadId
0x180011247  nop     dword ptr [rax+rax+00h]
0x18001124c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001124f  mov     r8, [rbx+110h]
0x180011256  mov     eax, [r8+48h]
0x18001125a  mov     [rbp+57h+arg_8], eax
0x18001125d  mov     [rbp+57h+arg_10], 2000000h
0x180011265  add     r8, 8
0x180011269  lea     rax, [rbp+57h+SRWLock]
0x18001126d  mov     [rsp+110h+var_E0], rax
0x180011272  lea     rax, [rbp+57h+arg_8]
0x180011276  mov     [rsp+110h+var_E8], rax
0x18001127b  lea     rax, [rbp+57h+arg_10]
0x18001127f  mov     [rsp+110h+var_F0], rax
0x180011284  lea     rdx, dword_18003BC2C
0x18001128b  mov     rcx, rdi
0x18001128e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011293  nop
0x180011294  lea     rcx, [rbx+120h]; this
0x18001129b  cmp     dword ptr [rcx+18h], 0
0x18001129f  jz      short loc_1800112A7
0x1800112a1  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800112a6  nop
0x1800112a7  add     rsp, 100h
0x1800112ae  pop     rdi
0x1800112af  pop     rbx
0x1800112b0  pop     rbp
0x1800112b1  retn
```
