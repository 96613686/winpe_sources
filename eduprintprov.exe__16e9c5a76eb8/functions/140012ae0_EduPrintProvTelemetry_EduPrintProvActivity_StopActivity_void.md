# EduPrintProvTelemetry::EduPrintProvActivity::StopActivity(void)

- ea: `0x140012ae0`
- end: `0x140012e20`
- name: `?StopActivity@EduPrintProvActivity@EduPrintProvTelemetry@@MEAAXXZ`
- size: `832`
- prototype: `void __fastcall(EduPrintProvTelemetry::EduPrintProvActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400010b0`
- `0x1400016dc`
- `0x140002600`
- `0x14000cfac`
- `0x140012014`
- `0x140012ae0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012b4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012ce2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012b4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140012ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012d21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012da8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012d21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012da8`

## string_xrefs

- `0x140012dc3`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EduPrintProvTelemetry::EduPrintProvActivity::StopActivity(
        EduPrintProvTelemetry::EduPrintProvActivity *this)
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
    wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = EduPrintProvLogging::Provider();
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
          (unsigned int)byte_140018251,
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
    wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v8 = EduPrintProvLogging::Provider();
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
        tlgWriteTransfer_EventWriteTransfer(v9, byte_14001837D, v11 + 8, 0, 5, v31);
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
0x140012ae0  mov     [rsp-8+arg_8], rbx
0x140012ae5  mov     [rsp-8+arg_10], rdi
0x140012aea  push    rbp
0x140012aeb  lea     rbp, [rsp-50h]
0x140012af0  sub     rsp, 170h
0x140012af7  mov     rax, cs:__security_cookie
0x140012afe  xor     rax, rsp
0x140012b01  mov     [rbp+50h+var_10], rax
0x140012b05  mov     rbx, rcx
0x140012b08  mov     rdi, [rcx+110h]
0x140012b0f  mov     eax, [rdi+48h]
0x140012b12  test    eax, eax
0x140012b14  jns     loc_140012CC3
0x140012b1a  add     rdi, 50h ; 'P'
0x140012b1e  cmp     eax, [rdi+8]
0x140012b21  jnz     loc_140012CC3
0x140012b27  test    rdi, rdi
0x140012b2a  jz      loc_140012CC3
0x140012b30  lea     rdx, [rbp+50h+SRWLock]
0x140012b34  call    ?LockExclusive@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140012b39  mov     rax, [rbx+110h]
0x140012b40  mov     dword ptr [rax], 2
0x140012b46  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x140012b4a  test    rcx, rcx
0x140012b4d  jz      short loc_140012B55
0x140012b4f  call    cs:__imp_ReleaseSRWLockExclusive
0x140012b55  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x140012b5a  mov     r9, rax
0x140012b5d  mov     ecx, [rax]
0x140012b5f  cmp     ecx, 5
0x140012b62  jbe     loc_140012D98
0x140012b68  mov     rax, [rax+18h]
0x140012b6c  mov     rcx, [r9+10h]
0x140012b70  mov     rdx, 400000000000h
0x140012b7a  test    rdx, rcx
0x140012b7d  jz      loc_140012D98
0x140012b83  mov     rcx, rax
0x140012b86  and     rcx, rdx
0x140012b89  cmp     rcx, rax
0x140012b8c  jnz     loc_140012D98
0x140012b92  mov     rax, [rdi+78h]
0x140012b96  mov     [rbp+50h+var_A8], rax
0x140012b9a  mov     rax, [rdi+70h]
0x140012b9e  mov     [rbp+50h+var_A0], rax
0x140012ba2  mov     eax, [rdi+68h]
0x140012ba5  mov     [rbp+50h+var_B8], eax
0x140012ba8  mov     rax, [rdi+60h]
0x140012bac  mov     [rbp+50h+var_98], rax
0x140012bb0  mov     rax, [rdi+58h]
0x140012bb4  mov     [rbp+50h+var_90], rax
0x140012bb8  mov     eax, [rdi+50h]
0x140012bbb  mov     [rbp+50h+var_B4], eax
0x140012bbe  mov     rax, [rdi+48h]
0x140012bc2  mov     [rbp+50h+var_88], rax
0x140012bc6  mov     eax, [rdi+20h]
0x140012bc9  mov     [rbp+50h+var_B0], eax
0x140012bcc  mov     rax, [rdi+18h]
0x140012bd0  mov     [rbp+50h+var_80], rax
0x140012bd4  mov     eax, [rdi]
0x140012bd6  mov     [rbp+50h+var_AC], eax
0x140012bd9  mov     rax, [rdi+80h]
0x140012be0  mov     [rbp+50h+var_78], rax
0x140012be4  mov     eax, [rdi+40h]
0x140012be7  mov     [rbp+50h+var_D0], eax
0x140012bea  mov     rax, [rdi+38h]
0x140012bee  mov     [rbp+50h+var_70], rax
0x140012bf2  mov     eax, [rdi+8]
0x140012bf5  mov     dword ptr [rbp+50h+SRWLock], eax
0x140012bf8  mov     [rbp+50h+var_68], 1000000h
0x140012c00  mov     [rbp+50h+var_C0], 0
0x140012c08  mov     r8, [rbx+110h]
0x140012c0f  add     r8, 8
0x140012c13  lea     rax, [rbp+50h+var_A8]
0x140012c17  mov     [rsp+170h+var_D8], rax
0x140012c1f  lea     rax, [rbp+50h+var_A0]
0x140012c23  mov     [rsp+170h+var_E0], rax
0x140012c2b  lea     rax, [rbp+50h+var_B8]
0x140012c2f  mov     [rsp+170h+var_E8], rax
0x140012c37  lea     rax, [rbp+50h+var_98]
0x140012c3b  mov     [rsp+170h+var_F0], rax
0x140012c43  lea     rax, [rbp+50h+var_90]
0x140012c47  mov     [rsp+170h+var_F8], rax
0x140012c4c  lea     rax, [rbp+50h+var_B4]
0x140012c50  mov     [rsp+170h+var_100], rax
0x140012c55  lea     rax, [rbp+50h+var_88]
0x140012c59  mov     [rsp+170h+var_108], rax
0x140012c5e  lea     rax, [rbp+50h+var_B0]
0x140012c62  mov     [rsp+170h+var_110], rax
0x140012c67  lea     rax, [rbp+50h+var_80]
0x140012c6b  mov     [rsp+170h+var_118], rax
0x140012c70  lea     rax, [rbp+50h+var_AC]
0x140012c74  mov     [rsp+170h+var_120], rax
0x140012c79  lea     rax, [rbp+50h+var_78]
0x140012c7d  mov     [rsp+170h+var_128], rax
0x140012c82  lea     rax, [rbp+50h+var_D0]
0x140012c86  mov     [rsp+170h+var_130], rax
0x140012c8b  lea     rax, [rbp+50h+var_70]
0x140012c8f  mov     [rsp+170h+var_138], rax
0x140012c94  lea     rax, [rbp+50h+SRWLock]
0x140012c98  mov     [rsp+170h+var_140], rax
0x140012c9d  lea     rax, [rbp+50h+var_68]
0x140012ca1  mov     [rsp+170h+var_148], rax
0x140012ca6  lea     rax, [rbp+50h+var_C0]
0x140012caa  mov     [rsp+170h+var_150], rax
0x140012caf  lea     rdx, byte_140018251
0x140012cb6  mov     rcx, r9
0x140012cb9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140012cbe  jmp     loc_140012D98
0x140012cc3  lea     rdx, [rbp+50h+var_C0]
0x140012cc7  call    ?LockExclusive@?$ActivityBase@VEduPrintProvLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EduPrintProvLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140012ccc  mov     rax, [rbx+110h]
0x140012cd3  mov     dword ptr [rax], 2
0x140012cd9  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x140012cdd  test    rcx, rcx
0x140012ce0  jz      short loc_140012CE8
0x140012ce2  call    cs:__imp_ReleaseSRWLockExclusive
0x140012ce8  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x140012ced  mov     rdi, rax
0x140012cf0  mov     ecx, [rax]
0x140012cf2  cmp     ecx, 5
0x140012cf5  jbe     loc_140012D98
0x140012cfb  mov     rax, [rax+18h]
0x140012cff  mov     rcx, [rdi+10h]
0x140012d03  mov     rdx, 400000000000h
0x140012d0d  test    rdx, rcx
0x140012d10  jz      loc_140012D98
0x140012d16  mov     rcx, rax
0x140012d19  and     rcx, rdx
0x140012d1c  cmp     rcx, rax
0x140012d1f  jnz     short loc_140012D98
0x140012d21  call    cs:__imp_GetCurrentThreadId
0x140012d27  mov     dword ptr [rbp+50h+SRWLock], eax
0x140012d2a  mov     r8, [rbx+110h]
0x140012d31  mov     eax, [r8+48h]
0x140012d35  mov     [rbp+50h+var_D0], eax
0x140012d38  mov     [rbp+50h+var_C0], 0
0x140012d40  lea     rax, [rbp+50h+SRWLock]
0x140012d44  mov     [rbp+50h+var_20], rax
0x140012d48  mov     [rbp+50h+var_18], 4
0x140012d50  lea     rax, [rbp+50h+var_D0]
0x140012d54  mov     [rbp+50h+var_30], rax
0x140012d58  mov     [rbp+50h+var_28], 4
0x140012d60  lea     rax, [rbp+50h+var_C0]
0x140012d64  mov     [rbp+50h+var_40], rax
0x140012d68  mov     [rbp+50h+var_38], 8
0x140012d70  add     r8, 8
0x140012d74  lea     rax, [rbp+50h+var_60]
0x140012d78  mov     [rsp+170h+var_148], rax
0x140012d7d  mov     dword ptr [rsp+170h+var_150], 5
0x140012d85  xor     r9d, r9d
0x140012d88  lea     rdx, byte_14001837D
0x140012d8f  mov     rcx, rdi
0x140012d92  call    _tlgWriteTransfer_EventWriteTransfer
0x140012d97  nop
0x140012d98  cmp     dword ptr [rbx+138h], 0
0x140012d9f  jz      short loc_140012DFF
0x140012da1  add     rbx, 120h
0x140012da8  call    cs:__imp_GetCurrentThreadId
0x140012dae  cmp     [rbx+18h], eax
0x140012db1  jz      short loc_140012DCF
0x140012db3  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140012dba  test    rax, rax
0x140012dbd  jz      short loc_140012DCF
0x140012dbf  mov     rdx, [rbp+58h]
0x140012dc3  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140012dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dcf  mov     dword ptr [rbx+18h], 0
0x140012dd6  mov     rcx, [rbx]
0x140012dd9  jmp     short loc_140012DE7
0x140012ddb  cmp     rax, rbx
0x140012dde  jz      short loc_140012DF1
0x140012de0  lea     rcx, [rax+10h]
0x140012de4  mov     [rbx], rcx
0x140012de7  mov     rax, [rcx]
0x140012dea  test    rax, rax
0x140012ded  jnz     short loc_140012DDB
0x140012def  jmp     short loc_140012DF8
0x140012df1  mov     rax, [rbx+10h]
0x140012df5  mov     [rcx], rax
0x140012df8  mov     qword ptr [rbx], 0
0x140012dff  mov     rcx, [rbp+50h+var_10]
0x140012e03  xor     rcx, rsp; StackCookie
0x140012e06  call    __security_check_cookie
0x140012e0b  lea     r11, [rsp+170h+var_s0]
0x140012e13  mov     rbx, [r11+18h]
0x140012e17  mov     rdi, [r11+20h]
0x140012e1b  mov     rsp, r11
0x140012e1e  pop     rbp
0x140012e1f  retn
```
