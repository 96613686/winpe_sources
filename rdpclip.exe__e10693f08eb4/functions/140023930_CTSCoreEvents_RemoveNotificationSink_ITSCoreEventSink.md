# CTSCoreEvents::RemoveNotificationSink(ITSCoreEventSink *)

- ea: `0x140023930`
- end: `0x140023b97`
- name: `?RemoveNotificationSink@CTSCoreEvents@@UEAAJPEAVITSCoreEventSink@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(CTSCoreEvents *__hidden this, struct ITSCoreEventSink *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400014d4`
- `0x1400015ec`
- `0x140005750`
- `0x1400081d0`
- `0x140023740`
- `0x140023930`
- `0x1400256b4`
- `0x14006b010`

## string_xrefs

- `0x140023982`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x140023ab1`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x140023b1e`: `onecore\termsrv\rdpplatform\common\devplatform\base\eventsvc.cpp`
- `0x140023969`: `RemoveNotificationSink`
- `0x140023a98`: `RemoveNotificationSink`
- `0x140023b05`: `RemoveNotificationSink`
- `0x140023a55`: `RemoveNotificationSink failed`

## pseudocode

```c
__int64 __fastcall CTSCoreEvents::RemoveNotificationSink(
        CTSCoreEvents *this,
        struct ITSCoreEventSink *a2,
        int a3,
        int a4)
{
  int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int ActivityIdPrefix; // eax
  int *v11; // rdx
  const char **v12; // rax
  const char **v14; // [rsp+30h] [rbp-50h]
  const char **v15; // [rsp+40h] [rbp-40h]
  const char *v16; // [rsp+50h] [rbp-30h] BYREF
  struct ITSAsyncCallback *v17; // [rsp+58h] [rbp-28h] BYREF
  const char *v18; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+A8h] [rbp+28h] BYREF
  int v22; // [rsp+B0h] [rbp+30h] BYREF
  int v23; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  v17 = 0;
  if ( !a2 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v22 = 839;
      v16 = "RemoveNotificationSink";
      v23 = -2147467259;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
      v19 = "NULL input parameter";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&word_14007F2C6,
        a3,
        a4,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v18,
        (__int64)&v22,
        (__int64)&v16);
    }
    v6 = -2147024809;
    goto LABEL_17;
  }
  v6 = (*(__int64 (__fastcall **)(struct ITSCoreEventSink *, unsigned int *))(*(_QWORD *)a2 + 24LL))(a2, &v21);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_1400880C8 <= 2 )
      goto LABEL_17;
    v23 = 857;
    v20[0] = "RemoveNotificationSink";
    v11 = &dword_14007F234;
    v19 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
    v18 = "GetEventID failed hr[0x%x]";
    v15 = (const char **)v20;
    v14 = &v19;
    v12 = &v18;
    goto LABEL_16;
  }
  v6 = (*(__int64 (__fastcall **)(struct ITSCoreEventSink *, struct ITSAsyncCallback **))(*(_QWORD *)a2 + 40LL))(
         a2,
         &v17);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_1400880C8 <= 2 )
      goto LABEL_17;
    v23 = 852;
    v19 = "RemoveNotificationSink";
    v11 = (int *)byte_14007F27D;
    v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\base\\eventsvc.cpp";
    v20[0] = "GetAsyncCallback failed hr[0x%x]";
    v15 = &v19;
    v14 = &v18;
    v12 = (const char **)v20;
LABEL_16:
    v22 = v6;
    LODWORD(v16) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (_DWORD)v11,
      v8,
      v9,
      (__int64)v12,
      (__int64)&v16,
      (__int64)v14,
      (__int64)&v23,
      (__int64)v15,
      (__int64)&v22);
    goto LABEL_17;
  }
  v6 = CTSCoreEvents::RemoveNotificationSink(this, v21, v17);
  if ( v6 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids,
      ActivityIdPrefix,
      (__int64)"RemoveNotificationSink failed",
      v6);
  }
LABEL_17:
  TCntPtr<IRdpHintApiEventSink>::SafeRelease(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140023930  mov     r11, rsp
0x140023933  mov     [r11+8], rbx
0x140023937  push    rbp
0x140023938  push    rsi
0x140023939  push    rdi
0x14002393a  mov     rbp, rsp
0x14002393d  sub     rsp, 80h
0x140023944  mov     rdi, rdx
0x140023947  mov     [rbp+arg_8], 0
0x14002394e  mov     rsi, rcx
0x140023951  mov     [rbp+var_28], 0
0x140023959  test    rdx, rdx
0x14002395c  jnz     short loc_1400239D6
0x14002395e  mov     eax, cs:dword_1400880C8
0x140023964  cmp     eax, 2
0x140023967  jbe     short loc_1400239CC
0x140023969  lea     rax, aRemovenotifica; "RemoveNotificationSink"
0x140023970  mov     [rbp+arg_10], 347h
0x140023977  mov     [rbp+var_30], rax
0x14002397b  lea     rdx, word_14007F2C6
0x140023982  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140023989  mov     [rbp+arg_18], 80004005h
0x140023990  mov     [rbp+var_20], rax
0x140023994  lea     rax, aNullInputParam; "NULL input parameter"
0x14002399b  mov     [rbp+var_18], rax
0x14002399f  lea     rax, [rbp+var_30]
0x1400239a3  mov     [r11-58h], rax
0x1400239a7  lea     rax, [rbp+arg_10]
0x1400239ab  mov     [r11-60h], rax
0x1400239af  lea     rax, [rbp+var_20]
0x1400239b3  mov     [r11-68h], rax
0x1400239b7  lea     rax, [rbp+arg_18]
0x1400239bb  mov     [r11-70h], rax
0x1400239bf  lea     rax, [rbp+var_18]
0x1400239c3  mov     [r11-78h], rax
0x1400239c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400239cc  mov     ebx, 80070057h
0x1400239d1  jmp     loc_140023B79
0x1400239d6  mov     rax, [rdx]
0x1400239d9  mov     rcx, rdi
0x1400239dc  lea     rdx, [rbp+arg_8]
0x1400239e0  mov     rax, [rax+18h]
0x1400239e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400239e9  mov     ebx, eax
0x1400239eb  test    eax, eax
0x1400239ed  js      loc_140023AFA
0x1400239f3  mov     rax, [rdi]
0x1400239f6  lea     rdx, [rbp+var_28]
0x1400239fa  mov     rcx, rdi
0x1400239fd  mov     rax, [rax+28h]
0x140023a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023a06  mov     ebx, eax
0x140023a08  test    eax, eax
0x140023a0a  js      short loc_140023A89
0x140023a0c  mov     r8, [rbp+var_28]; struct ITSAsyncCallback *
0x140023a10  mov     rcx, rsi; this
0x140023a13  mov     edx, [rbp+arg_8]; unsigned int
0x140023a16  call    ?RemoveNotificationSink@CTSCoreEvents@@UEAAJIPEAVITSAsyncCallback@@@Z; CTSCoreEvents::RemoveNotificationSink(uint,ITSAsyncCallback *)
0x140023a1b  mov     ebx, eax
0x140023a1d  test    eax, eax
0x140023a1f  jns     loc_140023B79
0x140023a25  mov     rax, cs:WPP_GLOBAL_Control
0x140023a2c  lea     rcx, WPP_GLOBAL_Control
0x140023a33  cmp     rax, rcx
0x140023a36  jz      loc_140023B79
0x140023a3c  test    byte ptr [rax+1Ch], 8
0x140023a40  jz      loc_140023B79
0x140023a46  cmp     byte ptr [rax+19h], 2
0x140023a4a  jb      loc_140023B79
0x140023a50  call    RdpX_GetActivityIdPrefix
0x140023a55  lea     rcx, aRemovenotifica_1; "RemoveNotificationSink failed"
0x140023a5c  mov     dword ptr [rsp+80h+var_58], ebx
0x140023a60  mov     [rsp+80h+var_60], rcx
0x140023a65  lea     r8, WPP_4fc62642b6223d8497902ab729b8bebd_Traceguids
0x140023a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a73  mov     edx, 28h ; '('
0x140023a78  mov     r9d, eax
0x140023a7b  mov     rcx, [rcx+10h]
0x140023a7f  call    WPP_SF_DsD
0x140023a84  jmp     loc_140023B79
0x140023a89  mov     eax, cs:dword_1400880C8
0x140023a8f  cmp     eax, 2
0x140023a92  jbe     loc_140023B79
0x140023a98  lea     rax, aRemovenotifica; "RemoveNotificationSink"
0x140023a9f  mov     [rbp+arg_18], 354h
0x140023aa6  mov     [rbp+var_18], rax
0x140023aaa  lea     rdx, byte_14007F27D
0x140023ab1  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140023ab8  mov     [rbp+var_20], rax
0x140023abc  lea     rax, aGetasynccallba; "GetAsyncCallback failed hr[0x%x]"
0x140023ac3  mov     [rbp+var_10], rax
0x140023ac7  lea     rax, [rbp+arg_10]
0x140023acb  mov     [rsp+80h+var_38], rax
0x140023ad0  lea     rax, [rbp+var_18]
0x140023ad4  mov     [rsp+80h+var_40], rax
0x140023ad9  lea     rax, [rbp+arg_18]
0x140023add  mov     [rsp+80h+var_48], rax
0x140023ae2  lea     rax, [rbp+var_20]
0x140023ae6  mov     [rsp+80h+var_50], rax
0x140023aeb  lea     rax, [rbp+var_30]
0x140023aef  mov     [rsp+80h+var_58], rax
0x140023af4  lea     rax, [rbp+var_10]
0x140023af8  jmp     short loc_140023B65
0x140023afa  mov     eax, cs:dword_1400880C8
0x140023b00  cmp     eax, 2
0x140023b03  jbe     short loc_140023B79
0x140023b05  lea     rax, aRemovenotifica; "RemoveNotificationSink"
0x140023b0c  mov     [rbp+arg_18], 359h
0x140023b13  mov     [rbp+var_10], rax
0x140023b17  lea     rdx, dword_14007F234
0x140023b1e  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140023b25  mov     [rbp+var_18], rax
0x140023b29  lea     rax, aGeteventidFail; "GetEventID failed hr[0x%x]"
0x140023b30  mov     [rbp+var_20], rax
0x140023b34  lea     rax, [rbp+arg_10]
0x140023b38  mov     [rsp+80h+var_38], rax
0x140023b3d  lea     rax, [rbp+var_10]
0x140023b41  mov     [rsp+80h+var_40], rax
0x140023b46  lea     rax, [rbp+arg_18]
0x140023b4a  mov     [rsp+80h+var_48], rax
0x140023b4f  lea     rax, [rbp+var_18]
0x140023b53  mov     [rsp+80h+var_50], rax
0x140023b58  lea     rax, [rbp+var_30]
0x140023b5c  mov     [rsp+80h+var_58], rax
0x140023b61  lea     rax, [rbp+var_20]
0x140023b65  mov     [rsp+80h+var_60], rax
0x140023b6a  mov     [rbp+arg_10], ebx
0x140023b6d  mov     dword ptr [rbp+var_30], 80004005h
0x140023b74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140023b79  lea     rcx, [rbp+var_28]
0x140023b7d  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140023b82  mov     eax, ebx
0x140023b84  mov     rbx, [rsp+80h+arg_0]
0x140023b8c  add     rsp, 80h
0x140023b93  pop     rdi
0x140023b94  pop     rsi
0x140023b95  pop     rbp
0x140023b96  retn
```
