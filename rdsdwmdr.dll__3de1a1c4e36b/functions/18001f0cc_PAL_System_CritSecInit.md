# PAL_System_CritSecInit

- ea: `0x18001f0cc`
- end: `0x18001f239`
- name: `PAL_System_CritSecInit`
- size: `365`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014044`
- `0x18002a278`

## callees

- `0x18000160c`
- `0x18001f0cc`
- `0x18001f2b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f19b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f19b`

## string_xrefs

- `0x18001f119`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001f1cb`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CritSecInit(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  int v8; // [rsp+70h] [rbp+8h] BYREF
  int v9; // [rsp+78h] [rbp+10h] BYREF
  const char *v10; // [rsp+80h] [rbp+18h] BYREF
  const char *v11; // [rsp+88h] [rbp+20h] BYREF

  if ( !a1 )
    return 2147942487LL;
  v3 = (struct _RTL_CRITICAL_SECTION *)PAL_System_MemAlloc(40);
  if ( v3 )
  {
    LODWORD(v10) = -2147467259;
    *a1 = v3;
    InitializeCriticalSection(v3);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v10 = "PAL_System_CritSecInit";
      v8 = 698;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v9 = -2147467259;
      v7 = "Failed to allocate CRITICAL_SECTION";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v4,
        (__int64)qword_18003ECE8,
        v5,
        v6,
        (const unsigned __int16 **)&v7,
        (__int64)&v9,
        (const unsigned __int16 **)&v11,
        (__int64)&v8,
        (const unsigned __int16 **)&v10);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001f0cc  push    rbx
0x18001f0ce  sub     rsp, 60h
0x18001f0d2  mov     rbx, rcx
0x18001f0d5  test    rcx, rcx
0x18001f0d8  jnz     short loc_18001F0E4
0x18001f0da  mov     eax, 80070057h
0x18001f0df  jmp     loc_18001F233
0x18001f0e4  mov     ecx, 28h ; '('
0x18001f0e9  call    PAL_System_MemAlloc
0x18001f0ee  test    rax, rax
0x18001f0f1  jnz     loc_18001F18A
0x18001f0f7  mov     eax, cs:dword_180044008
0x18001f0fd  cmp     eax, 2
0x18001f100  jbe     short loc_18001F180
0x18001f102  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x18001f109  mov     [rsp+68h+arg_10], rax
0x18001f111  mov     [rsp+68h+arg_0], 2BAh
0x18001f119  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001f120  mov     [rsp+68h+arg_18], rax
0x18001f128  mov     [rsp+68h+arg_8], 80004005h
0x18001f130  lea     rax, aFailedToAlloca_3; "Failed to allocate CRITICAL_SECTION"
0x18001f137  mov     [rsp+68h+var_18], rax
0x18001f13c  lea     rax, [rsp+68h+arg_10]
0x18001f144  mov     [rsp+68h+var_28], rax
0x18001f149  lea     rax, [rsp+68h+arg_0]
0x18001f14e  mov     [rsp+68h+var_30], rax
0x18001f153  lea     rax, [rsp+68h+arg_18]
0x18001f15b  mov     [rsp+68h+var_38], rax
0x18001f160  lea     rax, [rsp+68h+arg_8]
0x18001f165  mov     [rsp+68h+var_40], rax
0x18001f16a  lea     rax, [rsp+68h+var_18]
0x18001f16f  mov     [rsp+68h+var_48], rax
0x18001f174  lea     rdx, qword_18003ECE8
0x18001f17b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001f180  mov     eax, 8007000Eh
0x18001f185  jmp     loc_18001F233
0x18001f18a  mov     dword ptr [rsp+68h+arg_10], 80004005h
0x18001f195  mov     [rbx], rax
0x18001f198  mov     rcx, rax; lpCriticalSection
0x18001f19b  call    cs:__imp_InitializeCriticalSection
0x18001f1a1  nop
0x18001f1a2  xor     eax, eax
0x18001f1a4  jmp     loc_18001F233
0x18001f1a9  mov     eax, cs:dword_180044008
0x18001f1af  cmp     eax, 2
0x18001f1b2  jbe     short loc_18001F22C
0x18001f1b4  lea     rax, aPalSystemCrits; "PAL_System_CritSecInit"
0x18001f1bb  mov     [rsp+68h+arg_18], rax
0x18001f1c3  mov     [rsp+68h+arg_0], 2C5h
0x18001f1cb  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001f1d2  mov     [rsp+68h+var_18], rax
0x18001f1d7  mov     [rsp+68h+arg_8], 80004005h
0x18001f1df  lea     rax, aFailToInitialz; "Fail to initialzie critical section"
0x18001f1e6  mov     [rsp+68h+var_10], rax
0x18001f1eb  lea     rax, [rsp+68h+arg_18]
0x18001f1f3  mov     [rsp+68h+var_28], rax
0x18001f1f8  lea     rax, [rsp+68h+arg_0]
0x18001f1fd  mov     [rsp+68h+var_30], rax
0x18001f202  lea     rax, [rsp+68h+var_18]
0x18001f207  mov     [rsp+68h+var_38], rax
0x18001f20c  lea     rax, [rsp+68h+arg_8]
0x18001f211  mov     [rsp+68h+var_40], rax
0x18001f216  lea     rax, [rsp+68h+var_10]
0x18001f21b  mov     [rsp+68h+var_48], rax
0x18001f220  lea     rdx, byte_18003EF87
0x18001f227  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001f22c  mov     eax, dword ptr [rsp+68h+arg_10]
0x18001f233  add     rsp, 60h
0x18001f237  pop     rbx
0x18001f238  retn
```
