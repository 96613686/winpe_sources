# PpfTraceLoggingProvider::PpfScheduledTaskActivity::StopActivity(void)

- ea: `0x18001a0b0`
- end: `0x18001a343`
- name: `?StopActivity@PpfScheduledTaskActivity@PpfTraceLoggingProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfScheduledTaskActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x1800016e4`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x18001a0b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a10a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a2a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a10a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a2a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a2dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a2dd`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfScheduledTaskActivity::StopActivity(
        PpfTraceLoggingProvider::PpfScheduledTaskActivity *this)
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
          (__int64)&byte_1800694AF,
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
          (__int64)&word_18006917E,
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
0x18001a0b0  push    rbp
0x18001a0b2  push    rbx
0x18001a0b3  push    rdi
0x18001a0b4  lea     rbp, [rsp-47h]
0x18001a0b9  sub     rsp, 100h
0x18001a0c0  mov     rdi, [rcx+110h]
0x18001a0c7  mov     rbx, rcx
0x18001a0ca  mov     eax, [rdi+48h]
0x18001a0cd  test    eax, eax
0x18001a0cf  jns     loc_18001A281
0x18001a0d5  add     rdi, 50h ; 'P'
0x18001a0d9  cmp     eax, [rdi+8]
0x18001a0dc  jnz     loc_18001A281
0x18001a0e2  test    rdi, rdi
0x18001a0e5  jz      loc_18001A281
0x18001a0eb  lea     rdx, [rbp+57h+SRWLock]
0x18001a0ef  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a0f4  mov     rax, [rbx+110h]
0x18001a0fb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a0ff  mov     dword ptr [rax], 2
0x18001a105  test    rcx, rcx
0x18001a108  jz      short loc_18001A116
0x18001a10a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a111  nop     dword ptr [rax+rax+00h]
0x18001a116  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001a11b  mov     r9, rax
0x18001a11e  mov     ecx, [rax]
0x18001a120  cmp     ecx, 5
0x18001a123  jbe     loc_18001A331
0x18001a129  mov     rax, [rax+18h]
0x18001a12d  mov     rdx, 400000000000h
0x18001a137  mov     rcx, [r9+10h]
0x18001a13b  test    rdx, rcx
0x18001a13e  jz      loc_18001A331
0x18001a144  mov     rcx, rax
0x18001a147  and     rcx, rdx
0x18001a14a  cmp     rcx, rax
0x18001a14d  jnz     loc_18001A331
0x18001a153  mov     rax, [rdi+78h]
0x18001a157  lea     rdx, byte_1800694AF
0x18001a15e  mov     r8, [rbx+110h]
0x18001a165  mov     rcx, r9
0x18001a168  mov     [rbp+57h+var_68], rax
0x18001a16c  add     r8, 8
0x18001a170  mov     rax, [rdi+70h]
0x18001a174  mov     [rbp+57h+var_60], rax
0x18001a178  mov     eax, [rdi+68h]
0x18001a17b  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a17e  mov     rax, [rdi+60h]
0x18001a182  mov     [rbp+57h+var_58], rax
0x18001a186  mov     rax, [rdi+58h]
0x18001a18a  mov     [rbp+57h+var_50], rax
0x18001a18e  mov     eax, [rdi+50h]
0x18001a191  mov     [rbp+57h+arg_8], eax
0x18001a194  mov     rax, [rdi+48h]
0x18001a198  mov     [rbp+57h+var_48], rax
0x18001a19c  mov     eax, [rdi+20h]
0x18001a19f  mov     dword ptr [rbp+57h+arg_10], eax
0x18001a1a2  mov     rax, [rdi+18h]
0x18001a1a6  mov     [rbp+57h+var_40], rax
0x18001a1aa  mov     eax, [rdi]
0x18001a1ac  mov     [rbp+57h+arg_18], eax
0x18001a1af  mov     rax, [rdi+80h]
0x18001a1b6  mov     [rbp+57h+var_38], rax
0x18001a1ba  mov     eax, [rdi+40h]
0x18001a1bd  mov     [rbp+57h+var_70], eax
0x18001a1c0  mov     rax, [rdi+38h]
0x18001a1c4  mov     [rbp+57h+var_30], rax
0x18001a1c8  mov     eax, [rdi+8]
0x18001a1cb  mov     [rbp+57h+var_6C], eax
0x18001a1ce  mov     eax, 1000000h
0x18001a1d3  mov     [rbp+57h+var_28], rax
0x18001a1d7  mov     [rbp+57h+var_20], rax
0x18001a1db  lea     rax, [rbp+57h+var_68]
0x18001a1df  mov     [rsp+110h+var_78], rax
0x18001a1e7  lea     rax, [rbp+57h+var_60]
0x18001a1eb  mov     [rsp+110h+var_80], rax
0x18001a1f3  lea     rax, [rbp+57h+SRWLock]
0x18001a1f7  mov     [rsp+110h+var_88], rax
0x18001a1ff  lea     rax, [rbp+57h+var_58]
0x18001a203  mov     [rsp+110h+var_90], rax
0x18001a20b  lea     rax, [rbp+57h+var_50]
0x18001a20f  mov     [rsp+110h+var_98], rax
0x18001a214  lea     rax, [rbp+57h+arg_8]
0x18001a218  mov     [rsp+110h+var_A0], rax
0x18001a21d  lea     rax, [rbp+57h+var_48]
0x18001a221  mov     [rsp+110h+var_A8], rax
0x18001a226  lea     rax, [rbp+57h+arg_10]
0x18001a22a  mov     [rsp+110h+var_B0], rax
0x18001a22f  lea     rax, [rbp+57h+var_40]
0x18001a233  mov     [rsp+110h+var_B8], rax
0x18001a238  lea     rax, [rbp+57h+arg_18]
0x18001a23c  mov     [rsp+110h+var_C0], rax
0x18001a241  lea     rax, [rbp+57h+var_38]
0x18001a245  mov     [rsp+110h+var_C8], rax
0x18001a24a  lea     rax, [rbp+57h+var_70]
0x18001a24e  mov     [rsp+110h+var_D0], rax
0x18001a253  lea     rax, [rbp+57h+var_30]
0x18001a257  mov     [rsp+110h+var_D8], rax
0x18001a25c  lea     rax, [rbp+57h+var_6C]
0x18001a260  mov     [rsp+110h+var_E0], rax
0x18001a265  lea     rax, [rbp+57h+var_28]
0x18001a269  mov     [rsp+110h+var_E8], rax
0x18001a26e  lea     rax, [rbp+57h+var_20]
0x18001a272  mov     [rsp+110h+var_F0], rax
0x18001a277  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001a27c  jmp     loc_18001A331
0x18001a281  lea     rdx, [rbp+57h+SRWLock]
0x18001a285  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001a28a  mov     rax, [rbx+110h]
0x18001a291  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001a295  mov     dword ptr [rax], 2
0x18001a29b  test    rcx, rcx
0x18001a29e  jz      short loc_18001A2AC
0x18001a2a0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a2a7  nop     dword ptr [rax+rax+00h]
0x18001a2ac  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18001a2b1  mov     rdi, rax
0x18001a2b4  mov     ecx, [rax]
0x18001a2b6  cmp     ecx, 5
0x18001a2b9  jbe     short loc_18001A331
0x18001a2bb  mov     rax, [rax+18h]
0x18001a2bf  mov     rdx, 400000000000h
0x18001a2c9  mov     rcx, [rdi+10h]
0x18001a2cd  test    rdx, rcx
0x18001a2d0  jz      short loc_18001A331
0x18001a2d2  mov     rcx, rax
0x18001a2d5  and     rcx, rdx
0x18001a2d8  cmp     rcx, rax
0x18001a2db  jnz     short loc_18001A331
0x18001a2dd  call    cs:__imp_GetCurrentThreadId
0x18001a2e4  nop     dword ptr [rax+rax+00h]
0x18001a2e9  mov     r8, [rbx+110h]
0x18001a2f0  lea     rdx, word_18006917E
0x18001a2f7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001a2fa  mov     rcx, rdi
0x18001a2fd  mov     eax, [r8+48h]
0x18001a301  add     r8, 8
0x18001a305  mov     [rbp+57h+arg_8], eax
0x18001a308  mov     eax, 1000000h
0x18001a30d  mov     [rbp+57h+arg_10], rax
0x18001a311  lea     rax, [rbp+57h+SRWLock]
0x18001a315  mov     [rsp+110h+var_E0], rax
0x18001a31a  lea     rax, [rbp+57h+arg_8]
0x18001a31e  mov     [rsp+110h+var_E8], rax
0x18001a323  lea     rax, [rbp+57h+arg_10]
0x18001a327  mov     [rsp+110h+var_F0], rax
0x18001a32c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a331  mov     rcx, rbx
0x18001a334  add     rsp, 100h
0x18001a33b  pop     rdi
0x18001a33c  pop     rbx
0x18001a33d  pop     rbp
0x18001a33e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
