# CTSThread::SignalEventQueue(void)

- ea: `0x180026b30`
- end: `0x180026cc7`
- name: `?SignalEventQueue@CTSThread@@MEAAJXZ`
- size: `407`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022f00`
- `0x180024bb0`
- `0x180026480`
- `0x180027810`
- `0x180028934`

## callees

- `0x18000160c`
- `0x18001f088`
- `0x180026b30`
- `0x18002c010`

## string_xrefs

- `0x180026ba0`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026bdf`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026c3a`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026c72`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180026bab`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x180026c45`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x180026bea`: `_threadSignal is NULL!`
- `0x180026c7d`: `_hThreadSignalEvent is NULL!`

## pseudocode

```c
__int64 __fastcall CTSThread::SignalEventQueue(__int64 this, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  char *v5; // rdx
  const char *v6; // rax
  const char *v8; // [rsp+50h] [rbp-10h] BYREF
  int v9; // [rsp+80h] [rbp+20h] BYREF
  int v10; // [rsp+88h] [rbp+28h] BYREF
  const char *v11; // [rsp+90h] [rbp+30h] BYREF
  const char *v12; // [rsp+98h] [rbp+38h] BYREF

  v4 = -2147467259;
  if ( *(_DWORD *)(this + 184) )
  {
    if ( *(_QWORD *)(this + 680) )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(this + 736) + 64LL))(*(_QWORD *)(this + 736));
      if ( v4 < 0 )
      {
        this = (unsigned int)dword_180044008;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v9 = 2570;
          v11 = "SignalEventQueue";
          v5 = (char *)word_18003F572;
          v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
          v6 = "Failed to add thread for OnNotifyThreadMessage callback";
LABEL_14:
          v8 = v6;
          v10 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            this,
            (__int64)v5,
            a3,
            a4,
            (const unsigned __int16 **)&v8,
            (__int64)&v10,
            (const unsigned __int16 **)&v12,
            (__int64)&v9,
            (const unsigned __int16 **)&v11);
        }
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v9 = 2575;
      v11 = "SignalEventQueue";
      v5 = byte_18003F52D;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v6 = "_threadSignal is NULL!";
      goto LABEL_14;
    }
  }
  else
  {
    this = *(_QWORD *)(this + 688);
    if ( this == -1 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v9 = 2588;
        v11 = "SignalEventQueue";
        v5 = byte_18003F4A3;
        v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v6 = "_hThreadSignalEvent is NULL!";
        goto LABEL_14;
      }
    }
    else
    {
      v4 = PAL_System_CondSignal();
      if ( v4 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v9 = 2583;
        v11 = "SignalEventQueue";
        v5 = (char *)qword_18003F4E8;
        v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v6 = "Failed to add thread for OnNotifyThreadMessage callback";
        goto LABEL_14;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026b30  push    rbp
0x180026b32  push    rbx
0x180026b33  push    rdi
0x180026b34  mov     rbp, rsp
0x180026b37  sub     rsp, 60h
0x180026b3b  mov     edi, 80004005h
0x180026b40  mov     ebx, edi
0x180026b42  cmp     dword ptr [rcx+0B8h], 0
0x180026b49  jz      loc_180026BF6
0x180026b4f  mov     rdx, [rcx+2A8h]
0x180026b56  test    rdx, rdx
0x180026b59  jz      short loc_180026BB7
0x180026b5b  mov     rcx, [rcx+2E0h]
0x180026b62  mov     rax, [rcx]
0x180026b65  mov     rax, [rax+40h]
0x180026b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b6e  mov     ebx, eax
0x180026b70  test    eax, eax
0x180026b72  jns     loc_180026CBD
0x180026b78  mov     ecx, cs:dword_180044008
0x180026b7e  cmp     ecx, 2
0x180026b81  jbe     loc_180026CBD
0x180026b87  lea     rax, aSignaleventque; "SignalEventQueue"
0x180026b8e  mov     [rbp+arg_0], 0A0Ah
0x180026b95  mov     [rbp+arg_10], rax
0x180026b99  lea     rdx, word_18003F572
0x180026ba0  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026ba7  mov     [rbp+arg_18], rax
0x180026bab  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x180026bb2  jmp     loc_180026C84
0x180026bb7  mov     eax, cs:dword_180044008
0x180026bbd  cmp     eax, 2
0x180026bc0  jbe     loc_180026CBD
0x180026bc6  lea     rax, aSignaleventque; "SignalEventQueue"
0x180026bcd  mov     [rbp+arg_0], 0A0Fh
0x180026bd4  mov     [rbp+arg_10], rax
0x180026bd8  lea     rdx, byte_18003F52D
0x180026bdf  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026be6  mov     [rbp+arg_18], rax
0x180026bea  lea     rax, aThreadsignalIs; "_threadSignal is NULL!"
0x180026bf1  jmp     loc_180026C84
0x180026bf6  mov     rcx, [rcx+2B0h]
0x180026bfd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026c01  jz      short loc_180026C4E
0x180026c03  call    PAL_System_CondSignal
0x180026c08  mov     ebx, eax
0x180026c0a  test    eax, eax
0x180026c0c  jns     loc_180026CBD
0x180026c12  mov     eax, cs:dword_180044008
0x180026c18  cmp     eax, 2
0x180026c1b  jbe     loc_180026CBD
0x180026c21  lea     rax, aSignaleventque; "SignalEventQueue"
0x180026c28  mov     [rbp+arg_0], 0A17h
0x180026c2f  mov     [rbp+arg_10], rax
0x180026c33  lea     rdx, qword_18003F4E8
0x180026c3a  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026c41  mov     [rbp+arg_18], rax
0x180026c45  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x180026c4c  jmp     short loc_180026C84
0x180026c4e  mov     eax, cs:dword_180044008
0x180026c54  cmp     eax, 2
0x180026c57  jbe     short loc_180026CBD
0x180026c59  lea     rax, aSignaleventque; "SignalEventQueue"
0x180026c60  mov     [rbp+arg_0], 0A1Ch
0x180026c67  mov     [rbp+arg_10], rax
0x180026c6b  lea     rdx, byte_18003F4A3
0x180026c72  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180026c79  mov     [rbp+arg_18], rax
0x180026c7d  lea     rax, aHthreadsignale; "_hThreadSignalEvent is NULL!"
0x180026c84  mov     [rbp+var_10], rax
0x180026c88  lea     rax, [rbp+arg_10]
0x180026c8c  mov     [rsp+60h+var_20], rax
0x180026c91  lea     rax, [rbp+arg_0]
0x180026c95  mov     [rsp+60h+var_28], rax
0x180026c9a  lea     rax, [rbp+arg_18]
0x180026c9e  mov     [rsp+60h+var_30], rax
0x180026ca3  lea     rax, [rbp+arg_8]
0x180026ca7  mov     [rsp+60h+var_38], rax
0x180026cac  lea     rax, [rbp+var_10]
0x180026cb0  mov     [rsp+60h+var_40], rax
0x180026cb5  mov     [rbp+arg_8], edi
0x180026cb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026cbd  mov     eax, ebx
0x180026cbf  add     rsp, 60h
0x180026cc3  pop     rdi
0x180026cc4  pop     rbx
0x180026cc5  pop     rbp
0x180026cc6  retn
```
