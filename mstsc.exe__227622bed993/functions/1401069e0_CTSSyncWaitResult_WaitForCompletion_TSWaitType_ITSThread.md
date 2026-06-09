# CTSSyncWaitResult::WaitForCompletion(TSWaitType,ITSThread *)

- ea: `0x1401069e0`
- end: `0x140106c43`
- name: `?WaitForCompletion@CTSSyncWaitResult@@QEAAJW4TSWaitType@@PEAVITSThread@@@Z`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401011dc`
- `0x140103cf0`

## callees

- `0x140001010`
- `0x1400019e8`
- `0x140001b00`
- `0x14000dcac`
- `0x1401069e0`
- `0x140112010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140106a08`
- `KERNEL32!WaitForSingleObject` at `0x140106ba1`
- `KERNEL32!WaitForSingleObject` at `0x140106a08`
- `KERNEL32!WaitForSingleObject` at `0x140106ba1`

## string_xrefs

- `0x140106ab4`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140106b39`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140106bf7`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x140106b49`: `ThreadWaitForSingleObject failed with 0x%x`
- `0x140106ac4`: `ThreadWaitForSingleObject timed out`
- `0x140106a9b`: `WaitForCompletion`
- `0x140106b20`: `WaitForCompletion`
- `0x140106bde`: `WaitForCompletion`

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
    if ( (unsigned int)dword_140150118 > 5 )
    {
      v22 = "Event signaled, no need to wait";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140150118,
        (unsigned int)byte_140143951,
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v22) = 268;
        v17 = "WaitForCompletion";
        v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
        v19 = "ThreadWaitForSingleObject timed out";
        v23 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)&dword_14014390C,
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
      if ( (unsigned int)dword_140150118 <= 2 )
        goto LABEL_5;
      v23 = 272;
      v19 = "WaitForCompletion";
      v12 = &dword_1401439FC;
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
  if ( (unsigned int)dword_140150118 > 2 )
  {
    v23 = 287;
    v20 = "WaitForCompletion";
    v12 = (int *)byte_140143A45;
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
0x1401069e0  mov     [rsp-18h+arg_8], rbx
0x1401069e5  push    rbp
0x1401069e6  push    rsi
0x1401069e7  push    rdi
0x1401069e8  mov     rbp, rsp
0x1401069eb  sub     rsp, 80h
0x1401069f2  mov     rsi, r8
0x1401069f5  mov     [rbp+var_10], 0
0x1401069fd  mov     edi, edx
0x1401069ff  mov     rbx, rcx
0x140106a02  mov     rcx, [rcx+58h]; hHandle
0x140106a06  xor     edx, edx; dwMilliseconds
0x140106a08  call    cs:__imp_WaitForSingleObject
0x140106a0e  test    eax, eax
0x140106a10  jnz     short loc_140106A64
0x140106a12  mov     eax, cs:dword_140150118
0x140106a18  cmp     eax, 5
0x140106a1b  jbe     short loc_140106A44
0x140106a1d  lea     rax, aEventSignaledN; "Event signaled, no need to wait"
0x140106a24  mov     [rbp+arg_0], rax
0x140106a28  lea     rdx, byte_140143951
0x140106a2f  lea     rax, [rbp+arg_0]
0x140106a33  lea     rcx, dword_140150118
0x140106a3a  mov     [rsp+80h+var_60], rax
0x140106a3f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140106a44  xor     ebx, ebx
0x140106a46  lea     rcx, [rbp+var_10]
0x140106a4a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140106a4f  mov     eax, ebx
0x140106a51  mov     rbx, [rsp+80h+arg_8]
0x140106a59  add     rsp, 80h
0x140106a60  pop     rdi
0x140106a61  pop     rsi
0x140106a62  pop     rbp
0x140106a63  retn
0x140106a64  cmp     edi, 4
0x140106a67  jz      loc_140106B9A
0x140106a6d  mov     rax, [rsi]
0x140106a70  or      r9d, 0FFFFFFFFh
0x140106a74  mov     rdx, [rbx+58h]
0x140106a78  mov     r8d, edi
0x140106a7b  mov     rcx, rsi
0x140106a7e  mov     rax, [rax+48h]
0x140106a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140106a87  mov     ebx, eax
0x140106a89  cmp     eax, 83450004h
0x140106a8e  jnz     short loc_140106B09
0x140106a90  mov     ecx, cs:dword_140150118
0x140106a96  cmp     ecx, 2
0x140106a99  jbe     short loc_140106A46
0x140106a9b  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140106aa2  mov     dword ptr [rbp+arg_0], 10Ch
0x140106aa9  mov     [rbp+var_30], rax
0x140106aad  lea     rdx, dword_14014390C
0x140106ab4  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140106abb  mov     ecx, 80004005h
0x140106ac0  mov     [rbp+var_28], rax
0x140106ac4  lea     rax, aThreadwaitfors_0; "ThreadWaitForSingleObject timed out"
0x140106acb  mov     [rbp+var_20], rax
0x140106acf  lea     rax, [rbp+var_30]
0x140106ad3  mov     [rsp+80h+var_40], rax
0x140106ad8  lea     rax, [rbp+arg_0]
0x140106adc  mov     [rsp+80h+var_48], rax
0x140106ae1  lea     rax, [rbp+var_28]
0x140106ae5  mov     [rsp+80h+var_50], rax
0x140106aea  lea     rax, [rbp+arg_18]
0x140106aee  mov     [rsp+80h+var_58], rax
0x140106af3  lea     rax, [rbp+var_20]
0x140106af7  mov     [rsp+80h+var_60], rax
0x140106afc  mov     [rbp+arg_18], ecx
0x140106aff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140106b04  jmp     loc_140106A46
0x140106b09  test    ebx, ebx
0x140106b0b  jns     loc_140106A44
0x140106b11  mov     eax, cs:dword_140150118
0x140106b17  cmp     eax, 2
0x140106b1a  jbe     loc_140106A46
0x140106b20  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140106b27  mov     [rbp+arg_18], 110h
0x140106b2e  mov     [rbp+var_20], rax
0x140106b32  lea     rdx, dword_1401439FC
0x140106b39  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140106b40  mov     ecx, 80004005h
0x140106b45  mov     [rbp+var_28], rax
0x140106b49  lea     rax, aThreadwaitfors; "ThreadWaitForSingleObject failed with 0"...
0x140106b50  mov     [rbp+var_18], rax
0x140106b54  lea     rax, [rbp+arg_0]
0x140106b58  mov     [rsp+80h+var_38], rax
0x140106b5d  lea     rax, [rbp+var_20]
0x140106b61  mov     [rsp+80h+var_40], rax
0x140106b66  lea     rax, [rbp+arg_18]
0x140106b6a  mov     [rsp+80h+var_48], rax
0x140106b6f  lea     rax, [rbp+var_28]
0x140106b73  mov     [rsp+80h+var_50], rax
0x140106b78  lea     rax, [rbp+var_30]
0x140106b7c  mov     [rsp+80h+var_58], rax
0x140106b81  lea     rax, [rbp+var_18]
0x140106b85  mov     [rsp+80h+var_60], rax
0x140106b8a  mov     dword ptr [rbp+var_30], ecx
0x140106b8d  mov     dword ptr [rbp+arg_0], ebx
0x140106b90  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140106b95  jmp     loc_140106A46
0x140106b9a  mov     rcx, [rbx+58h]; hHandle
0x140106b9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140106ba1  call    cs:__imp_WaitForSingleObject
0x140106ba7  test    eax, eax
0x140106ba9  jz      loc_140106A44
0x140106baf  mov     ecx, 80004005h
0x140106bb4  cmp     eax, 80h
0x140106bb9  jz      short loc_140106BCA
0x140106bbb  cmp     eax, 102h
0x140106bc0  mov     ebx, 834500CBh
0x140106bc5  cmovnz  ebx, ecx
0x140106bc8  jmp     short loc_140106BCF
0x140106bca  mov     ebx, 834500CAh
0x140106bcf  mov     eax, cs:dword_140150118
0x140106bd5  cmp     eax, 2
0x140106bd8  jbe     loc_140106A46
0x140106bde  lea     rax, aWaitforcomplet_0; "WaitForCompletion"
0x140106be5  mov     [rbp+arg_18], 11Fh
0x140106bec  mov     [rbp+var_18], rax
0x140106bf0  lea     rdx, byte_140143A45
0x140106bf7  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140106bfe  mov     [rbp+var_20], rax
0x140106c02  lea     rax, aPalSystemSingl; "PAL_System_SingleCondWait failed with 0"...
0x140106c09  mov     [rbp+var_28], rax
0x140106c0d  lea     rax, [rbp+arg_0]
0x140106c11  mov     [rsp+80h+var_38], rax
0x140106c16  lea     rax, [rbp+var_18]
0x140106c1a  mov     [rsp+80h+var_40], rax
0x140106c1f  lea     rax, [rbp+arg_18]
0x140106c23  mov     [rsp+80h+var_48], rax
0x140106c28  lea     rax, [rbp+var_20]
0x140106c2c  mov     [rsp+80h+var_50], rax
0x140106c31  lea     rax, [rbp+var_30]
0x140106c35  mov     [rsp+80h+var_58], rax
0x140106c3a  lea     rax, [rbp+var_28]
0x140106c3e  jmp     loc_140106B85
```
