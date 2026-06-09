# ContainerProvider::CreateContainer::StopActivity(void)

- ea: `0x1800112c0`
- end: `0x18001154f`
- name: `?StopActivity@CreateContainer@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::CreateContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x1800112c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001131a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800114c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001131a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800114c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114dc`

## pseudocode

```c
void __fastcall ContainerProvider::CreateContainer::StopActivity(ContainerProvider::CreateContainer *this)
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
        (unsigned int)qword_18003B620,
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
        (unsigned int)&byte_18003B95F,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::CreateContainer *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800112c0  push    rbp
0x1800112c2  push    rbx
0x1800112c3  push    rdi
0x1800112c4  lea     rbp, [rsp+10h]
0x1800112c9  sub     rsp, 130h
0x1800112d0  mov     rbx, rcx
0x1800112d3  mov     rdi, [rcx+110h]
0x1800112da  mov     eax, [rdi+48h]
0x1800112dd  test    eax, eax
0x1800112df  jns     loc_1800114A2
0x1800112e5  add     rdi, 50h ; 'P'
0x1800112e9  cmp     eax, [rdi+8]
0x1800112ec  jnz     loc_1800114A2
0x1800112f2  test    rdi, rdi
0x1800112f5  jz      loc_1800114A2
0x1800112fb  lea     rdx, [rbp+SRWLock]
0x1800112ff  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011304  mov     rax, [rbx+110h]
0x18001130b  mov     dword ptr [rax], 2
0x180011311  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011315  test    rcx, rcx
0x180011318  jz      short loc_180011326
0x18001131a  call    cs:__imp_ReleaseSRWLockExclusive
0x180011321  nop     dword ptr [rax+rax+00h]
0x180011326  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001132b  mov     r9, rax
0x18001132e  mov     ecx, [rax]
0x180011330  cmp     ecx, 5
0x180011333  jbe     loc_180011530
0x180011339  mov     rcx, [rdi+30h]
0x18001133d  mov     [rbp+var_70], rcx
0x180011341  mov     ecx, [rdi+44h]
0x180011344  mov     dword ptr [rbp+SRWLock], ecx
0x180011347  mov     ecx, [rdi+10h]
0x18001134a  mov     [rbp+arg_8], ecx
0x18001134d  mov     rcx, [rdi+78h]
0x180011351  mov     [rbp+var_68], rcx
0x180011355  mov     rax, [rdi+70h]
0x180011359  mov     [rbp+var_60], rax
0x18001135d  mov     eax, [rdi+68h]
0x180011360  mov     dword ptr [rbp+arg_10], eax
0x180011363  mov     rax, [rdi+60h]
0x180011367  mov     [rbp+var_58], rax
0x18001136b  mov     rax, [rdi+58h]
0x18001136f  mov     [rbp+var_50], rax
0x180011373  mov     eax, [rdi+50h]
0x180011376  mov     [rbp+arg_18], eax
0x180011379  mov     rax, [rdi+48h]
0x18001137d  mov     [rbp+var_48], rax
0x180011381  mov     eax, [rdi+20h]
0x180011384  mov     [rbp+var_80], eax
0x180011387  mov     rax, [rdi+18h]
0x18001138b  mov     [rbp+var_40], rax
0x18001138f  mov     eax, [rdi]
0x180011391  mov     [rbp+var_7C], eax
0x180011394  mov     rax, [rdi+80h]
0x18001139b  mov     [rbp+var_38], rax
0x18001139f  mov     eax, [rdi+40h]
0x1800113a2  mov     [rbp+var_78], eax
0x1800113a5  mov     rax, [rdi+38h]
0x1800113a9  mov     [rbp+var_30], rax
0x1800113ad  mov     eax, [rdi+8]
0x1800113b0  mov     [rbp+var_74], eax
0x1800113b3  mov     [rbp+var_28], 1000000h
0x1800113bb  mov     [rbp+var_20], 0
0x1800113c3  mov     r8, [rbx+110h]
0x1800113ca  add     r8, 8
0x1800113ce  lea     rax, [rbp+var_70]
0x1800113d2  mov     [rsp+140h+var_90], rax
0x1800113da  lea     rax, [rbp+SRWLock]
0x1800113de  mov     [rsp+140h+var_98], rax
0x1800113e6  lea     rax, [rbp+arg_8]
0x1800113ea  mov     [rsp+140h+var_A0], rax
0x1800113f2  lea     rax, [rbp+var_68]
0x1800113f6  mov     [rsp+140h+var_A8], rax
0x1800113fe  lea     rax, [rbp+var_60]
0x180011402  mov     [rsp+140h+var_B0], rax
0x18001140a  lea     rax, [rbp+arg_10]
0x18001140e  mov     [rsp+140h+var_B8], rax
0x180011416  lea     rax, [rbp+var_58]
0x18001141a  mov     [rsp+140h+var_C0], rax
0x180011422  lea     rax, [rbp+var_50]
0x180011426  mov     [rsp+140h+var_C8], rax
0x18001142b  lea     rax, [rbp+arg_18]
0x18001142f  mov     [rsp+140h+var_D0], rax
0x180011434  lea     rax, [rbp+var_48]
0x180011438  mov     [rsp+140h+var_D8], rax
0x18001143d  lea     rax, [rbp+var_80]
0x180011441  mov     [rsp+140h+var_E0], rax
0x180011446  lea     rax, [rbp+var_40]
0x18001144a  mov     [rsp+140h+var_E8], rax
0x18001144f  lea     rax, [rbp+var_7C]
0x180011453  mov     [rsp+140h+var_F0], rax
0x180011458  lea     rax, [rbp+var_38]
0x18001145c  mov     [rsp+140h+var_F8], rax
0x180011461  lea     rax, [rbp+var_78]
0x180011465  mov     [rsp+140h+var_100], rax
0x18001146a  lea     rax, [rbp+var_30]
0x18001146e  mov     [rsp+140h+var_108], rax
0x180011473  lea     rax, [rbp+var_74]
0x180011477  mov     [rsp+140h+var_110], rax
0x18001147c  lea     rax, [rbp+var_28]
0x180011480  mov     [rsp+140h+var_118], rax
0x180011485  lea     rax, [rbp+var_20]
0x180011489  mov     [rsp+140h+var_120], rax
0x18001148e  lea     rdx, qword_18003B620
0x180011495  mov     rcx, r9
0x180011498  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001149d  jmp     loc_180011530
0x1800114a2  lea     rdx, [rbp+SRWLock]
0x1800114a6  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800114ab  mov     rax, [rbx+110h]
0x1800114b2  mov     dword ptr [rax], 2
0x1800114b8  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800114bc  test    rcx, rcx
0x1800114bf  jz      short loc_1800114CD
0x1800114c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800114c8  nop     dword ptr [rax+rax+00h]
0x1800114cd  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800114d2  mov     rdi, rax
0x1800114d5  mov     ecx, [rax]
0x1800114d7  cmp     ecx, 5
0x1800114da  jbe     short loc_180011530
0x1800114dc  call    cs:__imp_GetCurrentThreadId
0x1800114e3  nop     dword ptr [rax+rax+00h]
0x1800114e8  mov     dword ptr [rbp+SRWLock], eax
0x1800114eb  mov     r8, [rbx+110h]
0x1800114f2  mov     ecx, [r8+48h]
0x1800114f6  mov     [rbp+arg_8], ecx
0x1800114f9  mov     [rbp+arg_10], 0
0x180011501  add     r8, 8
0x180011505  lea     rax, [rbp+SRWLock]
0x180011509  mov     [rsp+140h+var_110], rax
0x18001150e  lea     rax, [rbp+arg_8]
0x180011512  mov     [rsp+140h+var_118], rax
0x180011517  lea     rax, [rbp+arg_10]
0x18001151b  mov     [rsp+140h+var_120], rax
0x180011520  lea     rdx, byte_18003B95F
0x180011527  mov     rcx, rdi
0x18001152a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001152f  nop
0x180011530  lea     rcx, [rbx+120h]; this
0x180011537  cmp     dword ptr [rcx+18h], 0
0x18001153b  jz      short loc_180011543
0x18001153d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180011542  nop
0x180011543  add     rsp, 130h
0x18001154a  pop     rdi
0x18001154b  pop     rbx
0x18001154c  pop     rbp
0x18001154d  retn
```
