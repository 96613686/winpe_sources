# PpfTraceLoggingProvider::PpfInitializeActivity::StopActivity(bool,uint,bool)

- ea: `0x180019cfc`
- end: `0x18001a0a7`
- name: `?StopActivity@PpfInitializeActivity@PpfTraceLoggingProvider@@QEAAX_NI0@Z`
- size: `939`
- prototype: `void __fastcall(PpfTraceLoggingProvider::PpfInitializeActivity *this, char, int, char)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800107e8`

## callees

- `0x180001640`
- `0x180002394`
- `0x180003270`
- `0x18000cb38`
- `0x18000cbbc`
- `0x18000de98`
- `0x180019cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019d81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019f57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PpfTraceLoggingProvider::PpfInitializeActivity::StopActivity(
        PpfTraceLoggingProvider::PpfInitializeActivity *this,
        char a2,
        int a3,
        char a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  RTL_SRWLOCK *v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  RTL_SRWLOCK *v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  const struct _tlgProvider_t *v18; // rdi
  __int64 v19; // rax
  DWORD CurrentThreadId; // eax
  __int64 v21; // r8
  char v22; // [rsp+C0h] [rbp-80h] BYREF
  _BYTE v23[3]; // [rsp+C1h] [rbp-7Fh] BYREF
  int v24; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v25; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v27; // [rsp+D8h] [rbp-68h] BYREF
  int v28; // [rsp+E0h] [rbp-60h] BYREF
  int v29; // [rsp+E4h] [rbp-5Ch] BYREF
  int v30; // [rsp+E8h] [rbp-58h] BYREF
  int v31; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v32; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v34; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v35; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v36; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v37; // [rsp+118h] [rbp-28h] BYREF
  const unsigned __int16 *v38; // [rsp+120h] [rbp-20h] BYREF
  const wchar_t *v39; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v40; // [rsp+130h] [rbp-10h] BYREF
  const unsigned __int16 *v41; // [rsp+138h] [rbp-8h] BYREF
  char v42[32]; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v43; // [rsp+160h] [rbp+20h]
  __int64 v44; // [rsp+168h] [rbp+28h]
  int *v45; // [rsp+170h] [rbp+30h]
  __int64 v46; // [rsp+178h] [rbp+38h]
  DWORD *v47; // [rsp+180h] [rbp+40h]
  __int64 v48; // [rsp+188h] [rbp+48h]
  char *v49; // [rsp+190h] [rbp+50h]
  __int64 v50; // [rsp+198h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+1A0h] [rbp+60h]
  __int64 v52; // [rsp+1A8h] [rbp+68h]
  _BYTE *v53; // [rsp+1B0h] [rbp+70h]
  __int64 v54; // [rsp+1B8h] [rbp+78h]
  PSRWLOCK *v55; // [rsp+1C0h] [rbp+80h]
  __int64 v56; // [rsp+1C8h] [rbp+88h]

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v11 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = PpfTraceLoggingProvider::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u )
    {
      v14 = *((_QWORD *)v12 + 3);
      if ( (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0 && (v14 & 0x400000000000LL) == v14 )
      {
        v34 = (const wchar_t *)*((_QWORD *)v10 + 15);
        v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
        v29 = v10[26];
        v15 = *((_QWORD *)this + 34);
        v36 = (const wchar_t *)*((_QWORD *)v10 + 12);
        v37 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
        v30 = v10[20];
        v38 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
        v31 = v10[8];
        v39 = (const wchar_t *)*((_QWORD *)v10 + 3);
        v24 = *v10;
        v40 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
        v25 = v10[16];
        v41 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v33 = 0x1000000;
        v22 = a4;
        v28 = a3;
        v23[0] = a2;
        v32 = 0x1000000;
        v27 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v13,
          (__int64)&dword_180068F54,
          v15 + 8,
          v13,
          (__int64)&v27,
          (__int64)&v32,
          (__int64)&SRWLock,
          &v41,
          (__int64)&v25,
          &v40,
          (__int64)&v24,
          &v39,
          (__int64)&v31,
          &v38,
          (__int64)&v30,
          &v37,
          &v36,
          (__int64)&v29,
          &v35,
          &v34,
          (__int64)v23,
          (__int64)&v28,
          (__int64)&v22,
          (__int64)&v33);
      }
    }
  }
  else
  {
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v27);
    v16 = v27;
    **((_DWORD **)this + 34) = 2;
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    v17 = PpfTraceLoggingProvider::Provider();
    v18 = v17;
    if ( *(_DWORD *)v17 > 5u )
    {
      v19 = *((_QWORD *)v17 + 3);
      if ( (*((_QWORD *)v18 + 2) & 0x400000000000LL) != 0 && (v19 & 0x400000000000LL) == v19 )
      {
        v23[0] = a4;
        v27 = (PSRWLOCK)0x1000000;
        LODWORD(SRWLock) = a3;
        v22 = a2;
        CurrentThreadId = GetCurrentThreadId();
        v21 = *((_QWORD *)this + 34);
        v25 = CurrentThreadId;
        v56 = 8;
        v54 = 1;
        v24 = *(_DWORD *)(v21 + 72);
        v55 = &v27;
        v53 = v23;
        p_SRWLock = &SRWLock;
        v49 = &v22;
        v47 = &v25;
        v45 = &v24;
        v43 = &v32;
        v32 = 0x1000000;
        v52 = 4;
        v50 = 1;
        v48 = 4;
        v46 = 4;
        v44 = 8;
        tlgWriteTransfer_EventWriteTransfer(v18, &byte_180068AAF, v21 + 8, 0, 9, v42);
      }
    }
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019cfc  mov     [rsp-8+arg_8], rbx
0x180019d01  mov     [rsp-8+arg_10], rsi
0x180019d06  push    rbp
0x180019d07  push    rdi
0x180019d08  push    r12
0x180019d0a  push    r14
0x180019d0c  push    r15
0x180019d0e  lea     rbp, [rsp-0A0h]
0x180019d16  sub     rsp, 1E0h
0x180019d1d  mov     rax, cs:__security_cookie
0x180019d24  xor     rax, rsp
0x180019d27  mov     [rbp+0C0h+var_30], rax
0x180019d2e  mov     rdi, [rcx+110h]
0x180019d35  mov     r14b, r9b
0x180019d38  mov     r15d, r8d
0x180019d3b  mov     r12b, dl
0x180019d3e  mov     rbx, rcx
0x180019d41  mov     eax, [rdi+48h]
0x180019d44  test    eax, eax
0x180019d46  jns     loc_180019F38
0x180019d4c  add     rdi, 50h ; 'P'
0x180019d50  cmp     eax, [rdi+8]
0x180019d53  jnz     loc_180019F38
0x180019d59  test    rdi, rdi
0x180019d5c  jz      loc_180019F38
0x180019d62  lea     rdx, [rbp+0C0h+SRWLock]
0x180019d66  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019d6b  mov     rax, [rbx+110h]
0x180019d72  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x180019d76  mov     dword ptr [rax], 2
0x180019d7c  test    rcx, rcx
0x180019d7f  jz      short loc_180019D8D
0x180019d81  call    cs:__imp_ReleaseSRWLockExclusive
0x180019d88  nop     dword ptr [rax+rax+00h]
0x180019d8d  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019d92  mov     r9, rax
0x180019d95  mov     ecx, [rax]
0x180019d97  cmp     ecx, 5
0x180019d9a  jbe     loc_18001A073
0x180019da0  mov     rax, [rax+18h]
0x180019da4  mov     rdx, 400000000000h
0x180019dae  mov     rcx, [r9+10h]
0x180019db2  test    rdx, rcx
0x180019db5  jz      loc_18001A073
0x180019dbb  mov     rcx, rax
0x180019dbe  and     rcx, rdx
0x180019dc1  cmp     rcx, rax
0x180019dc4  jnz     loc_18001A073
0x180019dca  mov     rax, [rdi+78h]
0x180019dce  lea     rdx, dword_180068F54
0x180019dd5  mov     [rbp+0C0h+var_100], rax
0x180019dd9  mov     esi, 1000000h
0x180019dde  mov     rax, [rdi+70h]
0x180019de2  mov     rcx, r9
0x180019de5  mov     [rbp+0C0h+var_F8], rax
0x180019de9  mov     eax, [rdi+68h]
0x180019dec  mov     [rbp+0C0h+var_11C], eax
0x180019def  mov     rax, [rdi+60h]
0x180019df3  mov     r8, [rbx+110h]
0x180019dfa  mov     [rbp+0C0h+var_F0], rax
0x180019dfe  add     r8, 8
0x180019e02  mov     rax, [rdi+58h]
0x180019e06  mov     [rbp+0C0h+var_E8], rax
0x180019e0a  mov     eax, [rdi+50h]
0x180019e0d  mov     [rbp+0C0h+var_118], eax
0x180019e10  mov     rax, [rdi+48h]
0x180019e14  mov     [rbp+0C0h+var_E0], rax
0x180019e18  mov     eax, [rdi+20h]
0x180019e1b  mov     [rbp+0C0h+var_114], eax
0x180019e1e  mov     rax, [rdi+18h]
0x180019e22  mov     [rbp+0C0h+var_D8], rax
0x180019e26  mov     eax, [rdi]
0x180019e28  mov     [rbp+0C0h+var_13C], eax
0x180019e2b  mov     rax, [rdi+80h]
0x180019e32  mov     [rbp+0C0h+var_D0], rax
0x180019e36  mov     eax, [rdi+40h]
0x180019e39  mov     [rbp+0C0h+var_138], eax
0x180019e3c  mov     rax, [rdi+38h]
0x180019e40  mov     [rbp+0C0h+var_C8], rax
0x180019e44  mov     eax, [rdi+8]
0x180019e47  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x180019e4a  lea     rax, [rbp+0C0h+var_108]
0x180019e4e  mov     [rsp+200h+var_148], rax
0x180019e56  lea     rax, [rbp+0C0h+var_140]
0x180019e5a  mov     [rsp+200h+var_150], rax
0x180019e62  lea     rax, [rbp+0C0h+var_120]
0x180019e66  mov     [rsp+200h+var_158], rax
0x180019e6e  lea     rax, [rbp+0C0h+var_13F]
0x180019e72  mov     [rsp+200h+var_160], rax
0x180019e7a  lea     rax, [rbp+0C0h+var_100]
0x180019e7e  mov     [rsp+200h+var_168], rax
0x180019e86  lea     rax, [rbp+0C0h+var_F8]
0x180019e8a  mov     [rsp+200h+var_170], rax
0x180019e92  lea     rax, [rbp+0C0h+var_11C]
0x180019e96  mov     [rsp+200h+var_178], rax
0x180019e9e  lea     rax, [rbp+0C0h+var_F0]
0x180019ea2  mov     [rsp+200h+var_180], rax
0x180019eaa  lea     rax, [rbp+0C0h+var_E8]
0x180019eae  mov     [rsp+200h+var_188], rax
0x180019eb3  lea     rax, [rbp+0C0h+var_118]
0x180019eb7  mov     [rsp+200h+var_190], rax
0x180019ebc  lea     rax, [rbp+0C0h+var_E0]
0x180019ec0  mov     [rsp+200h+var_198], rax
0x180019ec5  lea     rax, [rbp+0C0h+var_114]
0x180019ec9  mov     [rsp+200h+var_1A0], rax
0x180019ece  lea     rax, [rbp+0C0h+var_D8]
0x180019ed2  mov     [rsp+200h+var_1A8], rax
0x180019ed7  lea     rax, [rbp+0C0h+var_13C]
0x180019edb  mov     [rsp+200h+var_1B0], rax
0x180019ee0  lea     rax, [rbp+0C0h+var_D0]
0x180019ee4  mov     [rsp+200h+var_1B8], rax
0x180019ee9  lea     rax, [rbp+0C0h+var_138]
0x180019eed  mov     [rsp+200h+var_1C0], rax
0x180019ef2  lea     rax, [rbp+0C0h+var_C8]
0x180019ef6  mov     [rsp+200h+var_1C8], rax
0x180019efb  lea     rax, [rbp+0C0h+SRWLock]
0x180019eff  mov     [rsp+200h+var_1D0], rax
0x180019f04  lea     rax, [rbp+0C0h+var_110]
0x180019f08  mov     [rsp+200h+var_1D8], rax
0x180019f0d  lea     rax, [rbp+0C0h+var_128]
0x180019f11  mov     [rsp+200h+var_1E0], rax
0x180019f16  mov     [rbp+0C0h+var_108], rsi
0x180019f1a  mov     [rbp+0C0h+var_140], r14b
0x180019f1e  mov     [rbp+0C0h+var_120], r15d
0x180019f22  mov     [rbp+0C0h+var_13F], r12b
0x180019f26  mov     [rbp+0C0h+var_110], rsi
0x180019f2a  mov     [rbp+0C0h+var_128], rsi
0x180019f2e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U2@U5@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@473@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180019f33  jmp     loc_18001A073
0x180019f38  lea     rdx, [rbp+0C0h+var_128]
0x180019f3c  call    ?LockExclusive@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180019f41  mov     rax, [rbx+110h]
0x180019f48  mov     rcx, [rbp+0C0h+var_128]; SRWLock
0x180019f4c  mov     dword ptr [rax], 2
0x180019f52  test    rcx, rcx
0x180019f55  jz      short loc_180019F63
0x180019f57  call    cs:__imp_ReleaseSRWLockExclusive
0x180019f5e  nop     dword ptr [rax+rax+00h]
0x180019f63  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x180019f68  mov     rdi, rax
0x180019f6b  mov     ecx, [rax]
0x180019f6d  cmp     ecx, 5
0x180019f70  jbe     loc_18001A073
0x180019f76  mov     rax, [rax+18h]
0x180019f7a  mov     rdx, 400000000000h
0x180019f84  mov     rcx, [rdi+10h]
0x180019f88  test    rdx, rcx
0x180019f8b  jz      loc_18001A073
0x180019f91  mov     rcx, rax
0x180019f94  and     rcx, rdx
0x180019f97  cmp     rcx, rax
0x180019f9a  jnz     loc_18001A073
0x180019fa0  mov     esi, 1000000h
0x180019fa5  mov     [rbp+0C0h+var_13F], r14b
0x180019fa9  mov     [rbp+0C0h+var_128], rsi
0x180019fad  mov     dword ptr [rbp+0C0h+SRWLock], r15d
0x180019fb1  mov     [rbp+0C0h+var_140], r12b
0x180019fb5  call    cs:__imp_GetCurrentThreadId
0x180019fbc  nop     dword ptr [rax+rax+00h]
0x180019fc1  mov     r8, [rbx+110h]
0x180019fc8  lea     rdx, byte_180068AAF
0x180019fcf  mov     [rbp+0C0h+var_138], eax
0x180019fd2  xor     r9d, r9d
0x180019fd5  mov     rcx, rdi
0x180019fd8  mov     [rbp+0C0h+var_38], 8
0x180019fe3  mov     [rbp+0C0h+var_48], 1
0x180019feb  mov     eax, [r8+48h]
0x180019fef  add     r8, 8
0x180019ff3  mov     [rbp+0C0h+var_13C], eax
0x180019ff6  lea     rax, [rbp+0C0h+var_128]
0x180019ffa  mov     [rbp+0C0h+var_40], rax
0x18001a001  lea     rax, [rbp+0C0h+var_13F]
0x18001a005  mov     [rbp+0C0h+var_50], rax
0x18001a009  lea     rax, [rbp+0C0h+SRWLock]
0x18001a00d  mov     [rbp+0C0h+var_60], rax
0x18001a011  lea     rax, [rbp+0C0h+var_140]
0x18001a015  mov     [rbp+0C0h+var_70], rax
0x18001a019  lea     rax, [rbp+0C0h+var_138]
0x18001a01d  mov     [rbp+0C0h+var_80], rax
0x18001a021  lea     rax, [rbp+0C0h+var_13C]
0x18001a025  mov     [rbp+0C0h+var_90], rax
0x18001a029  lea     rax, [rbp+0C0h+var_110]
0x18001a02d  mov     [rbp+0C0h+var_A0], rax
0x18001a031  lea     rax, [rbp+0C0h+var_C0]
0x18001a035  mov     [rsp+200h+var_1D8], rax
0x18001a03a  mov     dword ptr [rsp+200h+var_1E0], 9
0x18001a042  mov     [rbp+0C0h+var_110], rsi
0x18001a046  mov     [rbp+0C0h+var_58], 4
0x18001a04e  mov     [rbp+0C0h+var_68], 1
0x18001a056  mov     [rbp+0C0h+var_78], 4
0x18001a05e  mov     [rbp+0C0h+var_88], 4
0x18001a066  mov     [rbp+0C0h+var_98], 8
0x18001a06e  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a073  mov     rcx, rbx
0x18001a076  call    ?IgnoreCurrentThread@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001a07b  mov     rcx, [rbp+0C0h+var_30]
0x18001a082  xor     rcx, rsp; StackCookie
0x18001a085  call    __security_check_cookie
0x18001a08a  lea     r11, [rsp+200h+var_20]
0x18001a092  mov     rbx, [r11+38h]
0x18001a096  mov     rsi, [r11+40h]
0x18001a09a  mov     rsp, r11
0x18001a09d  pop     r15
0x18001a09f  pop     r14
0x18001a0a1  pop     r12
0x18001a0a3  pop     rdi
0x18001a0a4  pop     rbp
0x18001a0a5  retn
```
