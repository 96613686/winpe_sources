# BrowserTelemetry::IEApplicationExit<ulong &,__int64 &>(ulong &,__int64 &)

- ea: `0x14000237c`
- end: `0x140002444`
- name: `??$IEApplicationExit@AEAKAEA_J@BrowserTelemetry@@SAXAEAKAEA_J@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x1400010d4`
- `0x1400012dc`
- `0x14000237c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1400023e3`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1400023e3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1400023d3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1400023d3`

## pseudocode

```c
__int64 __fastcall BrowserTelemetry::IEApplicationExit<unsigned long &,__int64 &>(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  __int64 *v4; // r8
  int *v5; // r9
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // [rsp+50h] [rbp-28h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v10; // [rsp+58h] [rbp-20h] BYREF
  __int64 v11[3]; // [rsp+60h] [rbp-18h] BYREF
  char v12; // [rsp+90h] [rbp+18h] BYREF
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v2 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  result = (unsigned int)dword_14000A000;
  *(_BYTE *)(v2 + 1) = 1;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(a1, a2, a2);
    if ( (_BYTE)result )
    {
      v9 = *v4;
      v13 = *v5;
      v12 = 1;
      v10 = GlobalThreadState();
      v11[0] = IEConfiguration_GetCLSID(268435459);
      result = _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                 v6,
                 (unsigned int)byte_140007FE9,
                 v7,
                 v8,
                 (__int64)v11,
                 (__int64)&v10,
                 (__int64)&v12,
                 (__int64)&v13,
                 (__int64)&v9);
    }
  }
  *(_BYTE *)(v2 + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x14000237c  mov     [rsp+arg_0], rbx
0x140002381  push    rdi
0x140002382  sub     rsp, 70h
0x140002386  mov     rax, gs:58h
0x14000238f  mov     r8, rdx
0x140002392  mov     edi, 1
0x140002397  mov     r9, rcx
0x14000239a  mov     rbx, [rax]
0x14000239d  mov     eax, cs:dword_14000A000
0x1400023a3  mov     byte ptr [rdi+rbx], 1
0x1400023a7  cmp     eax, 5
0x1400023aa  jbe     loc_140002432
0x1400023b0  call    _tlgKeywordOn
0x1400023b5  test    al, al
0x1400023b7  jz      short loc_140002432
0x1400023b9  mov     rax, [r8]
0x1400023bc  mov     [rsp+78h+var_28], rax
0x1400023c1  mov     eax, [r9]
0x1400023c4  mov     [rsp+78h+arg_18], eax
0x1400023cb  mov     [rsp+78h+arg_10], 1
0x1400023d3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1400023d9  mov     ecx, 10000003h
0x1400023de  mov     [rsp+78h+var_20], rax
0x1400023e3  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1400023e9  mov     [rsp+78h+var_18], rax
0x1400023ee  lea     rdx, byte_140007FE9
0x1400023f5  lea     rax, [rsp+78h+var_28]
0x1400023fa  mov     [rsp+78h+var_38], rax
0x1400023ff  lea     rax, [rsp+78h+arg_18]
0x140002407  mov     [rsp+78h+var_40], rax
0x14000240c  lea     rax, [rsp+78h+arg_10]
0x140002414  mov     [rsp+78h+var_48], rax
0x140002419  lea     rax, [rsp+78h+var_20]
0x14000241e  mov     [rsp+78h+var_50], rax
0x140002423  lea     rax, [rsp+78h+var_18]
0x140002428  mov     [rsp+78h+var_58], rax
0x14000242d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140002432  mov     byte ptr [rdi+rbx], 0
0x140002436  mov     rbx, [rsp+78h+arg_0]
0x14000243e  add     rsp, 70h
0x140002442  pop     rdi
0x140002443  retn
```
