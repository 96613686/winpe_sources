# AOMDHandler::SaveStateToRegistry(void)

- ea: `0x180010ac4`
- end: `0x180010c43`
- name: `?SaveStateToRegistry@AOMDHandler@@AEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x18000e7ec`
- `0x180010ac4`
- `0x180015668`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x180010b54`
- `ADVAPI32!RegSetKeyValueW` at `0x180010bae`
- `ADVAPI32!RegSetKeyValueW` at `0x180010c06`
- `ADVAPI32!RegSetKeyValueW` at `0x180010b54`
- `ADVAPI32!RegSetKeyValueW` at `0x180010bae`
- `ADVAPI32!RegSetKeyValueW` at `0x180010c06`

## string_xrefs

- `0x180010af6`: `SaveStateToRegistry_Starting`

## pseudocode

```c
__int64 __fastcall AOMDHandler::SaveStateToRegistry(AOMDHandler *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r9
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // r8
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const wchar_t *Data; // [rsp+40h] [rbp+8h] BYREF

  v2 = TlgHelper::Provider();
  if ( *(_DWORD *)v2 > 4u )
  {
    v4 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v2 + 2) & 2) != 0 && (*((_QWORD *)v2 + 3) & 2LL) == v4 )
    {
      Data = L"SaveStateToRegistry_Starting";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v2,
        (__int64)&word_180029B1E,
        v4,
        v3,
        (int **)&Data);
    }
  }
  Data = (const wchar_t *)*((_QWORD *)this + 12);
  v5 = RegSetKeyValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
         L"AOMDLastScanDecisionTime",
         0xBu,
         &Data,
         8u);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x440, v6, (const char *)(unsigned int)v5);
  Data = (const wchar_t *)*((_QWORD *)this + 13);
  v7 = RegSetKeyValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
         L"AOMDLastScanOfferedTime",
         0xBu,
         &Data,
         8u);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x446, v8, (const char *)(unsigned int)v7);
  LODWORD(Data) = *((_DWORD *)this + 28);
  v9 = RegSetKeyValueW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MemoryDiagnostic",
         L"AOMDNumScanOffersSinceLastDecision",
         4u,
         &Data,
         4u);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x44C, v10, (const char *)(unsigned int)v9);
  return 0;
}

```

## disassembly

```asm
0x180010ac4  mov     [rsp+arg_8], rdi
0x180010ac9  push    r15
0x180010acb  sub     rsp, 30h
0x180010acf  mov     rdi, rcx
0x180010ad2  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180010ad7  mov     edx, [rax]
0x180010ad9  cmp     edx, 4
0x180010adc  jbe     short loc_180010B1B
0x180010ade  mov     r8, [rax+18h]
0x180010ae2  mov     rdx, [rax+10h]
0x180010ae6  test    dl, 2
0x180010ae9  jz      short loc_180010B1B
0x180010aeb  mov     rcx, r8
0x180010aee  and     ecx, 2
0x180010af1  cmp     rcx, r8
0x180010af4  jnz     short loc_180010B1B
0x180010af6  lea     rcx, aSavestatetoreg; "SaveStateToRegistry_Starting"
0x180010afd  mov     [rsp+38h+Data], rcx
0x180010b02  lea     rcx, [rsp+38h+Data]
0x180010b07  mov     [rsp+38h+lpData], rcx
0x180010b0c  lea     rdx, word_180029B1E
0x180010b13  mov     rcx, rax
0x180010b16  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180010b1b  mov     rax, [rdi+60h]
0x180010b1f  mov     [rsp+38h+Data], rax
0x180010b24  mov     [rsp+38h+cbData], 8; cbData
0x180010b2c  lea     rax, [rsp+38h+Data]
0x180010b31  mov     [rsp+38h+lpData], rax; int
0x180010b36  mov     r9d, 0Bh; dwType
0x180010b3c  lea     r8, ValueName; "AOMDLastScanDecisionTime"
0x180010b43  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010b4a  mov     r15, 0FFFFFFFF80000001h
0x180010b51  mov     rcx, r15; hKey
0x180010b54  call    cs:__imp_RegSetKeyValueW
0x180010b5a  test    eax, eax
0x180010b5c  jle     short loc_180010B66
0x180010b5e  movzx   eax, ax
0x180010b61  or      eax, 80070000h
0x180010b66  mov     rcx, [rsp+38h]; this
0x180010b6b  test    eax, eax
0x180010b6d  jns     short loc_180010B7C
0x180010b6f  mov     r9d, eax; char *
0x180010b72  mov     edx, 440h; void *
0x180010b77  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010b7c  mov     rax, [rdi+68h]
0x180010b80  mov     [rsp+38h+Data], rax
0x180010b85  mov     [rsp+38h+cbData], 8; cbData
0x180010b8d  lea     rax, [rsp+38h+Data]
0x180010b92  mov     [rsp+38h+lpData], rax; int
0x180010b97  mov     r9d, 0Bh; dwType
0x180010b9d  lea     r8, aAomdlastscanof; "AOMDLastScanOfferedTime"
0x180010ba4  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010bab  mov     rcx, r15; hKey
0x180010bae  call    cs:__imp_RegSetKeyValueW
0x180010bb4  test    eax, eax
0x180010bb6  jle     short loc_180010BC0
0x180010bb8  movzx   eax, ax
0x180010bbb  or      eax, 80070000h
0x180010bc0  mov     rcx, [rsp+38h]; this
0x180010bc5  test    eax, eax
0x180010bc7  jns     short loc_180010BD6
0x180010bc9  mov     r9d, eax; char *
0x180010bcc  mov     edx, 446h; void *
0x180010bd1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010bd6  mov     eax, [rdi+70h]
0x180010bd9  mov     dword ptr [rsp+38h+Data], eax
0x180010bdd  mov     [rsp+38h+cbData], 4; cbData
0x180010be5  lea     rax, [rsp+38h+Data]
0x180010bea  mov     [rsp+38h+lpData], rax; int
0x180010bef  mov     r9d, 4; dwType
0x180010bf5  lea     r8, aAomdnumscanoff; "AOMDNumScanOffersSinceLastDecision"
0x180010bfc  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010c03  mov     rcx, r15; hKey
0x180010c06  call    cs:__imp_RegSetKeyValueW
0x180010c0c  test    eax, eax
0x180010c0e  jle     short loc_180010C18
0x180010c10  movzx   eax, ax
0x180010c13  or      eax, 80070000h
0x180010c18  mov     rcx, [rsp+38h]; this
0x180010c1d  test    eax, eax
0x180010c1f  jns     short loc_180010C2E
0x180010c21  mov     r9d, eax; char *
0x180010c24  mov     edx, 44Ch; void *
0x180010c29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010c2e  xor     eax, eax
0x180010c30  jmp     short loc_180010C36
0x180010c32  mov     eax, dword ptr [rsp+38h+Data]
0x180010c36  mov     rdi, [rsp+38h+arg_8]
0x180010c3b  add     rsp, 30h
0x180010c3f  pop     r15
0x180010c41  retn
```
