# CRdpIceLocalEndpoint::InitializeEndpoint(sockaddr_storage const &,unsigned __int64,ulong,ushort const *)

- ea: `0x180146cb0`
- end: `0x180146f73`
- name: `?InitializeEndpoint@CRdpIceLocalEndpoint@@MEAAJAEBUsockaddr_storage@@_KKPEBG@Z`
- size: `707`
- prototype: `__int64 __fastcall(CRdpIceLocalEndpoint *__hidden this, const struct sockaddr_storage *, unsigned __int64, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001aa0`
- `0x180002550`
- `0x1800787d4`
- `0x18007969c`
- `0x1801281e0`
- `0x180146cb0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146d42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180146d33`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180146d33`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180146ccc`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180146ccc`

## string_xrefs

- `0x180146d66`: `Failed to create socket event`
- `0x180146e0c`: `Failed to create shared handle in CRdpIceLocalEndpoint::InitializeEndpoint`

## pseudocode

```c
__int64 __fastcall CRdpIceLocalEndpoint::InitializeEndpoint(
        CRdpIceLocalEndpoint *this,
        const struct sockaddr_storage *a2)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  char *v10; // rdx
  const char **v11; // rax
  __int64 v12; // rcx
  void *v13; // rax
  void *v14; // rsi
  __int64 v15; // rcx
  int v16; // r9d
  const char **v18; // [rsp+30h] [rbp-40h]
  const char **v19; // [rsp+40h] [rbp-30h]
  const char **v20; // [rsp+48h] [rbp-28h]
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const char *v23; // [rsp+60h] [rbp-10h] BYREF
  const char *v24; // [rsp+68h] [rbp-8h] BYREF
  struct ISharedHandle *v25; // [rsp+90h] [rbp+20h] BYREF
  unsigned int v26; // [rsp+98h] [rbp+28h] BYREF

  InitializeConditionVariable((PCONDITION_VARIABLE)this + 96);
  *((_DWORD *)this + 194) = 1;
  *(struct sockaddr_storage *)((char *)this + 80) = *a2;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v25 = 0;
    v9 = SharedHandle::CreateInstance(EventW, &v25);
    if ( (v9 & 0x80000000) != 0 )
    {
      v6 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        return v9;
      LODWORD(v25) = 87;
      v24 = "Failed to create shared handle in CRdpIceLocalEndpoint::InitializeEndpoint";
      v10 = &byte_1801D60EF;
      v23 = "InitializeEndpoint";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpicelocalendpoint.cpp";
      v21 = "Error HResult failed";
      v20 = &v24;
      v19 = &v23;
      v18 = &v22;
      v11 = &v21;
      goto LABEL_6;
    }
    v12 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v25;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = operator new(0x80u);
    v14 = v13;
    if ( v13 )
      memset_0(v13, 0, 0x80u);
    else
      v14 = 0;
    v15 = *((_QWORD *)this + 98);
    *((_QWORD *)this + 99) = v14;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 64LL))(
      v15,
      ((unsigned __int64)this + 680) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 98) + 80LL))(
      *((_QWORD *)this + 98),
      ((unsigned __int64)this + 688) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 98) + 40LL))(
      *((_QWORD *)this + 98),
      (char *)this + 512);
    if ( (unsigned int)CallbackContext > 4 )
    {
      v25 = (struct ISharedHandle *)"Ice local endpoint initialized";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801D60B1,
        0,
        v16,
        (__int64)&v25);
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v25) = 83;
      v21 = "Failed to create socket event";
      v10 = &byte_1801D633F;
      v22 = "InitializeEndpoint";
      v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpicelocalendpoint.cpp";
      v24 = "Error condition failed";
      v20 = &v21;
      v19 = &v22;
      v18 = &v23;
      v11 = &v24;
LABEL_6:
      v26 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (_DWORD)v10,
        v7,
        v8,
        (__int64)v11,
        (__int64)&v26,
        (__int64)v18,
        (__int64)&v25,
        (__int64)v19,
        (__int64)v20);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180146cb0  mov     [rsp-18h+arg_10], rbx
0x180146cb5  push    rbp
0x180146cb6  push    rsi
0x180146cb7  push    rdi
0x180146cb8  mov     rbp, rsp
0x180146cbb  sub     rsp, 70h
0x180146cbf  mov     rdi, rcx
0x180146cc2  mov     rbx, rdx
0x180146cc5  add     rcx, 300h; ConditionVariable
0x180146ccc  call    cs:__imp_InitializeConditionVariable
0x180146cd2  mov     edx, 1; bManualReset
0x180146cd7  xor     r9d, r9d; lpName
0x180146cda  mov     [rdi+308h], edx
0x180146ce0  xor     r8d, r8d; bInitialState
0x180146ce3  movups  xmm0, xmmword ptr [rbx]
0x180146ce6  xor     ecx, ecx; lpEventAttributes
0x180146ce8  movups  xmmword ptr [rdi+50h], xmm0
0x180146cec  movups  xmm1, xmmword ptr [rbx+10h]
0x180146cf0  movups  xmmword ptr [rdi+60h], xmm1
0x180146cf4  movups  xmm0, xmmword ptr [rbx+20h]
0x180146cf8  movups  xmmword ptr [rdi+70h], xmm0
0x180146cfc  movups  xmm1, xmmword ptr [rbx+30h]
0x180146d00  movups  xmmword ptr [rdi+80h], xmm1
0x180146d07  movups  xmm0, xmmword ptr [rbx+40h]
0x180146d0b  movups  xmmword ptr [rdi+90h], xmm0
0x180146d12  movups  xmm1, xmmword ptr [rbx+50h]
0x180146d16  movups  xmmword ptr [rdi+0A0h], xmm1
0x180146d1d  movups  xmm0, xmmword ptr [rbx+60h]
0x180146d21  movups  xmmword ptr [rdi+0B0h], xmm0
0x180146d28  movups  xmm1, xmmword ptr [rbx+70h]
0x180146d2c  movups  xmmword ptr [rdi+0C0h], xmm1
0x180146d33  call    cs:__imp_CreateEventW
0x180146d39  test    rax, rax
0x180146d3c  jnz     loc_180146DE3
0x180146d42  call    cs:__imp_GetLastError
0x180146d48  mov     ebx, eax
0x180146d4a  test    eax, eax
0x180146d4c  jle     short loc_180146D57
0x180146d4e  movzx   ebx, ax
0x180146d51  or      ebx, 80070000h
0x180146d57  mov     eax, cs:CallbackContext
0x180146d5d  cmp     eax, 2
0x180146d60  jbe     loc_180146F61
0x180146d66  lea     rax, aFailedToCreate_86; "Failed to create socket event"
0x180146d6d  mov     dword ptr [rbp+arg_0], 53h ; 'S'
0x180146d74  mov     [rbp+var_20], rax
0x180146d78  lea     rdx, byte_1801D633F
0x180146d7f  lea     rax, aInitializeendp_0; "InitializeEndpoint"
0x180146d86  mov     [rbp+var_18], rax
0x180146d8a  lea     rax, aOnecoreTermsrv_53; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180146d91  mov     [rbp+var_10], rax
0x180146d95  lea     rax, aErrorCondition; "Error condition failed"
0x180146d9c  mov     [rbp+var_8], rax
0x180146da0  lea     rax, [rbp+var_20]
0x180146da4  mov     [rsp+70h+var_28], rax
0x180146da9  lea     rax, [rbp+var_18]
0x180146dad  mov     [rsp+70h+var_30], rax
0x180146db2  lea     rax, [rbp+arg_0]
0x180146db6  mov     [rsp+70h+var_38], rax
0x180146dbb  lea     rax, [rbp+var_10]
0x180146dbf  mov     [rsp+70h+var_40], rax
0x180146dc4  lea     rax, [rbp+arg_8]
0x180146dc8  mov     [rsp+70h+var_48], rax
0x180146dcd  lea     rax, [rbp+var_8]
0x180146dd1  mov     [rsp+70h+var_50], rax
0x180146dd6  mov     [rbp+arg_8], ebx
0x180146dd9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180146dde  jmp     loc_180146F61
0x180146de3  lea     rdx, [rbp+arg_0]; struct ISharedHandle **
0x180146de7  mov     [rbp+arg_0], 0
0x180146def  mov     rcx, rax; void *
0x180146df2  call    ?CreateInstance@SharedHandle@@SAJPEAXPEAPEAUISharedHandle@@@Z; SharedHandle::CreateInstance(void *,ISharedHandle * *)
0x180146df7  mov     ebx, eax
0x180146df9  test    eax, eax
0x180146dfb  jns     short loc_180146E7C
0x180146dfd  mov     ecx, cs:CallbackContext
0x180146e03  cmp     ecx, 2
0x180146e06  jbe     loc_180146F61
0x180146e0c  lea     rax, aFailedToCreate_42; "Failed to create shared handle in CRdpI"...
0x180146e13  mov     dword ptr [rbp+arg_0], 57h ; 'W'
0x180146e1a  mov     [rbp+var_8], rax
0x180146e1e  lea     rdx, byte_1801D60EF
0x180146e25  lea     rax, aInitializeendp_0; "InitializeEndpoint"
0x180146e2c  mov     [rbp+var_10], rax
0x180146e30  lea     rax, aOnecoreTermsrv_53; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180146e37  mov     [rbp+var_18], rax
0x180146e3b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180146e42  mov     [rbp+var_20], rax
0x180146e46  lea     rax, [rbp+var_8]
0x180146e4a  mov     [rsp+70h+var_28], rax
0x180146e4f  lea     rax, [rbp+var_10]
0x180146e53  mov     [rsp+70h+var_30], rax
0x180146e58  lea     rax, [rbp+arg_0]
0x180146e5c  mov     [rsp+70h+var_38], rax
0x180146e61  lea     rax, [rbp+var_18]
0x180146e65  mov     [rsp+70h+var_40], rax
0x180146e6a  lea     rax, [rbp+arg_8]
0x180146e6e  mov     [rsp+70h+var_48], rax
0x180146e73  lea     rax, [rbp+var_20]
0x180146e77  jmp     loc_180146DD1
0x180146e7c  mov     rcx, [rdi+38h]
0x180146e80  mov     rax, [rbp+arg_0]
0x180146e84  mov     [rdi+38h], rax
0x180146e88  test    rcx, rcx
0x180146e8b  jz      short loc_180146E99
0x180146e8d  mov     rax, [rcx]
0x180146e90  mov     rax, [rax+10h]
0x180146e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146e99  mov     ecx, 80h; Size
0x180146e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180146ea3  mov     rsi, rax
0x180146ea6  test    rax, rax
0x180146ea9  jz      short loc_180146EBD
0x180146eab  xor     edx, edx; Val
0x180146ead  mov     r8d, 80h; Size
0x180146eb3  mov     rcx, rax; void *
0x180146eb6  call    memset_0
0x180146ebb  jmp     short loc_180146EBF
0x180146ebd  xor     esi, esi
0x180146ebf  mov     rcx, [rdi+310h]
0x180146ec6  lea     r8, [rdi+2A8h]
0x180146ecd  mov     [rdi+318h], rsi
0x180146ed4  mov     rax, rdi
0x180146ed7  neg     rax
0x180146eda  mov     r9, [rcx]
0x180146edd  sbb     rdx, rdx
0x180146ee0  and     rdx, r8
0x180146ee3  mov     rax, [r9+40h]
0x180146ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146eec  mov     rcx, [rdi+310h]
0x180146ef3  lea     r8, [rdi+2B0h]
0x180146efa  mov     rax, rdi
0x180146efd  neg     rax
0x180146f00  mov     r9, [rcx]
0x180146f03  sbb     rdx, rdx
0x180146f06  and     rdx, r8
0x180146f09  mov     rax, [r9+50h]
0x180146f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146f12  mov     rcx, [rdi+310h]
0x180146f19  lea     rdx, [rdi+200h]
0x180146f20  mov     rax, [rcx]
0x180146f23  mov     rax, [rax+28h]
0x180146f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146f2c  mov     eax, cs:CallbackContext
0x180146f32  cmp     eax, 4
0x180146f35  jbe     short loc_180146F61
0x180146f37  lea     rax, aIceLocalEndpoi_1; "Ice local endpoint initialized"
0x180146f3e  xor     r8d, r8d
0x180146f41  mov     [rbp+arg_0], rax
0x180146f45  lea     rdx, byte_1801D60B1
0x180146f4c  lea     rax, [rbp+arg_0]
0x180146f50  lea     rcx, CallbackContext
0x180146f57  mov     [rsp+70h+var_50], rax
0x180146f5c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180146f61  mov     eax, ebx
0x180146f63  mov     rbx, [rsp+70h+arg_10]
0x180146f6b  add     rsp, 70h
0x180146f6f  pop     rdi
0x180146f70  pop     rsi
0x180146f71  pop     rbp
0x180146f72  retn
```
