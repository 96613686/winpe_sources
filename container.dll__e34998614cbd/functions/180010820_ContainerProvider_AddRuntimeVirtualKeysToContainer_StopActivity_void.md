# ContainerProvider::AddRuntimeVirtualKeysToContainer::StopActivity(void)

- ea: `0x180010820`
- end: `0x180010aaf`
- name: `?StopActivity@AddRuntimeVirtualKeysToContainer@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::AddRuntimeVirtualKeysToContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180010820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001087a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001087a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010a3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ContainerProvider::AddRuntimeVirtualKeysToContainer::StopActivity(
        ContainerProvider::AddRuntimeVirtualKeysToContainer *this)
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
        (unsigned int)&byte_18003C1EF,
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
        (unsigned int)word_18003B76A,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::AddRuntimeVirtualKeysToContainer *)((char *)this + 288));
}

```

## disassembly

```asm
0x180010820  push    rbp
0x180010822  push    rbx
0x180010823  push    rdi
0x180010824  lea     rbp, [rsp+10h]
0x180010829  sub     rsp, 130h
0x180010830  mov     rbx, rcx
0x180010833  mov     rdi, [rcx+110h]
0x18001083a  mov     eax, [rdi+48h]
0x18001083d  test    eax, eax
0x18001083f  jns     loc_180010A02
0x180010845  add     rdi, 50h ; 'P'
0x180010849  cmp     eax, [rdi+8]
0x18001084c  jnz     loc_180010A02
0x180010852  test    rdi, rdi
0x180010855  jz      loc_180010A02
0x18001085b  lea     rdx, [rbp+SRWLock]
0x18001085f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010864  mov     rax, [rbx+110h]
0x18001086b  mov     dword ptr [rax], 2
0x180010871  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010875  test    rcx, rcx
0x180010878  jz      short loc_180010886
0x18001087a  call    cs:__imp_ReleaseSRWLockExclusive
0x180010881  nop     dword ptr [rax+rax+00h]
0x180010886  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001088b  mov     r9, rax
0x18001088e  mov     ecx, [rax]
0x180010890  cmp     ecx, 5
0x180010893  jbe     loc_180010A90
0x180010899  mov     rcx, [rdi+30h]
0x18001089d  mov     [rbp+var_70], rcx
0x1800108a1  mov     ecx, [rdi+44h]
0x1800108a4  mov     dword ptr [rbp+SRWLock], ecx
0x1800108a7  mov     ecx, [rdi+10h]
0x1800108aa  mov     [rbp+arg_8], ecx
0x1800108ad  mov     rcx, [rdi+78h]
0x1800108b1  mov     [rbp+var_68], rcx
0x1800108b5  mov     rax, [rdi+70h]
0x1800108b9  mov     [rbp+var_60], rax
0x1800108bd  mov     eax, [rdi+68h]
0x1800108c0  mov     dword ptr [rbp+arg_10], eax
0x1800108c3  mov     rax, [rdi+60h]
0x1800108c7  mov     [rbp+var_58], rax
0x1800108cb  mov     rax, [rdi+58h]
0x1800108cf  mov     [rbp+var_50], rax
0x1800108d3  mov     eax, [rdi+50h]
0x1800108d6  mov     [rbp+arg_18], eax
0x1800108d9  mov     rax, [rdi+48h]
0x1800108dd  mov     [rbp+var_48], rax
0x1800108e1  mov     eax, [rdi+20h]
0x1800108e4  mov     [rbp+var_80], eax
0x1800108e7  mov     rax, [rdi+18h]
0x1800108eb  mov     [rbp+var_40], rax
0x1800108ef  mov     eax, [rdi]
0x1800108f1  mov     [rbp+var_7C], eax
0x1800108f4  mov     rax, [rdi+80h]
0x1800108fb  mov     [rbp+var_38], rax
0x1800108ff  mov     eax, [rdi+40h]
0x180010902  mov     [rbp+var_78], eax
0x180010905  mov     rax, [rdi+38h]
0x180010909  mov     [rbp+var_30], rax
0x18001090d  mov     eax, [rdi+8]
0x180010910  mov     [rbp+var_74], eax
0x180010913  mov     [rbp+var_28], 1000000h
0x18001091b  mov     [rbp+var_20], 0
0x180010923  mov     r8, [rbx+110h]
0x18001092a  add     r8, 8
0x18001092e  lea     rax, [rbp+var_70]
0x180010932  mov     [rsp+140h+var_90], rax
0x18001093a  lea     rax, [rbp+SRWLock]
0x18001093e  mov     [rsp+140h+var_98], rax
0x180010946  lea     rax, [rbp+arg_8]
0x18001094a  mov     [rsp+140h+var_A0], rax
0x180010952  lea     rax, [rbp+var_68]
0x180010956  mov     [rsp+140h+var_A8], rax
0x18001095e  lea     rax, [rbp+var_60]
0x180010962  mov     [rsp+140h+var_B0], rax
0x18001096a  lea     rax, [rbp+arg_10]
0x18001096e  mov     [rsp+140h+var_B8], rax
0x180010976  lea     rax, [rbp+var_58]
0x18001097a  mov     [rsp+140h+var_C0], rax
0x180010982  lea     rax, [rbp+var_50]
0x180010986  mov     [rsp+140h+var_C8], rax
0x18001098b  lea     rax, [rbp+arg_18]
0x18001098f  mov     [rsp+140h+var_D0], rax
0x180010994  lea     rax, [rbp+var_48]
0x180010998  mov     [rsp+140h+var_D8], rax
0x18001099d  lea     rax, [rbp+var_80]
0x1800109a1  mov     [rsp+140h+var_E0], rax
0x1800109a6  lea     rax, [rbp+var_40]
0x1800109aa  mov     [rsp+140h+var_E8], rax
0x1800109af  lea     rax, [rbp+var_7C]
0x1800109b3  mov     [rsp+140h+var_F0], rax
0x1800109b8  lea     rax, [rbp+var_38]
0x1800109bc  mov     [rsp+140h+var_F8], rax
0x1800109c1  lea     rax, [rbp+var_78]
0x1800109c5  mov     [rsp+140h+var_100], rax
0x1800109ca  lea     rax, [rbp+var_30]
0x1800109ce  mov     [rsp+140h+var_108], rax
0x1800109d3  lea     rax, [rbp+var_74]
0x1800109d7  mov     [rsp+140h+var_110], rax
0x1800109dc  lea     rax, [rbp+var_28]
0x1800109e0  mov     [rsp+140h+var_118], rax
0x1800109e5  lea     rax, [rbp+var_20]
0x1800109e9  mov     [rsp+140h+var_120], rax
0x1800109ee  lea     rdx, byte_18003C1EF
0x1800109f5  mov     rcx, r9
0x1800109f8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800109fd  jmp     loc_180010A90
0x180010a02  lea     rdx, [rbp+SRWLock]
0x180010a06  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180010a0b  mov     rax, [rbx+110h]
0x180010a12  mov     dword ptr [rax], 2
0x180010a18  mov     rcx, [rbp+SRWLock]; SRWLock
0x180010a1c  test    rcx, rcx
0x180010a1f  jz      short loc_180010A2D
0x180010a21  call    cs:__imp_ReleaseSRWLockExclusive
0x180010a28  nop     dword ptr [rax+rax+00h]
0x180010a2d  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180010a32  mov     rdi, rax
0x180010a35  mov     ecx, [rax]
0x180010a37  cmp     ecx, 5
0x180010a3a  jbe     short loc_180010A90
0x180010a3c  call    cs:__imp_GetCurrentThreadId
0x180010a43  nop     dword ptr [rax+rax+00h]
0x180010a48  mov     dword ptr [rbp+SRWLock], eax
0x180010a4b  mov     r8, [rbx+110h]
0x180010a52  mov     ecx, [r8+48h]
0x180010a56  mov     [rbp+arg_8], ecx
0x180010a59  mov     [rbp+arg_10], 0
0x180010a61  add     r8, 8
0x180010a65  lea     rax, [rbp+SRWLock]
0x180010a69  mov     [rsp+140h+var_110], rax
0x180010a6e  lea     rax, [rbp+arg_8]
0x180010a72  mov     [rsp+140h+var_118], rax
0x180010a77  lea     rax, [rbp+arg_10]
0x180010a7b  mov     [rsp+140h+var_120], rax
0x180010a80  lea     rdx, word_18003B76A
0x180010a87  mov     rcx, rdi
0x180010a8a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180010a8f  nop
0x180010a90  lea     rcx, [rbx+120h]; this
0x180010a97  cmp     dword ptr [rcx+18h], 0
0x180010a9b  jz      short loc_180010AA3
0x180010a9d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010aa2  nop
0x180010aa3  add     rsp, 130h
0x180010aaa  pop     rdi
0x180010aab  pop     rbx
0x180010aac  pop     rbp
0x180010aad  retn
```
