# CTSSyncWaitResult::Initialize(void)

- ea: `0x180029af0`
- end: `0x180029ba4`
- name: `?Initialize@CTSSyncWaitResult@@UEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CTSSyncWaitResult *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025a70`

## callees

- `0x180001f98`
- `0x18001f03c`
- `0x180029af0`

## string_xrefs

- `0x180029b3a`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::Initialize(CTSSyncWaitResult *this)
{
  int v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // ebx
  const char *v7; // [rsp+50h] [rbp-10h] BYREF
  const char *v8; // [rsp+58h] [rbp-8h] BYREF
  int v9; // [rsp+80h] [rbp+20h] BYREF
  int v10; // [rsp+88h] [rbp+28h] BYREF
  int v11; // [rsp+90h] [rbp+30h] BYREF
  const char *v12; // [rsp+98h] [rbp+38h] BYREF

  v2 = PAL_System_CondAlloc(0);
  v5 = v2;
  if ( v2 >= 0 )
  {
    *((_DWORD *)this + 5) |= 2u;
    return 0;
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v9 = v2;
    v10 = 99;
    v12 = "Initialize";
    v7 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v8 = "PAL_System_CondAlloc failed! hr = 0x%x";
    v11 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180044008,
      (__int64)byte_180040103,
      v3,
      v4,
      (const unsigned __int16 **)&v8,
      (__int64)&v11,
      (const unsigned __int16 **)&v7,
      (__int64)&v10,
      (const unsigned __int16 **)&v12,
      (__int64)&v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180029af0  push    rbp
0x180029af2  push    rbx
0x180029af3  push    rdi
0x180029af4  mov     rbp, rsp
0x180029af7  sub     rsp, 60h
0x180029afb  mov     rdi, rcx
0x180029afe  lea     rdx, [rcx+50h]
0x180029b02  xor     ecx, ecx; bManualReset
0x180029b04  call    PAL_System_CondAlloc
0x180029b09  mov     ebx, eax
0x180029b0b  test    eax, eax
0x180029b0d  jns     loc_180029B94
0x180029b13  mov     ecx, cs:dword_180044008
0x180029b19  cmp     ecx, 2
0x180029b1c  jbe     short loc_180029B9A
0x180029b1e  mov     [rbp+arg_0], eax
0x180029b21  lea     rdx, byte_180040103
0x180029b28  lea     rax, aInitialize; "Initialize"
0x180029b2f  mov     [rbp+arg_8], 63h ; 'c'
0x180029b36  mov     [rbp+arg_18], rax
0x180029b3a  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180029b41  mov     [rbp+var_10], rax
0x180029b45  lea     rax, aPalSystemConda; "PAL_System_CondAlloc failed! hr = 0x%x"
0x180029b4c  mov     [rbp+var_8], rax
0x180029b50  lea     rax, [rbp+arg_0]
0x180029b54  mov     [rsp+60h+var_18], rax
0x180029b59  lea     rax, [rbp+arg_18]
0x180029b5d  mov     [rsp+60h+var_20], rax
0x180029b62  lea     rax, [rbp+arg_8]
0x180029b66  mov     [rsp+60h+var_28], rax
0x180029b6b  lea     rax, [rbp+var_10]
0x180029b6f  mov     [rsp+60h+var_30], rax
0x180029b74  lea     rax, [rbp+arg_10]
0x180029b78  mov     [rsp+60h+var_38], rax
0x180029b7d  lea     rax, [rbp+var_8]
0x180029b81  mov     [rsp+60h+var_40], rax
0x180029b86  mov     [rbp+arg_10], 80004005h
0x180029b8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180029b92  jmp     short loc_180029B9A
0x180029b94  or      dword ptr [rdi+14h], 2
0x180029b98  xor     ebx, ebx
0x180029b9a  mov     eax, ebx
0x180029b9c  add     rsp, 60h
0x180029ba0  pop     rdi
0x180029ba1  pop     rbx
0x180029ba2  pop     rbp
0x180029ba3  retn
```
