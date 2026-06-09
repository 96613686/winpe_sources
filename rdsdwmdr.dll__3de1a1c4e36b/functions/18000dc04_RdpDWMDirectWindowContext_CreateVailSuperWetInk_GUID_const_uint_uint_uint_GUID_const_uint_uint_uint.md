# RdpDWMDirectWindowContext::CreateVailSuperWetInk(_GUID const &,uint,uint,uint,_GUID const &,uint,uint,uint)

- ea: `0x18000dc04`
- end: `0x18000dd6d`
- name: `?CreateVailSuperWetInk@RdpDWMDirectWindowContext@@QEAAJAEBU_GUID@@III0III@Z`
- size: `361`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, const struct _GUID *, __int64, __int64, unsigned int, const struct _GUID *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fff0`

## callees

- `0x180001188`
- `0x18000160c`
- `0x18000dc04`
- `0x18002c010`

## string_xrefs

- `0x18000dc90`: `CreateVailSuperWetInk`
- `0x18000dd00`: `CreateVailSuperWetInk`
- `0x18000dd07`: `OnCreateVailSuperWetInk failed: Aux redirection channel is not ready`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::CreateVailSuperWetInk(
        RdpDWMDirectWindowContext *this,
        const struct _GUID *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        const struct _GUID *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9)
{
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  const char *v15; // [rsp+60h] [rbp-20h] BYREF
  const char *v16; // [rsp+68h] [rbp-18h] BYREF
  const char *v17; // [rsp+70h] [rbp-10h] BYREF
  const char *v18; // [rsp+78h] [rbp-8h] BYREF
  int v19; // [rsp+90h] [rbp+10h] BYREF

  v10 = *((_QWORD *)this + 83);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, _QWORD, _DWORD, unsigned int, const struct _GUID *, unsigned int, unsigned int, unsigned int))(*(_QWORD *)v10 + 24LL))(
            v10,
            *((_QWORD *)this + 8),
            a2,
            (unsigned int)a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9);
    if ( v11 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v19 = v11;
      v15 = "CreateVailSuperWetInk";
      v16 = "Failed to send the vail super wet ink creation message";
      v17 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"CreateVailSuperWetInk",
        (__int64)word_180039362,
        v12,
        v13,
        (const unsigned __int16 **)&v17,
        (const unsigned __int16 **)&v16,
        (__int64)&v19,
        (const unsigned __int16 **)&v15);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v19 = 528;
    v16 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v17 = "CreateVailSuperWetInk";
    v18 = "OnCreateVailSuperWetInk failed: Aux redirection channel is not ready";
    LODWORD(v15) = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)"CreateVailSuperWetInk",
      (__int64)byte_18003931D,
      a3,
      a4,
      (const unsigned __int16 **)&v18,
      (__int64)&v15,
      (const unsigned __int16 **)&v16,
      (__int64)&v19,
      (const unsigned __int16 **)&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18000dc04  mov     [rsp-8+arg_8], rbx
0x18000dc09  mov     [rsp-8+arg_10], rdi
0x18000dc0e  push    rbp
0x18000dc0f  mov     rbp, rsp
0x18000dc12  sub     rsp, 80h
0x18000dc19  mov     r11, rcx
0x18000dc1c  mov     ebx, r8d
0x18000dc1f  mov     rcx, [rcx+298h]
0x18000dc26  mov     rdi, rdx
0x18000dc29  test    rcx, rcx
0x18000dc2c  jz      loc_18000DCE3
0x18000dc32  mov     r10d, [rbp+arg_40]
0x18000dc36  mov     r8d, [rbp+arg_38]
0x18000dc3a  mov     edx, [rbp+arg_30]
0x18000dc3d  mov     rax, [rcx]
0x18000dc40  mov     [rsp+80h+var_38], r10d
0x18000dc45  mov     dword ptr [rsp+80h+var_40], r8d
0x18000dc4a  mov     r8, rdi
0x18000dc4d  mov     dword ptr [rsp+80h+var_48], edx
0x18000dc51  mov     rdx, [rbp+arg_28]
0x18000dc55  mov     rax, [rax+18h]
0x18000dc59  mov     [rsp+80h+var_50], rdx
0x18000dc5e  mov     edx, [rbp+arg_20]
0x18000dc61  mov     dword ptr [rsp+80h+var_58], edx
0x18000dc65  mov     rdx, [r11+40h]
0x18000dc69  mov     dword ptr [rsp+80h+var_60], r9d
0x18000dc6e  mov     r9d, ebx
0x18000dc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc76  test    eax, eax
0x18000dc78  jns     loc_18000DD56
0x18000dc7e  mov     ecx, cs:dword_180044008
0x18000dc84  cmp     ecx, 3
0x18000dc87  jbe     loc_18000DD56
0x18000dc8d  mov     [rbp+arg_0], eax
0x18000dc90  lea     rcx, aCreatevailsupe_0; "CreateVailSuperWetInk"
0x18000dc97  lea     rax, aFailedToSendTh_6; "Failed to send the vail super wet ink c"...
0x18000dc9e  mov     [rbp+var_20], rcx
0x18000dca2  mov     [rbp+var_18], rax
0x18000dca6  lea     rdx, word_180039362
0x18000dcad  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000dcb4  mov     [rbp+var_10], rax
0x18000dcb8  lea     rax, [rbp+var_20]
0x18000dcbc  mov     [rsp+80h+var_48], rax
0x18000dcc1  lea     rax, [rbp+arg_0]
0x18000dcc5  mov     [rsp+80h+var_50], rax
0x18000dcca  lea     rax, [rbp+var_18]
0x18000dcce  mov     [rsp+80h+var_58], rax
0x18000dcd3  lea     rax, [rbp+var_10]
0x18000dcd7  mov     [rsp+80h+var_60], rax
0x18000dcdc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dce1  jmp     short loc_18000DD56
0x18000dce3  mov     eax, cs:dword_180044008
0x18000dce9  cmp     eax, 2
0x18000dcec  jbe     short loc_18000DD56
0x18000dcee  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000dcf5  mov     [rbp+arg_0], 210h
0x18000dcfc  mov     [rbp+var_18], rax
0x18000dd00  lea     rcx, aCreatevailsupe_0; "CreateVailSuperWetInk"
0x18000dd07  lea     rax, aOncreatevailsu_0; "OnCreateVailSuperWetInk failed: Aux red"...
0x18000dd0e  mov     [rbp+var_10], rcx
0x18000dd12  mov     [rbp+var_8], rax
0x18000dd16  lea     rdx, byte_18003931D
0x18000dd1d  lea     rax, [rbp+var_10]
0x18000dd21  mov     dword ptr [rbp+var_20], 8000FFFFh
0x18000dd28  mov     [rsp+80h+var_40], rax
0x18000dd2d  lea     rax, [rbp+arg_0]
0x18000dd31  mov     [rsp+80h+var_48], rax
0x18000dd36  lea     rax, [rbp+var_18]
0x18000dd3a  mov     [rsp+80h+var_50], rax
0x18000dd3f  lea     rax, [rbp+var_20]
0x18000dd43  mov     [rsp+80h+var_58], rax
0x18000dd48  lea     rax, [rbp+var_8]
0x18000dd4c  mov     [rsp+80h+var_60], rax
0x18000dd51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dd56  lea     r11, [rsp+80h+var_s0]
0x18000dd5e  xor     eax, eax
0x18000dd60  mov     rbx, [r11+18h]
0x18000dd64  mov     rdi, [r11+20h]
0x18000dd68  mov     rsp, r11
0x18000dd6b  pop     rbp
0x18000dd6c  retn
```
