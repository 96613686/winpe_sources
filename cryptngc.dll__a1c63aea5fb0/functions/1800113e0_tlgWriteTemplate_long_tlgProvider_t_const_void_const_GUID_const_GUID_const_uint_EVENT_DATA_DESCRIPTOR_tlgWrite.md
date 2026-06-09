# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x1800113e0`
- end: `0x1800114db`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$00@@5@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033e44`

## callees

- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800114c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800114c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int8 *v12; // [rsp+60h] [rbp-41h]
  int v13; // [rsp+68h] [rbp-39h]
  int v14; // [rsp+6Ch] [rbp-35h]
  __int64 v15; // [rsp+70h] [rbp-31h]
  __int64 v16; // [rsp+78h] [rbp-29h]
  __int64 v17; // [rsp+80h] [rbp-21h]
  __int64 v18; // [rsp+88h] [rbp-19h]
  __int64 v19; // [rsp+90h] [rbp-11h]
  __int64 v20; // [rsp+98h] [rbp-9h]
  __int64 v21; // [rsp+A0h] [rbp-1h]
  __int64 v22; // [rsp+A8h] [rbp+7h]
  __int64 v23; // [rsp+B0h] [rbp+Fh]
  __int64 v24; // [rsp+B8h] [rbp+17h]

  v23 = a9;
  v21 = a8;
  v19 = a7;
  v17 = a6;
  v15 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v24 = 1;
  v22 = 1;
  v20 = 4;
  v18 = 8;
  v16 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v13 = *(unsigned __int16 *)(a2 + 11);
  v12 = a2 + 11;
  UserData.Reserved = 2;
  v14 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 7u, &UserData);
}

```

## disassembly

```asm
0x1800113e0  push    rbp
0x1800113e2  lea     rbp, [rsp-2Fh]
0x1800113e7  sub     rsp, 0D0h
0x1800113ee  mov     rax, cs:__security_cookie
0x1800113f5  xor     rax, rsp
0x1800113f8  mov     [rbp+2Fh+var_10], rax
0x1800113fc  mov     rax, [rbp+2Fh+arg_40]
0x180011400  mov     r10, rcx
0x180011403  mov     [rbp+2Fh+var_20], rax
0x180011407  lea     rcx, [rdx+0Bh]
0x18001140b  mov     rax, [rbp+2Fh+arg_38]
0x18001140f  mov     [rbp+2Fh+var_30], rax
0x180011413  mov     rax, [rbp+2Fh+arg_30]
0x180011417  mov     [rbp+2Fh+var_40], rax
0x18001141b  mov     rax, [rbp+2Fh+arg_28]
0x18001141f  mov     [rbp+2Fh+var_50], rax
0x180011423  mov     rax, [rbp+2Fh+arg_20]
0x180011427  mov     [rbp+2Fh+var_60], rax
0x18001142b  movzx   eax, byte ptr [rdx]
0x18001142e  shl     eax, 18h
0x180011431  mov     dword ptr [rbp+2Fh+EventDescriptor.Id], eax
0x180011434  movzx   eax, word ptr [rdx+1]
0x180011438  mov     dword ptr [rbp+2Fh+EventDescriptor.Level], eax
0x18001143b  mov     rax, [rdx+3]
0x18001143f  lea     rdx, [rbp+2Fh+EventDescriptor]; EventDescriptor
0x180011443  mov     [rbp+2Fh+EventDescriptor.Keyword], rax
0x180011447  mov     rax, [r10+8]
0x18001144b  mov     [rbp+2Fh+var_80.Ptr], rax
0x18001144f  mov     [rbp+2Fh+var_18], 1
0x180011457  mov     [rbp+2Fh+var_28], 1
0x18001145f  mov     [rbp+2Fh+var_38], 4
0x180011467  mov     [rbp+2Fh+var_48], 8
0x18001146f  mov     [rbp+2Fh+var_58], 4
0x180011477  movzx   eax, word ptr [rax]
0x18001147a  mov     [rbp+2Fh+var_80.Size], eax
0x18001147d  movzx   eax, word ptr [rcx]
0x180011480  mov     [rbp+2Fh+var_68], eax
0x180011483  lea     rax, _TraceLoggingMetadataEnd
0x18001148a  mov     [rbp+2Fh+var_70], rcx
0x18001148e  lea     rcx, _TraceLoggingMetadata
0x180011495  sub     eax, ecx
0x180011497  mov     dword ptr [rbp+2Fh+var_80.0Ch], 2
0x18001149e  mov     [rbp+2Fh+var_64], 1
0x1800114a5  mov     [rbp+2Fh+var_A0], eax
0x1800114a8  mov     eax, [rbp+2Fh+var_A0]
0x1800114ab  mov     rcx, [r10+20h]; RegHandle
0x1800114af  lea     rax, [rbp+2Fh+var_80]
0x1800114b3  mov     [rsp+0D0h+UserData], rax; UserData
0x1800114b8  mov     [rsp+0D0h+UserDataCount], 7; UserDataCount
0x1800114c0  call    cs:__imp_EventWriteTransfer
0x1800114c6  mov     rcx, [rbp+2Fh+var_10]
0x1800114ca  xor     rcx, rsp; StackCookie
0x1800114cd  call    __security_check_cookie
0x1800114d2  add     rsp, 0D0h
0x1800114d9  pop     rbp
0x1800114da  retn
```
