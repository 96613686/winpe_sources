# NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StopActivity(void)

- ea: `0x18000fb90`
- end: `0x18000fed0`
- name: `?StopActivity@LaunchAdvancedProviderOrderSetting@NetworkLegacyUxTelemetry@@MEAAXXZ`
- size: `832`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001008`
- `0x1800018dc`
- `0x180001f90`
- `0x18000df94`
- `0x18000e970`
- `0x18000fb90`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fd92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fbff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fd92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fdd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fdd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe58`

## string_xrefs

- `0x18000fe73`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting::StopActivity(
        NetworkLegacyUxTelemetry::LaunchAdvancedProviderOrderSetting *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
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
  __int64 v22; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v29; // [rsp+100h] [rbp-20h] BYREF
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
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = NetworkLegacyUxLogging::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v18 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v19 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v20 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v21 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v15 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v17 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v6,
          (unsigned int)&unk_180016228,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v6,
          (__int64)&v17,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v15,
          (__int64)&v28,
          (__int64)&v21,
          (__int64)&v27,
          (__int64)&v20,
          (__int64)&v26,
          (__int64)&v19,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v18,
          (__int64)&v23,
          (__int64)&v22);
      }
    }
  }
  else
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = NetworkLegacyUxLogging::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v15 = *(_DWORD *)(v11 + 72);
        v17 = 0;
        p_SRWLock = &SRWLock;
        v37 = 4;
        v34 = &v15;
        v35 = 4;
        v32 = &v17;
        v33 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, byte_1800161C5, v11 + 8, 0, 5, v31);
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
0x18000fb90  mov     [rsp-8+arg_8], rbx
0x18000fb95  mov     [rsp-8+arg_10], rdi
0x18000fb9a  push    rbp
0x18000fb9b  lea     rbp, [rsp-50h]
0x18000fba0  sub     rsp, 170h
0x18000fba7  mov     rax, cs:__security_cookie
0x18000fbae  xor     rax, rsp
0x18000fbb1  mov     [rbp+50h+var_10], rax
0x18000fbb5  mov     rbx, rcx
0x18000fbb8  mov     rdi, [rcx+110h]
0x18000fbbf  mov     eax, [rdi+48h]
0x18000fbc2  test    eax, eax
0x18000fbc4  jns     loc_18000FD73
0x18000fbca  add     rdi, 50h ; 'P'
0x18000fbce  cmp     eax, [rdi+8]
0x18000fbd1  jnz     loc_18000FD73
0x18000fbd7  test    rdi, rdi
0x18000fbda  jz      loc_18000FD73
0x18000fbe0  lea     rdx, [rbp+50h+SRWLock]
0x18000fbe4  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fbe9  mov     rax, [rbx+110h]
0x18000fbf0  mov     dword ptr [rax], 2
0x18000fbf6  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000fbfa  test    rcx, rcx
0x18000fbfd  jz      short loc_18000FC05
0x18000fbff  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc05  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000fc0a  mov     r9, rax
0x18000fc0d  mov     ecx, [rax]
0x18000fc0f  cmp     ecx, 5
0x18000fc12  jbe     loc_18000FE48
0x18000fc18  mov     rax, [rax+18h]
0x18000fc1c  mov     rcx, [r9+10h]
0x18000fc20  mov     rdx, 400000000000h
0x18000fc2a  test    rdx, rcx
0x18000fc2d  jz      loc_18000FE48
0x18000fc33  mov     rcx, rax
0x18000fc36  and     rcx, rdx
0x18000fc39  cmp     rcx, rax
0x18000fc3c  jnz     loc_18000FE48
0x18000fc42  mov     rax, [rdi+78h]
0x18000fc46  mov     [rbp+50h+var_A8], rax
0x18000fc4a  mov     rax, [rdi+70h]
0x18000fc4e  mov     [rbp+50h+var_A0], rax
0x18000fc52  mov     eax, [rdi+68h]
0x18000fc55  mov     [rbp+50h+var_B8], eax
0x18000fc58  mov     rax, [rdi+60h]
0x18000fc5c  mov     [rbp+50h+var_98], rax
0x18000fc60  mov     rax, [rdi+58h]
0x18000fc64  mov     [rbp+50h+var_90], rax
0x18000fc68  mov     eax, [rdi+50h]
0x18000fc6b  mov     [rbp+50h+var_B4], eax
0x18000fc6e  mov     rax, [rdi+48h]
0x18000fc72  mov     [rbp+50h+var_88], rax
0x18000fc76  mov     eax, [rdi+20h]
0x18000fc79  mov     [rbp+50h+var_B0], eax
0x18000fc7c  mov     rax, [rdi+18h]
0x18000fc80  mov     [rbp+50h+var_80], rax
0x18000fc84  mov     eax, [rdi]
0x18000fc86  mov     [rbp+50h+var_AC], eax
0x18000fc89  mov     rax, [rdi+80h]
0x18000fc90  mov     [rbp+50h+var_78], rax
0x18000fc94  mov     eax, [rdi+40h]
0x18000fc97  mov     [rbp+50h+var_D0], eax
0x18000fc9a  mov     rax, [rdi+38h]
0x18000fc9e  mov     [rbp+50h+var_70], rax
0x18000fca2  mov     eax, [rdi+8]
0x18000fca5  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000fca8  mov     [rbp+50h+var_68], 1000000h
0x18000fcb0  mov     [rbp+50h+var_C0], 0
0x18000fcb8  mov     r8, [rbx+110h]
0x18000fcbf  add     r8, 8
0x18000fcc3  lea     rax, [rbp+50h+var_A8]
0x18000fcc7  mov     [rsp+170h+var_D8], rax
0x18000fccf  lea     rax, [rbp+50h+var_A0]
0x18000fcd3  mov     [rsp+170h+var_E0], rax
0x18000fcdb  lea     rax, [rbp+50h+var_B8]
0x18000fcdf  mov     [rsp+170h+var_E8], rax
0x18000fce7  lea     rax, [rbp+50h+var_98]
0x18000fceb  mov     [rsp+170h+var_F0], rax
0x18000fcf3  lea     rax, [rbp+50h+var_90]
0x18000fcf7  mov     [rsp+170h+var_F8], rax
0x18000fcfc  lea     rax, [rbp+50h+var_B4]
0x18000fd00  mov     [rsp+170h+var_100], rax
0x18000fd05  lea     rax, [rbp+50h+var_88]
0x18000fd09  mov     [rsp+170h+var_108], rax
0x18000fd0e  lea     rax, [rbp+50h+var_B0]
0x18000fd12  mov     [rsp+170h+var_110], rax
0x18000fd17  lea     rax, [rbp+50h+var_80]
0x18000fd1b  mov     [rsp+170h+var_118], rax
0x18000fd20  lea     rax, [rbp+50h+var_AC]
0x18000fd24  mov     [rsp+170h+var_120], rax
0x18000fd29  lea     rax, [rbp+50h+var_78]
0x18000fd2d  mov     [rsp+170h+var_128], rax
0x18000fd32  lea     rax, [rbp+50h+var_D0]
0x18000fd36  mov     [rsp+170h+var_130], rax
0x18000fd3b  lea     rax, [rbp+50h+var_70]
0x18000fd3f  mov     [rsp+170h+var_138], rax
0x18000fd44  lea     rax, [rbp+50h+SRWLock]
0x18000fd48  mov     [rsp+170h+var_140], rax
0x18000fd4d  lea     rax, [rbp+50h+var_68]
0x18000fd51  mov     [rsp+170h+var_148], rax
0x18000fd56  lea     rax, [rbp+50h+var_C0]
0x18000fd5a  mov     [rsp+170h+var_150], rax
0x18000fd5f  lea     rdx, unk_180016228
0x18000fd66  mov     rcx, r9
0x18000fd69  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000fd6e  jmp     loc_18000FE48
0x18000fd73  lea     rdx, [rbp+50h+var_C0]
0x18000fd77  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fd7c  mov     rax, [rbx+110h]
0x18000fd83  mov     dword ptr [rax], 2
0x18000fd89  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000fd8d  test    rcx, rcx
0x18000fd90  jz      short loc_18000FD98
0x18000fd92  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fd98  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000fd9d  mov     rdi, rax
0x18000fda0  mov     ecx, [rax]
0x18000fda2  cmp     ecx, 5
0x18000fda5  jbe     loc_18000FE48
0x18000fdab  mov     rax, [rax+18h]
0x18000fdaf  mov     rcx, [rdi+10h]
0x18000fdb3  mov     rdx, 400000000000h
0x18000fdbd  test    rdx, rcx
0x18000fdc0  jz      loc_18000FE48
0x18000fdc6  mov     rcx, rax
0x18000fdc9  and     rcx, rdx
0x18000fdcc  cmp     rcx, rax
0x18000fdcf  jnz     short loc_18000FE48
0x18000fdd1  call    cs:__imp_GetCurrentThreadId
0x18000fdd7  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000fdda  mov     r8, [rbx+110h]
0x18000fde1  mov     eax, [r8+48h]
0x18000fde5  mov     [rbp+50h+var_D0], eax
0x18000fde8  mov     [rbp+50h+var_C0], 0
0x18000fdf0  lea     rax, [rbp+50h+SRWLock]
0x18000fdf4  mov     [rbp+50h+var_20], rax
0x18000fdf8  mov     [rbp+50h+var_18], 4
0x18000fe00  lea     rax, [rbp+50h+var_D0]
0x18000fe04  mov     [rbp+50h+var_30], rax
0x18000fe08  mov     [rbp+50h+var_28], 4
0x18000fe10  lea     rax, [rbp+50h+var_C0]
0x18000fe14  mov     [rbp+50h+var_40], rax
0x18000fe18  mov     [rbp+50h+var_38], 8
0x18000fe20  add     r8, 8
0x18000fe24  lea     rax, [rbp+50h+var_60]
0x18000fe28  mov     [rsp+170h+var_148], rax
0x18000fe2d  mov     dword ptr [rsp+170h+var_150], 5
0x18000fe35  xor     r9d, r9d
0x18000fe38  lea     rdx, byte_1800161C5
0x18000fe3f  mov     rcx, rdi
0x18000fe42  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fe47  nop
0x18000fe48  cmp     dword ptr [rbx+138h], 0
0x18000fe4f  jz      short loc_18000FEAF
0x18000fe51  add     rbx, 120h
0x18000fe58  call    cs:__imp_GetCurrentThreadId
0x18000fe5e  cmp     [rbx+18h], eax
0x18000fe61  jz      short loc_18000FE7F
0x18000fe63  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000fe6a  test    rax, rax
0x18000fe6d  jz      short loc_18000FE7F
0x18000fe6f  mov     rdx, [rbp+58h]
0x18000fe73  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000fe7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe7f  mov     dword ptr [rbx+18h], 0
0x18000fe86  mov     rcx, [rbx]
0x18000fe89  jmp     short loc_18000FE97
0x18000fe8b  cmp     rax, rbx
0x18000fe8e  jz      short loc_18000FEA1
0x18000fe90  lea     rcx, [rax+10h]
0x18000fe94  mov     [rbx], rcx
0x18000fe97  mov     rax, [rcx]
0x18000fe9a  test    rax, rax
0x18000fe9d  jnz     short loc_18000FE8B
0x18000fe9f  jmp     short loc_18000FEA8
0x18000fea1  mov     rax, [rbx+10h]
0x18000fea5  mov     [rcx], rax
0x18000fea8  mov     qword ptr [rbx], 0
0x18000feaf  mov     rcx, [rbp+50h+var_10]
0x18000feb3  xor     rcx, rsp; StackCookie
0x18000feb6  call    __security_check_cookie
0x18000febb  lea     r11, [rsp+170h+var_s0]
0x18000fec3  mov     rbx, [r11+18h]
0x18000fec7  mov     rdi, [r11+20h]
0x18000fecb  mov     rsp, r11
0x18000fece  pop     rbp
0x18000fecf  retn
```
