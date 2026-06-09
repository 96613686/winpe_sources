# DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StopActivity(void)

- ea: `0x14000d6e0`
- end: `0x14000da1e`
- name: `?StopActivity@DXGIAdapterCacheHealthActivity@DXGIAdapterCacheTelemetry@@MEAAXXZ`
- size: `830`
- prototype: `void __fastcall(DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001008`
- `0x140001bac`
- `0x1400022a0`
- `0x140009e44`
- `0x14000a9b4`
- `0x14000d6e0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d74f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d8df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d74f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d8df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d91e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d9a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d91e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d9a6`

## string_xrefs

- `0x14000d9c1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity::StopActivity(
        DXGIAdapterCacheTelemetry::DXGIAdapterCacheHealthActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+B0h] [rbp-70h] BYREF
  int v18; // [rsp+B8h] [rbp-68h] BYREF
  int v19; // [rsp+BCh] [rbp-64h] BYREF
  int v20; // [rsp+C0h] [rbp-60h] BYREF
  int v21; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 *v22; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-50h] BYREF
  __int64 *v24; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-38h] BYREF
  __int64 *v27; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-20h] BYREF
  __int64 v30; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v31[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]
  void *retaddr; // [rsp+178h] [rbp+58h]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = DXGIAdapterCacheLogging::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v22 = (__int64 *)*((_QWORD *)v4 + 15);
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = (__int64 *)*((_QWORD *)v4 + 12);
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = (__int64 *)*((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&byte_1400152AF,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          &v29,
          (__int64)&v15,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          (__int64)&v19,
          &v25,
          &v24,
          (__int64)&v18,
          &v23,
          &v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = DXGIAdapterCacheLogging::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, byte_140015733, v11 + 8, 0, 5, v31);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x14000d6e0  mov     [rsp-8+arg_8], rbx
0x14000d6e5  mov     [rsp-8+arg_10], rdi
0x14000d6ea  push    rbp
0x14000d6eb  lea     rbp, [rsp-50h]
0x14000d6f0  sub     rsp, 170h
0x14000d6f7  mov     rax, cs:__security_cookie
0x14000d6fe  xor     rax, rsp
0x14000d701  mov     [rbp+50h+var_10], rax
0x14000d705  mov     rbx, rcx
0x14000d708  mov     rdi, [rcx+110h]
0x14000d70f  mov     eax, [rdi+48h]
0x14000d712  test    eax, eax
0x14000d714  jns     loc_14000D8C0
0x14000d71a  add     rdi, 50h ; 'P'
0x14000d71e  cmp     eax, [rdi+8]
0x14000d721  jnz     loc_14000D8C0
0x14000d727  test    rdi, rdi
0x14000d72a  jz      loc_14000D8C0
0x14000d730  lea     rdx, [rbp+50h+SRWLock]
0x14000d734  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000d739  mov     rax, [rbx+110h]
0x14000d740  mov     dword ptr [rax], 2
0x14000d746  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x14000d74a  test    rcx, rcx
0x14000d74d  jz      short loc_14000D755
0x14000d74f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d755  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000d75a  mov     r9, rax
0x14000d75d  mov     ecx, [rax]
0x14000d75f  cmp     ecx, 5
0x14000d762  jbe     loc_14000D996
0x14000d768  mov     rax, [rax+18h]
0x14000d76c  mov     rcx, [r9+10h]
0x14000d770  mov     rdx, 400000000000h
0x14000d77a  test    rdx, rcx
0x14000d77d  jz      loc_14000D996
0x14000d783  mov     rcx, rax
0x14000d786  and     rcx, rdx
0x14000d789  cmp     rcx, rax
0x14000d78c  jnz     loc_14000D996
0x14000d792  mov     rax, [rdi+78h]
0x14000d796  mov     [rbp+50h+var_A8], rax
0x14000d79a  mov     rax, [rdi+70h]
0x14000d79e  mov     [rbp+50h+var_A0], rax
0x14000d7a2  mov     eax, [rdi+68h]
0x14000d7a5  mov     [rbp+50h+var_B8], eax
0x14000d7a8  mov     rax, [rdi+60h]
0x14000d7ac  mov     [rbp+50h+var_98], rax
0x14000d7b0  mov     rax, [rdi+58h]
0x14000d7b4  mov     [rbp+50h+var_90], rax
0x14000d7b8  mov     eax, [rdi+50h]
0x14000d7bb  mov     [rbp+50h+var_B4], eax
0x14000d7be  mov     rax, [rdi+48h]
0x14000d7c2  mov     [rbp+50h+var_88], rax
0x14000d7c6  mov     eax, [rdi+20h]
0x14000d7c9  mov     [rbp+50h+var_B0], eax
0x14000d7cc  mov     rax, [rdi+18h]
0x14000d7d0  mov     [rbp+50h+var_80], rax
0x14000d7d4  mov     eax, [rdi]
0x14000d7d6  mov     [rbp+50h+var_AC], eax
0x14000d7d9  mov     rax, [rdi+80h]
0x14000d7e0  mov     [rbp+50h+var_78], rax
0x14000d7e4  mov     eax, [rdi+40h]
0x14000d7e7  mov     [rbp+50h+var_D0], eax
0x14000d7ea  mov     rax, [rdi+38h]
0x14000d7ee  mov     [rbp+50h+var_70], rax
0x14000d7f2  mov     eax, [rdi+8]
0x14000d7f5  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000d7f8  mov     eax, 1000000h
0x14000d7fd  mov     [rbp+50h+var_68], rax
0x14000d801  mov     [rbp+50h+var_C0], rax
0x14000d805  mov     r8, [rbx+110h]
0x14000d80c  add     r8, 8
0x14000d810  lea     rax, [rbp+50h+var_A8]
0x14000d814  mov     [rsp+170h+var_D8], rax
0x14000d81c  lea     rax, [rbp+50h+var_A0]
0x14000d820  mov     [rsp+170h+var_E0], rax
0x14000d828  lea     rax, [rbp+50h+var_B8]
0x14000d82c  mov     [rsp+170h+var_E8], rax
0x14000d834  lea     rax, [rbp+50h+var_98]
0x14000d838  mov     [rsp+170h+var_F0], rax
0x14000d840  lea     rax, [rbp+50h+var_90]
0x14000d844  mov     [rsp+170h+var_F8], rax
0x14000d849  lea     rax, [rbp+50h+var_B4]
0x14000d84d  mov     [rsp+170h+var_100], rax
0x14000d852  lea     rax, [rbp+50h+var_88]
0x14000d856  mov     [rsp+170h+var_108], rax
0x14000d85b  lea     rax, [rbp+50h+var_B0]
0x14000d85f  mov     [rsp+170h+var_110], rax
0x14000d864  lea     rax, [rbp+50h+var_80]
0x14000d868  mov     [rsp+170h+var_118], rax
0x14000d86d  lea     rax, [rbp+50h+var_AC]
0x14000d871  mov     [rsp+170h+var_120], rax
0x14000d876  lea     rax, [rbp+50h+var_78]
0x14000d87a  mov     [rsp+170h+var_128], rax
0x14000d87f  lea     rax, [rbp+50h+var_D0]
0x14000d883  mov     [rsp+170h+var_130], rax
0x14000d888  lea     rax, [rbp+50h+var_70]
0x14000d88c  mov     [rsp+170h+var_138], rax
0x14000d891  lea     rax, [rbp+50h+SRWLock]
0x14000d895  mov     [rsp+170h+var_140], rax
0x14000d89a  lea     rax, [rbp+50h+var_68]
0x14000d89e  mov     [rsp+170h+var_148], rax
0x14000d8a3  lea     rax, [rbp+50h+var_C0]
0x14000d8a7  mov     [rsp+170h+var_150], rax
0x14000d8ac  lea     rdx, byte_1400152AF
0x14000d8b3  mov     rcx, r9
0x14000d8b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000d8bb  jmp     loc_14000D996
0x14000d8c0  lea     rdx, [rbp+50h+var_C0]
0x14000d8c4  call    ?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000d8c9  mov     rax, [rbx+110h]
0x14000d8d0  mov     dword ptr [rax], 2
0x14000d8d6  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x14000d8da  test    rcx, rcx
0x14000d8dd  jz      short loc_14000D8E5
0x14000d8df  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d8e5  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x14000d8ea  mov     rdi, rax
0x14000d8ed  mov     ecx, [rax]
0x14000d8ef  cmp     ecx, 5
0x14000d8f2  jbe     loc_14000D996
0x14000d8f8  mov     rax, [rax+18h]
0x14000d8fc  mov     rcx, [rdi+10h]
0x14000d900  mov     rdx, 400000000000h
0x14000d90a  test    rdx, rcx
0x14000d90d  jz      loc_14000D996
0x14000d913  mov     rcx, rax
0x14000d916  and     rcx, rdx
0x14000d919  cmp     rcx, rax
0x14000d91c  jnz     short loc_14000D996
0x14000d91e  call    cs:__imp_GetCurrentThreadId
0x14000d924  mov     dword ptr [rbp+50h+SRWLock], eax
0x14000d927  mov     r8, [rbx+110h]
0x14000d92e  mov     eax, [r8+48h]
0x14000d932  mov     [rbp+50h+var_D0], eax
0x14000d935  mov     eax, 1000000h
0x14000d93a  mov     [rbp+50h+var_C0], rax
0x14000d93e  lea     rax, [rbp+50h+SRWLock]
0x14000d942  mov     [rbp+50h+var_20], rax
0x14000d946  mov     [rbp+50h+var_18], 4
0x14000d94e  lea     rax, [rbp+50h+var_D0]
0x14000d952  mov     [rbp+50h+var_30], rax
0x14000d956  mov     [rbp+50h+var_28], 4
0x14000d95e  lea     rax, [rbp+50h+var_C0]
0x14000d962  mov     [rbp+50h+var_40], rax
0x14000d966  mov     [rbp+50h+var_38], 8
0x14000d96e  add     r8, 8
0x14000d972  lea     rax, [rbp+50h+var_60]
0x14000d976  mov     [rsp+170h+var_148], rax
0x14000d97b  mov     dword ptr [rsp+170h+var_150], 5
0x14000d983  xor     r9d, r9d
0x14000d986  lea     rdx, byte_140015733
0x14000d98d  mov     rcx, rdi
0x14000d990  call    _tlgWriteTransfer_EventWriteTransfer
0x14000d995  nop
0x14000d996  cmp     dword ptr [rbx+138h], 0
0x14000d99d  jz      short loc_14000D9FD
0x14000d99f  add     rbx, 120h
0x14000d9a6  call    cs:__imp_GetCurrentThreadId
0x14000d9ac  cmp     [rbx+18h], eax
0x14000d9af  jz      short loc_14000D9CD
0x14000d9b1  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000d9b8  test    rax, rax
0x14000d9bb  jz      short loc_14000D9CD
0x14000d9bd  mov     rdx, [rbp+58h]
0x14000d9c1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000d9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9cd  mov     dword ptr [rbx+18h], 0
0x14000d9d4  mov     rcx, [rbx]
0x14000d9d7  jmp     short loc_14000D9E5
0x14000d9d9  cmp     rax, rbx
0x14000d9dc  jz      short loc_14000D9EF
0x14000d9de  lea     rcx, [rax+10h]
0x14000d9e2  mov     [rbx], rcx
0x14000d9e5  mov     rax, [rcx]
0x14000d9e8  test    rax, rax
0x14000d9eb  jnz     short loc_14000D9D9
0x14000d9ed  jmp     short loc_14000D9F6
0x14000d9ef  mov     rax, [rbx+10h]
0x14000d9f3  mov     [rcx], rax
0x14000d9f6  mov     qword ptr [rbx], 0
0x14000d9fd  mov     rcx, [rbp+50h+var_10]
0x14000da01  xor     rcx, rsp; StackCookie
0x14000da04  call    __security_check_cookie
0x14000da09  lea     r11, [rsp+170h+var_s0]
0x14000da11  mov     rbx, [r11+18h]
0x14000da15  mov     rdi, [r11+20h]
0x14000da19  mov     rsp, r11
0x14000da1c  pop     rbp
0x14000da1d  retn
```
