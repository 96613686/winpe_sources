# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180011310`
- end: `0x1800113da`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `202`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x180028ff0`
- `0x1800355e4`
- `0x180035ab0`
- `0x180035b54`
- `0x180035ebc`
- `0x18003606c`
- `0x180036110`
- `0x1800361b4`
- `0x18003634c`
- `0x1800363f0`
- `0x18003662c`
- `0x180036be0`
- `0x180036d60`
- `0x180036ee0`
- `0x180037080`
- `0x1800371e0`
- `0x180037360`
- `0x1800382e0`
- `0x1800387a0`
- `0x180038910`
- `0x180038a80`
- `0x1800393a8`
- `0x180039660`
- `0x180039b74`
- `0x18003a274`
- `0x18003b780`
- `0x18003b8c0`
- `0x18003ba10`
- `0x18003c1a4`
- `0x18003c248`
- `0x18003c8f0`

## callees

- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800113bf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800113bf`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 *v9; // [rsp+60h] [rbp+7h]
  int v10; // [rsp+68h] [rbp+Fh]
  int v11; // [rsp+6Ch] [rbp+13h]
  __int64 v12; // [rsp+70h] [rbp+17h]
  __int64 v13; // [rsp+78h] [rbp+1Fh]
  __int64 v14; // [rsp+80h] [rbp+27h]
  __int64 v15; // [rsp+88h] [rbp+2Fh]

  v14 = a6;
  v12 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v15 = 8;
  v13 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v10 = *(unsigned __int16 *)(a2 + 11);
  v9 = a2 + 11;
  UserData.Reserved = 2;
  v11 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 4u, &UserData);
}

```

## disassembly

```asm
0x180011310  push    rbp
0x180011312  lea     rbp, [rsp-47h]
0x180011317  sub     rsp, 0A0h
0x18001131e  mov     rax, cs:__security_cookie
0x180011325  xor     rax, rsp
0x180011328  mov     [rbp+47h+var_10], rax
0x18001132c  mov     rax, [rbp+47h+arg_28]
0x180011330  mov     r10, rcx
0x180011333  mov     [rbp+47h+var_20], rax
0x180011337  lea     rcx, [rdx+0Bh]
0x18001133b  mov     rax, [rbp+47h+arg_20]
0x18001133f  mov     r11d, 4
0x180011345  mov     [rbp+47h+var_30], rax
0x180011349  movzx   eax, byte ptr [rdx]
0x18001134c  shl     eax, 18h
0x18001134f  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x180011352  movzx   eax, word ptr [rdx+1]
0x180011356  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180011359  mov     rax, [rdx+3]
0x18001135d  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180011361  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180011365  mov     rax, [r10+8]
0x180011369  mov     [rbp+47h+var_50.Ptr], rax
0x18001136d  mov     [rbp+47h+var_18], 8
0x180011375  mov     [rbp+47h+var_28], r11
0x180011379  movzx   eax, word ptr [rax]
0x18001137c  mov     [rbp+47h+var_50.Size], eax
0x18001137f  movzx   eax, word ptr [rcx]
0x180011382  mov     [rbp+47h+var_38], eax
0x180011385  lea     rax, _TraceLoggingMetadataEnd
0x18001138c  mov     [rbp+47h+var_40], rcx
0x180011390  lea     rcx, _TraceLoggingMetadata
0x180011397  sub     eax, ecx
0x180011399  mov     dword ptr [rbp+47h+var_50.0Ch], 2
0x1800113a0  mov     [rbp+47h+var_34], 1
0x1800113a7  mov     [rbp+47h+var_70], eax
0x1800113aa  mov     eax, [rbp+47h+var_70]
0x1800113ad  mov     rcx, [r10+20h]; RegHandle
0x1800113b1  lea     rax, [rbp+47h+var_50]
0x1800113b5  mov     [rsp+0A0h+UserData], rax; UserData
0x1800113ba  mov     [rsp+0A0h+UserDataCount], r11d; UserDataCount
0x1800113bf  call    cs:__imp_EventWriteTransfer
0x1800113c5  mov     rcx, [rbp+47h+var_10]
0x1800113c9  xor     rcx, rsp; StackCookie
0x1800113cc  call    __security_check_cookie
0x1800113d1  add     rsp, 0A0h
0x1800113d8  pop     rbp
0x1800113d9  retn
```
