# ContainerProvider::LaunchApplicationContainer::StopActivity(void)

- ea: `0x180011560`
- end: `0x180011803`
- name: `?StopActivity@LaunchApplicationContainer@ContainerProvider@@MEAAXXZ`
- size: `675`
- prototype: `void __fastcall(ContainerProvider::LaunchApplicationContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001098`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180011560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011753`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800115ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011790`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011790`

## pseudocode

```c
void __fastcall ContainerProvider::LaunchApplicationContainer::StopActivity(
        ContainerProvider::LaunchApplicationContainer *this)
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
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
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
        v24[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)word_18003C592,
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
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_18003BCD9,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::LaunchApplicationContainer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011560  push    rbp
0x180011562  push    rbx
0x180011563  push    rdi
0x180011564  lea     rbp, [rsp-47h]
0x180011569  sub     rsp, 100h
0x180011570  mov     rbx, rcx
0x180011573  mov     rdi, [rcx+110h]
0x18001157a  mov     eax, [rdi+48h]
0x18001157d  test    eax, eax
0x18001157f  jns     loc_180011734
0x180011585  add     rdi, 50h ; 'P'
0x180011589  cmp     eax, [rdi+8]
0x18001158c  jnz     loc_180011734
0x180011592  test    rdi, rdi
0x180011595  jz      loc_180011734
0x18001159b  lea     rdx, [rbp+57h+SRWLock]
0x18001159f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800115a4  mov     rax, [rbx+110h]
0x1800115ab  mov     dword ptr [rax], 2
0x1800115b1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800115b5  test    rcx, rcx
0x1800115b8  jz      short loc_1800115C6
0x1800115ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800115c1  nop     dword ptr [rax+rax+00h]
0x1800115c6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800115cb  mov     r9, rax
0x1800115ce  mov     ecx, [rax]
0x1800115d0  cmp     ecx, 5
0x1800115d3  jbe     loc_1800117E4
0x1800115d9  mov     rax, [rax+18h]
0x1800115dd  mov     rcx, [r9+10h]
0x1800115e1  mov     rdx, 400000000000h
0x1800115eb  test    rdx, rcx
0x1800115ee  jz      loc_1800117E4
0x1800115f4  mov     rcx, rax
0x1800115f7  and     rcx, rdx
0x1800115fa  cmp     rcx, rax
0x1800115fd  jnz     loc_1800117E4
0x180011603  mov     rax, [rdi+78h]
0x180011607  mov     [rbp+57h+var_68], rax
0x18001160b  mov     rax, [rdi+70h]
0x18001160f  mov     [rbp+57h+var_60], rax
0x180011613  mov     eax, [rdi+68h]
0x180011616  mov     dword ptr [rbp+57h+SRWLock], eax
0x180011619  mov     rax, [rdi+60h]
0x18001161d  mov     [rbp+57h+var_58], rax
0x180011621  mov     rax, [rdi+58h]
0x180011625  mov     [rbp+57h+var_50], rax
0x180011629  mov     eax, [rdi+50h]
0x18001162c  mov     [rbp+57h+arg_8], eax
0x18001162f  mov     rax, [rdi+48h]
0x180011633  mov     [rbp+57h+var_48], rax
0x180011637  mov     eax, [rdi+20h]
0x18001163a  mov     dword ptr [rbp+57h+arg_10], eax
0x18001163d  mov     rax, [rdi+18h]
0x180011641  mov     [rbp+57h+var_40], rax
0x180011645  mov     eax, [rdi]
0x180011647  mov     [rbp+57h+arg_18], eax
0x18001164a  mov     rax, [rdi+80h]
0x180011651  mov     [rbp+57h+var_38], rax
0x180011655  mov     eax, [rdi+40h]
0x180011658  mov     [rbp+57h+var_70], eax
0x18001165b  mov     rax, [rdi+38h]
0x18001165f  mov     [rbp+57h+var_30], rax
0x180011663  mov     eax, [rdi+8]
0x180011666  mov     [rbp+57h+var_6C], eax
0x180011669  mov     [rbp+57h+var_28], 1000000h
0x180011671  mov     [rbp+57h+var_20], 0
0x180011679  mov     r8, [rbx+110h]
0x180011680  add     r8, 8
0x180011684  lea     rax, [rbp+57h+var_68]
0x180011688  mov     [rsp+110h+var_78], rax
0x180011690  lea     rax, [rbp+57h+var_60]
0x180011694  mov     [rsp+110h+var_80], rax
0x18001169c  lea     rax, [rbp+57h+SRWLock]
0x1800116a0  mov     [rsp+110h+var_88], rax
0x1800116a8  lea     rax, [rbp+57h+var_58]
0x1800116ac  mov     [rsp+110h+var_90], rax
0x1800116b4  lea     rax, [rbp+57h+var_50]
0x1800116b8  mov     [rsp+110h+var_98], rax
0x1800116bd  lea     rax, [rbp+57h+arg_8]
0x1800116c1  mov     [rsp+110h+var_A0], rax
0x1800116c6  lea     rax, [rbp+57h+var_48]
0x1800116ca  mov     [rsp+110h+var_A8], rax
0x1800116cf  lea     rax, [rbp+57h+arg_10]
0x1800116d3  mov     [rsp+110h+var_B0], rax
0x1800116d8  lea     rax, [rbp+57h+var_40]
0x1800116dc  mov     [rsp+110h+var_B8], rax
0x1800116e1  lea     rax, [rbp+57h+arg_18]
0x1800116e5  mov     [rsp+110h+var_C0], rax
0x1800116ea  lea     rax, [rbp+57h+var_38]
0x1800116ee  mov     [rsp+110h+var_C8], rax
0x1800116f3  lea     rax, [rbp+57h+var_70]
0x1800116f7  mov     [rsp+110h+var_D0], rax
0x1800116fc  lea     rax, [rbp+57h+var_30]
0x180011700  mov     [rsp+110h+var_D8], rax
0x180011705  lea     rax, [rbp+57h+var_6C]
0x180011709  mov     [rsp+110h+var_E0], rax
0x18001170e  lea     rax, [rbp+57h+var_28]
0x180011712  mov     [rsp+110h+var_E8], rax
0x180011717  lea     rax, [rbp+57h+var_20]
0x18001171b  mov     [rsp+110h+var_F0], rax
0x180011720  lea     rdx, word_18003C592
0x180011727  mov     rcx, r9
0x18001172a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001172f  jmp     loc_1800117E4
0x180011734  lea     rdx, [rbp+57h+SRWLock]
0x180011738  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001173d  mov     rax, [rbx+110h]
0x180011744  mov     dword ptr [rax], 2
0x18001174a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001174e  test    rcx, rcx
0x180011751  jz      short loc_18001175F
0x180011753  call    cs:__imp_ReleaseSRWLockExclusive
0x18001175a  nop     dword ptr [rax+rax+00h]
0x18001175f  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011764  mov     rdi, rax
0x180011767  mov     ecx, [rax]
0x180011769  cmp     ecx, 5
0x18001176c  jbe     short loc_1800117E4
0x18001176e  mov     rax, [rax+18h]
0x180011772  mov     rcx, [rdi+10h]
0x180011776  mov     rdx, 400000000000h
0x180011780  test    rdx, rcx
0x180011783  jz      short loc_1800117E4
0x180011785  mov     rcx, rax
0x180011788  and     rcx, rdx
0x18001178b  cmp     rcx, rax
0x18001178e  jnz     short loc_1800117E4
0x180011790  call    cs:__imp_GetCurrentThreadId
0x180011797  nop     dword ptr [rax+rax+00h]
0x18001179c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001179f  mov     r8, [rbx+110h]
0x1800117a6  mov     eax, [r8+48h]
0x1800117aa  mov     [rbp+57h+arg_8], eax
0x1800117ad  mov     [rbp+57h+arg_10], 0
0x1800117b5  add     r8, 8
0x1800117b9  lea     rax, [rbp+57h+SRWLock]
0x1800117bd  mov     [rsp+110h+var_E0], rax
0x1800117c2  lea     rax, [rbp+57h+arg_8]
0x1800117c6  mov     [rsp+110h+var_E8], rax
0x1800117cb  lea     rax, [rbp+57h+arg_10]
0x1800117cf  mov     [rsp+110h+var_F0], rax
0x1800117d4  lea     rdx, byte_18003BCD9
0x1800117db  mov     rcx, rdi
0x1800117de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800117e3  nop
0x1800117e4  lea     rcx, [rbx+120h]; this
0x1800117eb  cmp     dword ptr [rcx+18h], 0
0x1800117ef  jz      short loc_1800117F7
0x1800117f1  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800117f6  nop
0x1800117f7  add     rsp, 100h
0x1800117fe  pop     rdi
0x1800117ff  pop     rbx
0x180011800  pop     rbp
0x180011801  retn
```
