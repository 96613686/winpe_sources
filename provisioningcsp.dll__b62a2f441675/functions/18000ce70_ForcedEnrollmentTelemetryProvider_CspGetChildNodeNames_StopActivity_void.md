# ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StopActivity(void)

- ea: `0x18000ce70`
- end: `0x18000d105`
- name: `?StopActivity@CspGetChildNodeNames@ForcedEnrollmentTelemetryProvider@@MEAAXXZ`
- size: `661`
- prototype: `void __fastcall(ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001150`
- `0x180001404`
- `0x18000bec0`
- `0x18000bf44`
- `0x18000c3fc`
- `0x18000ce70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ceca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d063`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ceca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d063`

## pseudocode

```c
void __fastcall ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StopActivity(
        ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = ForcedEnrollmentTelemetryProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = *((_QWORD *)v4 + 15);
        v20 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = *((_QWORD *)v4 + 12);
        v22 = *((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = *((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = *((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = *((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = *((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)word_180040B32,
          v9 + 8,
          (_DWORD)v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v31,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&SRWLock,
          (__int64)&v20,
          (__int64)&v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = ForcedEnrollmentTelemetryProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v12,
          (unsigned int)&dword_1800410EC,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000ce70  push    rbp
0x18000ce72  push    rbx
0x18000ce73  push    rdi
0x18000ce74  lea     rbp, [rsp-47h]
0x18000ce79  sub     rsp, 100h
0x18000ce80  mov     rdi, [rcx+110h]
0x18000ce87  mov     rbx, rcx
0x18000ce8a  mov     eax, [rdi+48h]
0x18000ce8d  test    eax, eax
0x18000ce8f  jns     loc_18000D044
0x18000ce95  add     rdi, 50h ; 'P'
0x18000ce99  cmp     eax, [rdi+8]
0x18000ce9c  jnz     loc_18000D044
0x18000cea2  test    rdi, rdi
0x18000cea5  jz      loc_18000D044
0x18000ceab  lea     rdx, [rbp+57h+SRWLock]
0x18000ceaf  call    ?LockExclusive@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ceb4  mov     rax, [rbx+110h]
0x18000cebb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000cebf  mov     dword ptr [rax], 2
0x18000cec5  test    rcx, rcx
0x18000cec8  jz      short loc_18000CED6
0x18000ceca  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ced1  nop     dword ptr [rax+rax+00h]
0x18000ced6  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000cedb  mov     r9, rax
0x18000cede  mov     ecx, [rax]
0x18000cee0  cmp     ecx, 5
0x18000cee3  jbe     loc_18000D0F3
0x18000cee9  mov     rax, [rax+18h]
0x18000ceed  mov     rdx, 400000000000h
0x18000cef7  mov     rcx, [r9+10h]
0x18000cefb  test    rdx, rcx
0x18000cefe  jz      loc_18000D0F3
0x18000cf04  mov     rcx, rax
0x18000cf07  and     rcx, rdx
0x18000cf0a  cmp     rcx, rax
0x18000cf0d  jnz     loc_18000D0F3
0x18000cf13  mov     rax, [rdi+78h]
0x18000cf17  lea     rdx, word_180040B32
0x18000cf1e  mov     r8, [rbx+110h]
0x18000cf25  mov     rcx, r9
0x18000cf28  mov     [rbp+57h+var_68], rax
0x18000cf2c  add     r8, 8
0x18000cf30  mov     rax, [rdi+70h]
0x18000cf34  mov     [rbp+57h+var_60], rax
0x18000cf38  mov     eax, [rdi+68h]
0x18000cf3b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000cf3e  mov     rax, [rdi+60h]
0x18000cf42  mov     [rbp+57h+var_58], rax
0x18000cf46  mov     rax, [rdi+58h]
0x18000cf4a  mov     [rbp+57h+var_50], rax
0x18000cf4e  mov     eax, [rdi+50h]
0x18000cf51  mov     [rbp+57h+arg_8], eax
0x18000cf54  mov     rax, [rdi+48h]
0x18000cf58  mov     [rbp+57h+var_48], rax
0x18000cf5c  mov     eax, [rdi+20h]
0x18000cf5f  mov     dword ptr [rbp+57h+arg_10], eax
0x18000cf62  mov     rax, [rdi+18h]
0x18000cf66  mov     [rbp+57h+var_40], rax
0x18000cf6a  mov     eax, [rdi]
0x18000cf6c  mov     [rbp+57h+arg_18], eax
0x18000cf6f  mov     rax, [rdi+80h]
0x18000cf76  mov     [rbp+57h+var_38], rax
0x18000cf7a  mov     eax, [rdi+40h]
0x18000cf7d  mov     [rbp+57h+var_70], eax
0x18000cf80  mov     rax, [rdi+38h]
0x18000cf84  mov     [rbp+57h+var_30], rax
0x18000cf88  mov     eax, [rdi+8]
0x18000cf8b  mov     [rbp+57h+var_6C], eax
0x18000cf8e  lea     rax, [rbp+57h+var_68]
0x18000cf92  mov     [rsp+110h+var_78], rax
0x18000cf9a  lea     rax, [rbp+57h+var_60]
0x18000cf9e  mov     [rsp+110h+var_80], rax
0x18000cfa6  lea     rax, [rbp+57h+SRWLock]
0x18000cfaa  mov     [rsp+110h+var_88], rax
0x18000cfb2  lea     rax, [rbp+57h+var_58]
0x18000cfb6  mov     [rsp+110h+var_90], rax
0x18000cfbe  lea     rax, [rbp+57h+var_50]
0x18000cfc2  mov     [rsp+110h+var_98], rax
0x18000cfc7  lea     rax, [rbp+57h+arg_8]
0x18000cfcb  mov     [rsp+110h+var_A0], rax
0x18000cfd0  lea     rax, [rbp+57h+var_48]
0x18000cfd4  mov     [rsp+110h+var_A8], rax
0x18000cfd9  lea     rax, [rbp+57h+arg_10]
0x18000cfdd  mov     [rsp+110h+var_B0], rax
0x18000cfe2  lea     rax, [rbp+57h+var_40]
0x18000cfe6  mov     [rsp+110h+var_B8], rax
0x18000cfeb  lea     rax, [rbp+57h+arg_18]
0x18000cfef  mov     [rsp+110h+var_C0], rax
0x18000cff4  lea     rax, [rbp+57h+var_38]
0x18000cff8  mov     [rsp+110h+var_C8], rax
0x18000cffd  lea     rax, [rbp+57h+var_70]
0x18000d001  mov     [rsp+110h+var_D0], rax
0x18000d006  lea     rax, [rbp+57h+var_30]
0x18000d00a  mov     [rsp+110h+var_D8], rax
0x18000d00f  lea     rax, [rbp+57h+var_6C]
0x18000d013  mov     [rsp+110h+var_E0], rax
0x18000d018  lea     rax, [rbp+57h+var_28]
0x18000d01c  mov     [rsp+110h+var_E8], rax
0x18000d021  lea     rax, [rbp+57h+var_20]
0x18000d025  mov     [rsp+110h+var_F0], rax
0x18000d02a  mov     [rbp+57h+var_28], 1000000h
0x18000d032  mov     [rbp+57h+var_20], 0
0x18000d03a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000d03f  jmp     loc_18000D0F3
0x18000d044  lea     rdx, [rbp+57h+SRWLock]
0x18000d048  call    ?LockExclusive@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d04d  mov     rax, [rbx+110h]
0x18000d054  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000d058  mov     dword ptr [rax], 2
0x18000d05e  test    rcx, rcx
0x18000d061  jz      short loc_18000D06F
0x18000d063  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d06a  nop     dword ptr [rax+rax+00h]
0x18000d06f  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000d074  mov     rdi, rax
0x18000d077  mov     ecx, [rax]
0x18000d079  cmp     ecx, 5
0x18000d07c  jbe     short loc_18000D0F3
0x18000d07e  mov     rax, [rax+18h]
0x18000d082  mov     rdx, 400000000000h
0x18000d08c  mov     rcx, [rdi+10h]
0x18000d090  test    rdx, rcx
0x18000d093  jz      short loc_18000D0F3
0x18000d095  mov     rcx, rax
0x18000d098  and     rcx, rdx
0x18000d09b  cmp     rcx, rax
0x18000d09e  jnz     short loc_18000D0F3
0x18000d0a0  call    cs:__imp_GetCurrentThreadId
0x18000d0a7  nop     dword ptr [rax+rax+00h]
0x18000d0ac  mov     r8, [rbx+110h]
0x18000d0b3  lea     rdx, dword_1800410EC
0x18000d0ba  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000d0bd  mov     rcx, rdi
0x18000d0c0  mov     eax, [r8+48h]
0x18000d0c4  add     r8, 8
0x18000d0c8  mov     [rbp+57h+arg_8], eax
0x18000d0cb  lea     rax, [rbp+57h+SRWLock]
0x18000d0cf  mov     [rsp+110h+var_E0], rax
0x18000d0d4  lea     rax, [rbp+57h+arg_8]
0x18000d0d8  mov     [rsp+110h+var_E8], rax
0x18000d0dd  lea     rax, [rbp+57h+arg_10]
0x18000d0e1  mov     [rsp+110h+var_F0], rax
0x18000d0e6  mov     [rbp+57h+arg_10], 0
0x18000d0ee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d0f3  mov     rcx, rbx
0x18000d0f6  add     rsp, 100h
0x18000d0fd  pop     rdi
0x18000d0fe  pop     rbx
0x18000d0ff  pop     rbp
0x18000d100  jmp     ?IgnoreCurrentThread@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
