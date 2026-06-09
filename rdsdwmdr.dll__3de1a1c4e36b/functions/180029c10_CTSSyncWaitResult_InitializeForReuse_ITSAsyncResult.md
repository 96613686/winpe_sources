# CTSSyncWaitResult::InitializeForReuse(ITSAsyncResult *)

- ea: `0x180029c10`
- end: `0x180029cf8`
- name: `?InitializeForReuse@CTSSyncWaitResult@@QEAAJPEAVITSAsyncResult@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(CTSSyncWaitResult *__hidden this, struct ITSAsyncResult *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027e10`

## callees

- `0x180001f98`
- `0x18000f068`
- `0x18000f08c`
- `0x180029c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029c29`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029c29`

## string_xrefs

- `0x180029c64`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::InitializeForReuse(CTSSyncWaitResult *this, struct ITSAsyncResult *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  const char *v9; // [rsp+50h] [rbp-20h] BYREF
  const char *v10; // [rsp+58h] [rbp-18h] BYREF
  const char *v11; // [rsp+60h] [rbp-10h] BYREF
  int v12; // [rsp+90h] [rbp+20h] BYREF
  int v13; // [rsp+A0h] [rbp+30h] BYREF
  int v14; // [rsp+A8h] [rbp+38h] BYREF

  if ( ResetEvent(*((HANDLE *)this + 11)) )
  {
    *((_DWORD *)this + 24) = -2147467259;
    if ( a2 != *((struct ITSAsyncResult **)this + 13) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 104);
      *((_QWORD *)this + 13) = a2;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 104);
    }
    return 0;
  }
  else
  {
    v7 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v12 = -2147467259;
      v9 = "InitializeForReuse";
      v13 = 181;
      v10 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v11 = "PAL_System_CondReset failed! hr = 0x%x";
      v14 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v4,
        (__int64)byte_180040075,
        v5,
        v6,
        (const unsigned __int16 **)&v11,
        (__int64)&v14,
        (const unsigned __int16 **)&v10,
        (__int64)&v13,
        (const unsigned __int16 **)&v9,
        (__int64)&v12);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180029c10  mov     [rsp-18h+arg_8], rbx
0x180029c15  push    rbp
0x180029c16  push    rsi
0x180029c17  push    rdi
0x180029c18  mov     rbp, rsp
0x180029c1b  sub     rsp, 70h
0x180029c1f  mov     rsi, rdx
0x180029c22  mov     rdi, rcx
0x180029c25  mov     rcx, [rcx+58h]; hEvent
0x180029c29  call    cs:__imp_ResetEvent
0x180029c2f  test    eax, eax
0x180029c31  jnz     loc_180029CC1
0x180029c37  mov     eax, cs:dword_180044008
0x180029c3d  mov     ebx, 80004005h
0x180029c42  cmp     eax, 2
0x180029c45  jbe     loc_180029CE6
0x180029c4b  lea     rax, aInitializeforr_0; "InitializeForReuse"
0x180029c52  mov     [rbp+arg_0], 80004005h
0x180029c59  mov     [rbp+var_20], rax
0x180029c5d  lea     rdx, byte_180040075
0x180029c64  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180029c6b  mov     [rbp+arg_10], 0B5h
0x180029c72  mov     [rbp+var_18], rax
0x180029c76  lea     rax, aPalSystemCondr; "PAL_System_CondReset failed! hr = 0x%x"
0x180029c7d  mov     [rbp+var_10], rax
0x180029c81  lea     rax, [rbp+arg_0]
0x180029c85  mov     [rsp+70h+var_28], rax
0x180029c8a  lea     rax, [rbp+var_20]
0x180029c8e  mov     [rsp+70h+var_30], rax
0x180029c93  lea     rax, [rbp+arg_10]
0x180029c97  mov     [rsp+70h+var_38], rax
0x180029c9c  lea     rax, [rbp+var_18]
0x180029ca0  mov     [rsp+70h+var_40], rax
0x180029ca5  lea     rax, [rbp+arg_18]
0x180029ca9  mov     [rsp+70h+var_48], rax
0x180029cae  lea     rax, [rbp+var_10]
0x180029cb2  mov     [rsp+70h+var_50], rax
0x180029cb7  mov     [rbp+arg_18], ebx
0x180029cba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029cbf  jmp     short loc_180029CE6
0x180029cc1  lea     rbx, [rdi+68h]
0x180029cc5  mov     dword ptr [rdi+60h], 80004005h
0x180029ccc  cmp     rsi, [rbx]
0x180029ccf  jz      short loc_180029CE4
0x180029cd1  mov     rcx, rbx
0x180029cd4  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180029cd9  mov     rcx, rbx
0x180029cdc  mov     [rbx], rsi
0x180029cdf  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180029ce4  xor     ebx, ebx
0x180029ce6  mov     eax, ebx
0x180029ce8  mov     rbx, [rsp+70h+arg_8]
0x180029cf0  add     rsp, 70h
0x180029cf4  pop     rdi
0x180029cf5  pop     rsi
0x180029cf6  pop     rbp
0x180029cf7  retn
```
