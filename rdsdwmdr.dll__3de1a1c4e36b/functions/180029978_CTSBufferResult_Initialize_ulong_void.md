# CTSBufferResult::Initialize(ulong,void *)

- ea: `0x180029978`
- end: `0x180029a68`
- name: `?Initialize@CTSBufferResult@@IEAAJKPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(CTSBufferResult *this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800294b0`
- `0x180029a70`

## callees

- `0x18000160c`
- `0x18001f2b8`
- `0x180029978`
- `0x18002b922`

## string_xrefs

- `0x1800299f0`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`

## pseudocode

```c
__int64 __fastcall CTSBufferResult::Initialize(CTSBufferResult *this, unsigned int a2, void *a3)
{
  void *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v11; // [rsp+50h] [rbp-28h] BYREF
  const char *v12; // [rsp+58h] [rbp-20h] BYREF
  int v13; // [rsp+80h] [rbp+8h] BYREF
  int v14; // [rsp+88h] [rbp+10h] BYREF
  const char *v15; // [rsp+98h] [rbp+20h] BYREF

  v6 = (void *)PAL_System_MemAlloc(a2);
  *((_QWORD *)this + 12) = v6;
  if ( v6 )
  {
    if ( a3 )
      memcpy_0(v6, a3, a2);
    *((_DWORD *)this + 22) = a2;
    *((_DWORD *)this + 26) = a2;
    *((_DWORD *)this + 7) |= 2u;
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v14 = 632;
      v15 = "Initialize";
      v13 = -2147467259;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v12 = "OOM on CTSBuffer cbLen allocation!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (__int64)byte_18003FE8D,
        v8,
        v9,
        (const unsigned __int16 **)&v12,
        (__int64)&v13,
        (const unsigned __int16 **)&v11,
        (__int64)&v14,
        (const unsigned __int16 **)&v15);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180029978  mov     [rsp+arg_10], rbx
0x18002997d  push    rbp
0x18002997e  push    rsi
0x18002997f  push    rdi
0x180029980  sub     rsp, 60h
0x180029984  mov     rsi, r8
0x180029987  mov     edi, edx
0x180029989  mov     rbx, rcx
0x18002998c  mov     ecx, edx
0x18002998e  call    PAL_System_MemAlloc
0x180029993  mov     [rbx+60h], rax
0x180029997  test    rax, rax
0x18002999a  jz      short loc_1800299C0
0x18002999c  test    rsi, rsi
0x18002999f  jz      short loc_1800299AF
0x1800299a1  mov     r8d, edi; Size
0x1800299a4  mov     rdx, rsi; Src
0x1800299a7  mov     rcx, rax; void *
0x1800299aa  call    memcpy_0
0x1800299af  mov     [rbx+58h], edi
0x1800299b2  mov     [rbx+68h], edi
0x1800299b5  or      dword ptr [rbx+1Ch], 2
0x1800299b9  xor     eax, eax
0x1800299bb  jmp     loc_180029A58
0x1800299c0  mov     eax, cs:dword_180044008
0x1800299c6  cmp     eax, 2
0x1800299c9  jbe     loc_180029A53
0x1800299cf  lea     rax, aInitialize; "Initialize"
0x1800299d6  mov     [rsp+78h+arg_8], 278h
0x1800299e1  mov     [rsp+78h+arg_18], rax
0x1800299e9  lea     rdx, byte_18003FE8D
0x1800299f0  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800299f7  mov     [rsp+78h+arg_0], 80004005h
0x180029a02  mov     [rsp+78h+var_28], rax
0x180029a07  lea     rax, aOomOnCtsbuffer_0; "OOM on CTSBuffer cbLen allocation!"
0x180029a0e  mov     [rsp+78h+var_20], rax
0x180029a13  lea     rax, [rsp+78h+arg_18]
0x180029a1b  mov     [rsp+78h+var_38], rax
0x180029a20  lea     rax, [rsp+78h+arg_8]
0x180029a28  mov     [rsp+78h+var_40], rax
0x180029a2d  lea     rax, [rsp+78h+var_28]
0x180029a32  mov     [rsp+78h+var_48], rax
0x180029a37  lea     rax, [rsp+78h+arg_0]
0x180029a3f  mov     [rsp+78h+var_50], rax
0x180029a44  lea     rax, [rsp+78h+var_20]
0x180029a49  mov     [rsp+78h+var_58], rax
0x180029a4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180029a53  mov     eax, 8007000Eh
0x180029a58  mov     rbx, [rsp+78h+arg_10]
0x180029a60  add     rsp, 60h
0x180029a64  pop     rdi
0x180029a65  pop     rsi
0x180029a66  pop     rbp
0x180029a67  retn
```
