# RdsDWMDirectUpdateProcessor::ProcessWindowDestroy(RdpDWMDirectWindowContext *)

- ea: `0x1800117ac`
- end: `0x180011963`
- name: `?ProcessWindowDestroy@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@@Z`
- size: `439`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x18000dd74`
- `0x1800117ac`
- `0x18002c010`

## string_xrefs

- `0x180011800`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800118fd`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800117dc`: `No target window for destroy window update.`
- `0x18001185b`: `RdsDWMDirectUpdateProcessor::ProcessWindowDestroy`
- `0x1800118d9`: `Failed to remove window from surface`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessWindowDestroy(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        __int64 a3,
        __int64 a4)
{
  RdsDWMDirectUpdateProcessor *v5; // rsi
  int v6; // ebx
  char *v7; // rdx
  const unsigned __int16 **v8; // rax
  const char *v9; // rax
  const unsigned __int16 **v11; // [rsp+40h] [rbp-30h]
  const char *v12; // [rsp+50h] [rbp-20h] BYREF
  const char *v13; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v15; // [rsp+98h] [rbp+28h] BYREF
  const char *v16; // [rsp+A0h] [rbp+30h] BYREF
  const char *v17; // [rsp+A8h] [rbp+38h] BYREF

  v5 = (RdsDWMDirectUpdateProcessor *)this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v15 = *((_QWORD *)a2 + 8);
      v16 = "RdsDWMDirectUpdateProcessor::ProcessWindowDestroy";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)&word_18003AC6E,
        a3,
        a4,
        (const unsigned __int16 **)&v16,
        (__int64)&v15);
    }
    v6 = RdpDWMDirectWindowContext::DestroySurface(a2);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, struct RdpDWMDirectWindowContext *))(*((_QWORD *)v5 + 1) + 16LL))(
             (__int64)v5 + 8,
             a2);
      if ( v6 >= 0 || (unsigned int)dword_180044008 <= 2 )
        return (unsigned int)v6;
      v9 = "Failed to remove window from surface";
      LODWORD(v15) = 938;
      v7 = (char *)&dword_18003ABD4;
    }
    else
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 <= 2 )
        return (unsigned int)v6;
      v9 = "Failed to destroy the window rendering context.";
      LODWORD(v15) = 935;
      v7 = byte_18003AC21;
    }
    v17 = v9;
    v14[0] = "ProcessWindowDestroy";
    v13 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
    v12 = "Error HResult failed";
    v11 = (const unsigned __int16 **)v14;
    v8 = (const unsigned __int16 **)&v12;
    goto LABEL_13;
  }
  v6 = -2147418113;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v15) = 925;
    v17 = "No target window for destroy window update.";
    v7 = byte_18003AC99;
    v12 = "ProcessWindowDestroy";
    v13 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
    v14[0] = "Error condition failed";
    v11 = (const unsigned __int16 **)&v12;
    v8 = (const unsigned __int16 **)v14;
LABEL_13:
    LODWORD(v16) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      this,
      (__int64)v7,
      a3,
      a4,
      v8,
      (__int64)&v16,
      (const unsigned __int16 **)&v13,
      (__int64)&v15,
      v11,
      (const unsigned __int16 **)&v17);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800117ac  mov     r11, rsp
0x1800117af  mov     [r11+8], rbx
0x1800117b3  push    rbp
0x1800117b4  push    rsi
0x1800117b5  push    rdi
0x1800117b6  mov     rbp, rsp
0x1800117b9  sub     rsp, 70h
0x1800117bd  mov     eax, cs:dword_180044008
0x1800117c3  mov     rdi, rdx
0x1800117c6  mov     rsi, rcx
0x1800117c9  test    rdx, rdx
0x1800117cc  jnz     short loc_180011847
0x1800117ce  mov     ebx, 8000FFFFh
0x1800117d3  cmp     eax, 2
0x1800117d6  jbe     loc_180011951
0x1800117dc  lea     rax, aNoTargetWindow_1; "No target window for destroy window upd"...
0x1800117e3  mov     dword ptr [rbp+arg_8], 39Dh
0x1800117ea  mov     [rbp+arg_18], rax
0x1800117ee  lea     rdx, byte_18003AC99
0x1800117f5  lea     rax, aProcesswindowd_0; "ProcessWindowDestroy"
0x1800117fc  mov     [rbp+var_20], rax
0x180011800  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011807  mov     [rbp+var_18], rax
0x18001180b  lea     rax, aErrorCondition; "Error condition failed"
0x180011812  mov     [rbp+var_10], rax
0x180011816  lea     rax, [rbp+arg_18]
0x18001181a  mov     [r11-40h], rax
0x18001181e  lea     rax, [rbp+var_20]
0x180011822  mov     [r11-48h], rax
0x180011826  lea     rax, [rbp+arg_8]
0x18001182a  mov     [r11-50h], rax
0x18001182e  lea     rax, [rbp+var_18]
0x180011832  mov     [r11-58h], rax
0x180011836  lea     rax, [rbp+arg_10]
0x18001183a  mov     [r11-60h], rax
0x18001183e  lea     rax, [rbp+var_10]
0x180011842  jmp     loc_180011944
0x180011847  cmp     eax, 4
0x18001184a  jbe     short loc_18001187D
0x18001184c  mov     rax, [rdx+40h]
0x180011850  lea     rdx, word_18003AC6E
0x180011857  mov     [rbp+arg_8], rax
0x18001185b  lea     rax, aRdsdwmdirectup_6; "RdsDWMDirectUpdateProcessor::ProcessWin"...
0x180011862  mov     [rbp+arg_10], rax
0x180011866  lea     rax, [rbp+arg_8]
0x18001186a  mov     [rsp+70h+var_48], rax
0x18001186f  lea     rax, [rbp+arg_10]
0x180011873  mov     [rsp+70h+var_50], rax
0x180011878  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001187d  mov     rcx, rdi; this
0x180011880  call    ?DestroySurface@RdpDWMDirectWindowContext@@QEAAJXZ; RdpDWMDirectWindowContext::DestroySurface(void)
0x180011885  mov     ebx, eax
0x180011887  test    eax, eax
0x180011889  jns     short loc_1800118B1
0x18001188b  mov     ecx, cs:dword_180044008
0x180011891  cmp     ecx, 2
0x180011894  jbe     loc_180011951
0x18001189a  lea     rax, aFailedToDestro_0; "Failed to destroy the window rendering "...
0x1800118a1  mov     dword ptr [rbp+arg_8], 3A7h
0x1800118a8  lea     rdx, byte_18003AC21
0x1800118af  jmp     short loc_1800118EE
0x1800118b1  lea     rcx, [rsi+8]
0x1800118b5  mov     rdx, rdi
0x1800118b8  mov     rax, [rcx]
0x1800118bb  mov     rax, [rax+10h]
0x1800118bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c4  mov     ebx, eax
0x1800118c6  test    eax, eax
0x1800118c8  jns     loc_180011951
0x1800118ce  mov     eax, cs:dword_180044008
0x1800118d4  cmp     eax, 2
0x1800118d7  jbe     short loc_180011951
0x1800118d9  lea     rax, aFailedToRemove; "Failed to remove window from surface"
0x1800118e0  mov     dword ptr [rbp+arg_8], 3AAh
0x1800118e7  lea     rdx, dword_18003ABD4
0x1800118ee  mov     [rbp+arg_18], rax
0x1800118f2  lea     rax, aProcesswindowd_0; "ProcessWindowDestroy"
0x1800118f9  mov     [rbp+var_10], rax
0x1800118fd  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011904  mov     [rbp+var_18], rax
0x180011908  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001190f  mov     [rbp+var_20], rax
0x180011913  lea     rax, [rbp+arg_18]
0x180011917  mov     [rsp+70h+var_28], rax
0x18001191c  lea     rax, [rbp+var_10]
0x180011920  mov     [rsp+70h+var_30], rax
0x180011925  lea     rax, [rbp+arg_8]
0x180011929  mov     [rsp+70h+var_38], rax
0x18001192e  lea     rax, [rbp+var_18]
0x180011932  mov     [rsp+70h+var_40], rax
0x180011937  lea     rax, [rbp+arg_10]
0x18001193b  mov     [rsp+70h+var_48], rax
0x180011940  lea     rax, [rbp+var_20]
0x180011944  mov     [rsp+70h+var_50], rax
0x180011949  mov     dword ptr [rbp+arg_10], ebx
0x18001194c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180011951  mov     eax, ebx
0x180011953  mov     rbx, [rsp+70h+arg_0]
0x18001195b  add     rsp, 70h
0x18001195f  pop     rdi
0x180011960  pop     rsi
0x180011961  pop     rbp
0x180011962  retn
```
