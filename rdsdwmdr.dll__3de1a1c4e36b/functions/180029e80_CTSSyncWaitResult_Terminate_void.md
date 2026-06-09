# CTSSyncWaitResult::Terminate(void)

- ea: `0x180029e80`
- end: `0x180029f5a`
- name: `?Terminate@CTSSyncWaitResult@@UEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(CTSSyncWaitResult *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800293c4`

## callees

- `0x18000160c`
- `0x18001f298`
- `0x180029e80`

## string_xrefs

- `0x180029edc`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::Terminate(CTSSyncWaitResult *this)
{
  int v2; // edi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v7; // [rsp+50h] [rbp-28h] BYREF
  int v8; // [rsp+80h] [rbp+8h] BYREF
  int v9; // [rsp+88h] [rbp+10h] BYREF
  const char *v10; // [rsp+90h] [rbp+18h] BYREF
  const char *v11; // [rsp+98h] [rbp+20h] BYREF

  v2 = -2147467259;
  v3 = *((_QWORD *)this + 10);
  if ( v3 != -1 )
  {
    v2 = PAL_System_HandleFree(v3);
    if ( v2 < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v8 = 138;
      v10 = "Terminate";
      v9 = -2147467259;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
      v7 = "Failed to free handle";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&word_1800400BE,
        v4,
        v5,
        (const unsigned __int16 **)&v7,
        (__int64)&v9,
        (const unsigned __int16 **)&v11,
        (__int64)&v8,
        (const unsigned __int16 **)&v10);
    }
    *((_QWORD *)this + 10) = -1;
  }
  *((_DWORD *)this + 5) |= 4u;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180029e80  push    rbx
0x180029e82  push    rdi
0x180029e83  sub     rsp, 68h
0x180029e87  mov     rbx, rcx
0x180029e8a  mov     edi, 80004005h
0x180029e8f  mov     rcx, [rcx+50h]
0x180029e93  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029e97  jz      loc_180029F4D
0x180029e9d  call    PAL_System_HandleFree
0x180029ea2  mov     edi, eax
0x180029ea4  test    eax, eax
0x180029ea6  jns     loc_180029F45
0x180029eac  mov     ecx, cs:dword_180044008
0x180029eb2  cmp     ecx, 2
0x180029eb5  jbe     loc_180029F45
0x180029ebb  lea     rax, aTerminate; "Terminate"
0x180029ec2  mov     [rsp+78h+arg_0], 8Ah
0x180029ecd  mov     [rsp+78h+arg_10], rax
0x180029ed5  lea     rdx, word_1800400BE
0x180029edc  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180029ee3  mov     [rsp+78h+arg_8], 80004005h
0x180029eee  mov     [rsp+78h+arg_18], rax
0x180029ef6  lea     rax, aFailedToFreeHa; "Failed to free handle"
0x180029efd  mov     [rsp+78h+var_28], rax
0x180029f02  lea     rax, [rsp+78h+arg_10]
0x180029f0a  mov     [rsp+78h+var_38], rax
0x180029f0f  lea     rax, [rsp+78h+arg_0]
0x180029f17  mov     [rsp+78h+var_40], rax
0x180029f1c  lea     rax, [rsp+78h+arg_18]
0x180029f24  mov     [rsp+78h+var_48], rax
0x180029f29  lea     rax, [rsp+78h+arg_8]
0x180029f31  mov     [rsp+78h+var_50], rax
0x180029f36  lea     rax, [rsp+78h+var_28]
0x180029f3b  mov     [rsp+78h+var_58], rax
0x180029f40  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180029f45  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x180029f4d  or      dword ptr [rbx+14h], 4
0x180029f51  mov     eax, edi
0x180029f53  add     rsp, 68h
0x180029f57  pop     rdi
0x180029f58  pop     rbx
0x180029f59  retn
```
