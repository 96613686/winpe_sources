# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x140025450`
- end: `0x1400256ac`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `604`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001f1ac`
- `0x14002268c`

## callees

- `0x1400010c0`
- `0x1400014d4`
- `0x1400015ec`
- `0x1400081d0`
- `0x140025450`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140025478`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002560a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140025478`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002560a`

## string_xrefs

- `0x14002551d`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x1400255a2`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140025660`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140025504`: `WaitForCompletion`
- `0x140025589`: `WaitForCompletion`
- `0x140025647`: `WaitForCompletion`
- `0x14002552d`: `ThreadWaitForSingleObject timed out`
- `0x1400255b2`: `ThreadWaitForSingleObject failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::WaitForCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  int v11; // r8d
  int v12; // r9d
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
    if ( (unsigned int)dword_1400880C8 > 5 )
    {
      v23 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_14007FB19,
        v7,
        v8,
        (__int64)&v23);
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
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        LODWORD(v23) = 268;
        v18 = "WaitForCompletion";
        v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v20 = "ThreadWaitForSingleObject timed out";
        v24 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)&dword_14007FAD4,
          v11,
          v12,
          (__int64)&v20,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v18);
      }
      goto LABEL_5;
    }
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_1400880C8 <= 2 )
        goto LABEL_5;
      v24 = 272;
      v20 = "WaitForCompletion";
      v13 = (__int16 *)byte_14007FA8B;
      v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v21 = "ThreadWaitForSingleObject failed with 0x%x";
      v17 = &v20;
      v16 = &v19;
      v14 = &v21;
LABEL_13:
      LODWORD(v18) = -2147467259;
      LODWORD(v23) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        -2147467259,
        (_DWORD)v13,
        v11,
        v12,
        (__int64)v14,
        (__int64)&v18,
        (__int64)v16,
        (__int64)&v24,
        (__int64)v17,
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
  if ( (unsigned int)dword_1400880C8 > 2 )
  {
    v24 = 287;
    v21 = "WaitForCompletion";
    v13 = word_14007FA42;
    v20 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v19 = "PAL_System_SingleCondWait failed with 0x%x";
    v17 = &v21;
    v16 = &v20;
    v14 = &v19;
    goto LABEL_13;
  }
LABEL_5:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140025450  mov     [rsp-18h+arg_8], rbx
0x140025455  push    rbp
0x140025456  push    rsi
0x140025457  push    rdi
0x140025458  mov     rbp, rsp
0x14002545b  sub     rsp, 80h
0x140025462  mov     rsi, r8
0x140025465  mov     [rbp+var_10], 0
0x14002546d  mov     edi, edx
0x14002546f  mov     rbx, rcx
0x140025472  mov     rcx, [rcx+58h]; hHandle
0x140025476  xor     edx, edx; dwMilliseconds
0x140025478  call    cs:__imp_WaitForSingleObject
0x14002547e  test    eax, eax
0x140025480  jnz     short loc_1400254CD
0x140025482  mov     eax, cs:dword_1400880C8
0x140025488  cmp     eax, 5
0x14002548b  jbe     short loc_1400254AD
0x14002548d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x140025494  mov     [rbp+arg_0], rax
0x140025498  lea     rdx, byte_14007FB19
0x14002549f  lea     rax, [rbp+arg_0]
0x1400254a3  mov     [rsp+80h+var_60], rax
0x1400254a8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400254ad  xor     ebx, ebx
0x1400254af  lea     rcx, [rbp+var_10]
0x1400254b3  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400254b8  mov     eax, ebx
0x1400254ba  mov     rbx, [rsp+80h+arg_8]
0x1400254c2  add     rsp, 80h
0x1400254c9  pop     rdi
0x1400254ca  pop     rsi
0x1400254cb  pop     rbp
0x1400254cc  retn
0x1400254cd  cmp     edi, 4
0x1400254d0  jz      loc_140025603
0x1400254d6  mov     rax, [rsi]
0x1400254d9  or      r9d, 0FFFFFFFFh
0x1400254dd  mov     rdx, [rbx+58h]
0x1400254e1  mov     r8d, edi
0x1400254e4  mov     rcx, rsi
0x1400254e7  mov     rax, [rax+48h]
0x1400254eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400254f0  mov     ebx, eax
0x1400254f2  cmp     eax, 83450004h
0x1400254f7  jnz     short loc_140025572
0x1400254f9  mov     ecx, cs:dword_1400880C8
0x1400254ff  cmp     ecx, 2
0x140025502  jbe     short loc_1400254AF
0x140025504  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x14002550b  mov     dword ptr [rbp+arg_0], 10Ch
0x140025512  mov     [rbp+var_30], rax
0x140025516  lea     rdx, dword_14007FAD4
0x14002551d  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140025524  mov     ecx, 80004005h
0x140025529  mov     [rbp+var_28], rax
0x14002552d  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x140025534  mov     [rbp+var_20], rax
0x140025538  lea     rax, [rbp+var_30]
0x14002553c  mov     [rsp+80h+var_40], rax
0x140025541  lea     rax, [rbp+arg_0]
0x140025545  mov     [rsp+80h+var_48], rax
0x14002554a  lea     rax, [rbp+var_28]
0x14002554e  mov     [rsp+80h+var_50], rax
0x140025553  lea     rax, [rbp+arg_18]
0x140025557  mov     [rsp+80h+var_58], rax
0x14002555c  lea     rax, [rbp+var_20]
0x140025560  mov     [rsp+80h+var_60], rax
0x140025565  mov     [rbp+arg_18], ecx
0x140025568  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14002556d  jmp     loc_1400254AF
0x140025572  test    ebx, ebx
0x140025574  jns     loc_1400254AD
0x14002557a  mov     eax, cs:dword_1400880C8
0x140025580  cmp     eax, 2
0x140025583  jbe     loc_1400254AF
0x140025589  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140025590  mov     [rbp+arg_18], 110h
0x140025597  mov     [rbp+var_20], rax
0x14002559b  lea     rdx, byte_14007FA8B
0x1400255a2  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400255a9  mov     ecx, 80004005h
0x1400255ae  mov     [rbp+var_28], rax
0x1400255b2  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x1400255b9  mov     [rbp+var_18], rax
0x1400255bd  lea     rax, [rbp+arg_0]
0x1400255c1  mov     [rsp+80h+var_38], rax
0x1400255c6  lea     rax, [rbp+var_20]
0x1400255ca  mov     [rsp+80h+var_40], rax
0x1400255cf  lea     rax, [rbp+arg_18]
0x1400255d3  mov     [rsp+80h+var_48], rax
0x1400255d8  lea     rax, [rbp+var_28]
0x1400255dc  mov     [rsp+80h+var_50], rax
0x1400255e1  lea     rax, [rbp+var_30]
0x1400255e5  mov     [rsp+80h+var_58], rax
0x1400255ea  lea     rax, [rbp+var_18]
0x1400255ee  mov     [rsp+80h+var_60], rax
0x1400255f3  mov     dword ptr [rbp+var_30], ecx
0x1400255f6  mov     dword ptr [rbp+arg_0], ebx
0x1400255f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400255fe  jmp     loc_1400254AF
0x140025603  mov     rcx, [rbx+58h]; hHandle
0x140025607  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002560a  call    cs:__imp_WaitForSingleObject
0x140025610  test    eax, eax
0x140025612  jz      loc_1400254AD
0x140025618  mov     ecx, 80004005h
0x14002561d  cmp     eax, 80h
0x140025622  jz      short loc_140025633
0x140025624  cmp     eax, 102h
0x140025629  mov     ebx, 834500CBh
0x14002562e  cmovnz  ebx, ecx
0x140025631  jmp     short loc_140025638
0x140025633  mov     ebx, 834500CAh
0x140025638  mov     eax, cs:dword_1400880C8
0x14002563e  cmp     eax, 2
0x140025641  jbe     loc_1400254AF
0x140025647  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x14002564e  mov     [rbp+arg_18], 11Fh
0x140025655  mov     [rbp+var_18], rax
0x140025659  lea     rdx, word_14007FA42
0x140025660  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140025667  mov     [rbp+var_20], rax
0x14002566b  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x140025672  mov     [rbp+var_28], rax
0x140025676  lea     rax, [rbp+arg_0]
0x14002567a  mov     [rsp+80h+var_38], rax
0x14002567f  lea     rax, [rbp+var_18]
0x140025683  mov     [rsp+80h+var_40], rax
0x140025688  lea     rax, [rbp+arg_18]
0x14002568c  mov     [rsp+80h+var_48], rax
0x140025691  lea     rax, [rbp+var_20]
0x140025695  mov     [rsp+80h+var_50], rax
0x14002569a  lea     rax, [rbp+var_30]
0x14002569e  mov     [rsp+80h+var_58], rax
0x1400256a3  lea     rax, [rbp+var_28]
0x1400256a7  jmp     loc_1400255EE
```
