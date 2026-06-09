# ContainerProvider::TerminationNotification::StopActivity(void)

- ea: `0x18002bfc0`
- end: `0x18002c24f`
- name: `?StopActivity@TerminationNotification@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::TerminationNotification *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x18002bfc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c01a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c1c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c01a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c1c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1dc`

## pseudocode

```c
void __fastcall ContainerProvider::TerminationNotification::StopActivity(
        ContainerProvider::TerminationNotification *this)
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
        (unsigned int)byte_18003D321,
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
        (unsigned int)word_18003D0DA,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::TerminationNotification *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002bfc0  push    rbp
0x18002bfc2  push    rbx
0x18002bfc3  push    rdi
0x18002bfc4  lea     rbp, [rsp+10h]
0x18002bfc9  sub     rsp, 130h
0x18002bfd0  mov     rbx, rcx
0x18002bfd3  mov     rdi, [rcx+110h]
0x18002bfda  mov     eax, [rdi+48h]
0x18002bfdd  test    eax, eax
0x18002bfdf  jns     loc_18002C1A2
0x18002bfe5  add     rdi, 50h ; 'P'
0x18002bfe9  cmp     eax, [rdi+8]
0x18002bfec  jnz     loc_18002C1A2
0x18002bff2  test    rdi, rdi
0x18002bff5  jz      loc_18002C1A2
0x18002bffb  lea     rdx, [rbp+SRWLock]
0x18002bfff  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c004  mov     rax, [rbx+110h]
0x18002c00b  mov     dword ptr [rax], 2
0x18002c011  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c015  test    rcx, rcx
0x18002c018  jz      short loc_18002C026
0x18002c01a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c021  nop     dword ptr [rax+rax+00h]
0x18002c026  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18002c02b  mov     r9, rax
0x18002c02e  mov     ecx, [rax]
0x18002c030  cmp     ecx, 5
0x18002c033  jbe     loc_18002C230
0x18002c039  mov     rcx, [rdi+30h]
0x18002c03d  mov     [rbp+var_70], rcx
0x18002c041  mov     ecx, [rdi+44h]
0x18002c044  mov     dword ptr [rbp+SRWLock], ecx
0x18002c047  mov     ecx, [rdi+10h]
0x18002c04a  mov     [rbp+arg_8], ecx
0x18002c04d  mov     rcx, [rdi+78h]
0x18002c051  mov     [rbp+var_68], rcx
0x18002c055  mov     rax, [rdi+70h]
0x18002c059  mov     [rbp+var_60], rax
0x18002c05d  mov     eax, [rdi+68h]
0x18002c060  mov     dword ptr [rbp+arg_10], eax
0x18002c063  mov     rax, [rdi+60h]
0x18002c067  mov     [rbp+var_58], rax
0x18002c06b  mov     rax, [rdi+58h]
0x18002c06f  mov     [rbp+var_50], rax
0x18002c073  mov     eax, [rdi+50h]
0x18002c076  mov     [rbp+arg_18], eax
0x18002c079  mov     rax, [rdi+48h]
0x18002c07d  mov     [rbp+var_48], rax
0x18002c081  mov     eax, [rdi+20h]
0x18002c084  mov     [rbp+var_80], eax
0x18002c087  mov     rax, [rdi+18h]
0x18002c08b  mov     [rbp+var_40], rax
0x18002c08f  mov     eax, [rdi]
0x18002c091  mov     [rbp+var_7C], eax
0x18002c094  mov     rax, [rdi+80h]
0x18002c09b  mov     [rbp+var_38], rax
0x18002c09f  mov     eax, [rdi+40h]
0x18002c0a2  mov     [rbp+var_78], eax
0x18002c0a5  mov     rax, [rdi+38h]
0x18002c0a9  mov     [rbp+var_30], rax
0x18002c0ad  mov     eax, [rdi+8]
0x18002c0b0  mov     [rbp+var_74], eax
0x18002c0b3  mov     [rbp+var_28], 1000000h
0x18002c0bb  mov     [rbp+var_20], 0
0x18002c0c3  mov     r8, [rbx+110h]
0x18002c0ca  add     r8, 8
0x18002c0ce  lea     rax, [rbp+var_70]
0x18002c0d2  mov     [rsp+140h+var_90], rax
0x18002c0da  lea     rax, [rbp+SRWLock]
0x18002c0de  mov     [rsp+140h+var_98], rax
0x18002c0e6  lea     rax, [rbp+arg_8]
0x18002c0ea  mov     [rsp+140h+var_A0], rax
0x18002c0f2  lea     rax, [rbp+var_68]
0x18002c0f6  mov     [rsp+140h+var_A8], rax
0x18002c0fe  lea     rax, [rbp+var_60]
0x18002c102  mov     [rsp+140h+var_B0], rax
0x18002c10a  lea     rax, [rbp+arg_10]
0x18002c10e  mov     [rsp+140h+var_B8], rax
0x18002c116  lea     rax, [rbp+var_58]
0x18002c11a  mov     [rsp+140h+var_C0], rax
0x18002c122  lea     rax, [rbp+var_50]
0x18002c126  mov     [rsp+140h+var_C8], rax
0x18002c12b  lea     rax, [rbp+arg_18]
0x18002c12f  mov     [rsp+140h+var_D0], rax
0x18002c134  lea     rax, [rbp+var_48]
0x18002c138  mov     [rsp+140h+var_D8], rax
0x18002c13d  lea     rax, [rbp+var_80]
0x18002c141  mov     [rsp+140h+var_E0], rax
0x18002c146  lea     rax, [rbp+var_40]
0x18002c14a  mov     [rsp+140h+var_E8], rax
0x18002c14f  lea     rax, [rbp+var_7C]
0x18002c153  mov     [rsp+140h+var_F0], rax
0x18002c158  lea     rax, [rbp+var_38]
0x18002c15c  mov     [rsp+140h+var_F8], rax
0x18002c161  lea     rax, [rbp+var_78]
0x18002c165  mov     [rsp+140h+var_100], rax
0x18002c16a  lea     rax, [rbp+var_30]
0x18002c16e  mov     [rsp+140h+var_108], rax
0x18002c173  lea     rax, [rbp+var_74]
0x18002c177  mov     [rsp+140h+var_110], rax
0x18002c17c  lea     rax, [rbp+var_28]
0x18002c180  mov     [rsp+140h+var_118], rax
0x18002c185  lea     rax, [rbp+var_20]
0x18002c189  mov     [rsp+140h+var_120], rax
0x18002c18e  lea     rdx, byte_18003D321
0x18002c195  mov     rcx, r9
0x18002c198  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002c19d  jmp     loc_18002C230
0x18002c1a2  lea     rdx, [rbp+SRWLock]
0x18002c1a6  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c1ab  mov     rax, [rbx+110h]
0x18002c1b2  mov     dword ptr [rax], 2
0x18002c1b8  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c1bc  test    rcx, rcx
0x18002c1bf  jz      short loc_18002C1CD
0x18002c1c1  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c1c8  nop     dword ptr [rax+rax+00h]
0x18002c1cd  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18002c1d2  mov     rdi, rax
0x18002c1d5  mov     ecx, [rax]
0x18002c1d7  cmp     ecx, 5
0x18002c1da  jbe     short loc_18002C230
0x18002c1dc  call    cs:__imp_GetCurrentThreadId
0x18002c1e3  nop     dword ptr [rax+rax+00h]
0x18002c1e8  mov     dword ptr [rbp+SRWLock], eax
0x18002c1eb  mov     r8, [rbx+110h]
0x18002c1f2  mov     ecx, [r8+48h]
0x18002c1f6  mov     [rbp+arg_8], ecx
0x18002c1f9  mov     [rbp+arg_10], 0
0x18002c201  add     r8, 8
0x18002c205  lea     rax, [rbp+SRWLock]
0x18002c209  mov     [rsp+140h+var_110], rax
0x18002c20e  lea     rax, [rbp+arg_8]
0x18002c212  mov     [rsp+140h+var_118], rax
0x18002c217  lea     rax, [rbp+arg_10]
0x18002c21b  mov     [rsp+140h+var_120], rax
0x18002c220  lea     rdx, word_18003D0DA
0x18002c227  mov     rcx, rdi
0x18002c22a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002c22f  nop
0x18002c230  lea     rcx, [rbx+120h]; this
0x18002c237  cmp     dword ptr [rcx+18h], 0
0x18002c23b  jz      short loc_18002C243
0x18002c23d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002c242  nop
0x18002c243  add     rsp, 130h
0x18002c24a  pop     rdi
0x18002c24b  pop     rbx
0x18002c24c  pop     rbp
0x18002c24d  retn
```
