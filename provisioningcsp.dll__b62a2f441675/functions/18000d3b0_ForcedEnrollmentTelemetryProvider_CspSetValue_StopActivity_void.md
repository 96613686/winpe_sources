# ForcedEnrollmentTelemetryProvider::CspSetValue::StopActivity(void)

- ea: `0x18000d3b0`
- end: `0x18000d645`
- name: `?StopActivity@CspSetValue@ForcedEnrollmentTelemetryProvider@@MEAAXXZ`
- size: `661`
- prototype: `void __fastcall(ForcedEnrollmentTelemetryProvider::CspSetValue *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001150`
- `0x180001404`
- `0x18000bec0`
- `0x18000bf44`
- `0x18000c3fc`
- `0x18000d3b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d5e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d40a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d5a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d40a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d5a3`

## pseudocode

```c
void __fastcall ForcedEnrollmentTelemetryProvider::CspSetValue::StopActivity(
        ForcedEnrollmentTelemetryProvider::CspSetValue *this)
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
          (unsigned int)byte_180040711,
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
          (unsigned int)&word_180040AE6,
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
0x18000d3b0  push    rbp
0x18000d3b2  push    rbx
0x18000d3b3  push    rdi
0x18000d3b4  lea     rbp, [rsp-47h]
0x18000d3b9  sub     rsp, 100h
0x18000d3c0  mov     rdi, [rcx+110h]
0x18000d3c7  mov     rbx, rcx
0x18000d3ca  mov     eax, [rdi+48h]
0x18000d3cd  test    eax, eax
0x18000d3cf  jns     loc_18000D584
0x18000d3d5  add     rdi, 50h ; 'P'
0x18000d3d9  cmp     eax, [rdi+8]
0x18000d3dc  jnz     loc_18000D584
0x18000d3e2  test    rdi, rdi
0x18000d3e5  jz      loc_18000D584
0x18000d3eb  lea     rdx, [rbp+57h+SRWLock]
0x18000d3ef  call    ?LockExclusive@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d3f4  mov     rax, [rbx+110h]
0x18000d3fb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000d3ff  mov     dword ptr [rax], 2
0x18000d405  test    rcx, rcx
0x18000d408  jz      short loc_18000D416
0x18000d40a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d411  nop     dword ptr [rax+rax+00h]
0x18000d416  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000d41b  mov     r9, rax
0x18000d41e  mov     ecx, [rax]
0x18000d420  cmp     ecx, 5
0x18000d423  jbe     loc_18000D633
0x18000d429  mov     rax, [rax+18h]
0x18000d42d  mov     rdx, 400000000000h
0x18000d437  mov     rcx, [r9+10h]
0x18000d43b  test    rdx, rcx
0x18000d43e  jz      loc_18000D633
0x18000d444  mov     rcx, rax
0x18000d447  and     rcx, rdx
0x18000d44a  cmp     rcx, rax
0x18000d44d  jnz     loc_18000D633
0x18000d453  mov     rax, [rdi+78h]
0x18000d457  lea     rdx, byte_180040711
0x18000d45e  mov     r8, [rbx+110h]
0x18000d465  mov     rcx, r9
0x18000d468  mov     [rbp+57h+var_68], rax
0x18000d46c  add     r8, 8
0x18000d470  mov     rax, [rdi+70h]
0x18000d474  mov     [rbp+57h+var_60], rax
0x18000d478  mov     eax, [rdi+68h]
0x18000d47b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000d47e  mov     rax, [rdi+60h]
0x18000d482  mov     [rbp+57h+var_58], rax
0x18000d486  mov     rax, [rdi+58h]
0x18000d48a  mov     [rbp+57h+var_50], rax
0x18000d48e  mov     eax, [rdi+50h]
0x18000d491  mov     [rbp+57h+arg_8], eax
0x18000d494  mov     rax, [rdi+48h]
0x18000d498  mov     [rbp+57h+var_48], rax
0x18000d49c  mov     eax, [rdi+20h]
0x18000d49f  mov     dword ptr [rbp+57h+arg_10], eax
0x18000d4a2  mov     rax, [rdi+18h]
0x18000d4a6  mov     [rbp+57h+var_40], rax
0x18000d4aa  mov     eax, [rdi]
0x18000d4ac  mov     [rbp+57h+arg_18], eax
0x18000d4af  mov     rax, [rdi+80h]
0x18000d4b6  mov     [rbp+57h+var_38], rax
0x18000d4ba  mov     eax, [rdi+40h]
0x18000d4bd  mov     [rbp+57h+var_70], eax
0x18000d4c0  mov     rax, [rdi+38h]
0x18000d4c4  mov     [rbp+57h+var_30], rax
0x18000d4c8  mov     eax, [rdi+8]
0x18000d4cb  mov     [rbp+57h+var_6C], eax
0x18000d4ce  lea     rax, [rbp+57h+var_68]
0x18000d4d2  mov     [rsp+110h+var_78], rax
0x18000d4da  lea     rax, [rbp+57h+var_60]
0x18000d4de  mov     [rsp+110h+var_80], rax
0x18000d4e6  lea     rax, [rbp+57h+SRWLock]
0x18000d4ea  mov     [rsp+110h+var_88], rax
0x18000d4f2  lea     rax, [rbp+57h+var_58]
0x18000d4f6  mov     [rsp+110h+var_90], rax
0x18000d4fe  lea     rax, [rbp+57h+var_50]
0x18000d502  mov     [rsp+110h+var_98], rax
0x18000d507  lea     rax, [rbp+57h+arg_8]
0x18000d50b  mov     [rsp+110h+var_A0], rax
0x18000d510  lea     rax, [rbp+57h+var_48]
0x18000d514  mov     [rsp+110h+var_A8], rax
0x18000d519  lea     rax, [rbp+57h+arg_10]
0x18000d51d  mov     [rsp+110h+var_B0], rax
0x18000d522  lea     rax, [rbp+57h+var_40]
0x18000d526  mov     [rsp+110h+var_B8], rax
0x18000d52b  lea     rax, [rbp+57h+arg_18]
0x18000d52f  mov     [rsp+110h+var_C0], rax
0x18000d534  lea     rax, [rbp+57h+var_38]
0x18000d538  mov     [rsp+110h+var_C8], rax
0x18000d53d  lea     rax, [rbp+57h+var_70]
0x18000d541  mov     [rsp+110h+var_D0], rax
0x18000d546  lea     rax, [rbp+57h+var_30]
0x18000d54a  mov     [rsp+110h+var_D8], rax
0x18000d54f  lea     rax, [rbp+57h+var_6C]
0x18000d553  mov     [rsp+110h+var_E0], rax
0x18000d558  lea     rax, [rbp+57h+var_28]
0x18000d55c  mov     [rsp+110h+var_E8], rax
0x18000d561  lea     rax, [rbp+57h+var_20]
0x18000d565  mov     [rsp+110h+var_F0], rax
0x18000d56a  mov     [rbp+57h+var_28], 1000000h
0x18000d572  mov     [rbp+57h+var_20], 0
0x18000d57a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000d57f  jmp     loc_18000D633
0x18000d584  lea     rdx, [rbp+57h+SRWLock]
0x18000d588  call    ?LockExclusive@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d58d  mov     rax, [rbx+110h]
0x18000d594  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000d598  mov     dword ptr [rax], 2
0x18000d59e  test    rcx, rcx
0x18000d5a1  jz      short loc_18000D5AF
0x18000d5a3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d5aa  nop     dword ptr [rax+rax+00h]
0x18000d5af  call    ?Provider@ForcedEnrollmentTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; ForcedEnrollmentTelemetryProvider::Provider(void)
0x18000d5b4  mov     rdi, rax
0x18000d5b7  mov     ecx, [rax]
0x18000d5b9  cmp     ecx, 5
0x18000d5bc  jbe     short loc_18000D633
0x18000d5be  mov     rax, [rax+18h]
0x18000d5c2  mov     rdx, 400000000000h
0x18000d5cc  mov     rcx, [rdi+10h]
0x18000d5d0  test    rdx, rcx
0x18000d5d3  jz      short loc_18000D633
0x18000d5d5  mov     rcx, rax
0x18000d5d8  and     rcx, rdx
0x18000d5db  cmp     rcx, rax
0x18000d5de  jnz     short loc_18000D633
0x18000d5e0  call    cs:__imp_GetCurrentThreadId
0x18000d5e7  nop     dword ptr [rax+rax+00h]
0x18000d5ec  mov     r8, [rbx+110h]
0x18000d5f3  lea     rdx, word_180040AE6
0x18000d5fa  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000d5fd  mov     rcx, rdi
0x18000d600  mov     eax, [r8+48h]
0x18000d604  add     r8, 8
0x18000d608  mov     [rbp+57h+arg_8], eax
0x18000d60b  lea     rax, [rbp+57h+SRWLock]
0x18000d60f  mov     [rsp+110h+var_E0], rax
0x18000d614  lea     rax, [rbp+57h+arg_8]
0x18000d618  mov     [rsp+110h+var_E8], rax
0x18000d61d  lea     rax, [rbp+57h+arg_10]
0x18000d621  mov     [rsp+110h+var_F0], rax
0x18000d626  mov     [rbp+57h+arg_10], 0
0x18000d62e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d633  mov     rcx, rbx
0x18000d636  add     rsp, 100h
0x18000d63d  pop     rdi
0x18000d63e  pop     rbx
0x18000d63f  pop     rbp
0x18000d640  jmp     ?IgnoreCurrentThread@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
