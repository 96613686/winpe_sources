# ContainerProvider::SetRegistryFlushState::StopActivity(void)

- ea: `0x180011810`
- end: `0x180011a9f`
- name: `?StopActivity@SetRegistryFlushState@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::SetRegistryFlushState *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180011810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001186a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001186a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a2c`

## pseudocode

```c
void __fastcall ContainerProvider::SetRegistryFlushState::StopActivity(ContainerProvider::SetRegistryFlushState *this)
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
        (unsigned int)&unk_18003AE18,
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
        (unsigned int)&dword_18003B034,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::SetRegistryFlushState *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011810  push    rbp
0x180011812  push    rbx
0x180011813  push    rdi
0x180011814  lea     rbp, [rsp+10h]
0x180011819  sub     rsp, 130h
0x180011820  mov     rbx, rcx
0x180011823  mov     rdi, [rcx+110h]
0x18001182a  mov     eax, [rdi+48h]
0x18001182d  test    eax, eax
0x18001182f  jns     loc_1800119F2
0x180011835  add     rdi, 50h ; 'P'
0x180011839  cmp     eax, [rdi+8]
0x18001183c  jnz     loc_1800119F2
0x180011842  test    rdi, rdi
0x180011845  jz      loc_1800119F2
0x18001184b  lea     rdx, [rbp+SRWLock]
0x18001184f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011854  mov     rax, [rbx+110h]
0x18001185b  mov     dword ptr [rax], 2
0x180011861  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011865  test    rcx, rcx
0x180011868  jz      short loc_180011876
0x18001186a  call    cs:__imp_ReleaseSRWLockExclusive
0x180011871  nop     dword ptr [rax+rax+00h]
0x180011876  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18001187b  mov     r9, rax
0x18001187e  mov     ecx, [rax]
0x180011880  cmp     ecx, 5
0x180011883  jbe     loc_180011A80
0x180011889  mov     rcx, [rdi+30h]
0x18001188d  mov     [rbp+var_70], rcx
0x180011891  mov     ecx, [rdi+44h]
0x180011894  mov     dword ptr [rbp+SRWLock], ecx
0x180011897  mov     ecx, [rdi+10h]
0x18001189a  mov     [rbp+arg_8], ecx
0x18001189d  mov     rcx, [rdi+78h]
0x1800118a1  mov     [rbp+var_68], rcx
0x1800118a5  mov     rax, [rdi+70h]
0x1800118a9  mov     [rbp+var_60], rax
0x1800118ad  mov     eax, [rdi+68h]
0x1800118b0  mov     dword ptr [rbp+arg_10], eax
0x1800118b3  mov     rax, [rdi+60h]
0x1800118b7  mov     [rbp+var_58], rax
0x1800118bb  mov     rax, [rdi+58h]
0x1800118bf  mov     [rbp+var_50], rax
0x1800118c3  mov     eax, [rdi+50h]
0x1800118c6  mov     [rbp+arg_18], eax
0x1800118c9  mov     rax, [rdi+48h]
0x1800118cd  mov     [rbp+var_48], rax
0x1800118d1  mov     eax, [rdi+20h]
0x1800118d4  mov     [rbp+var_80], eax
0x1800118d7  mov     rax, [rdi+18h]
0x1800118db  mov     [rbp+var_40], rax
0x1800118df  mov     eax, [rdi]
0x1800118e1  mov     [rbp+var_7C], eax
0x1800118e4  mov     rax, [rdi+80h]
0x1800118eb  mov     [rbp+var_38], rax
0x1800118ef  mov     eax, [rdi+40h]
0x1800118f2  mov     [rbp+var_78], eax
0x1800118f5  mov     rax, [rdi+38h]
0x1800118f9  mov     [rbp+var_30], rax
0x1800118fd  mov     eax, [rdi+8]
0x180011900  mov     [rbp+var_74], eax
0x180011903  mov     [rbp+var_28], 1000000h
0x18001190b  mov     [rbp+var_20], 0
0x180011913  mov     r8, [rbx+110h]
0x18001191a  add     r8, 8
0x18001191e  lea     rax, [rbp+var_70]
0x180011922  mov     [rsp+140h+var_90], rax
0x18001192a  lea     rax, [rbp+SRWLock]
0x18001192e  mov     [rsp+140h+var_98], rax
0x180011936  lea     rax, [rbp+arg_8]
0x18001193a  mov     [rsp+140h+var_A0], rax
0x180011942  lea     rax, [rbp+var_68]
0x180011946  mov     [rsp+140h+var_A8], rax
0x18001194e  lea     rax, [rbp+var_60]
0x180011952  mov     [rsp+140h+var_B0], rax
0x18001195a  lea     rax, [rbp+arg_10]
0x18001195e  mov     [rsp+140h+var_B8], rax
0x180011966  lea     rax, [rbp+var_58]
0x18001196a  mov     [rsp+140h+var_C0], rax
0x180011972  lea     rax, [rbp+var_50]
0x180011976  mov     [rsp+140h+var_C8], rax
0x18001197b  lea     rax, [rbp+arg_18]
0x18001197f  mov     [rsp+140h+var_D0], rax
0x180011984  lea     rax, [rbp+var_48]
0x180011988  mov     [rsp+140h+var_D8], rax
0x18001198d  lea     rax, [rbp+var_80]
0x180011991  mov     [rsp+140h+var_E0], rax
0x180011996  lea     rax, [rbp+var_40]
0x18001199a  mov     [rsp+140h+var_E8], rax
0x18001199f  lea     rax, [rbp+var_7C]
0x1800119a3  mov     [rsp+140h+var_F0], rax
0x1800119a8  lea     rax, [rbp+var_38]
0x1800119ac  mov     [rsp+140h+var_F8], rax
0x1800119b1  lea     rax, [rbp+var_78]
0x1800119b5  mov     [rsp+140h+var_100], rax
0x1800119ba  lea     rax, [rbp+var_30]
0x1800119be  mov     [rsp+140h+var_108], rax
0x1800119c3  lea     rax, [rbp+var_74]
0x1800119c7  mov     [rsp+140h+var_110], rax
0x1800119cc  lea     rax, [rbp+var_28]
0x1800119d0  mov     [rsp+140h+var_118], rax
0x1800119d5  lea     rax, [rbp+var_20]
0x1800119d9  mov     [rsp+140h+var_120], rax
0x1800119de  lea     rdx, unk_18003AE18
0x1800119e5  mov     rcx, r9
0x1800119e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800119ed  jmp     loc_180011A80
0x1800119f2  lea     rdx, [rbp+SRWLock]
0x1800119f6  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800119fb  mov     rax, [rbx+110h]
0x180011a02  mov     dword ptr [rax], 2
0x180011a08  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011a0c  test    rcx, rcx
0x180011a0f  jz      short loc_180011A1D
0x180011a11  call    cs:__imp_ReleaseSRWLockExclusive
0x180011a18  nop     dword ptr [rax+rax+00h]
0x180011a1d  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011a22  mov     rdi, rax
0x180011a25  mov     ecx, [rax]
0x180011a27  cmp     ecx, 5
0x180011a2a  jbe     short loc_180011A80
0x180011a2c  call    cs:__imp_GetCurrentThreadId
0x180011a33  nop     dword ptr [rax+rax+00h]
0x180011a38  mov     dword ptr [rbp+SRWLock], eax
0x180011a3b  mov     r8, [rbx+110h]
0x180011a42  mov     ecx, [r8+48h]
0x180011a46  mov     [rbp+arg_8], ecx
0x180011a49  mov     [rbp+arg_10], 0
0x180011a51  add     r8, 8
0x180011a55  lea     rax, [rbp+SRWLock]
0x180011a59  mov     [rsp+140h+var_110], rax
0x180011a5e  lea     rax, [rbp+arg_8]
0x180011a62  mov     [rsp+140h+var_118], rax
0x180011a67  lea     rax, [rbp+arg_10]
0x180011a6b  mov     [rsp+140h+var_120], rax
0x180011a70  lea     rdx, dword_18003B034
0x180011a77  mov     rcx, rdi
0x180011a7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011a7f  nop
0x180011a80  lea     rcx, [rbx+120h]; this
0x180011a87  cmp     dword ptr [rcx+18h], 0
0x180011a8b  jz      short loc_180011A93
0x180011a8d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180011a92  nop
0x180011a93  add     rsp, 130h
0x180011a9a  pop     rdi
0x180011a9b  pop     rbx
0x180011a9c  pop     rbp
0x180011a9d  retn
```
