# CUiccHandler2::IsSystemStateValidForProvisioning(_MVProvisionData &)

- ea: `0x180030840`
- end: `0x1800308ca`
- name: `?IsSystemStateValidForProvisioning@CUiccHandler2@@KA_NAEAU_MVProvisionData@@@Z`
- size: `138`
- prototype: `bool __fastcall(struct _MVProvisionData *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031100`
- `0x180031410`

## callees

- `0x180001850`
- `0x180030840`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003085f`
- `msvcrt!_wcsnicmp` at `0x18003085f`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180030876`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180030876`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CUiccHandler2::IsSystemStateValidForProvisioning(struct _MVProvisionData *a1)
{
  const wchar_t *v1; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+48h] [rbp+10h] BYREF
  const WCHAR *v9; // [rsp+50h] [rbp+18h] BYREF

  v1 = (const wchar_t *)*((_QWORD *)a1 + 5);
  if ( !v1 || _wcsnicmp(L"bc7d58c6-0fe1-5a75-aca2-7cbb1490c220", v1, 0x24u) )
    return 1;
  v7 = 1;
  OOBEComplete(&v7);
  if ( (unsigned int)dword_180052170 > 4 )
  {
    v8 = v7;
    v9 = (const WCHAR *)*((_QWORD *)a1 + 1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v3,
      (__int64)&byte_1800498AF,
      v4,
      v5,
      &v9,
      (__int64)&v8);
  }
  return v7 != 0;
}

```

## disassembly

```asm
0x180030840  push    rbx
0x180030842  sub     rsp, 30h
0x180030846  mov     rdx, [rcx+28h]; String2
0x18003084a  mov     rbx, rcx
0x18003084d  test    rdx, rdx
0x180030850  jz      short loc_1800308C2
0x180030852  mov     r8d, 24h ; '$'; MaxCount
0x180030858  lea     rcx, aBc7d58c60fe15a; "bc7d58c6-0fe1-5a75-aca2-7cbb1490c220"
0x18003085f  call    cs:__imp__wcsnicmp
0x180030865  test    eax, eax
0x180030867  jnz     short loc_1800308C2
0x180030869  lea     rcx, [rsp+38h+arg_0]
0x18003086e  mov     [rsp+38h+arg_0], 1
0x180030876  call    cs:__imp_OOBEComplete
0x18003087c  mov     eax, cs:dword_180052170
0x180030882  cmp     eax, 4
0x180030885  jbe     short loc_1800308B8
0x180030887  mov     eax, [rsp+38h+arg_0]
0x18003088b  lea     rdx, byte_1800498AF
0x180030892  mov     [rsp+38h+arg_8], eax
0x180030896  mov     rax, [rbx+8]
0x18003089a  mov     [rsp+38h+arg_10], rax
0x18003089f  lea     rax, [rsp+38h+arg_8]
0x1800308a4  mov     [rsp+38h+var_10], rax
0x1800308a9  lea     rax, [rsp+38h+arg_10]
0x1800308ae  mov     [rsp+38h+var_18], rax
0x1800308b3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800308b8  cmp     [rsp+38h+arg_0], 0
0x1800308bd  setnz   al
0x1800308c0  jmp     short loc_1800308C4
0x1800308c2  mov     al, 1
0x1800308c4  add     rsp, 30h
0x1800308c8  pop     rbx
0x1800308c9  retn
```
