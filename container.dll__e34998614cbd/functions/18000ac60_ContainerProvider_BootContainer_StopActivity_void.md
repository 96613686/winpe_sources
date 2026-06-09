# ContainerProvider::BootContainer::StopActivity(void)

- ea: `0x18000ac60`
- end: `0x18000af03`
- name: `?StopActivity@BootContainer@ContainerProvider@@MEAAXXZ`
- size: `675`
- prototype: `void __fastcall(ContainerProvider::BootContainer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001098`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000ac60`
- `0x18000af0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000acba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ContainerProvider::BootContainer::StopActivity(ContainerProvider::BootContainer *this)
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
          (unsigned int)byte_18003AB89,
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
          (unsigned int)word_18003A9DA,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::BootContainer *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000ac60  push    rbp
0x18000ac62  push    rbx
0x18000ac63  push    rdi
0x18000ac64  lea     rbp, [rsp-47h]
0x18000ac69  sub     rsp, 100h
0x18000ac70  mov     rbx, rcx
0x18000ac73  mov     rdi, [rcx+110h]
0x18000ac7a  mov     eax, [rdi+48h]
0x18000ac7d  test    eax, eax
0x18000ac7f  jns     loc_18000AE34
0x18000ac85  add     rdi, 50h ; 'P'
0x18000ac89  cmp     eax, [rdi+8]
0x18000ac8c  jnz     loc_18000AE34
0x18000ac92  test    rdi, rdi
0x18000ac95  jz      loc_18000AE34
0x18000ac9b  lea     rdx, [rbp+57h+SRWLock]
0x18000ac9f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000aca4  mov     rax, [rbx+110h]
0x18000acab  mov     dword ptr [rax], 2
0x18000acb1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000acb5  test    rcx, rcx
0x18000acb8  jz      short loc_18000ACC6
0x18000acba  call    cs:__imp_ReleaseSRWLockExclusive
0x18000acc1  nop     dword ptr [rax+rax+00h]
0x18000acc6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000accb  mov     r9, rax
0x18000acce  mov     ecx, [rax]
0x18000acd0  cmp     ecx, 5
0x18000acd3  jbe     loc_18000AEE4
0x18000acd9  mov     rax, [rax+18h]
0x18000acdd  mov     rcx, [r9+10h]
0x18000ace1  mov     rdx, 400000000000h
0x18000aceb  test    rdx, rcx
0x18000acee  jz      loc_18000AEE4
0x18000acf4  mov     rcx, rax
0x18000acf7  and     rcx, rdx
0x18000acfa  cmp     rcx, rax
0x18000acfd  jnz     loc_18000AEE4
0x18000ad03  mov     rax, [rdi+78h]
0x18000ad07  mov     [rbp+57h+var_68], rax
0x18000ad0b  mov     rax, [rdi+70h]
0x18000ad0f  mov     [rbp+57h+var_60], rax
0x18000ad13  mov     eax, [rdi+68h]
0x18000ad16  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000ad19  mov     rax, [rdi+60h]
0x18000ad1d  mov     [rbp+57h+var_58], rax
0x18000ad21  mov     rax, [rdi+58h]
0x18000ad25  mov     [rbp+57h+var_50], rax
0x18000ad29  mov     eax, [rdi+50h]
0x18000ad2c  mov     [rbp+57h+arg_8], eax
0x18000ad2f  mov     rax, [rdi+48h]
0x18000ad33  mov     [rbp+57h+var_48], rax
0x18000ad37  mov     eax, [rdi+20h]
0x18000ad3a  mov     dword ptr [rbp+57h+arg_10], eax
0x18000ad3d  mov     rax, [rdi+18h]
0x18000ad41  mov     [rbp+57h+var_40], rax
0x18000ad45  mov     eax, [rdi]
0x18000ad47  mov     [rbp+57h+arg_18], eax
0x18000ad4a  mov     rax, [rdi+80h]
0x18000ad51  mov     [rbp+57h+var_38], rax
0x18000ad55  mov     eax, [rdi+40h]
0x18000ad58  mov     [rbp+57h+var_70], eax
0x18000ad5b  mov     rax, [rdi+38h]
0x18000ad5f  mov     [rbp+57h+var_30], rax
0x18000ad63  mov     eax, [rdi+8]
0x18000ad66  mov     [rbp+57h+var_6C], eax
0x18000ad69  mov     [rbp+57h+var_28], 1000000h
0x18000ad71  mov     [rbp+57h+var_20], 0
0x18000ad79  mov     r8, [rbx+110h]
0x18000ad80  add     r8, 8
0x18000ad84  lea     rax, [rbp+57h+var_68]
0x18000ad88  mov     [rsp+110h+var_78], rax
0x18000ad90  lea     rax, [rbp+57h+var_60]
0x18000ad94  mov     [rsp+110h+var_80], rax
0x18000ad9c  lea     rax, [rbp+57h+SRWLock]
0x18000ada0  mov     [rsp+110h+var_88], rax
0x18000ada8  lea     rax, [rbp+57h+var_58]
0x18000adac  mov     [rsp+110h+var_90], rax
0x18000adb4  lea     rax, [rbp+57h+var_50]
0x18000adb8  mov     [rsp+110h+var_98], rax
0x18000adbd  lea     rax, [rbp+57h+arg_8]
0x18000adc1  mov     [rsp+110h+var_A0], rax
0x18000adc6  lea     rax, [rbp+57h+var_48]
0x18000adca  mov     [rsp+110h+var_A8], rax
0x18000adcf  lea     rax, [rbp+57h+arg_10]
0x18000add3  mov     [rsp+110h+var_B0], rax
0x18000add8  lea     rax, [rbp+57h+var_40]
0x18000addc  mov     [rsp+110h+var_B8], rax
0x18000ade1  lea     rax, [rbp+57h+arg_18]
0x18000ade5  mov     [rsp+110h+var_C0], rax
0x18000adea  lea     rax, [rbp+57h+var_38]
0x18000adee  mov     [rsp+110h+var_C8], rax
0x18000adf3  lea     rax, [rbp+57h+var_70]
0x18000adf7  mov     [rsp+110h+var_D0], rax
0x18000adfc  lea     rax, [rbp+57h+var_30]
0x18000ae00  mov     [rsp+110h+var_D8], rax
0x18000ae05  lea     rax, [rbp+57h+var_6C]
0x18000ae09  mov     [rsp+110h+var_E0], rax
0x18000ae0e  lea     rax, [rbp+57h+var_28]
0x18000ae12  mov     [rsp+110h+var_E8], rax
0x18000ae17  lea     rax, [rbp+57h+var_20]
0x18000ae1b  mov     [rsp+110h+var_F0], rax
0x18000ae20  lea     rdx, byte_18003AB89
0x18000ae27  mov     rcx, r9
0x18000ae2a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000ae2f  jmp     loc_18000AEE4
0x18000ae34  lea     rdx, [rbp+57h+SRWLock]
0x18000ae38  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ae3d  mov     rax, [rbx+110h]
0x18000ae44  mov     dword ptr [rax], 2
0x18000ae4a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000ae4e  test    rcx, rcx
0x18000ae51  jz      short loc_18000AE5F
0x18000ae53  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae5a  nop     dword ptr [rax+rax+00h]
0x18000ae5f  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x18000ae64  mov     rdi, rax
0x18000ae67  mov     ecx, [rax]
0x18000ae69  cmp     ecx, 5
0x18000ae6c  jbe     short loc_18000AEE4
0x18000ae6e  mov     rax, [rax+18h]
0x18000ae72  mov     rcx, [rdi+10h]
0x18000ae76  mov     rdx, 400000000000h
0x18000ae80  test    rdx, rcx
0x18000ae83  jz      short loc_18000AEE4
0x18000ae85  mov     rcx, rax
0x18000ae88  and     rcx, rdx
0x18000ae8b  cmp     rcx, rax
0x18000ae8e  jnz     short loc_18000AEE4
0x18000ae90  call    cs:__imp_GetCurrentThreadId
0x18000ae97  nop     dword ptr [rax+rax+00h]
0x18000ae9c  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000ae9f  mov     r8, [rbx+110h]
0x18000aea6  mov     eax, [r8+48h]
0x18000aeaa  mov     [rbp+57h+arg_8], eax
0x18000aead  mov     [rbp+57h+arg_10], 0
0x18000aeb5  add     r8, 8
0x18000aeb9  lea     rax, [rbp+57h+SRWLock]
0x18000aebd  mov     [rsp+110h+var_E0], rax
0x18000aec2  lea     rax, [rbp+57h+arg_8]
0x18000aec6  mov     [rsp+110h+var_E8], rax
0x18000aecb  lea     rax, [rbp+57h+arg_10]
0x18000aecf  mov     [rsp+110h+var_F0], rax
0x18000aed4  lea     rdx, word_18003A9DA
0x18000aedb  mov     rcx, rdi
0x18000aede  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000aee3  nop
0x18000aee4  lea     rcx, [rbx+120h]; this
0x18000aeeb  cmp     dword ptr [rcx+18h], 0
0x18000aeef  jz      short loc_18000AEF7
0x18000aef1  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000aef6  nop
0x18000aef7  add     rsp, 100h
0x18000aefe  pop     rdi
0x18000aeff  pop     rbx
0x18000af00  pop     rbp
0x18000af01  retn
```
