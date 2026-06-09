# ContainerProvider::CleanupContainer::StopActivity(void)

- ea: `0x180010ac0`
- end: `0x180010d63`
- name: `?StopActivity@CleanupContainer@ContainerProvider@@MEAAXXZ`
- size: `675`
- prototype: `void __fastcall(ContainerProvider::CleanupContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001098`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180010ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010cb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010b1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010cb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010cf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010cf0`

## pseudocode

```c
void __fastcall ContainerProvider::CleanupContainer::StopActivity(ContainerProvider::CleanupContainer *this)
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
          (unsigned int)&dword_18003BB04,
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
          (unsigned int)word_18003B8E2,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::CleanupContainer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010ac0  push    rbp
0x180010ac2  push    rbx
0x180010ac3  push    rdi
0x180010ac4  lea     rbp, [rsp-47h]
0x180010ac9  sub     rsp, 100h
0x180010ad0  mov     rbx, rcx
0x180010ad3  mov     rdi, [rcx+110h]
0x180010ada  mov     eax, [rdi+48h]
0x180010add  test    eax, eax
0x180010adf  jns     loc_180010C94
0x180010ae5  add     rdi, 50h ; 'P'
0x180010ae9  cmp     eax, [rdi+8]
0x180010aec  jnz     loc_180010C94
0x180010af2  test    rdi, rdi
0x180010af5  jz      loc_180010C94
0x180010afb  lea     rdx, [rbp+57h+SRWLock]
0x180010aff  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010b04  mov     rax, [rbx+110h]
0x180010b0b  mov     dword ptr [rax], 2
0x180010b11  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180010b15  test    rcx, rcx
0x180010b18  jz      short loc_180010B26
0x180010b1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180010b21  nop     dword ptr [rax+rax+00h]
0x180010b26  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010b2b  mov     r9, rax
0x180010b2e  mov     ecx, [rax]
0x180010b30  cmp     ecx, 5
0x180010b33  jbe     loc_180010D44
0x180010b39  mov     rax, [rax+18h]
0x180010b3d  mov     rcx, [r9+10h]
0x180010b41  mov     rdx, 400000000000h
0x180010b4b  test    rdx, rcx
0x180010b4e  jz      loc_180010D44
0x180010b54  mov     rcx, rax
0x180010b57  and     rcx, rdx
0x180010b5a  cmp     rcx, rax
0x180010b5d  jnz     loc_180010D44
0x180010b63  mov     rax, [rdi+78h]
0x180010b67  mov     [rbp+57h+var_68], rax
0x180010b6b  mov     rax, [rdi+70h]
0x180010b6f  mov     [rbp+57h+var_60], rax
0x180010b73  mov     eax, [rdi+68h]
0x180010b76  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010b79  mov     rax, [rdi+60h]
0x180010b7d  mov     [rbp+57h+var_58], rax
0x180010b81  mov     rax, [rdi+58h]
0x180010b85  mov     [rbp+57h+var_50], rax
0x180010b89  mov     eax, [rdi+50h]
0x180010b8c  mov     [rbp+57h+arg_8], eax
0x180010b8f  mov     rax, [rdi+48h]
0x180010b93  mov     [rbp+57h+var_48], rax
0x180010b97  mov     eax, [rdi+20h]
0x180010b9a  mov     dword ptr [rbp+57h+arg_10], eax
0x180010b9d  mov     rax, [rdi+18h]
0x180010ba1  mov     [rbp+57h+var_40], rax
0x180010ba5  mov     eax, [rdi]
0x180010ba7  mov     [rbp+57h+arg_18], eax
0x180010baa  mov     rax, [rdi+80h]
0x180010bb1  mov     [rbp+57h+var_38], rax
0x180010bb5  mov     eax, [rdi+40h]
0x180010bb8  mov     [rbp+57h+var_70], eax
0x180010bbb  mov     rax, [rdi+38h]
0x180010bbf  mov     [rbp+57h+var_30], rax
0x180010bc3  mov     eax, [rdi+8]
0x180010bc6  mov     [rbp+57h+var_6C], eax
0x180010bc9  mov     [rbp+57h+var_28], 1000000h
0x180010bd1  mov     [rbp+57h+var_20], 0
0x180010bd9  mov     r8, [rbx+110h]
0x180010be0  add     r8, 8
0x180010be4  lea     rax, [rbp+57h+var_68]
0x180010be8  mov     [rsp+110h+var_78], rax
0x180010bf0  lea     rax, [rbp+57h+var_60]
0x180010bf4  mov     [rsp+110h+var_80], rax
0x180010bfc  lea     rax, [rbp+57h+SRWLock]
0x180010c00  mov     [rsp+110h+var_88], rax
0x180010c08  lea     rax, [rbp+57h+var_58]
0x180010c0c  mov     [rsp+110h+var_90], rax
0x180010c14  lea     rax, [rbp+57h+var_50]
0x180010c18  mov     [rsp+110h+var_98], rax
0x180010c1d  lea     rax, [rbp+57h+arg_8]
0x180010c21  mov     [rsp+110h+var_A0], rax
0x180010c26  lea     rax, [rbp+57h+var_48]
0x180010c2a  mov     [rsp+110h+var_A8], rax
0x180010c2f  lea     rax, [rbp+57h+arg_10]
0x180010c33  mov     [rsp+110h+var_B0], rax
0x180010c38  lea     rax, [rbp+57h+var_40]
0x180010c3c  mov     [rsp+110h+var_B8], rax
0x180010c41  lea     rax, [rbp+57h+arg_18]
0x180010c45  mov     [rsp+110h+var_C0], rax
0x180010c4a  lea     rax, [rbp+57h+var_38]
0x180010c4e  mov     [rsp+110h+var_C8], rax
0x180010c53  lea     rax, [rbp+57h+var_70]
0x180010c57  mov     [rsp+110h+var_D0], rax
0x180010c5c  lea     rax, [rbp+57h+var_30]
0x180010c60  mov     [rsp+110h+var_D8], rax
0x180010c65  lea     rax, [rbp+57h+var_6C]
0x180010c69  mov     [rsp+110h+var_E0], rax
0x180010c6e  lea     rax, [rbp+57h+var_28]
0x180010c72  mov     [rsp+110h+var_E8], rax
0x180010c77  lea     rax, [rbp+57h+var_20]
0x180010c7b  mov     [rsp+110h+var_F0], rax
0x180010c80  lea     rdx, dword_18003BB04
0x180010c87  mov     rcx, r9
0x180010c8a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180010c8f  jmp     loc_180010D44
0x180010c94  lea     rdx, [rbp+57h+SRWLock]
0x180010c98  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010c9d  mov     rax, [rbx+110h]
0x180010ca4  mov     dword ptr [rax], 2
0x180010caa  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180010cae  test    rcx, rcx
0x180010cb1  jz      short loc_180010CBF
0x180010cb3  call    cs:__imp_ReleaseSRWLockExclusive
0x180010cba  nop     dword ptr [rax+rax+00h]
0x180010cbf  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010cc4  mov     rdi, rax
0x180010cc7  mov     ecx, [rax]
0x180010cc9  cmp     ecx, 5
0x180010ccc  jbe     short loc_180010D44
0x180010cce  mov     rax, [rax+18h]
0x180010cd2  mov     rcx, [rdi+10h]
0x180010cd6  mov     rdx, 400000000000h
0x180010ce0  test    rdx, rcx
0x180010ce3  jz      short loc_180010D44
0x180010ce5  mov     rcx, rax
0x180010ce8  and     rcx, rdx
0x180010ceb  cmp     rcx, rax
0x180010cee  jnz     short loc_180010D44
0x180010cf0  call    cs:__imp_GetCurrentThreadId
0x180010cf7  nop     dword ptr [rax+rax+00h]
0x180010cfc  mov     dword ptr [rbp+57h+SRWLock], eax
0x180010cff  mov     r8, [rbx+110h]
0x180010d06  mov     eax, [r8+48h]
0x180010d0a  mov     [rbp+57h+arg_8], eax
0x180010d0d  mov     [rbp+57h+arg_10], 0
0x180010d15  add     r8, 8
0x180010d19  lea     rax, [rbp+57h+SRWLock]
0x180010d1d  mov     [rsp+110h+var_E0], rax
0x180010d22  lea     rax, [rbp+57h+arg_8]
0x180010d26  mov     [rsp+110h+var_E8], rax
0x180010d2b  lea     rax, [rbp+57h+arg_10]
0x180010d2f  mov     [rsp+110h+var_F0], rax
0x180010d34  lea     rdx, word_18003B8E2
0x180010d3b  mov     rcx, rdi
0x180010d3e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010d43  nop
0x180010d44  lea     rcx, [rbx+120h]; this
0x180010d4b  cmp     dword ptr [rcx+18h], 0
0x180010d4f  jz      short loc_180010D57
0x180010d51  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010d56  nop
0x180010d57  add     rsp, 100h
0x180010d5e  pop     rdi
0x180010d5f  pop     rbx
0x180010d60  pop     rbp
0x180010d61  retn
```
