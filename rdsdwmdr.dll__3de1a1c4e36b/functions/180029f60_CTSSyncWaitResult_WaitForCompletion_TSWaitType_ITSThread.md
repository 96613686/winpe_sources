# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x180029f60`
- end: `0x18002a1bc`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180027e10`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x180001f98`
- `0x18000f08c`
- `0x180029f60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029f88`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a11a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029f88`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a11a`

## string_xrefs

- `0x18002a02d`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18002a0b2`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18002a170`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x18002a014`: `WaitForCompletion`
- `0x18002a099`: `WaitForCompletion`
- `0x18002a157`: `WaitForCompletion`
- `0x18002a03d`: `ThreadWaitForSingleObject timed out`
- `0x18002a0c2`: `ThreadWaitForSingleObject failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::WaitForCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 *v13; // rdx
  const char **v14; // rax
  DWORD v15; // eax
  const char **v16; // [rsp+30h] [rbp-50h]
  const char **v17; // [rsp+40h] [rbp-40h]
  const char *v18; // [rsp+50h] [rbp-30h] BYREF
  const char *v19; // [rsp+58h] [rbp-28h] BYREF
  const char *v20; // [rsp+60h] [rbp-20h] BYREF
  const char *v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h] BYREF
  const char *v23; // [rsp+A0h] [rbp+20h] BYREF
  int v24; // [rsp+B8h] [rbp+38h] BYREF

  v22 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v23 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (__int64)&dword_180040054,
        v7,
        v8,
        (const unsigned __int16 **)&v23);
    }
    goto LABEL_4;
  }
  if ( a2 != 4 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a3 + 72LL))(
           a3,
           *(_QWORD *)(a1 + 88),
           a2,
           0xFFFFFFFFLL);
    if ( v9 == -2092630012 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v23) = 268;
        v18 = "WaitForCompletion";
        v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v20 = "ThreadWaitForSingleObject timed out";
        v24 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          2147500037LL,
          (__int64)&byte_18004000F,
          v11,
          v12,
          (const unsigned __int16 **)&v20,
          (__int64)&v24,
          (const unsigned __int16 **)&v19,
          (__int64)&v23,
          (const unsigned __int16 **)&v18);
      }
      goto LABEL_5;
    }
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_5;
      v24 = 272;
      v20 = "WaitForCompletion";
      v13 = &word_18003FFC6;
      v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v21 = "ThreadWaitForSingleObject failed with 0x%x";
      v17 = &v20;
      v16 = &v19;
      v14 = &v21;
LABEL_13:
      LODWORD(v18) = -2147467259;
      LODWORD(v23) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        2147500037LL,
        (__int64)v13,
        v11,
        v12,
        (const unsigned __int16 **)v14,
        (__int64)&v18,
        (const unsigned __int16 **)v16,
        (__int64)&v24,
        (const unsigned __int16 **)v17,
        (__int64)&v23);
      goto LABEL_5;
    }
LABEL_4:
    v9 = 0;
    goto LABEL_5;
  }
  v15 = WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
  if ( !v15 )
    goto LABEL_4;
  if ( v15 == 128 )
  {
    v9 = -2092629814;
  }
  else
  {
    v9 = -2092629813;
    if ( v15 != 258 )
      v9 = -2147467259;
  }
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v24 = 287;
    v21 = "WaitForCompletion";
    v13 = (__int16 *)byte_18003FF7D;
    v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v19 = "PAL_System_SingleCondWait failed with 0x%x";
    v17 = &v21;
    v16 = &v20;
    v14 = &v19;
    goto LABEL_13;
  }
LABEL_5:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029f60  mov     [rsp-18h+arg_8], rbx
0x180029f65  push    rbp
0x180029f66  push    rsi
0x180029f67  push    rdi
0x180029f68  mov     rbp, rsp
0x180029f6b  sub     rsp, 80h
0x180029f72  mov     rsi, r8
0x180029f75  mov     [rbp+var_10], 0
0x180029f7d  mov     edi, edx
0x180029f7f  mov     rbx, rcx
0x180029f82  mov     rcx, [rcx+58h]; hHandle
0x180029f86  xor     edx, edx; dwMilliseconds
0x180029f88  call    cs:__imp_WaitForSingleObject
0x180029f8e  test    eax, eax
0x180029f90  jnz     short loc_180029FDD
0x180029f92  mov     eax, cs:dword_180044008
0x180029f98  cmp     eax, 5
0x180029f9b  jbe     short loc_180029FBD
0x180029f9d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x180029fa4  mov     [rbp+arg_0], rax
0x180029fa8  lea     rdx, dword_180040054
0x180029faf  lea     rax, [rbp+arg_0]
0x180029fb3  mov     [rsp+80h+var_60], rax
0x180029fb8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180029fbd  xor     ebx, ebx
0x180029fbf  lea     rcx, [rbp+var_10]
0x180029fc3  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180029fc8  mov     eax, ebx
0x180029fca  mov     rbx, [rsp+80h+arg_8]
0x180029fd2  add     rsp, 80h
0x180029fd9  pop     rdi
0x180029fda  pop     rsi
0x180029fdb  pop     rbp
0x180029fdc  retn
0x180029fdd  cmp     edi, 4
0x180029fe0  jz      loc_18002A113
0x180029fe6  mov     rax, [rsi]
0x180029fe9  or      r9d, 0FFFFFFFFh
0x180029fed  mov     rdx, [rbx+58h]
0x180029ff1  mov     r8d, edi
0x180029ff4  mov     rcx, rsi
0x180029ff7  mov     rax, [rax+48h]
0x180029ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a000  mov     ebx, eax
0x18002a002  cmp     eax, 83450004h
0x18002a007  jnz     short loc_18002A082
0x18002a009  mov     ecx, cs:dword_180044008
0x18002a00f  cmp     ecx, 2
0x18002a012  jbe     short loc_180029FBF
0x18002a014  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18002a01b  mov     dword ptr [rbp+arg_0], 10Ch
0x18002a022  mov     [rbp+var_30], rax
0x18002a026  lea     rdx, byte_18004000F
0x18002a02d  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a034  mov     ecx, 80004005h
0x18002a039  mov     [rbp+var_28], rax
0x18002a03d  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x18002a044  mov     [rbp+var_20], rax
0x18002a048  lea     rax, [rbp+var_30]
0x18002a04c  mov     [rsp+80h+var_40], rax
0x18002a051  lea     rax, [rbp+arg_0]
0x18002a055  mov     [rsp+80h+var_48], rax
0x18002a05a  lea     rax, [rbp+var_28]
0x18002a05e  mov     [rsp+80h+var_50], rax
0x18002a063  lea     rax, [rbp+arg_18]
0x18002a067  mov     [rsp+80h+var_58], rax
0x18002a06c  lea     rax, [rbp+var_20]
0x18002a070  mov     [rsp+80h+var_60], rax
0x18002a075  mov     [rbp+arg_18], ecx
0x18002a078  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002a07d  jmp     loc_180029FBF
0x18002a082  test    ebx, ebx
0x18002a084  jns     loc_180029FBD
0x18002a08a  mov     eax, cs:dword_180044008
0x18002a090  cmp     eax, 2
0x18002a093  jbe     loc_180029FBF
0x18002a099  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18002a0a0  mov     [rbp+arg_18], 110h
0x18002a0a7  mov     [rbp+var_20], rax
0x18002a0ab  lea     rdx, word_18003FFC6
0x18002a0b2  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a0b9  mov     ecx, 80004005h
0x18002a0be  mov     [rbp+var_28], rax
0x18002a0c2  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x18002a0c9  mov     [rbp+var_18], rax
0x18002a0cd  lea     rax, [rbp+arg_0]
0x18002a0d1  mov     [rsp+80h+var_38], rax
0x18002a0d6  lea     rax, [rbp+var_20]
0x18002a0da  mov     [rsp+80h+var_40], rax
0x18002a0df  lea     rax, [rbp+arg_18]
0x18002a0e3  mov     [rsp+80h+var_48], rax
0x18002a0e8  lea     rax, [rbp+var_28]
0x18002a0ec  mov     [rsp+80h+var_50], rax
0x18002a0f1  lea     rax, [rbp+var_30]
0x18002a0f5  mov     [rsp+80h+var_58], rax
0x18002a0fa  lea     rax, [rbp+var_18]
0x18002a0fe  mov     [rsp+80h+var_60], rax
0x18002a103  mov     dword ptr [rbp+var_30], ecx
0x18002a106  mov     dword ptr [rbp+arg_0], ebx
0x18002a109  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002a10e  jmp     loc_180029FBF
0x18002a113  mov     rcx, [rbx+58h]; hHandle
0x18002a117  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002a11a  call    cs:__imp_WaitForSingleObject
0x18002a120  test    eax, eax
0x18002a122  jz      loc_180029FBD
0x18002a128  mov     ecx, 80004005h
0x18002a12d  cmp     eax, 80h
0x18002a132  jz      short loc_18002A143
0x18002a134  cmp     eax, 102h
0x18002a139  mov     ebx, 834500CBh
0x18002a13e  cmovnz  ebx, ecx
0x18002a141  jmp     short loc_18002A148
0x18002a143  mov     ebx, 834500CAh
0x18002a148  mov     eax, cs:dword_180044008
0x18002a14e  cmp     eax, 2
0x18002a151  jbe     loc_180029FBF
0x18002a157  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x18002a15e  mov     [rbp+arg_18], 11Fh
0x18002a165  mov     [rbp+var_18], rax
0x18002a169  lea     rdx, byte_18003FF7D
0x18002a170  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a177  mov     [rbp+var_20], rax
0x18002a17b  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x18002a182  mov     [rbp+var_28], rax
0x18002a186  lea     rax, [rbp+arg_0]
0x18002a18a  mov     [rsp+80h+var_38], rax
0x18002a18f  lea     rax, [rbp+var_18]
0x18002a193  mov     [rsp+80h+var_40], rax
0x18002a198  lea     rax, [rbp+arg_18]
0x18002a19c  mov     [rsp+80h+var_48], rax
0x18002a1a1  lea     rax, [rbp+var_20]
0x18002a1a5  mov     [rsp+80h+var_50], rax
0x18002a1aa  lea     rax, [rbp+var_30]
0x18002a1ae  mov     [rsp+80h+var_58], rax
0x18002a1b3  lea     rax, [rbp+var_28]
0x18002a1b7  jmp     loc_18002A0FE
```
