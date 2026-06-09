# AOMDHandler::SaveStateToRegistry(void)

- ea: `0x1800114d0`
- end: `0x18001165a`
- name: `?SaveStateToRegistry@AOMDHandler@@AEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x18000f144`
- `0x1800114d0`
- `0x18001634c`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x180011559`
- `ADVAPI32!RegSetKeyValueW` at `0x1800115b9`
- `ADVAPI32!RegSetKeyValueW` at `0x180011617`
- `ADVAPI32!RegSetKeyValueW` at `0x180011559`
- `ADVAPI32!RegSetKeyValueW` at `0x1800115b9`
- `ADVAPI32!RegSetKeyValueW` at `0x180011617`

## string_xrefs

- `0x1800114fb`: `SaveStateToRegistry_Starting`

## pseudocode

```c
__int64 __fastcall AOMDHandler::SaveStateToRegistry(AOMDHandler *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // r8d
  int v4; // r9d
  int v5; // eax
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // eax
  unsigned int v10; // r8d
  int lpData; // [rsp+20h] [rbp-18h]
  int lpDataa; // [rsp+20h] [rbp-18h]
  int lpDatab; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const wchar_t *Data; // [rsp+40h] [rbp+8h] BYREF

  v2 = TlgHelper::Provider();
  if ( *(_DWORD *)v2 > 4u && (*((_BYTE *)v2 + 16) & 2) != 0 && (*((_QWORD *)v2 + 3) & 2LL) == *((_QWORD *)v2 + 3) )
  {
    Data = L"SaveStateToRegistry_Starting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v2,
      (unsigned int)&unk_18002AB01,
      v3,
      v4,
      (__int64)&Data);
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
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x49F, v6, (const char *)(unsigned int)v5, lpData);
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
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4A5, v8, (const char *)(unsigned int)v7, lpDataa);
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
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4AB, v10, (const char *)(unsigned int)v9, lpDatab);
  return 0;
}

```

## disassembly

```asm
0x1800114d0  mov     [rsp+arg_8], rdi
0x1800114d5  push    r15
0x1800114d7  sub     rsp, 30h
0x1800114db  mov     rdi, rcx
0x1800114de  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x1800114e3  cmp     dword ptr [rax], 4
0x1800114e6  jbe     short loc_180011520
0x1800114e8  test    byte ptr [rax+10h], 2
0x1800114ec  jz      short loc_180011520
0x1800114ee  mov     rcx, [rax+18h]
0x1800114f2  and     ecx, 2
0x1800114f5  cmp     rcx, [rax+18h]
0x1800114f9  jnz     short loc_180011520
0x1800114fb  lea     rcx, aSavestatetoreg; "SaveStateToRegistry_Starting"
0x180011502  mov     [rsp+38h+Data], rcx
0x180011507  lea     rcx, [rsp+38h+Data]
0x18001150c  mov     [rsp+38h+lpData], rcx
0x180011511  lea     rdx, byte_18002AB01
0x180011518  mov     rcx, rax
0x18001151b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180011520  mov     rax, [rdi+60h]
0x180011524  mov     [rsp+38h+Data], rax
0x180011529  mov     [rsp+38h+cbData], 8; cbData
0x180011531  lea     rax, [rsp+38h+Data]
0x180011536  mov     [rsp+38h+lpData], rax; int
0x18001153b  mov     r9d, 0Bh; dwType
0x180011541  lea     r8, ValueName; "AOMDLastScanDecisionTime"
0x180011548  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001154f  mov     r15, 0FFFFFFFF80000001h
0x180011556  mov     rcx, r15; hKey
0x180011559  call    cs:__imp_RegSetKeyValueW
0x180011560  nop     dword ptr [rax+rax+00h]
0x180011565  test    eax, eax
0x180011567  jle     short loc_180011571
0x180011569  movzx   eax, ax
0x18001156c  or      eax, 80070000h
0x180011571  mov     rcx, [rsp+38h]; this
0x180011576  test    eax, eax
0x180011578  jns     short loc_180011587
0x18001157a  mov     r9d, eax; char *
0x18001157d  mov     edx, 49Fh; void *
0x180011582  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011587  mov     rax, [rdi+68h]
0x18001158b  mov     [rsp+38h+Data], rax
0x180011590  mov     [rsp+38h+cbData], 8; cbData
0x180011598  lea     rax, [rsp+38h+Data]
0x18001159d  mov     [rsp+38h+lpData], rax; int
0x1800115a2  mov     r9d, 0Bh; dwType
0x1800115a8  lea     r8, aAomdlastscanof; "AOMDLastScanOfferedTime"
0x1800115af  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800115b6  mov     rcx, r15; hKey
0x1800115b9  call    cs:__imp_RegSetKeyValueW
0x1800115c0  nop     dword ptr [rax+rax+00h]
0x1800115c5  test    eax, eax
0x1800115c7  jle     short loc_1800115D1
0x1800115c9  movzx   eax, ax
0x1800115cc  or      eax, 80070000h
0x1800115d1  mov     rcx, [rsp+38h]; this
0x1800115d6  test    eax, eax
0x1800115d8  jns     short loc_1800115E7
0x1800115da  mov     r9d, eax; char *
0x1800115dd  mov     edx, 4A5h; void *
0x1800115e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800115e7  mov     eax, [rdi+70h]
0x1800115ea  mov     dword ptr [rsp+38h+Data], eax
0x1800115ee  mov     [rsp+38h+cbData], 4; cbData
0x1800115f6  lea     rax, [rsp+38h+Data]
0x1800115fb  mov     [rsp+38h+lpData], rax; int
0x180011600  mov     r9d, 4; dwType
0x180011606  lea     r8, aAomdnumscanoff; "AOMDNumScanOffersSinceLastDecision"
0x18001160d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180011614  mov     rcx, r15; hKey
0x180011617  call    cs:__imp_RegSetKeyValueW
0x18001161e  nop     dword ptr [rax+rax+00h]
0x180011623  test    eax, eax
0x180011625  jle     short loc_18001162F
0x180011627  movzx   eax, ax
0x18001162a  or      eax, 80070000h
0x18001162f  mov     rcx, [rsp+38h]; this
0x180011634  test    eax, eax
0x180011636  jns     short loc_180011645
0x180011638  mov     r9d, eax; char *
0x18001163b  mov     edx, 4ABh; void *
0x180011640  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011645  xor     eax, eax
0x180011647  jmp     short loc_18001164D
0x180011649  mov     eax, dword ptr [rsp+38h+Data]
0x18001164d  mov     rdi, [rsp+38h+arg_8]
0x180011652  add     rsp, 30h
0x180011656  pop     r15
0x180011658  retn
```
