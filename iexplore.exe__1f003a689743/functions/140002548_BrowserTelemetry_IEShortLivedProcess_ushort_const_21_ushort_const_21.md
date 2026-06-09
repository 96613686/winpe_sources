# BrowserTelemetry::IEShortLivedProcess<ushort const (&)[21]>(ushort const (&)[21])

- ea: `0x140002548`
- end: `0x1400025ca`
- name: `??$IEShortLivedProcess@AEAY0BF@$$CBG@BrowserTelemetry@@SAXAEAY0BF@$$CBG@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x140001008`
- `0x1400012dc`
- `0x140002548`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x140002586`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x140002586`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140002576`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x140002576`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::IEShortLivedProcess<unsigned short const (&)[21]>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  const wchar_t *v8; // [rsp+58h] [rbp+10h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v9; // [rsp+60h] [rbp+18h] BYREF
  __int64 CLSID; // [rsp+68h] [rbp+20h] BYREF

  v7 = a1;
  result = (unsigned int)dword_14000A000;
  if ( (unsigned int)dword_14000A000 > 5 )
  {
    result = tlgKeywordOn(a1, a2, a3);
    if ( (_BYTE)result )
    {
      LOBYTE(v7) = 1;
      v8 = L"ResetDestinationList";
      v9 = GlobalThreadState();
      CLSID = IEConfiguration_GetCLSID(268435459);
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
               v4,
               (unsigned int)&unk_1400080C0,
               v5,
               v6,
               (__int64)&CLSID,
               (__int64)&v9,
               (__int64)&v7,
               (__int64)&v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002548  mov     [rsp+arg_0], rcx
0x14000254d  sub     rsp, 48h
0x140002551  mov     eax, cs:dword_14000A000
0x140002557  cmp     eax, 5
0x14000255a  jbe     short loc_1400025C5
0x14000255c  call    _tlgKeywordOn
0x140002561  test    al, al
0x140002563  jz      short loc_1400025C5
0x140002565  lea     rax, aResetdestinati_0; "ResetDestinationList"
0x14000256c  mov     byte ptr [rsp+48h+arg_0], 1
0x140002571  mov     [rsp+48h+arg_8], rax
0x140002576  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x14000257c  mov     ecx, 10000003h
0x140002581  mov     [rsp+48h+arg_10], rax
0x140002586  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x14000258c  mov     [rsp+48h+arg_18], rax
0x140002591  lea     rdx, unk_1400080C0
0x140002598  lea     rax, [rsp+48h+arg_8]
0x14000259d  mov     [rsp+48h+var_10], rax
0x1400025a2  lea     rax, [rsp+48h+arg_0]
0x1400025a7  mov     [rsp+48h+var_18], rax
0x1400025ac  lea     rax, [rsp+48h+arg_10]
0x1400025b1  mov     [rsp+48h+var_20], rax
0x1400025b6  lea     rax, [rsp+48h+arg_18]
0x1400025bb  mov     [rsp+48h+var_28], rax
0x1400025c0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x1400025c5  add     rsp, 48h
0x1400025c9  retn
```
