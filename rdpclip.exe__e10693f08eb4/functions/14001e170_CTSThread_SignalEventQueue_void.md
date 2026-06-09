# CTSThread::SignalEventQueue(void)

- ea: `0x14001e170`
- end: `0x14001e307`
- name: `?SignalEventQueue@CTSThread@@MEAAJXZ`
- size: `407`
- prototype: `__int64 __fastcall(CTSThread *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001a520`
- `0x14001c210`
- `0x14001dad0`
- `0x14001ee50`
- `0x14001fcd0`

## callees

- `0x1400014d4`
- `0x1400184b4`
- `0x14001e170`
- `0x14006b010`

## string_xrefs

- `0x14001e1e0`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e21f`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e27a`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e2b2`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001e1eb`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x14001e285`: `Failed to add thread for OnNotifyThreadMessage callback`
- `0x14001e22a`: `_threadSignal is NULL!`
- `0x14001e2bd`: `_hThreadSignalEvent is NULL!`

## pseudocode

```c
__int64 __fastcall CTSThread::SignalEventQueue(CTSThread *this, __int64 a2, int a3, int a4)
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
  if ( *((_DWORD *)this + 46) )
  {
    if ( *((_QWORD *)this + 85) )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 92) + 64LL))(*((_QWORD *)this + 92));
      if ( v4 < 0 )
      {
        LODWORD(this) = dword_1400880C8;
        if ( (unsigned int)dword_1400880C8 > 2 )
        {
          v9 = 2570;
          v11 = "SignalEventQueue";
          v5 = &byte_14007E45F;
          v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
          v6 = "Failed to add thread for OnNotifyThreadMessage callback";
LABEL_14:
          v8 = v6;
          v10 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)this,
            (_DWORD)v5,
            a3,
            a4,
            (__int64)&v8,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v9,
            (__int64)&v11);
        }
      }
    }
    else if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v9 = 2575;
      v11 = "SignalEventQueue";
      v5 = (char *)word_14007E41A;
      v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v6 = "_threadSignal is NULL!";
      goto LABEL_14;
    }
  }
  else
  {
    this = (CTSThread *)*((_QWORD *)this + 86);
    if ( this == (CTSThread *)-1LL )
    {
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v9 = 2588;
        v11 = "SignalEventQueue";
        v5 = (char *)qword_14007E390;
        v12 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v6 = "_hThreadSignalEvent is NULL!";
        goto LABEL_14;
      }
    }
    else
    {
      v4 = PAL_System_CondSignal();
      if ( v4 < 0 && (unsigned int)dword_1400880C8 > 2 )
      {
        v9 = 2583;
        v11 = "SignalEventQueue";
        v5 = byte_14007E3D5;
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
0x14001e170  push    rbp
0x14001e172  push    rbx
0x14001e173  push    rdi
0x14001e174  mov     rbp, rsp
0x14001e177  sub     rsp, 60h
0x14001e17b  mov     edi, 80004005h
0x14001e180  mov     ebx, edi
0x14001e182  cmp     dword ptr [rcx+0B8h], 0
0x14001e189  jz      loc_14001E236
0x14001e18f  mov     rdx, [rcx+2A8h]
0x14001e196  test    rdx, rdx
0x14001e199  jz      short loc_14001E1F7
0x14001e19b  mov     rcx, [rcx+2E0h]
0x14001e1a2  mov     rax, [rcx]
0x14001e1a5  mov     rax, [rax+40h]
0x14001e1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e1ae  mov     ebx, eax
0x14001e1b0  test    eax, eax
0x14001e1b2  jns     loc_14001E2FD
0x14001e1b8  mov     ecx, cs:dword_1400880C8
0x14001e1be  cmp     ecx, 2
0x14001e1c1  jbe     loc_14001E2FD
0x14001e1c7  lea     rax, aSignaleventque; "SignalEventQueue"
0x14001e1ce  mov     [rbp+arg_0], 0A0Ah
0x14001e1d5  mov     [rbp+arg_10], rax
0x14001e1d9  lea     rdx, byte_14007E45F
0x14001e1e0  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e1e7  mov     [rbp+arg_18], rax
0x14001e1eb  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x14001e1f2  jmp     loc_14001E2C4
0x14001e1f7  mov     eax, cs:dword_1400880C8
0x14001e1fd  cmp     eax, 2
0x14001e200  jbe     loc_14001E2FD
0x14001e206  lea     rax, aSignaleventque; "SignalEventQueue"
0x14001e20d  mov     [rbp+arg_0], 0A0Fh
0x14001e214  mov     [rbp+arg_10], rax
0x14001e218  lea     rdx, word_14007E41A
0x14001e21f  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e226  mov     [rbp+arg_18], rax
0x14001e22a  lea     rax, aThreadsignalIs; "_threadSignal is NULL!"
0x14001e231  jmp     loc_14001E2C4
0x14001e236  mov     rcx, [rcx+2B0h]
0x14001e23d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001e241  jz      short loc_14001E28E
0x14001e243  call    PAL_System_CondSignal
0x14001e248  mov     ebx, eax
0x14001e24a  test    eax, eax
0x14001e24c  jns     loc_14001E2FD
0x14001e252  mov     eax, cs:dword_1400880C8
0x14001e258  cmp     eax, 2
0x14001e25b  jbe     loc_14001E2FD
0x14001e261  lea     rax, aSignaleventque; "SignalEventQueue"
0x14001e268  mov     [rbp+arg_0], 0A17h
0x14001e26f  mov     [rbp+arg_10], rax
0x14001e273  lea     rdx, byte_14007E3D5
0x14001e27a  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e281  mov     [rbp+arg_18], rax
0x14001e285  lea     rax, aFailedToAddThr; "Failed to add thread for OnNotifyThread"...
0x14001e28c  jmp     short loc_14001E2C4
0x14001e28e  mov     eax, cs:dword_1400880C8
0x14001e294  cmp     eax, 2
0x14001e297  jbe     short loc_14001E2FD
0x14001e299  lea     rax, aSignaleventque; "SignalEventQueue"
0x14001e2a0  mov     [rbp+arg_0], 0A1Ch
0x14001e2a7  mov     [rbp+arg_10], rax
0x14001e2ab  lea     rdx, qword_14007E390
0x14001e2b2  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001e2b9  mov     [rbp+arg_18], rax
0x14001e2bd  lea     rax, aHthreadsignale; "_hThreadSignalEvent is NULL!"
0x14001e2c4  mov     [rbp+var_10], rax
0x14001e2c8  lea     rax, [rbp+arg_10]
0x14001e2cc  mov     [rsp+60h+var_20], rax
0x14001e2d1  lea     rax, [rbp+arg_0]
0x14001e2d5  mov     [rsp+60h+var_28], rax
0x14001e2da  lea     rax, [rbp+arg_18]
0x14001e2de  mov     [rsp+60h+var_30], rax
0x14001e2e3  lea     rax, [rbp+arg_8]
0x14001e2e7  mov     [rsp+60h+var_38], rax
0x14001e2ec  lea     rax, [rbp+var_10]
0x14001e2f0  mov     [rsp+60h+var_40], rax
0x14001e2f5  mov     [rbp+arg_8], edi
0x14001e2f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001e2fd  mov     eax, ebx
0x14001e2ff  add     rsp, 60h
0x14001e303  pop     rdi
0x14001e304  pop     rbx
0x14001e305  pop     rbp
0x14001e306  retn
```
