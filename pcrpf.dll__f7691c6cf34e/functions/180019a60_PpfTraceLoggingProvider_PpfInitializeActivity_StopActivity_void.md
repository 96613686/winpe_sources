# PpfTraceLoggingProvider::PpfInitializeActivity::StopActivity(void)

- ea: `0x180019a60`
- end: `0x180019cf3`
- name: `?StopActivity@PpfInitializeActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfInitializeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180019a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019c50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfInitializeActivity::StopActivity(
        PpfTraceLoggingProvider::PpfInitializeActivity *this)
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
          (__int64)&unk_180068CC8,
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
          (__int64)&byte_1800691D7,
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
0x180019a60  push    rbp
0x180019a62  push    rbx
0x180019a63  push    rdi
0x180019a64  lea     rbp, [rsp-47h]
0x180019a69  sub     rsp, 100h
0x180019a70  mov     rdi, [rcx+110h]
0x180019a77  mov     rbx, rcx
0x180019a7a  mov     eax, [rdi+48h]
0x180019a7d  test    eax, eax
0x180019a7f  jns     loc_180019C31
0x180019a85  add     rdi, 50h ; 'P'
0x180019a89  cmp     eax, [rdi+8]
0x180019a8c  jnz     loc_180019C31
0x180019a92  test    rdi, rdi
0x180019a95  jz      loc_180019C31
0x180019a9b  lea     rdx, [rbp+57h+SRWLock]
0x180019a9f  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019aa4  mov     rax, [rbx+110h]
0x180019aab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019aaf  mov     dword ptr [rax], 2
0x180019ab5  test    rcx, rcx
0x180019ab8  jz      short loc_180019AC6
0x180019aba  call    cs:__imp_ReleaseSRWLockExclusive
0x180019ac1  nop     dword ptr [rax+rax+00h]
0x180019ac6  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019acb  mov     r9, rax
0x180019ace  mov     ecx, [rax]
0x180019ad0  cmp     ecx, 5
0x180019ad3  jbe     loc_180019CE1
0x180019ad9  mov     rax, [rax+18h]
0x180019add  mov     rdx, 400000000000h
0x180019ae7  mov     rcx, [r9+10h]
0x180019aeb  test    rdx, rcx
0x180019aee  jz      loc_180019CE1
0x180019af4  mov     rcx, rax
0x180019af7  and     rcx, rdx
0x180019afa  cmp     rcx, rax
0x180019afd  jnz     loc_180019CE1
0x180019b03  mov     rax, [rdi+78h]
0x180019b07  lea     rdx, unk_180068CC8
0x180019b0e  mov     r8, [rbx+110h]
0x180019b15  mov     rcx, r9
0x180019b18  mov     [rbp+57h+var_68], rax
0x180019b1c  add     r8, 8
0x180019b20  mov     rax, [rdi+70h]
0x180019b24  mov     [rbp+57h+var_60], rax
0x180019b28  mov     eax, [rdi+68h]
0x180019b2b  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019b2e  mov     rax, [rdi+60h]
0x180019b32  mov     [rbp+57h+var_58], rax
0x180019b36  mov     rax, [rdi+58h]
0x180019b3a  mov     [rbp+57h+var_50], rax
0x180019b3e  mov     eax, [rdi+50h]
0x180019b41  mov     [rbp+57h+arg_8], eax
0x180019b44  mov     rax, [rdi+48h]
0x180019b48  mov     [rbp+57h+var_48], rax
0x180019b4c  mov     eax, [rdi+20h]
0x180019b4f  mov     dword ptr [rbp+57h+arg_10], eax
0x180019b52  mov     rax, [rdi+18h]
0x180019b56  mov     [rbp+57h+var_40], rax
0x180019b5a  mov     eax, [rdi]
0x180019b5c  mov     [rbp+57h+arg_18], eax
0x180019b5f  mov     rax, [rdi+80h]
0x180019b66  mov     [rbp+57h+var_38], rax
0x180019b6a  mov     eax, [rdi+40h]
0x180019b6d  mov     [rbp+57h+var_70], eax
0x180019b70  mov     rax, [rdi+38h]
0x180019b74  mov     [rbp+57h+var_30], rax
0x180019b78  mov     eax, [rdi+8]
0x180019b7b  mov     [rbp+57h+var_6C], eax
0x180019b7e  mov     eax, 1000000h
0x180019b83  mov     [rbp+57h+var_28], rax
0x180019b87  mov     [rbp+57h+var_20], rax
0x180019b8b  lea     rax, [rbp+57h+var_68]
0x180019b8f  mov     [rsp+110h+var_78], rax
0x180019b97  lea     rax, [rbp+57h+var_60]
0x180019b9b  mov     [rsp+110h+var_80], rax
0x180019ba3  lea     rax, [rbp+57h+SRWLock]
0x180019ba7  mov     [rsp+110h+var_88], rax
0x180019baf  lea     rax, [rbp+57h+var_58]
0x180019bb3  mov     [rsp+110h+var_90], rax
0x180019bbb  lea     rax, [rbp+57h+var_50]
0x180019bbf  mov     [rsp+110h+var_98], rax
0x180019bc4  lea     rax, [rbp+57h+arg_8]
0x180019bc8  mov     [rsp+110h+var_A0], rax
0x180019bcd  lea     rax, [rbp+57h+var_48]
0x180019bd1  mov     [rsp+110h+var_A8], rax
0x180019bd6  lea     rax, [rbp+57h+arg_10]
0x180019bda  mov     [rsp+110h+var_B0], rax
0x180019bdf  lea     rax, [rbp+57h+var_40]
0x180019be3  mov     [rsp+110h+var_B8], rax
0x180019be8  lea     rax, [rbp+57h+arg_18]
0x180019bec  mov     [rsp+110h+var_C0], rax
0x180019bf1  lea     rax, [rbp+57h+var_38]
0x180019bf5  mov     [rsp+110h+var_C8], rax
0x180019bfa  lea     rax, [rbp+57h+var_70]
0x180019bfe  mov     [rsp+110h+var_D0], rax
0x180019c03  lea     rax, [rbp+57h+var_30]
0x180019c07  mov     [rsp+110h+var_D8], rax
0x180019c0c  lea     rax, [rbp+57h+var_6C]
0x180019c10  mov     [rsp+110h+var_E0], rax
0x180019c15  lea     rax, [rbp+57h+var_28]
0x180019c19  mov     [rsp+110h+var_E8], rax
0x180019c1e  lea     rax, [rbp+57h+var_20]
0x180019c22  mov     [rsp+110h+var_F0], rax
0x180019c27  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019c2c  jmp     loc_180019CE1
0x180019c31  lea     rdx, [rbp+57h+SRWLock]
0x180019c35  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019c3a  mov     rax, [rbx+110h]
0x180019c41  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180019c45  mov     dword ptr [rax], 2
0x180019c4b  test    rcx, rcx
0x180019c4e  jz      short loc_180019C5C
0x180019c50  call    cs:__imp_ReleaseSRWLockExclusive
0x180019c57  nop     dword ptr [rax+rax+00h]
0x180019c5c  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019c61  mov     rdi, rax
0x180019c64  mov     ecx, [rax]
0x180019c66  cmp     ecx, 5
0x180019c69  jbe     short loc_180019CE1
0x180019c6b  mov     rax, [rax+18h]
0x180019c6f  mov     rdx, 400000000000h
0x180019c79  mov     rcx, [rdi+10h]
0x180019c7d  test    rdx, rcx
0x180019c80  jz      short loc_180019CE1
0x180019c82  mov     rcx, rax
0x180019c85  and     rcx, rdx
0x180019c88  cmp     rcx, rax
0x180019c8b  jnz     short loc_180019CE1
0x180019c8d  call    cs:__imp_GetCurrentThreadId
0x180019c94  nop     dword ptr [rax+rax+00h]
0x180019c99  mov     r8, [rbx+110h]
0x180019ca0  lea     rdx, byte_1800691D7
0x180019ca7  mov     dword ptr [rbp+57h+SRWLock], eax
0x180019caa  mov     rcx, rdi
0x180019cad  mov     eax, [r8+48h]
0x180019cb1  add     r8, 8
0x180019cb5  mov     [rbp+57h+arg_8], eax
0x180019cb8  mov     eax, 1000000h
0x180019cbd  mov     [rbp+57h+arg_10], rax
0x180019cc1  lea     rax, [rbp+57h+SRWLock]
0x180019cc5  mov     [rsp+110h+var_E0], rax
0x180019cca  lea     rax, [rbp+57h+arg_8]
0x180019cce  mov     [rsp+110h+var_E8], rax
0x180019cd3  lea     rax, [rbp+57h+arg_10]
0x180019cd7  mov     [rsp+110h+var_F0], rax
0x180019cdc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019ce1  mov     rcx, rbx
0x180019ce4  add     rsp, 100h
0x180019ceb  pop     rdi
0x180019cec  pop     rbx
0x180019ced  pop     rbp
0x180019cee  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
