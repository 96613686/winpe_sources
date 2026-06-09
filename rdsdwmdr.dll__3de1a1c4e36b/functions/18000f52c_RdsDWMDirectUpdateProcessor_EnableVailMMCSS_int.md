# RdsDWMDirectUpdateProcessor::EnableVailMMCSS(int)

- ea: `0x18000f52c`
- end: `0x18000f66a`
- name: `?EnableVailMMCSS@RdsDWMDirectUpdateProcessor@@IEAAJH@Z`
- size: `318`
- prototype: `__int64 __fastcall(RdsDWMDirectUpdateProcessor *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000f670`
- `0x180010a30`

## callees

- `0x18000160c`
- `0x180001724`
- `0x18000f52c`
- `0x18002c010`

## string_xrefs

- `0x18000f596`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000f60f`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000f61d`: `EnableVailMMCSS failed: Aux redirection channel is not ready`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::EnableVailMMCSS(
        RdsDWMDirectUpdateProcessor *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // ebx
  const char *v10; // [rsp+50h] [rbp-20h] BYREF
  const char *v11; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v12[2]; // [rsp+60h] [rbp-10h] BYREF
  int v13; // [rsp+80h] [rbp+10h] BYREF
  int v14; // [rsp+90h] [rbp+20h] BYREF
  const char *v15; // [rsp+98h] [rbp+28h] BYREF

  v4 = *((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v4 + 56) + 48LL))(v4 + 56);
    v8 = v5;
    if ( v5 < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v13 = 1209;
      v15 = "Failed to send enable MMCSS message";
      v14 = v5;
      v10 = "EnableVailMMCSS";
      v11 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v12[0] = (const unsigned __int16 *)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)&dword_180039F24,
        v6,
        v7,
        v12,
        (__int64)&v14,
        (const unsigned __int16 **)&v11,
        (__int64)&v13,
        (const unsigned __int16 **)&v10,
        (const unsigned __int16 **)&v15);
    }
  }
  else
  {
    v8 = 0;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v13 = 1213;
      v15 = "EnableVailMMCSS";
      v14 = 0;
      v12[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v11 = "EnableVailMMCSS failed: Aux redirection channel is not ready";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)&byte_180039EDF,
        a3,
        a4,
        (const unsigned __int16 **)&v11,
        (__int64)&v14,
        v12,
        (__int64)&v13,
        (const unsigned __int16 **)&v15);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000f52c  mov     [rsp-8+arg_8], rbx
0x18000f531  push    rbp
0x18000f532  mov     rbp, rsp
0x18000f535  sub     rsp, 70h
0x18000f539  mov     rcx, [rcx+38h]
0x18000f53d  test    rcx, rcx
0x18000f540  jz      loc_18000F5E9
0x18000f546  add     rcx, 38h ; '8'
0x18000f54a  mov     rax, [rcx]
0x18000f54d  mov     rax, [rax+30h]
0x18000f551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f556  mov     ebx, eax
0x18000f558  test    eax, eax
0x18000f55a  jns     loc_18000F65A
0x18000f560  mov     ecx, cs:dword_180044008
0x18000f566  cmp     ecx, 2
0x18000f569  jbe     loc_18000F65A
0x18000f56f  lea     rax, aFailedToSendEn; "Failed to send enable MMCSS message"
0x18000f576  mov     [rbp+arg_0], 4B9h
0x18000f57d  mov     [rbp+arg_18], rax
0x18000f581  lea     rdx, dword_180039F24
0x18000f588  lea     rax, aEnablevailmmcs_0; "EnableVailMMCSS"
0x18000f58f  mov     [rbp+arg_10], ebx
0x18000f592  mov     [rbp+var_20], rax
0x18000f596  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000f59d  mov     [rbp+var_18], rax
0x18000f5a1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000f5a8  mov     [rbp+var_10], rax
0x18000f5ac  lea     rax, [rbp+arg_18]
0x18000f5b0  mov     [rsp+70h+var_28], rax
0x18000f5b5  lea     rax, [rbp+var_20]
0x18000f5b9  mov     [rsp+70h+var_30], rax
0x18000f5be  lea     rax, [rbp+arg_0]
0x18000f5c2  mov     [rsp+70h+var_38], rax
0x18000f5c7  lea     rax, [rbp+var_18]
0x18000f5cb  mov     [rsp+70h+var_40], rax
0x18000f5d0  lea     rax, [rbp+arg_10]
0x18000f5d4  mov     [rsp+70h+var_48], rax
0x18000f5d9  lea     rax, [rbp+var_10]
0x18000f5dd  mov     [rsp+70h+var_50], rax
0x18000f5e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000f5e7  jmp     short loc_18000F65A
0x18000f5e9  mov     eax, cs:dword_180044008
0x18000f5ef  xor     ebx, ebx
0x18000f5f1  cmp     eax, 2
0x18000f5f4  jbe     short loc_18000F65A
0x18000f5f6  lea     rax, aEnablevailmmcs_0; "EnableVailMMCSS"
0x18000f5fd  mov     [rbp+arg_0], 4BDh
0x18000f604  mov     [rbp+arg_18], rax
0x18000f608  lea     rdx, byte_180039EDF
0x18000f60f  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000f616  mov     [rbp+arg_10], ebx
0x18000f619  mov     [rbp+var_10], rax
0x18000f61d  lea     rax, aEnablevailmmcs; "EnableVailMMCSS failed: Aux redirection"...
0x18000f624  mov     [rbp+var_18], rax
0x18000f628  lea     rax, [rbp+arg_18]
0x18000f62c  mov     [rsp+70h+var_30], rax
0x18000f631  lea     rax, [rbp+arg_0]
0x18000f635  mov     [rsp+70h+var_38], rax
0x18000f63a  lea     rax, [rbp+var_10]
0x18000f63e  mov     [rsp+70h+var_40], rax
0x18000f643  lea     rax, [rbp+arg_10]
0x18000f647  mov     [rsp+70h+var_48], rax
0x18000f64c  lea     rax, [rbp+var_18]
0x18000f650  mov     [rsp+70h+var_50], rax
0x18000f655  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f65a  mov     eax, ebx
0x18000f65c  mov     rbx, [rsp+70h+arg_8]
0x18000f664  add     rsp, 70h
0x18000f668  pop     rbp
0x18000f669  retn
```
