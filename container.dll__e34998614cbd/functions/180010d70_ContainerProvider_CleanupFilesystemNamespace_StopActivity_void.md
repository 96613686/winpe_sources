# ContainerProvider::CleanupFilesystemNamespace::StopActivity(void)

- ea: `0x180010d70`
- end: `0x180010fff`
- name: `?StopActivity@CleanupFilesystemNamespace@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::CleanupFilesystemNamespace *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180010d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010f71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f8c`

## pseudocode

```c
void __fastcall ContainerProvider::CleanupFilesystemNamespace::StopActivity(
        ContainerProvider::CleanupFilesystemNamespace *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  __int64 v8; // r8
  int v9; // r9d
  int v10; // [rsp+C0h] [rbp-80h] BYREF
  int v11; // [rsp+C4h] [rbp-7Ch] BYREF
  int v12; // [rsp+C8h] [rbp-78h] BYREF
  int v13; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v14; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+100h] [rbp-40h] BYREF
  __int64 v21; // [rsp+108h] [rbp-38h] BYREF
  __int64 v22; // [rsp+110h] [rbp-30h] BYREF
  __int64 v23; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v24[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v26; // [rsp+158h] [rbp+18h] BYREF
  __int64 v27; // [rsp+160h] [rbp+20h] BYREF
  int v28; // [rsp+168h] [rbp+28h] BYREF

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
    if ( *(_DWORD *)v5 > 5u )
    {
      v14 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v26 = v4[4];
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(v27) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v28 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      v10 = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v11 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v12 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v13 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&byte_18003B9AF,
        *((_QWORD *)this + 34) + 8,
        (_DWORD)v5,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v11,
        (__int64)&v20,
        (__int64)&v10,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v14);
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
    v6 = ContainerProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v26 = *(_DWORD *)(v8 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)word_18003B08A,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::CleanupFilesystemNamespace *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010d70  push    rbp
0x180010d72  push    rbx
0x180010d73  push    rdi
0x180010d74  lea     rbp, [rsp+10h]
0x180010d79  sub     rsp, 130h
0x180010d80  mov     rbx, rcx
0x180010d83  mov     rdi, [rcx+110h]
0x180010d8a  mov     eax, [rdi+48h]
0x180010d8d  test    eax, eax
0x180010d8f  jns     loc_180010F52
0x180010d95  add     rdi, 50h ; 'P'
0x180010d99  cmp     eax, [rdi+8]
0x180010d9c  jnz     loc_180010F52
0x180010da2  test    rdi, rdi
0x180010da5  jz      loc_180010F52
0x180010dab  lea     rdx, [rbp+SRWLock]
0x180010daf  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010db4  mov     rax, [rbx+110h]
0x180010dbb  mov     dword ptr [rax], 2
0x180010dc1  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010dc5  test    rcx, rcx
0x180010dc8  jz      short loc_180010DD6
0x180010dca  call    cs:__imp_ReleaseSRWLockExclusive
0x180010dd1  nop     dword ptr [rax+rax+00h]
0x180010dd6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010ddb  mov     r9, rax
0x180010dde  mov     ecx, [rax]
0x180010de0  cmp     ecx, 5
0x180010de3  jbe     loc_180010FE0
0x180010de9  mov     rcx, [rdi+30h]
0x180010ded  mov     [rbp+var_70], rcx
0x180010df1  mov     ecx, [rdi+44h]
0x180010df4  mov     dword ptr [rbp+SRWLock], ecx
0x180010df7  mov     ecx, [rdi+10h]
0x180010dfa  mov     [rbp+arg_8], ecx
0x180010dfd  mov     rcx, [rdi+78h]
0x180010e01  mov     [rbp+var_68], rcx
0x180010e05  mov     rax, [rdi+70h]
0x180010e09  mov     [rbp+var_60], rax
0x180010e0d  mov     eax, [rdi+68h]
0x180010e10  mov     dword ptr [rbp+arg_10], eax
0x180010e13  mov     rax, [rdi+60h]
0x180010e17  mov     [rbp+var_58], rax
0x180010e1b  mov     rax, [rdi+58h]
0x180010e1f  mov     [rbp+var_50], rax
0x180010e23  mov     eax, [rdi+50h]
0x180010e26  mov     [rbp+arg_18], eax
0x180010e29  mov     rax, [rdi+48h]
0x180010e2d  mov     [rbp+var_48], rax
0x180010e31  mov     eax, [rdi+20h]
0x180010e34  mov     [rbp+var_80], eax
0x180010e37  mov     rax, [rdi+18h]
0x180010e3b  mov     [rbp+var_40], rax
0x180010e3f  mov     eax, [rdi]
0x180010e41  mov     [rbp+var_7C], eax
0x180010e44  mov     rax, [rdi+80h]
0x180010e4b  mov     [rbp+var_38], rax
0x180010e4f  mov     eax, [rdi+40h]
0x180010e52  mov     [rbp+var_78], eax
0x180010e55  mov     rax, [rdi+38h]
0x180010e59  mov     [rbp+var_30], rax
0x180010e5d  mov     eax, [rdi+8]
0x180010e60  mov     [rbp+var_74], eax
0x180010e63  mov     [rbp+var_28], 1000000h
0x180010e6b  mov     [rbp+var_20], 0
0x180010e73  mov     r8, [rbx+110h]
0x180010e7a  add     r8, 8
0x180010e7e  lea     rax, [rbp+var_70]
0x180010e82  mov     [rsp+140h+var_90], rax
0x180010e8a  lea     rax, [rbp+SRWLock]
0x180010e8e  mov     [rsp+140h+var_98], rax
0x180010e96  lea     rax, [rbp+arg_8]
0x180010e9a  mov     [rsp+140h+var_A0], rax
0x180010ea2  lea     rax, [rbp+var_68]
0x180010ea6  mov     [rsp+140h+var_A8], rax
0x180010eae  lea     rax, [rbp+var_60]
0x180010eb2  mov     [rsp+140h+var_B0], rax
0x180010eba  lea     rax, [rbp+arg_10]
0x180010ebe  mov     [rsp+140h+var_B8], rax
0x180010ec6  lea     rax, [rbp+var_58]
0x180010eca  mov     [rsp+140h+var_C0], rax
0x180010ed2  lea     rax, [rbp+var_50]
0x180010ed6  mov     [rsp+140h+var_C8], rax
0x180010edb  lea     rax, [rbp+arg_18]
0x180010edf  mov     [rsp+140h+var_D0], rax
0x180010ee4  lea     rax, [rbp+var_48]
0x180010ee8  mov     [rsp+140h+var_D8], rax
0x180010eed  lea     rax, [rbp+var_80]
0x180010ef1  mov     [rsp+140h+var_E0], rax
0x180010ef6  lea     rax, [rbp+var_40]
0x180010efa  mov     [rsp+140h+var_E8], rax
0x180010eff  lea     rax, [rbp+var_7C]
0x180010f03  mov     [rsp+140h+var_F0], rax
0x180010f08  lea     rax, [rbp+var_38]
0x180010f0c  mov     [rsp+140h+var_F8], rax
0x180010f11  lea     rax, [rbp+var_78]
0x180010f15  mov     [rsp+140h+var_100], rax
0x180010f1a  lea     rax, [rbp+var_30]
0x180010f1e  mov     [rsp+140h+var_108], rax
0x180010f23  lea     rax, [rbp+var_74]
0x180010f27  mov     [rsp+140h+var_110], rax
0x180010f2c  lea     rax, [rbp+var_28]
0x180010f30  mov     [rsp+140h+var_118], rax
0x180010f35  lea     rax, [rbp+var_20]
0x180010f39  mov     [rsp+140h+var_120], rax
0x180010f3e  lea     rdx, byte_18003B9AF
0x180010f45  mov     rcx, r9
0x180010f48  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010f4d  jmp     loc_180010FE0
0x180010f52  lea     rdx, [rbp+SRWLock]
0x180010f56  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010f5b  mov     rax, [rbx+110h]
0x180010f62  mov     dword ptr [rax], 2
0x180010f68  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010f6c  test    rcx, rcx
0x180010f6f  jz      short loc_180010F7D
0x180010f71  call    cs:__imp_ReleaseSRWLockExclusive
0x180010f78  nop     dword ptr [rax+rax+00h]
0x180010f7d  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010f82  mov     rdi, rax
0x180010f85  mov     ecx, [rax]
0x180010f87  cmp     ecx, 5
0x180010f8a  jbe     short loc_180010FE0
0x180010f8c  call    cs:__imp_GetCurrentThreadId
0x180010f93  nop     dword ptr [rax+rax+00h]
0x180010f98  mov     dword ptr [rbp+SRWLock], eax
0x180010f9b  mov     r8, [rbx+110h]
0x180010fa2  mov     ecx, [r8+48h]
0x180010fa6  mov     [rbp+arg_8], ecx
0x180010fa9  mov     [rbp+arg_10], 0
0x180010fb1  add     r8, 8
0x180010fb5  lea     rax, [rbp+SRWLock]
0x180010fb9  mov     [rsp+140h+var_110], rax
0x180010fbe  lea     rax, [rbp+arg_8]
0x180010fc2  mov     [rsp+140h+var_118], rax
0x180010fc7  lea     rax, [rbp+arg_10]
0x180010fcb  mov     [rsp+140h+var_120], rax
0x180010fd0  lea     rdx, word_18003B08A
0x180010fd7  mov     rcx, rdi
0x180010fda  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010fdf  nop
0x180010fe0  lea     rcx, [rbx+120h]; this
0x180010fe7  cmp     dword ptr [rcx+18h], 0
0x180010feb  jz      short loc_180010FF3
0x180010fed  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010ff2  nop
0x180010ff3  add     rsp, 130h
0x180010ffa  pop     rdi
0x180010ffb  pop     rbx
0x180010ffc  pop     rbp
0x180010ffd  retn
```
