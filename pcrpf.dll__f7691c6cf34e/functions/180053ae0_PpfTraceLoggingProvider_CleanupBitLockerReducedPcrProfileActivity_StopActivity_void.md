# PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StopActivity(void)

- ea: `0x180053ae0`
- end: `0x180053d73`
- name: `?StopActivity@CleanupBitLockerReducedPcrProfileActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180053ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053cd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053b3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053cd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StopActivity(
        PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v19; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v20; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v21; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v22; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v24; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = PpfTraceLoggingProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = (const wchar_t *)*((_QWORD *)v4 + 15);
        v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = (const wchar_t *)*((_QWORD *)v4 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = (const wchar_t *)*((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&unk_180069ED0,
          v9 + 8,
          v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v32,
          &v24,
          (__int64)&v31,
          &v23,
          (__int64)&v30,
          &v22,
          &v21,
          (__int64)&SRWLock,
          &v20,
          &v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = PpfTraceLoggingProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (__int64)byte_18006A011,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180053ae0  push    rbp
0x180053ae2  push    rbx
0x180053ae3  push    rdi
0x180053ae4  lea     rbp, [rsp-47h]
0x180053ae9  sub     rsp, 100h
0x180053af0  mov     rdi, [rcx+110h]
0x180053af7  mov     rbx, rcx
0x180053afa  mov     eax, [rdi+48h]
0x180053afd  test    eax, eax
0x180053aff  jns     loc_180053CB1
0x180053b05  add     rdi, 50h ; 'P'
0x180053b09  cmp     eax, [rdi+8]
0x180053b0c  jnz     loc_180053CB1
0x180053b12  test    rdi, rdi
0x180053b15  jz      loc_180053CB1
0x180053b1b  lea     rdx, [rbp+57h+SRWLock]
0x180053b1f  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180053b24  mov     rax, [rbx+110h]
0x180053b2b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180053b2f  mov     dword ptr [rax], 2
0x180053b35  test    rcx, rcx
0x180053b38  jz      short loc_180053B46
0x180053b3a  call    cs:__imp_ReleaseSRWLockExclusive
0x180053b41  nop     dword ptr [rax+rax+00h]
0x180053b46  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180053b4b  mov     r9, rax
0x180053b4e  mov     ecx, [rax]
0x180053b50  cmp     ecx, 5
0x180053b53  jbe     loc_180053D61
0x180053b59  mov     rax, [rax+18h]
0x180053b5d  mov     rdx, 400000000000h
0x180053b67  mov     rcx, [r9+10h]
0x180053b6b  test    rdx, rcx
0x180053b6e  jz      loc_180053D61
0x180053b74  mov     rcx, rax
0x180053b77  and     rcx, rdx
0x180053b7a  cmp     rcx, rax
0x180053b7d  jnz     loc_180053D61
0x180053b83  mov     rax, [rdi+78h]
0x180053b87  lea     rdx, unk_180069ED0
0x180053b8e  mov     r8, [rbx+110h]
0x180053b95  mov     rcx, r9
0x180053b98  mov     [rbp+57h+var_68], rax
0x180053b9c  add     r8, 8
0x180053ba0  mov     rax, [rdi+70h]
0x180053ba4  mov     [rbp+57h+var_60], rax
0x180053ba8  mov     eax, [rdi+68h]
0x180053bab  mov     dword ptr [rbp+57h+SRWLock], eax
0x180053bae  mov     rax, [rdi+60h]
0x180053bb2  mov     [rbp+57h+var_58], rax
0x180053bb6  mov     rax, [rdi+58h]
0x180053bba  mov     [rbp+57h+var_50], rax
0x180053bbe  mov     eax, [rdi+50h]
0x180053bc1  mov     [rbp+57h+arg_8], eax
0x180053bc4  mov     rax, [rdi+48h]
0x180053bc8  mov     [rbp+57h+var_48], rax
0x180053bcc  mov     eax, [rdi+20h]
0x180053bcf  mov     dword ptr [rbp+57h+arg_10], eax
0x180053bd2  mov     rax, [rdi+18h]
0x180053bd6  mov     [rbp+57h+var_40], rax
0x180053bda  mov     eax, [rdi]
0x180053bdc  mov     [rbp+57h+arg_18], eax
0x180053bdf  mov     rax, [rdi+80h]
0x180053be6  mov     [rbp+57h+var_38], rax
0x180053bea  mov     eax, [rdi+40h]
0x180053bed  mov     [rbp+57h+var_70], eax
0x180053bf0  mov     rax, [rdi+38h]
0x180053bf4  mov     [rbp+57h+var_30], rax
0x180053bf8  mov     eax, [rdi+8]
0x180053bfb  mov     [rbp+57h+var_6C], eax
0x180053bfe  mov     eax, 1000000h
0x180053c03  mov     [rbp+57h+var_28], rax
0x180053c07  mov     [rbp+57h+var_20], rax
0x180053c0b  lea     rax, [rbp+57h+var_68]
0x180053c0f  mov     [rsp+110h+var_78], rax
0x180053c17  lea     rax, [rbp+57h+var_60]
0x180053c1b  mov     [rsp+110h+var_80], rax
0x180053c23  lea     rax, [rbp+57h+SRWLock]
0x180053c27  mov     [rsp+110h+var_88], rax
0x180053c2f  lea     rax, [rbp+57h+var_58]
0x180053c33  mov     [rsp+110h+var_90], rax
0x180053c3b  lea     rax, [rbp+57h+var_50]
0x180053c3f  mov     [rsp+110h+var_98], rax
0x180053c44  lea     rax, [rbp+57h+arg_8]
0x180053c48  mov     [rsp+110h+var_A0], rax
0x180053c4d  lea     rax, [rbp+57h+var_48]
0x180053c51  mov     [rsp+110h+var_A8], rax
0x180053c56  lea     rax, [rbp+57h+arg_10]
0x180053c5a  mov     [rsp+110h+var_B0], rax
0x180053c5f  lea     rax, [rbp+57h+var_40]
0x180053c63  mov     [rsp+110h+var_B8], rax
0x180053c68  lea     rax, [rbp+57h+arg_18]
0x180053c6c  mov     [rsp+110h+var_C0], rax
0x180053c71  lea     rax, [rbp+57h+var_38]
0x180053c75  mov     [rsp+110h+var_C8], rax
0x180053c7a  lea     rax, [rbp+57h+var_70]
0x180053c7e  mov     [rsp+110h+var_D0], rax
0x180053c83  lea     rax, [rbp+57h+var_30]
0x180053c87  mov     [rsp+110h+var_D8], rax
0x180053c8c  lea     rax, [rbp+57h+var_6C]
0x180053c90  mov     [rsp+110h+var_E0], rax
0x180053c95  lea     rax, [rbp+57h+var_28]
0x180053c99  mov     [rsp+110h+var_E8], rax
0x180053c9e  lea     rax, [rbp+57h+var_20]
0x180053ca2  mov     [rsp+110h+var_F0], rax
0x180053ca7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180053cac  jmp     loc_180053D61
0x180053cb1  lea     rdx, [rbp+57h+SRWLock]
0x180053cb5  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180053cba  mov     rax, [rbx+110h]
0x180053cc1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180053cc5  mov     dword ptr [rax], 2
0x180053ccb  test    rcx, rcx
0x180053cce  jz      short loc_180053CDC
0x180053cd0  call    cs:__imp_ReleaseSRWLockExclusive
0x180053cd7  nop     dword ptr [rax+rax+00h]
0x180053cdc  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180053ce1  mov     rdi, rax
0x180053ce4  mov     ecx, [rax]
0x180053ce6  cmp     ecx, 5
0x180053ce9  jbe     short loc_180053D61
0x180053ceb  mov     rax, [rax+18h]
0x180053cef  mov     rdx, 400000000000h
0x180053cf9  mov     rcx, [rdi+10h]
0x180053cfd  test    rdx, rcx
0x180053d00  jz      short loc_180053D61
0x180053d02  mov     rcx, rax
0x180053d05  and     rcx, rdx
0x180053d08  cmp     rcx, rax
0x180053d0b  jnz     short loc_180053D61
0x180053d0d  call    cs:__imp_GetCurrentThreadId
0x180053d14  nop     dword ptr [rax+rax+00h]
0x180053d19  mov     r8, [rbx+110h]
0x180053d20  lea     rdx, byte_18006A011
0x180053d27  mov     dword ptr [rbp+57h+SRWLock], eax
0x180053d2a  mov     rcx, rdi
0x180053d2d  mov     eax, [r8+48h]
0x180053d31  add     r8, 8
0x180053d35  mov     [rbp+57h+arg_8], eax
0x180053d38  mov     eax, 1000000h
0x180053d3d  mov     [rbp+57h+arg_10], rax
0x180053d41  lea     rax, [rbp+57h+SRWLock]
0x180053d45  mov     [rsp+110h+var_E0], rax
0x180053d4a  lea     rax, [rbp+57h+arg_8]
0x180053d4e  mov     [rsp+110h+var_E8], rax
0x180053d53  lea     rax, [rbp+57h+arg_10]
0x180053d57  mov     [rsp+110h+var_F0], rax
0x180053d5c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180053d61  mov     rcx, rbx
0x180053d64  add     rsp, 100h
0x180053d6b  pop     rdi
0x180053d6c  pop     rbx
0x180053d6d  pop     rbp
0x180053d6e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
