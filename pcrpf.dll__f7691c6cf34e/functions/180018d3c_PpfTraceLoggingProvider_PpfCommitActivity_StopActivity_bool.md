# PpfTraceLoggingProvider::PpfCommitActivity::StopActivity(bool)

- ea: `0x180018d3c`
- end: `0x180019082`
- name: `?StopActivity@PpfCommitActivity@PpfTraceLoggingProvider@@QEAAX_N@Z`
- size: `838`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfCommitActivity *this, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fec8`

## callees

- `0x180001640`
- `0x1800020c0`
- `0x180003270`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180018d3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018fbd`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::PpfCommitActivity::StopActivity(
        PpfTraceLoggingProvider::PpfCommitActivity *this,
        char a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  RTL_SRWLOCK *v12; // rcx
  const struct _tlgProvider_t *v13; // rax
  const struct _tlgProvider_t *v14; // rdi
  __int64 v15; // rax
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  _BYTE v18[4]; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v21; // [rsp+C0h] [rbp-70h] BYREF
  int v22; // [rsp+C8h] [rbp-68h] BYREF
  int v23; // [rsp+CCh] [rbp-64h] BYREF
  int v24; // [rsp+D0h] [rbp-60h] BYREF
  int v25; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v26; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v28; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v29; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v30; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v31; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v32; // [rsp+108h] [rbp-28h] BYREF
  const wchar_t *v33; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v34; // [rsp+118h] [rbp-18h] BYREF
  const unsigned __int16 *v35; // [rsp+120h] [rbp-10h] BYREF
  _BYTE v36[32]; // [rsp+130h] [rbp+0h] BYREF
  __int64 *v37; // [rsp+150h] [rbp+20h]
  __int64 v38; // [rsp+158h] [rbp+28h]
  int *v39; // [rsp+160h] [rbp+30h]
  __int64 v40; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v42; // [rsp+178h] [rbp+48h]
  _BYTE *v43; // [rsp+180h] [rbp+50h]
  __int64 v44; // [rsp+188h] [rbp+58h]
  PSRWLOCK *v45; // [rsp+190h] [rbp+60h]
  __int64 v46; // [rsp+198h] [rbp+68h]

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v7 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = PpfTraceLoggingProvider::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        v28 = (const wchar_t *)*((_QWORD *)v6 + 15);
        v11 = *((_QWORD *)this + 34);
        v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
        v22 = v6[26];
        v30 = (const wchar_t *)*((_QWORD *)v6 + 12);
        v31 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
        v23 = v6[20];
        v32 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
        v24 = v6[8];
        v33 = (const wchar_t *)*((_QWORD *)v6 + 3);
        v25 = *v6;
        v34 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
        v19 = v6[16];
        v35 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
        LODWORD(SRWLock) = v6[2];
        v27 = 0x1000000;
        v18[0] = a2;
        v26 = 0x1000000;
        v21 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v9,
          (__int64)&unk_1800684A0,
          v11 + 8,
          v9,
          (__int64)&v21,
          (__int64)&v26,
          (__int64)&SRWLock,
          &v35,
          (__int64)&v19,
          &v34,
          (__int64)&v25,
          &v33,
          (__int64)&v24,
          &v32,
          (__int64)&v23,
          &v31,
          &v30,
          (__int64)&v22,
          &v29,
          &v28,
          (__int64)v18,
          (__int64)&v27);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v21);
    v12 = v21;
    **((_DWORD **)this + 34) = 2;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v13 = PpfTraceLoggingProvider::Provider();
    v14 = v13;
    if ( *(_DWORD *)v13 > 5u )
    {
      v15 = *((_QWORD *)v13 + 3);
      if ( (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0 && (v15 & 0x400000000000LL) == v15 )
      {
        v18[0] = a2;
        v21 = (PSRWLOCK)0x1000000;
        CurrentThreadId = GetCurrentThreadId();
        v17 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v46 = 8;
        v44 = 1;
        v19 = *(_DWORD *)(v17 + 72);
        v45 = &v21;
        v43 = v18;
        p_SRWLock = &SRWLock;
        v39 = &v19;
        v37 = &v26;
        v26 = 0x1000000;
        v42 = 4;
        v40 = 4;
        v38 = 8;
        tlgWriteTransfer_EventWriteTransfer(v14, &unk_180068640, v17 + 8, 0, 7, v36);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180018d3c  mov     [rsp-8+arg_8], rbx
0x180018d41  mov     [rsp-8+arg_10], rsi
0x180018d46  push    rbp
0x180018d47  push    rdi
0x180018d48  push    r14
0x180018d4a  lea     rbp, [rsp-80h]
0x180018d4f  sub     rsp, 1B0h
0x180018d56  mov     rax, cs:__security_cookie
0x180018d5d  xor     rax, rsp
0x180018d60  mov     [rbp+90h+var_20], rax
0x180018d64  mov     rdi, [rcx+110h]
0x180018d6b  mov     r14b, dl
0x180018d6e  mov     rbx, rcx
0x180018d71  mov     eax, [rdi+48h]
0x180018d74  test    eax, eax
0x180018d76  jns     loc_180018F48
0x180018d7c  add     rdi, 50h ; 'P'
0x180018d80  cmp     eax, [rdi+8]
0x180018d83  jnz     loc_180018F48
0x180018d89  test    rdi, rdi
0x180018d8c  jz      loc_180018F48
0x180018d92  lea     rdx, [rbp+90h+SRWLock]
0x180018d96  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018d9b  mov     rax, [rbx+110h]
0x180018da2  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x180018da6  mov     dword ptr [rax], 2
0x180018dac  test    rcx, rcx
0x180018daf  jz      short loc_180018DBD
0x180018db1  call    cs:__imp_ReleaseSRWLockExclusive
0x180018db8  nop     dword ptr [rax+rax+00h]
0x180018dbd  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018dc2  mov     r9, rax
0x180018dc5  mov     ecx, [rax]
0x180018dc7  cmp     ecx, 5
0x180018dca  jbe     loc_180019055
0x180018dd0  mov     rax, [rax+18h]
0x180018dd4  mov     rdx, 400000000000h
0x180018dde  mov     rcx, [r9+10h]
0x180018de2  test    rdx, rcx
0x180018de5  jz      loc_180019055
0x180018deb  mov     rcx, rax
0x180018dee  and     rcx, rdx
0x180018df1  cmp     rcx, rax
0x180018df4  jnz     loc_180019055
0x180018dfa  mov     rax, [rdi+78h]
0x180018dfe  lea     rdx, unk_1800684A0
0x180018e05  mov     [rbp+90h+var_D8], rax
0x180018e09  mov     esi, 1000000h
0x180018e0e  mov     rax, [rdi+70h]
0x180018e12  mov     rcx, r9
0x180018e15  mov     r8, [rbx+110h]
0x180018e1c  mov     [rbp+90h+var_D0], rax
0x180018e20  add     r8, 8
0x180018e24  mov     eax, [rdi+68h]
0x180018e27  mov     [rbp+90h+var_F8], eax
0x180018e2a  mov     rax, [rdi+60h]
0x180018e2e  mov     [rbp+90h+var_C8], rax
0x180018e32  mov     rax, [rdi+58h]
0x180018e36  mov     [rbp+90h+var_C0], rax
0x180018e3a  mov     eax, [rdi+50h]
0x180018e3d  mov     [rbp+90h+var_F4], eax
0x180018e40  mov     rax, [rdi+48h]
0x180018e44  mov     [rbp+90h+var_B8], rax
0x180018e48  mov     eax, [rdi+20h]
0x180018e4b  mov     [rbp+90h+var_F0], eax
0x180018e4e  mov     rax, [rdi+18h]
0x180018e52  mov     [rbp+90h+var_B0], rax
0x180018e56  mov     eax, [rdi]
0x180018e58  mov     [rbp+90h+var_EC], eax
0x180018e5b  mov     rax, [rdi+80h]
0x180018e62  mov     [rbp+90h+var_A8], rax
0x180018e66  mov     eax, [rdi+40h]
0x180018e69  mov     [rbp+90h+var_10C], eax
0x180018e6c  mov     rax, [rdi+38h]
0x180018e70  mov     [rbp+90h+var_A0], rax
0x180018e74  mov     eax, [rdi+8]
0x180018e77  mov     dword ptr [rbp+90h+SRWLock], eax
0x180018e7a  lea     rax, [rbp+90h+var_E0]
0x180018e7e  mov     [rsp+1C0h+var_118], rax
0x180018e86  lea     rax, [rbp+90h+var_110]
0x180018e8a  mov     [rsp+1C0h+var_120], rax
0x180018e92  lea     rax, [rbp+90h+var_D8]
0x180018e96  mov     [rsp+1C0h+var_128], rax
0x180018e9e  lea     rax, [rbp+90h+var_D0]
0x180018ea2  mov     [rsp+1C0h+var_130], rax
0x180018eaa  lea     rax, [rbp+90h+var_F8]
0x180018eae  mov     [rsp+1C0h+var_138], rax
0x180018eb6  lea     rax, [rbp+90h+var_C8]
0x180018eba  mov     [rsp+1C0h+var_140], rax
0x180018ec2  lea     rax, [rbp+90h+var_C0]
0x180018ec6  mov     [rsp+1C0h+var_148], rax
0x180018ecb  lea     rax, [rbp+90h+var_F4]
0x180018ecf  mov     [rsp+1C0h+var_150], rax
0x180018ed4  lea     rax, [rbp+90h+var_B8]
0x180018ed8  mov     [rsp+1C0h+var_158], rax
0x180018edd  lea     rax, [rbp+90h+var_F0]
0x180018ee1  mov     [rsp+1C0h+var_160], rax
0x180018ee6  lea     rax, [rbp+90h+var_B0]
0x180018eea  mov     [rsp+1C0h+var_168], rax
0x180018eef  lea     rax, [rbp+90h+var_EC]
0x180018ef3  mov     [rsp+1C0h+var_170], rax
0x180018ef8  lea     rax, [rbp+90h+var_A8]
0x180018efc  mov     [rsp+1C0h+var_178], rax
0x180018f01  lea     rax, [rbp+90h+var_10C]
0x180018f05  mov     [rsp+1C0h+var_180], rax
0x180018f0a  lea     rax, [rbp+90h+var_A0]
0x180018f0e  mov     [rsp+1C0h+var_188], rax
0x180018f13  lea     rax, [rbp+90h+SRWLock]
0x180018f17  mov     [rsp+1C0h+var_190], rax
0x180018f1c  lea     rax, [rbp+90h+var_E8]
0x180018f20  mov     [rsp+1C0h+var_198], rax
0x180018f25  lea     rax, [rbp+90h+var_100]
0x180018f29  mov     [rsp+1C0h+var_1A0], rax
0x180018f2e  mov     [rbp+90h+var_E0], rsi
0x180018f32  mov     [rbp+90h+var_110], r14b
0x180018f36  mov     [rbp+90h+var_E8], rsi
0x180018f3a  mov     [rbp+90h+var_100], rsi
0x180018f3e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180018f43  jmp     loc_180019055
0x180018f48  lea     rdx, [rbp+90h+var_100]
0x180018f4c  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018f51  mov     rax, [rbx+110h]
0x180018f58  mov     rcx, [rbp+90h+var_100]; SRWLock
0x180018f5c  mov     dword ptr [rax], 2
0x180018f62  test    rcx, rcx
0x180018f65  jz      short loc_180018F73
0x180018f67  call    cs:__imp_ReleaseSRWLockExclusive
0x180018f6e  nop     dword ptr [rax+rax+00h]
0x180018f73  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180018f78  mov     rdi, rax
0x180018f7b  mov     ecx, [rax]
0x180018f7d  cmp     ecx, 5
0x180018f80  jbe     loc_180019055
0x180018f86  mov     rax, [rax+18h]
0x180018f8a  mov     rdx, 400000000000h
0x180018f94  mov     rcx, [rdi+10h]
0x180018f98  test    rdx, rcx
0x180018f9b  jz      loc_180019055
0x180018fa1  mov     rcx, rax
0x180018fa4  and     rcx, rdx
0x180018fa7  cmp     rcx, rax
0x180018faa  jnz     loc_180019055
0x180018fb0  mov     esi, 1000000h
0x180018fb5  mov     [rbp+90h+var_110], r14b
0x180018fb9  mov     [rbp+90h+var_100], rsi
0x180018fbd  call    cs:__imp_GetCurrentThreadId
0x180018fc4  nop     dword ptr [rax+rax+00h]
0x180018fc9  mov     r8, [rbx+110h]
0x180018fd0  lea     rdx, unk_180068640
0x180018fd7  mov     dword ptr [rbp+90h+SRWLock], eax
0x180018fda  xor     r9d, r9d
0x180018fdd  mov     rcx, rdi
0x180018fe0  mov     [rbp+90h+var_28], 8
0x180018fe8  mov     [rbp+90h+var_38], 1
0x180018ff0  mov     eax, [r8+48h]
0x180018ff4  add     r8, 8
0x180018ff8  mov     [rbp+90h+var_10C], eax
0x180018ffb  lea     rax, [rbp+90h+var_100]
0x180018fff  mov     [rbp+90h+var_30], rax
0x180019003  lea     rax, [rbp+90h+var_110]
0x180019007  mov     [rbp+90h+var_40], rax
0x18001900b  lea     rax, [rbp+90h+SRWLock]
0x18001900f  mov     [rbp+90h+var_50], rax
0x180019013  lea     rax, [rbp+90h+var_10C]
0x180019017  mov     [rbp+90h+var_60], rax
0x18001901b  lea     rax, [rbp+90h+var_E8]
0x18001901f  mov     [rbp+90h+var_70], rax
0x180019023  lea     rax, [rbp+90h+var_90]
0x180019027  mov     [rsp+1C0h+var_198], rax
0x18001902c  mov     dword ptr [rsp+1C0h+var_1A0], 7
0x180019034  mov     [rbp+90h+var_E8], rsi
0x180019038  mov     [rbp+90h+var_48], 4
0x180019040  mov     [rbp+90h+var_58], 4
0x180019048  mov     [rbp+90h+var_68], 8
0x180019050  call    _tlgWriteTransfer_EventWriteTransfer
0x180019055  mov     rcx, rbx
0x180019058  call    ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001905d  mov     rcx, [rbp+90h+var_20]
0x180019061  xor     rcx, rsp; StackCookie
0x180019064  call    __security_check_cookie
0x180019069  lea     r11, [rsp+1C0h+var_10]
0x180019071  mov     rbx, [r11+28h]
0x180019075  mov     rsi, [r11+30h]
0x180019079  mov     rsp, r11
0x18001907c  pop     r14
0x18001907e  pop     rdi
0x18001907f  pop     rbp
0x180019080  retn
```
