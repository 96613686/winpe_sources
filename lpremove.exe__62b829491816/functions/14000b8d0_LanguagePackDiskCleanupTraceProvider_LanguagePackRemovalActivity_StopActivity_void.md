# LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::StopActivity(void)

- ea: `0x14000b8d0`
- end: `0x14000bc13`
- name: `?StopActivity@LanguagePackRemovalActivity@LanguagePackDiskCleanupTraceProvider@@MEAAXXZ`
- size: `835`
- prototype: `void __fastcall(LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001008`
- `0x140001b9c`
- `0x140002190`
- `0x140007eac`
- `0x1400084b8`
- `0x14000b8d0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000bb14`
- `KERNEL32!GetCurrentThreadId` at `0x14000bb9b`
- `KERNEL32!GetCurrentThreadId` at `0x14000bb14`
- `KERNEL32!GetCurrentThreadId` at `0x14000bb9b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b93f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000bad4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000b93f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000bad4`

## string_xrefs

- `0x14000bbb6`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity::StopActivity(
        LanguagePackDiskCleanupTraceProvider::LanguagePackRemovalActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  char *v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v13; // [rsp+B0h] [rbp-70h] BYREF
  int v14; // [rsp+B8h] [rbp-68h] BYREF
  int v15; // [rsp+BCh] [rbp-64h] BYREF
  int v16; // [rsp+C0h] [rbp-60h] BYREF
  int v17; // [rsp+C4h] [rbp-5Ch] BYREF
  int *v18; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+D0h] [rbp-50h] BYREF
  int *v20; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v21; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+E8h] [rbp-38h] BYREF
  int *v23; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v24; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v25; // [rsp+100h] [rbp-20h] BYREF
  __int64 v26; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v27[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v28; // [rsp+130h] [rbp+10h]
  __int64 v29; // [rsp+138h] [rbp+18h]
  int *v30; // [rsp+140h] [rbp+20h]
  __int64 v31; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v33; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x200000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v18 = (int *)*((_QWORD *)v4 + 15);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v14 = v4[26];
      v20 = (int *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v15 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v16 = v4[8];
      v23 = (int *)*((_QWORD *)v4 + 3);
      v17 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v11 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v26 = 0x1000000;
      v13 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_140014625,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)&v13,
        (__int64)&v26,
        (__int64)&SRWLock,
        &v25,
        (__int64)&v11,
        &v24,
        (__int64)&v17,
        &v23,
        (__int64)&v16,
        &v22,
        (__int64)&v15,
        &v21,
        &v20,
        (__int64)&v14,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v13);
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v6 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v11 = *(_DWORD *)(v7 + 72);
      v13 = 0;
      p_SRWLock = &SRWLock;
      v33 = 4;
      v30 = &v11;
      v31 = 4;
      v28 = &v13;
      v29 = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, byte_1400145C9, v7 + 8, 0, 5, v27);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( *((_DWORD *)v8 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v8 + 6) = 0;
    v9 = *(__int64 **)v8;
    while ( 1 )
    {
      v10 = *v9;
      if ( !*v9 )
        break;
      if ( (char *)v10 == v8 )
      {
        *v9 = *((_QWORD *)v8 + 2);
        break;
      }
      v9 = (__int64 *)(v10 + 16);
      *(_QWORD *)v8 = v10 + 16;
    }
    *(_QWORD *)v8 = 0;
  }
}

```

## disassembly

```asm
0x14000b8d0  mov     [rsp-8+arg_8], rbx
0x14000b8d5  mov     [rsp-8+arg_10], rdi
0x14000b8da  push    rbp
0x14000b8db  lea     rbp, [rsp-50h]
0x14000b8e0  sub     rsp, 170h
0x14000b8e7  mov     rax, cs:__security_cookie
0x14000b8ee  xor     rax, rsp
0x14000b8f1  mov     [rbp+50h+var_10], rax
0x14000b8f5  mov     rbx, rcx
0x14000b8f8  mov     rdi, [rcx+110h]
0x14000b8ff  mov     eax, [rdi+48h]
0x14000b902  test    eax, eax
0x14000b904  jns     loc_14000BAB5
0x14000b90a  add     rdi, 50h ; 'P'
0x14000b90e  cmp     eax, [rdi+8]
0x14000b911  jnz     loc_14000BAB5
0x14000b917  test    rdi, rdi
0x14000b91a  jz      loc_14000BAB5
0x14000b920  lea     rdx, [rbp+50h+SRWLock]
0x14000b924  call    ?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b929  mov     rax, [rbx+110h]
0x14000b930  mov     dword ptr [rax], 2
0x14000b936  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x14000b93a  test    rcx, rcx
0x14000b93d  jz      short loc_14000B945
0x14000b93f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b945  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000b94a  mov     r9, [rax+8]
0x14000b94e  mov     eax, [r9]
0x14000b951  cmp     eax, 5
0x14000b954  jbe     loc_14000BB8B
0x14000b95a  mov     rdx, [r9+18h]
0x14000b95e  mov     rax, [r9+10h]
0x14000b962  mov     rcx, 200000000000h
0x14000b96c  test    rcx, rax
0x14000b96f  jz      loc_14000BB8B
0x14000b975  mov     rax, rdx
0x14000b978  and     rax, rcx
0x14000b97b  cmp     rax, rdx
0x14000b97e  jnz     loc_14000BB8B
0x14000b984  mov     rax, [rdi+78h]
0x14000b988  mov     [rbp+50h+var_A8], rax
0x14000b98c  mov     rax, [rdi+70h]
0x14000b990  mov     [rbp+50h+var_A0], rax
0x14000b994  mov     eax, [rdi+68h]
0x14000b997  mov     [rbp+50h+var_B8], eax
0x14000b99a  mov     rax, [rdi+60h]
0x14000b99e  mov     [rbp+50h+var_98], rax
0x14000b9a2  mov     rax, [rdi+58h]
0x14000b9a6  mov     [rbp+50h+var_90], rax
0x14000b9aa  mov     eax, [rdi+50h]
0x14000b9ad  mov     [rbp+50h+var_B4], eax
0x14000b9b0  mov     rax, [rdi+48h]
0x14000b9b4  mov     [rbp+50h+var_88], rax
0x14000b9b8  mov     eax, [rdi+20h]
0x14000b9bb  mov     [rbp+50h+var_B0], eax
0x14000b9be  mov     rax, [rdi+18h]
0x14000b9c2  mov     [rbp+50h+var_80], rax
0x14000b9c6  mov     eax, [rdi]
0x14000b9c8  mov     [rbp+50h+var_AC], eax
0x14000b9cb  mov     rax, [rdi+80h]
0x14000b9d2  mov     [rbp+50h+var_78], rax
0x14000b9d6  mov     eax, [rdi+40h]
0x14000b9d9  mov     [rbp+50h+var_D0], eax
0x14000b9dc  mov     rax, [rdi+38h]
0x14000b9e0  mov     [rbp+50h+var_70], rax
0x14000b9e4  mov     eax, [rdi+8]
0x14000b9e7  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000b9ea  mov     [rbp+50h+var_68], 1000000h
0x14000b9f2  mov     [rbp+50h+var_C0], 0
0x14000b9fa  mov     r8, [rbx+110h]
0x14000ba01  add     r8, 8
0x14000ba05  lea     rax, [rbp+50h+var_A8]
0x14000ba09  mov     [rsp+170h+var_D8], rax
0x14000ba11  lea     rax, [rbp+50h+var_A0]
0x14000ba15  mov     [rsp+170h+var_E0], rax
0x14000ba1d  lea     rax, [rbp+50h+var_B8]
0x14000ba21  mov     [rsp+170h+var_E8], rax
0x14000ba29  lea     rax, [rbp+50h+var_98]
0x14000ba2d  mov     [rsp+170h+var_F0], rax
0x14000ba35  lea     rax, [rbp+50h+var_90]
0x14000ba39  mov     [rsp+170h+var_F8], rax
0x14000ba3e  lea     rax, [rbp+50h+var_B4]
0x14000ba42  mov     [rsp+170h+var_100], rax
0x14000ba47  lea     rax, [rbp+50h+var_88]
0x14000ba4b  mov     [rsp+170h+var_108], rax
0x14000ba50  lea     rax, [rbp+50h+var_B0]
0x14000ba54  mov     [rsp+170h+var_110], rax
0x14000ba59  lea     rax, [rbp+50h+var_80]
0x14000ba5d  mov     [rsp+170h+var_118], rax
0x14000ba62  lea     rax, [rbp+50h+var_AC]
0x14000ba66  mov     [rsp+170h+var_120], rax
0x14000ba6b  lea     rax, [rbp+50h+var_78]
0x14000ba6f  mov     [rsp+170h+var_128], rax
0x14000ba74  lea     rax, [rbp+50h+var_D0]
0x14000ba78  mov     [rsp+170h+var_130], rax
0x14000ba7d  lea     rax, [rbp+50h+var_70]
0x14000ba81  mov     [rsp+170h+var_138], rax
0x14000ba86  lea     rax, [rbp+50h+SRWLock]
0x14000ba8a  mov     [rsp+170h+var_140], rax
0x14000ba8f  lea     rax, [rbp+50h+var_68]
0x14000ba93  mov     [rsp+170h+var_148], rax
0x14000ba98  lea     rax, [rbp+50h+var_C0]
0x14000ba9c  mov     [rsp+170h+var_150], rax
0x14000baa1  lea     rdx, byte_140014625
0x14000baa8  mov     rcx, r9
0x14000baab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000bab0  jmp     loc_14000BB8B
0x14000bab5  lea     rdx, [rbp+50h+var_C0]
0x14000bab9  call    ?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000babe  mov     rax, [rbx+110h]
0x14000bac5  mov     dword ptr [rax], 2
0x14000bacb  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x14000bacf  test    rcx, rcx
0x14000bad2  jz      short loc_14000BADA
0x14000bad4  call    cs:__imp_ReleaseSRWLockExclusive
0x14000bada  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000badf  mov     rdi, [rax+8]
0x14000bae3  mov     eax, [rdi]
0x14000bae5  cmp     eax, 5
0x14000bae8  jbe     loc_14000BB8B
0x14000baee  mov     rdx, [rdi+18h]
0x14000baf2  mov     rax, [rdi+10h]
0x14000baf6  mov     rcx, 200000000000h
0x14000bb00  test    rcx, rax
0x14000bb03  jz      loc_14000BB8B
0x14000bb09  mov     rax, rdx
0x14000bb0c  and     rax, rcx
0x14000bb0f  cmp     rax, rdx
0x14000bb12  jnz     short loc_14000BB8B
0x14000bb14  call    cs:__imp_GetCurrentThreadId
0x14000bb1a  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000bb1d  mov     r8, [rbx+110h]
0x14000bb24  mov     eax, [r8+48h]
0x14000bb28  mov     [rbp+50h+var_D0], eax
0x14000bb2b  mov     [rbp+50h+var_C0], 0
0x14000bb33  lea     rax, [rbp+50h+SRWLock]
0x14000bb37  mov     [rbp+50h+var_20], rax
0x14000bb3b  mov     [rbp+50h+var_18], 4
0x14000bb43  lea     rax, [rbp+50h+var_D0]
0x14000bb47  mov     [rbp+50h+var_30], rax
0x14000bb4b  mov     [rbp+50h+var_28], 4
0x14000bb53  lea     rax, [rbp+50h+var_C0]
0x14000bb57  mov     [rbp+50h+var_40], rax
0x14000bb5b  mov     [rbp+50h+var_38], 8
0x14000bb63  add     r8, 8
0x14000bb67  lea     rax, [rbp+50h+var_60]
0x14000bb6b  mov     [rsp+170h+var_148], rax
0x14000bb70  mov     dword ptr [rsp+170h+var_150], 5
0x14000bb78  xor     r9d, r9d
0x14000bb7b  lea     rdx, byte_1400145C9
0x14000bb82  mov     rcx, rdi
0x14000bb85  call    _tlgWriteTransfer_EventWriteTransfer
0x14000bb8a  nop
0x14000bb8b  cmp     dword ptr [rbx+138h], 0
0x14000bb92  jz      short loc_14000BBF2
0x14000bb94  add     rbx, 120h
0x14000bb9b  call    cs:__imp_GetCurrentThreadId
0x14000bba1  cmp     [rbx+18h], eax
0x14000bba4  jz      short loc_14000BBC2
0x14000bba6  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000bbad  test    rax, rax
0x14000bbb0  jz      short loc_14000BBC2
0x14000bbb2  mov     rdx, [rbp+58h]
0x14000bbb6  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000bbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbc2  mov     dword ptr [rbx+18h], 0
0x14000bbc9  mov     rcx, [rbx]
0x14000bbcc  jmp     short loc_14000BBDA
0x14000bbce  cmp     rax, rbx
0x14000bbd1  jz      short loc_14000BBE4
0x14000bbd3  lea     rcx, [rax+10h]
0x14000bbd7  mov     [rbx], rcx
0x14000bbda  mov     rax, [rcx]
0x14000bbdd  test    rax, rax
0x14000bbe0  jnz     short loc_14000BBCE
0x14000bbe2  jmp     short loc_14000BBEB
0x14000bbe4  mov     rax, [rbx+10h]
0x14000bbe8  mov     [rcx], rax
0x14000bbeb  mov     qword ptr [rbx], 0
0x14000bbf2  mov     rcx, [rbp+50h+var_10]
0x14000bbf6  xor     rcx, rsp; StackCookie
0x14000bbf9  call    __security_check_cookie
0x14000bbfe  lea     r11, [rsp+170h+var_s0]
0x14000bc06  mov     rbx, [r11+18h]
0x14000bc0a  mov     rdi, [r11+20h]
0x14000bc0e  mov     rsp, r11
0x14000bc11  pop     rbp
0x14000bc12  retn
```
