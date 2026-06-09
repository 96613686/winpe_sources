# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800110c0`
- end: `0x1800111b2`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@3@Z`
- size: `242`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800399a8`
- `0x180039a64`
- `0x18003a0b4`
- `0x18003bc90`
- `0x18003be10`

## callees

- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011194`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011194`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v7; // eax
  EVENT_DESCRIPTOR v9; // [rsp+38h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 *v11; // [rsp+60h] [rbp-58h]
  int v12; // [rsp+68h] [rbp-50h]
  int v13; // [rsp+6Ch] [rbp-4Ch]
  __int64 v14; // [rsp+70h] [rbp-48h]
  __int64 v15; // [rsp+78h] [rbp-40h]
  __int64 v16; // [rsp+80h] [rbp-38h]
  __int64 v17; // [rsp+88h] [rbp-30h]
  __int64 v18; // [rsp+90h] [rbp-28h]
  __int64 v19; // [rsp+98h] [rbp-20h]

  v18 = a7;
  v16 = a6;
  v14 = a5;
  *(_DWORD *)&v9.Id = *a2 << 24;
  *(_DWORD *)&v9.Level = *(unsigned __int16 *)(a2 + 1);
  v9.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v19 = 4;
  v17 = 8;
  v15 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v7 = *(unsigned __int16 *)(a2 + 11);
  UserData.Reserved = 2;
  v11 = a2 + 11;
  v12 = v7;
  v13 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v9, a3, a4, 5u, &UserData);
}

```

## disassembly

```asm
0x1800110c0  mov     r11, rsp
0x1800110c3  sub     rsp, 0B8h
0x1800110ca  mov     rax, cs:__security_cookie
0x1800110d1  xor     rax, rsp
0x1800110d4  mov     [rsp+0B8h+var_18], rax
0x1800110dc  mov     rax, [rsp+0B8h+arg_30]
0x1800110e4  mov     r10, rcx
0x1800110e7  mov     [r11-28h], rax
0x1800110eb  lea     rcx, [rdx+0Bh]
0x1800110ef  mov     rax, [rsp+0B8h+arg_28]
0x1800110f7  mov     [r11-38h], rax
0x1800110fb  mov     rax, [rsp+0B8h+arg_20]
0x180011103  mov     [r11-48h], rax
0x180011107  movzx   eax, byte ptr [rdx]
0x18001110a  shl     eax, 18h
0x18001110d  mov     [rsp+0B8h+var_80], eax
0x180011111  movzx   eax, word ptr [rdx+1]
0x180011115  mov     [rsp+0B8h+var_7C], eax
0x180011119  mov     rax, [rdx+3]
0x18001111d  lea     rdx, [r11-80h]; EventDescriptor
0x180011121  mov     [r11-78h], rax
0x180011125  mov     rax, [r10+8]
0x180011129  mov     [r11-68h], rax
0x18001112d  mov     qword ptr [r11-20h], 4
0x180011135  mov     qword ptr [r11-30h], 8
0x18001113d  mov     qword ptr [r11-40h], 4
0x180011145  movzx   eax, word ptr [rax]
0x180011148  mov     [rsp+0B8h+var_60], eax
0x18001114c  movzx   eax, word ptr [rcx]
0x18001114f  mov     [rsp+0B8h+var_5C], 2
0x180011157  mov     [r11-58h], rcx
0x18001115b  lea     rcx, _TraceLoggingMetadata
0x180011162  mov     [rsp+0B8h+var_50], eax
0x180011166  lea     rax, _TraceLoggingMetadataEnd
0x18001116d  sub     eax, ecx
0x18001116f  mov     [rsp+0B8h+var_4C], 1
0x180011177  mov     [rsp+0B8h+var_88], eax
0x18001117b  mov     eax, [rsp+0B8h+var_88]
0x18001117f  mov     rcx, [r10+20h]; RegHandle
0x180011183  lea     rax, [r11-68h]
0x180011187  mov     [rsp+0B8h+UserData], rax; UserData
0x18001118c  mov     [rsp+0B8h+UserDataCount], 5; UserDataCount
0x180011194  call    cs:__imp_EventWriteTransfer
0x18001119a  mov     rcx, [rsp+0B8h+var_18]
0x1800111a2  xor     rcx, rsp; StackCookie
0x1800111a5  call    __security_check_cookie
0x1800111aa  add     rsp, 0B8h
0x1800111b1  retn
```
