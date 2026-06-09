# CTSSyncWaitResult::SetCompleted(long)

- ea: `0x180029d70`
- end: `0x180029e25`
- name: `?SetCompleted@CTSSyncWaitResult@@UEAAJJ@Z`
- size: `181`
- prototype: `__int64 __fastcall(CTSSyncWaitResult *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000160c`
- `0x18001f088`
- `0x180029d70`

## string_xrefs

- `0x180029db9`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventrslt.cpp`
- `0x180029d9b`: `SetCompleted`

## pseudocode

```c
__int64 __fastcall CTSSyncWaitResult::SetCompleted(CTSSyncWaitResult *this, int a2)
{
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  const char *v6; // [rsp+50h] [rbp-18h] BYREF
  int v7; // [rsp+70h] [rbp+8h] BYREF
  int v8; // [rsp+78h] [rbp+10h] BYREF
  const char *v9; // [rsp+80h] [rbp+18h] BYREF
  const char *v10; // [rsp+88h] [rbp+20h] BYREF

  *((_DWORD *)this + 4) = a2;
  v2 = PAL_System_CondSignal(*((_QWORD *)this + 1));
  if ( v2 >= 0 )
  {
    return 0;
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v8 = 334;
    v9 = "SetCompleted";
    v7 = -2147467259;
    v10 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventrslt.cpp";
    v6 = "Failed to signal condition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)qword_18003FF38,
      v3,
      v4,
      (const unsigned __int16 **)&v6,
      (__int64)&v7,
      (const unsigned __int16 **)&v10,
      (__int64)&v8,
      (const unsigned __int16 **)&v9);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180029d70  push    rbx
0x180029d72  sub     rsp, 60h
0x180029d76  mov     [rcx+10h], edx
0x180029d79  mov     rcx, [rcx+8]
0x180029d7d  call    PAL_System_CondSignal
0x180029d82  mov     ebx, eax
0x180029d84  test    eax, eax
0x180029d86  jns     loc_180029E1B
0x180029d8c  mov     ecx, cs:dword_180044008
0x180029d92  cmp     ecx, 2
0x180029d95  jbe     loc_180029E1D
0x180029d9b  lea     rax, aSetcompleted; "SetCompleted"
0x180029da2  mov     [rsp+68h+arg_8], 14Eh
0x180029daa  mov     [rsp+68h+arg_10], rax
0x180029db2  lea     rdx, qword_18003FF38
0x180029db9  lea     rax, aOnecoreTermsrv; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180029dc0  mov     [rsp+68h+arg_0], 80004005h
0x180029dc8  mov     [rsp+68h+arg_18], rax
0x180029dd0  lea     rax, aFailedToSignal_2; "Failed to signal condition"
0x180029dd7  mov     [rsp+68h+var_18], rax
0x180029ddc  lea     rax, [rsp+68h+arg_10]
0x180029de4  mov     [rsp+68h+var_28], rax
0x180029de9  lea     rax, [rsp+68h+arg_8]
0x180029dee  mov     [rsp+68h+var_30], rax
0x180029df3  lea     rax, [rsp+68h+arg_18]
0x180029dfb  mov     [rsp+68h+var_38], rax
0x180029e00  lea     rax, [rsp+68h+arg_0]
0x180029e05  mov     [rsp+68h+var_40], rax
0x180029e0a  lea     rax, [rsp+68h+var_18]
0x180029e0f  mov     [rsp+68h+var_48], rax
0x180029e14  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180029e19  jmp     short loc_180029E1D
0x180029e1b  xor     ebx, ebx
0x180029e1d  mov     eax, ebx
0x180029e1f  add     rsp, 60h
0x180029e23  pop     rbx
0x180029e24  retn
```
