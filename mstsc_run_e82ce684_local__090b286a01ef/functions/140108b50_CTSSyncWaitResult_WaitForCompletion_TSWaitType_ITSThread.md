# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x140108b50`
- end: `0x140108db3`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14010334c`
- `0x140105e60`

## callees

- `0x140001010`
- `0x1400019e8`
- `0x140001b00`
- `0x14000dcac`
- `0x140108b50`
- `0x140114010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140108b78`
- `KERNEL32!WaitForSingleObject` at `0x140108d11`
- `KERNEL32!WaitForSingleObject` at `0x140108b78`
- `KERNEL32!WaitForSingleObject` at `0x140108d11`

## string_xrefs

- `0x140108c24`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140108ca9`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140108d67`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140108c0b`: `WaitForCompletion`
- `0x140108c90`: `WaitForCompletion`
- `0x140108d4e`: `WaitForCompletion`
- `0x140108cb9`: `ThreadWaitForSingleObject failed with 0x%x`
- `0x140108c34`: `ThreadWaitForSingleObject timed out`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::WaitForCompletion(__int64 a1, unsigned int a2, __int64 a3)
{
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  int v10; // r8d
  int v11; // r9d
  int *v12; // rdx
  const char **v13; // rax
  DWORD v14; // eax
  const char **v15; // [rsp+30h] [rbp-50h]
  const char **v16; // [rsp+40h] [rbp-40h]
  const char *v17; // [rsp+50h] [rbp-30h] BYREF
  const char *v18; // [rsp+58h] [rbp-28h] BYREF
  const char *v19; // [rsp+60h] [rbp-20h] BYREF
  const char *v20; // [rsp+68h] [rbp-18h] BYREF
  __int64 v21; // [rsp+70h] [rbp-10h] BYREF
  const char *v22; // [rsp+A0h] [rbp+20h] BYREF
  int v23; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
    if ( (unsigned int)dword_140152118 > 5 )
    {
      v22 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140152118,
        (unsigned int)&word_140145BEE,
        v6,
        v7,
        (__int64)&v22);
    }
    goto LABEL_4;
  }
  if ( a2 != 4 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a3 + 72LL))(
           a3,
           *(_QWORD *)(a1 + 88),
           a2,
           0xFFFFFFFFLL);
    if ( v8 == -2092630012 )
    {
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v22) = 268;
        v17 = "WaitForCompletion";
        v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v19 = "ThreadWaitForSingleObject timed out";
        v23 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)byte_140145AB5,
          v10,
          v11,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v18,
          (__int64)&v22,
          (__int64)&v17);
      }
      goto LABEL_5;
    }
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_140152118 <= 2 )
        goto LABEL_5;
      v23 = 272;
      v19 = "WaitForCompletion";
      v12 = (int *)byte_140145A23;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v20 = "ThreadWaitForSingleObject failed with 0x%x";
      v16 = &v19;
      v15 = &v18;
      v13 = &v20;
LABEL_13:
      LODWORD(v17) = -2147467259;
      LODWORD(v22) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        -2147467259,
        (_DWORD)v12,
        v10,
        v11,
        (__int64)v13,
        (__int64)&v17,
        (__int64)v15,
        (__int64)&v23,
        (__int64)v16,
        (__int64)&v22);
      goto LABEL_5;
    }
LABEL_4:
    v8 = 0;
    goto LABEL_5;
  }
  v14 = WaitForSingleObject(*(HANDLE *)(a1 + 88), 0xFFFFFFFF);
  if ( !v14 )
    goto LABEL_4;
  if ( v14 == 128 )
  {
    v8 = -2092629814;
  }
  else
  {
    v8 = -2092629813;
    if ( v14 != 258 )
      v8 = -2147467259;
  }
  if ( (unsigned int)dword_140152118 > 2 )
  {
    v23 = 287;
    v20 = "WaitForCompletion";
    v12 = &dword_140145A6C;
    v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v18 = "PAL_System_SingleCondWait failed with 0x%x";
    v16 = &v20;
    v15 = &v19;
    v13 = &v18;
    goto LABEL_13;
  }
LABEL_5:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140108b50  mov     [rsp-18h+arg_8], rbx
0x140108b55  push    rbp
0x140108b56  push    rsi
0x140108b57  push    rdi
0x140108b58  mov     rbp, rsp
0x140108b5b  sub     rsp, 80h
0x140108b62  mov     rsi, r8
0x140108b65  mov     [rbp+var_10], 0
0x140108b6d  mov     edi, edx
0x140108b6f  mov     rbx, rcx
0x140108b72  mov     rcx, [rcx+58h]; hHandle
0x140108b76  xor     edx, edx; dwMilliseconds
0x140108b78  call    cs:__imp_WaitForSingleObject
0x140108b7e  test    eax, eax
0x140108b80  jnz     short loc_140108BD4
0x140108b82  mov     eax, cs:dword_140152118
0x140108b88  cmp     eax, 5
0x140108b8b  jbe     short loc_140108BB4
0x140108b8d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x140108b94  mov     [rbp+arg_0], rax
0x140108b98  lea     rdx, word_140145BEE
0x140108b9f  lea     rax, [rbp+arg_0]
0x140108ba3  lea     rcx, dword_140152118
0x140108baa  mov     [rsp+80h+var_60], rax
0x140108baf  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140108bb4  xor     ebx, ebx
0x140108bb6  lea     rcx, [rbp+var_10]
0x140108bba  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140108bbf  mov     eax, ebx
0x140108bc1  mov     rbx, [rsp+80h+arg_8]
0x140108bc9  add     rsp, 80h
0x140108bd0  pop     rdi
0x140108bd1  pop     rsi
0x140108bd2  pop     rbp
0x140108bd3  retn
0x140108bd4  cmp     edi, 4
0x140108bd7  jz      loc_140108D0A
0x140108bdd  mov     rax, [rsi]
0x140108be0  or      r9d, 0FFFFFFFFh
0x140108be4  mov     rdx, [rbx+58h]
0x140108be8  mov     r8d, edi
0x140108beb  mov     rcx, rsi
0x140108bee  mov     rax, [rax+48h]
0x140108bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140108bf7  mov     ebx, eax
0x140108bf9  cmp     eax, 83450004h
0x140108bfe  jnz     short loc_140108C79
0x140108c00  mov     ecx, cs:dword_140152118
0x140108c06  cmp     ecx, 2
0x140108c09  jbe     short loc_140108BB6
0x140108c0b  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140108c12  mov     dword ptr [rbp+arg_0], 10Ch
0x140108c19  mov     [rbp+var_30], rax
0x140108c1d  lea     rdx, byte_140145AB5
0x140108c24  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140108c2b  mov     ecx, 80004005h
0x140108c30  mov     [rbp+var_28], rax
0x140108c34  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x140108c3b  mov     [rbp+var_20], rax
0x140108c3f  lea     rax, [rbp+var_30]
0x140108c43  mov     [rsp+80h+var_40], rax
0x140108c48  lea     rax, [rbp+arg_0]
0x140108c4c  mov     [rsp+80h+var_48], rax
0x140108c51  lea     rax, [rbp+var_28]
0x140108c55  mov     [rsp+80h+var_50], rax
0x140108c5a  lea     rax, [rbp+arg_18]
0x140108c5e  mov     [rsp+80h+var_58], rax
0x140108c63  lea     rax, [rbp+var_20]
0x140108c67  mov     [rsp+80h+var_60], rax
0x140108c6c  mov     [rbp+arg_18], ecx
0x140108c6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140108c74  jmp     loc_140108BB6
0x140108c79  test    ebx, ebx
0x140108c7b  jns     loc_140108BB4
0x140108c81  mov     eax, cs:dword_140152118
0x140108c87  cmp     eax, 2
0x140108c8a  jbe     loc_140108BB6
0x140108c90  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140108c97  mov     [rbp+arg_18], 110h
0x140108c9e  mov     [rbp+var_20], rax
0x140108ca2  lea     rdx, byte_140145A23
0x140108ca9  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140108cb0  mov     ecx, 80004005h
0x140108cb5  mov     [rbp+var_28], rax
0x140108cb9  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x140108cc0  mov     [rbp+var_18], rax
0x140108cc4  lea     rax, [rbp+arg_0]
0x140108cc8  mov     [rsp+80h+var_38], rax
0x140108ccd  lea     rax, [rbp+var_20]
0x140108cd1  mov     [rsp+80h+var_40], rax
0x140108cd6  lea     rax, [rbp+arg_18]
0x140108cda  mov     [rsp+80h+var_48], rax
0x140108cdf  lea     rax, [rbp+var_28]
0x140108ce3  mov     [rsp+80h+var_50], rax
0x140108ce8  lea     rax, [rbp+var_30]
0x140108cec  mov     [rsp+80h+var_58], rax
0x140108cf1  lea     rax, [rbp+var_18]
0x140108cf5  mov     [rsp+80h+var_60], rax
0x140108cfa  mov     dword ptr [rbp+var_30], ecx
0x140108cfd  mov     dword ptr [rbp+arg_0], ebx
0x140108d00  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140108d05  jmp     loc_140108BB6
0x140108d0a  mov     rcx, [rbx+58h]; hHandle
0x140108d0e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140108d11  call    cs:__imp_WaitForSingleObject
0x140108d17  test    eax, eax
0x140108d19  jz      loc_140108BB4
0x140108d1f  mov     ecx, 80004005h
0x140108d24  cmp     eax, 80h
0x140108d29  jz      short loc_140108D3A
0x140108d2b  cmp     eax, 102h
0x140108d30  mov     ebx, 834500CBh
0x140108d35  cmovnz  ebx, ecx
0x140108d38  jmp     short loc_140108D3F
0x140108d3a  mov     ebx, 834500CAh
0x140108d3f  mov     eax, cs:dword_140152118
0x140108d45  cmp     eax, 2
0x140108d48  jbe     loc_140108BB6
0x140108d4e  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140108d55  mov     [rbp+arg_18], 11Fh
0x140108d5c  mov     [rbp+var_18], rax
0x140108d60  lea     rdx, dword_140145A6C
0x140108d67  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140108d6e  mov     [rbp+var_20], rax
0x140108d72  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x140108d79  mov     [rbp+var_28], rax
0x140108d7d  lea     rax, [rbp+arg_0]
0x140108d81  mov     [rsp+80h+var_38], rax
0x140108d86  lea     rax, [rbp+var_18]
0x140108d8a  mov     [rsp+80h+var_40], rax
0x140108d8f  lea     rax, [rbp+arg_18]
0x140108d93  mov     [rsp+80h+var_48], rax
0x140108d98  lea     rax, [rbp+var_20]
0x140108d9c  mov     [rsp+80h+var_50], rax
0x140108da1  lea     rax, [rbp+var_30]
0x140108da5  mov     [rsp+80h+var_58], rax
0x140108daa  lea     rax, [rbp+var_28]
0x140108dae  jmp     loc_140108CF5
```
