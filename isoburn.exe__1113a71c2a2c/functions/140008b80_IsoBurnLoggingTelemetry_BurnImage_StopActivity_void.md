# IsoBurnLoggingTelemetry::BurnImage::StopActivity(void)

- ea: `0x140008b80`
- end: `0x140008ebf`
- name: `?StopActivity@BurnImage@IsoBurnLoggingTelemetry@@MEAAXXZ`
- size: `831`
- prototype: `void __fastcall(IsoBurnLoggingTelemetry::BurnImage *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001008`
- `0x1400018dc`
- `0x140001fa0`
- `0x140006c34`
- `0x140007610`
- `0x140008b80`
- `0x140010010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008bef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008d82`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008bef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008d82`
- `KERNEL32!GetCurrentThreadId` at `0x140008dc1`
- `KERNEL32!GetCurrentThreadId` at `0x140008e47`
- `KERNEL32!GetCurrentThreadId` at `0x140008dc1`
- `KERNEL32!GetCurrentThreadId` at `0x140008e47`

## string_xrefs

- `0x140008e62`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall IsoBurnLoggingTelemetry::BurnImage::StopActivity(IsoBurnLoggingTelemetry::BurnImage *this)
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
  char *v16; // rbx
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v21; // [rsp+B0h] [rbp-70h] BYREF
  int v22; // [rsp+B8h] [rbp-68h] BYREF
  int v23; // [rsp+BCh] [rbp-64h] BYREF
  int v24; // [rsp+C0h] [rbp-60h] BYREF
  int v25; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 v26; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v33; // [rsp+100h] [rbp-20h] BYREF
  __int64 v34; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v35[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v36; // [rsp+130h] [rbp+10h]
  __int64 v37; // [rsp+138h] [rbp+18h]
  int *v38; // [rsp+140h] [rbp+20h]
  __int64 v39; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v41; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = IsoBurnLoggingProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v26 = *((_QWORD *)v4 + 15);
        v27 = *((_QWORD *)v4 + 14);
        v22 = v4[26];
        v28 = *((_QWORD *)v4 + 12);
        v29 = *((_QWORD *)v4 + 11);
        v23 = v4[20];
        v30 = *((_QWORD *)v4 + 9);
        v24 = v4[8];
        v31 = *((_QWORD *)v4 + 3);
        v25 = *v4;
        v32 = *((_QWORD *)v4 + 16);
        v19 = v4[16];
        v33 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v34 = 0x1000000;
        v21 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&word_1400134AE,
          v9 + 8,
          (_DWORD)v7,
          (__int64)&v21,
          (__int64)&v34,
          (__int64)&SRWLock,
          (__int64)&v33,
          (__int64)&v19,
          (__int64)&v32,
          (__int64)&v25,
          (__int64)&v31,
          (__int64)&v24,
          (__int64)&v30,
          (__int64)&v23,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v22,
          (__int64)&v27,
          (__int64)&v26);
      }
    }
  }
  else
  {
    wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v21);
    v10 = v21;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = IsoBurnLoggingProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v41 = 4;
        v39 = 4;
        v19 = *(_DWORD *)(v15 + 72);
        p_SRWLock = &SRWLock;
        v38 = &v19;
        v36 = &v21;
        v21 = 0;
        v37 = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, &dword_140013464, v15 + 8, 0, 5, v35);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v16 = (char *)this + 288;
    if ( *((_DWORD *)v16 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v17 = *(__int64 **)v16;
    *((_DWORD *)v16 + 6) = 0;
    while ( 1 )
    {
      v18 = *v17;
      if ( !*v17 )
        break;
      if ( (char *)v18 == v16 )
      {
        *v17 = *((_QWORD *)v16 + 2);
        break;
      }
      v17 = (__int64 *)(v18 + 16);
      *(_QWORD *)v16 = v18 + 16;
    }
    *(_QWORD *)v16 = 0;
  }
}

```

## disassembly

```asm
0x140008b80  mov     [rsp-8+arg_8], rbx
0x140008b85  mov     [rsp-8+arg_10], rdi
0x140008b8a  push    rbp
0x140008b8b  lea     rbp, [rsp-50h]
0x140008b90  sub     rsp, 170h
0x140008b97  mov     rax, cs:__security_cookie
0x140008b9e  xor     rax, rsp
0x140008ba1  mov     [rbp+50h+var_10], rax
0x140008ba5  mov     rdi, [rcx+110h]
0x140008bac  mov     rbx, rcx
0x140008baf  mov     eax, [rdi+48h]
0x140008bb2  test    eax, eax
0x140008bb4  jns     loc_140008D63
0x140008bba  add     rdi, 50h ; 'P'
0x140008bbe  cmp     eax, [rdi+8]
0x140008bc1  jnz     loc_140008D63
0x140008bc7  test    rdi, rdi
0x140008bca  jz      loc_140008D63
0x140008bd0  lea     rdx, [rbp+50h+SRWLock]
0x140008bd4  call    ?LockExclusive@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008bd9  mov     rax, [rbx+110h]
0x140008be0  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x140008be4  mov     dword ptr [rax], 2
0x140008bea  test    rcx, rcx
0x140008bed  jz      short loc_140008BF5
0x140008bef  call    cs:__imp_ReleaseSRWLockExclusive
0x140008bf5  call    ?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; IsoBurnLoggingProvider::Provider(void)
0x140008bfa  mov     r9, rax
0x140008bfd  mov     ecx, [rax]
0x140008bff  cmp     ecx, 5
0x140008c02  jbe     loc_140008E37
0x140008c08  mov     rax, [rax+18h]
0x140008c0c  mov     rdx, 200000000000h
0x140008c16  mov     rcx, [r9+10h]
0x140008c1a  test    rdx, rcx
0x140008c1d  jz      loc_140008E37
0x140008c23  mov     rcx, rax
0x140008c26  and     rcx, rdx
0x140008c29  cmp     rcx, rax
0x140008c2c  jnz     loc_140008E37
0x140008c32  mov     rax, [rdi+78h]
0x140008c36  lea     rdx, word_1400134AE
0x140008c3d  mov     r8, [rbx+110h]
0x140008c44  mov     rcx, r9
0x140008c47  mov     [rbp+50h+var_A8], rax
0x140008c4b  add     r8, 8
0x140008c4f  mov     rax, [rdi+70h]
0x140008c53  mov     [rbp+50h+var_A0], rax
0x140008c57  mov     eax, [rdi+68h]
0x140008c5a  mov     [rbp+50h+var_B8], eax
0x140008c5d  mov     rax, [rdi+60h]
0x140008c61  mov     [rbp+50h+var_98], rax
0x140008c65  mov     rax, [rdi+58h]
0x140008c69  mov     [rbp+50h+var_90], rax
0x140008c6d  mov     eax, [rdi+50h]
0x140008c70  mov     [rbp+50h+var_B4], eax
0x140008c73  mov     rax, [rdi+48h]
0x140008c77  mov     [rbp+50h+var_88], rax
0x140008c7b  mov     eax, [rdi+20h]
0x140008c7e  mov     [rbp+50h+var_B0], eax
0x140008c81  mov     rax, [rdi+18h]
0x140008c85  mov     [rbp+50h+var_80], rax
0x140008c89  mov     eax, [rdi]
0x140008c8b  mov     [rbp+50h+var_AC], eax
0x140008c8e  mov     rax, [rdi+80h]
0x140008c95  mov     [rbp+50h+var_78], rax
0x140008c99  mov     eax, [rdi+40h]
0x140008c9c  mov     [rbp+50h+var_D0], eax
0x140008c9f  mov     rax, [rdi+38h]
0x140008ca3  mov     [rbp+50h+var_70], rax
0x140008ca7  mov     eax, [rdi+8]
0x140008caa  mov     dword ptr [rbp+50h+SRWLock], eax
0x140008cad  lea     rax, [rbp+50h+var_A8]
0x140008cb1  mov     [rsp+170h+var_D8], rax
0x140008cb9  lea     rax, [rbp+50h+var_A0]
0x140008cbd  mov     [rsp+170h+var_E0], rax
0x140008cc5  lea     rax, [rbp+50h+var_B8]
0x140008cc9  mov     [rsp+170h+var_E8], rax
0x140008cd1  lea     rax, [rbp+50h+var_98]
0x140008cd5  mov     [rsp+170h+var_F0], rax
0x140008cdd  lea     rax, [rbp+50h+var_90]
0x140008ce1  mov     [rsp+170h+var_F8], rax
0x140008ce6  lea     rax, [rbp+50h+var_B4]
0x140008cea  mov     [rsp+170h+var_100], rax
0x140008cef  lea     rax, [rbp+50h+var_88]
0x140008cf3  mov     [rsp+170h+var_108], rax
0x140008cf8  lea     rax, [rbp+50h+var_B0]
0x140008cfc  mov     [rsp+170h+var_110], rax
0x140008d01  lea     rax, [rbp+50h+var_80]
0x140008d05  mov     [rsp+170h+var_118], rax
0x140008d0a  lea     rax, [rbp+50h+var_AC]
0x140008d0e  mov     [rsp+170h+var_120], rax
0x140008d13  lea     rax, [rbp+50h+var_78]
0x140008d17  mov     [rsp+170h+var_128], rax
0x140008d1c  lea     rax, [rbp+50h+var_D0]
0x140008d20  mov     [rsp+170h+var_130], rax
0x140008d25  lea     rax, [rbp+50h+var_70]
0x140008d29  mov     [rsp+170h+var_138], rax
0x140008d2e  lea     rax, [rbp+50h+SRWLock]
0x140008d32  mov     [rsp+170h+var_140], rax
0x140008d37  lea     rax, [rbp+50h+var_68]
0x140008d3b  mov     [rsp+170h+var_148], rax
0x140008d40  lea     rax, [rbp+50h+var_C0]
0x140008d44  mov     [rsp+170h+var_150], rax
0x140008d49  mov     [rbp+50h+var_68], 1000000h
0x140008d51  mov     [rbp+50h+var_C0], 0
0x140008d59  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140008d5e  jmp     loc_140008E37
0x140008d63  lea     rdx, [rbp+50h+var_C0]
0x140008d67  call    ?LockExclusive@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008d6c  mov     rax, [rbx+110h]
0x140008d73  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x140008d77  mov     dword ptr [rax], 2
0x140008d7d  test    rcx, rcx
0x140008d80  jz      short loc_140008D88
0x140008d82  call    cs:__imp_ReleaseSRWLockExclusive
0x140008d88  call    ?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; IsoBurnLoggingProvider::Provider(void)
0x140008d8d  mov     rdi, rax
0x140008d90  mov     ecx, [rax]
0x140008d92  cmp     ecx, 5
0x140008d95  jbe     loc_140008E37
0x140008d9b  mov     rax, [rax+18h]
0x140008d9f  mov     rdx, 200000000000h
0x140008da9  mov     rcx, [rdi+10h]
0x140008dad  test    rdx, rcx
0x140008db0  jz      loc_140008E37
0x140008db6  mov     rcx, rax
0x140008db9  and     rcx, rdx
0x140008dbc  cmp     rcx, rax
0x140008dbf  jnz     short loc_140008E37
0x140008dc1  call    cs:__imp_GetCurrentThreadId
0x140008dc7  mov     r8, [rbx+110h]
0x140008dce  lea     rdx, dword_140013464
0x140008dd5  mov     dword ptr [rbp+50h+SRWLock], eax
0x140008dd8  xor     r9d, r9d
0x140008ddb  mov     rcx, rdi
0x140008dde  mov     [rbp+50h+var_18], 4
0x140008de6  mov     [rbp+50h+var_28], 4
0x140008dee  mov     eax, [r8+48h]
0x140008df2  add     r8, 8
0x140008df6  mov     [rbp+50h+var_D0], eax
0x140008df9  lea     rax, [rbp+50h+SRWLock]
0x140008dfd  mov     [rbp+50h+var_20], rax
0x140008e01  lea     rax, [rbp+50h+var_D0]
0x140008e05  mov     [rbp+50h+var_30], rax
0x140008e09  lea     rax, [rbp+50h+var_C0]
0x140008e0d  mov     [rbp+50h+var_40], rax
0x140008e11  lea     rax, [rbp+50h+var_60]
0x140008e15  mov     [rsp+170h+var_148], rax
0x140008e1a  mov     dword ptr [rsp+170h+var_150], 5
0x140008e22  mov     [rbp+50h+var_C0], 0
0x140008e2a  mov     [rbp+50h+var_38], 8
0x140008e32  call    _tlgWriteTransfer_EventWriteTransfer
0x140008e37  cmp     dword ptr [rbx+138h], 0
0x140008e3e  jz      short loc_140008E9E
0x140008e40  add     rbx, 120h
0x140008e47  call    cs:__imp_GetCurrentThreadId
0x140008e4d  cmp     [rbx+18h], eax
0x140008e50  jz      short loc_140008E6E
0x140008e52  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140008e59  test    rax, rax
0x140008e5c  jz      short loc_140008E6E
0x140008e5e  mov     rdx, [rbp+58h]
0x140008e62  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140008e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e6e  mov     rcx, [rbx]
0x140008e71  mov     dword ptr [rbx+18h], 0
0x140008e78  jmp     short loc_140008E86
0x140008e7a  cmp     rax, rbx
0x140008e7d  jz      short loc_140008E90
0x140008e7f  lea     rcx, [rax+10h]
0x140008e83  mov     [rbx], rcx
0x140008e86  mov     rax, [rcx]
0x140008e89  test    rax, rax
0x140008e8c  jnz     short loc_140008E7A
0x140008e8e  jmp     short loc_140008E97
0x140008e90  mov     rax, [rbx+10h]
0x140008e94  mov     [rcx], rax
0x140008e97  mov     qword ptr [rbx], 0
0x140008e9e  mov     rcx, [rbp+50h+var_10]
0x140008ea2  xor     rcx, rsp; StackCookie
0x140008ea5  call    __security_check_cookie
0x140008eaa  lea     r11, [rsp+170h+var_s0]
0x140008eb2  mov     rbx, [r11+18h]
0x140008eb6  mov     rdi, [r11+20h]
0x140008eba  mov     rsp, r11
0x140008ebd  pop     rbp
0x140008ebe  retn
```
