# ContainerProvider::SetupFilesystemNamespace::StopActivity(void)

- ea: `0x180011ab0`
- end: `0x180011d3f`
- name: `?StopActivity@SetupFilesystemNamespace@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::SetupFilesystemNamespace *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180011ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011b0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011cb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011b0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ccc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011ccc`

## pseudocode

```c
void __fastcall ContainerProvider::SetupFilesystemNamespace::StopActivity(
        ContainerProvider::SetupFilesystemNamespace *this)
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
        (unsigned int)&byte_18003B407,
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
        (unsigned int)&dword_18003C144,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::SetupFilesystemNamespace *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011ab0  push    rbp
0x180011ab2  push    rbx
0x180011ab3  push    rdi
0x180011ab4  lea     rbp, [rsp+10h]
0x180011ab9  sub     rsp, 130h
0x180011ac0  mov     rbx, rcx
0x180011ac3  mov     rdi, [rcx+110h]
0x180011aca  mov     eax, [rdi+48h]
0x180011acd  test    eax, eax
0x180011acf  jns     loc_180011C92
0x180011ad5  add     rdi, 50h ; 'P'
0x180011ad9  cmp     eax, [rdi+8]
0x180011adc  jnz     loc_180011C92
0x180011ae2  test    rdi, rdi
0x180011ae5  jz      loc_180011C92
0x180011aeb  lea     rdx, [rbp+SRWLock]
0x180011aef  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011af4  mov     rax, [rbx+110h]
0x180011afb  mov     dword ptr [rax], 2
0x180011b01  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011b05  test    rcx, rcx
0x180011b08  jz      short loc_180011B16
0x180011b0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180011b11  nop     dword ptr [rax+rax+00h]
0x180011b16  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011b1b  mov     r9, rax
0x180011b1e  mov     ecx, [rax]
0x180011b20  cmp     ecx, 5
0x180011b23  jbe     loc_180011D20
0x180011b29  mov     rcx, [rdi+30h]
0x180011b2d  mov     [rbp+var_70], rcx
0x180011b31  mov     ecx, [rdi+44h]
0x180011b34  mov     dword ptr [rbp+SRWLock], ecx
0x180011b37  mov     ecx, [rdi+10h]
0x180011b3a  mov     [rbp+arg_8], ecx
0x180011b3d  mov     rcx, [rdi+78h]
0x180011b41  mov     [rbp+var_68], rcx
0x180011b45  mov     rax, [rdi+70h]
0x180011b49  mov     [rbp+var_60], rax
0x180011b4d  mov     eax, [rdi+68h]
0x180011b50  mov     dword ptr [rbp+arg_10], eax
0x180011b53  mov     rax, [rdi+60h]
0x180011b57  mov     [rbp+var_58], rax
0x180011b5b  mov     rax, [rdi+58h]
0x180011b5f  mov     [rbp+var_50], rax
0x180011b63  mov     eax, [rdi+50h]
0x180011b66  mov     [rbp+arg_18], eax
0x180011b69  mov     rax, [rdi+48h]
0x180011b6d  mov     [rbp+var_48], rax
0x180011b71  mov     eax, [rdi+20h]
0x180011b74  mov     [rbp+var_80], eax
0x180011b77  mov     rax, [rdi+18h]
0x180011b7b  mov     [rbp+var_40], rax
0x180011b7f  mov     eax, [rdi]
0x180011b81  mov     [rbp+var_7C], eax
0x180011b84  mov     rax, [rdi+80h]
0x180011b8b  mov     [rbp+var_38], rax
0x180011b8f  mov     eax, [rdi+40h]
0x180011b92  mov     [rbp+var_78], eax
0x180011b95  mov     rax, [rdi+38h]
0x180011b99  mov     [rbp+var_30], rax
0x180011b9d  mov     eax, [rdi+8]
0x180011ba0  mov     [rbp+var_74], eax
0x180011ba3  mov     [rbp+var_28], 1000000h
0x180011bab  mov     [rbp+var_20], 0
0x180011bb3  mov     r8, [rbx+110h]
0x180011bba  add     r8, 8
0x180011bbe  lea     rax, [rbp+var_70]
0x180011bc2  mov     [rsp+140h+var_90], rax
0x180011bca  lea     rax, [rbp+SRWLock]
0x180011bce  mov     [rsp+140h+var_98], rax
0x180011bd6  lea     rax, [rbp+arg_8]
0x180011bda  mov     [rsp+140h+var_A0], rax
0x180011be2  lea     rax, [rbp+var_68]
0x180011be6  mov     [rsp+140h+var_A8], rax
0x180011bee  lea     rax, [rbp+var_60]
0x180011bf2  mov     [rsp+140h+var_B0], rax
0x180011bfa  lea     rax, [rbp+arg_10]
0x180011bfe  mov     [rsp+140h+var_B8], rax
0x180011c06  lea     rax, [rbp+var_58]
0x180011c0a  mov     [rsp+140h+var_C0], rax
0x180011c12  lea     rax, [rbp+var_50]
0x180011c16  mov     [rsp+140h+var_C8], rax
0x180011c1b  lea     rax, [rbp+arg_18]
0x180011c1f  mov     [rsp+140h+var_D0], rax
0x180011c24  lea     rax, [rbp+var_48]
0x180011c28  mov     [rsp+140h+var_D8], rax
0x180011c2d  lea     rax, [rbp+var_80]
0x180011c31  mov     [rsp+140h+var_E0], rax
0x180011c36  lea     rax, [rbp+var_40]
0x180011c3a  mov     [rsp+140h+var_E8], rax
0x180011c3f  lea     rax, [rbp+var_7C]
0x180011c43  mov     [rsp+140h+var_F0], rax
0x180011c48  lea     rax, [rbp+var_38]
0x180011c4c  mov     [rsp+140h+var_F8], rax
0x180011c51  lea     rax, [rbp+var_78]
0x180011c55  mov     [rsp+140h+var_100], rax
0x180011c5a  lea     rax, [rbp+var_30]
0x180011c5e  mov     [rsp+140h+var_108], rax
0x180011c63  lea     rax, [rbp+var_74]
0x180011c67  mov     [rsp+140h+var_110], rax
0x180011c6c  lea     rax, [rbp+var_28]
0x180011c70  mov     [rsp+140h+var_118], rax
0x180011c75  lea     rax, [rbp+var_20]
0x180011c79  mov     [rsp+140h+var_120], rax
0x180011c7e  lea     rdx, byte_18003B407
0x180011c85  mov     rcx, r9
0x180011c88  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011c8d  jmp     loc_180011D20
0x180011c92  lea     rdx, [rbp+SRWLock]
0x180011c96  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011c9b  mov     rax, [rbx+110h]
0x180011ca2  mov     dword ptr [rax], 2
0x180011ca8  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011cac  test    rcx, rcx
0x180011caf  jz      short loc_180011CBD
0x180011cb1  call    cs:__imp_ReleaseSRWLockExclusive
0x180011cb8  nop     dword ptr [rax+rax+00h]
0x180011cbd  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011cc2  mov     rdi, rax
0x180011cc5  mov     ecx, [rax]
0x180011cc7  cmp     ecx, 5
0x180011cca  jbe     short loc_180011D20
0x180011ccc  call    cs:__imp_GetCurrentThreadId
0x180011cd3  nop     dword ptr [rax+rax+00h]
0x180011cd8  mov     dword ptr [rbp+SRWLock], eax
0x180011cdb  mov     r8, [rbx+110h]
0x180011ce2  mov     ecx, [r8+48h]
0x180011ce6  mov     [rbp+arg_8], ecx
0x180011ce9  mov     [rbp+arg_10], 0
0x180011cf1  add     r8, 8
0x180011cf5  lea     rax, [rbp+SRWLock]
0x180011cf9  mov     [rsp+140h+var_110], rax
0x180011cfe  lea     rax, [rbp+arg_8]
0x180011d02  mov     [rsp+140h+var_118], rax
0x180011d07  lea     rax, [rbp+arg_10]
0x180011d0b  mov     [rsp+140h+var_120], rax
0x180011d10  lea     rdx, dword_18003C144
0x180011d17  mov     rcx, rdi
0x180011d1a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011d1f  nop
0x180011d20  lea     rcx, [rbx+120h]; this
0x180011d27  cmp     dword ptr [rcx+18h], 0
0x180011d2b  jz      short loc_180011D33
0x180011d2d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180011d32  nop
0x180011d33  add     rsp, 130h
0x180011d3a  pop     rdi
0x180011d3b  pop     rbx
0x180011d3c  pop     rbp
0x180011d3d  retn
```
