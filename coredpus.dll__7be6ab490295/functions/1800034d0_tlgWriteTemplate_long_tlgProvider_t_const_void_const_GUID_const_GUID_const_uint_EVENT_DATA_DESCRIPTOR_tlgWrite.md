# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x1800034d0`
- end: `0x1800035a0`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `208`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x180019060`
- `0x18001d8e4`
- `0x18001e454`
- `0x18001e960`
- `0x18001eae0`
- `0x18001ed20`
- `0x18001ef60`
- `0x18001f290`
- `0x18001f5a0`
- `0x18001f7a0`
- `0x18001fa3c`
- `0x18001fee0`
- `0x180020150`
- `0x1800202a0`
- `0x1800203e0`
- `0x1800208f0`
- `0x180020b30`
- `0x180020cd0`
- `0x180020d80`
- `0x180020fa8`
- `0x1800212c8`
- `0x1800216cc`
- `0x180021880`
- `0x180021980`
- `0x180023010`
- `0x180029240`
- `0x18002f7ba`
- `0x18002f8af`
- `0x18002fc0f`
- `0x18002fc84`

## callees

- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000357e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000357e`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // eax
  EVENT_DESCRIPTOR v7; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int8 *v9; // [rsp+58h] [rbp-30h]
  int v10; // [rsp+60h] [rbp-28h]
  int v11; // [rsp+64h] [rbp-24h]
  __int64 v12; // [rsp+68h] [rbp-20h]
  __int64 v13; // [rsp+70h] [rbp-18h]

  v12 = a5;
  *(_DWORD *)&v7.Id = *a2 << 24;
  *(_DWORD *)&v7.Level = *(unsigned __int16 *)(a2 + 1);
  v7.Keyword = *(_QWORD *)(a2 + 3);
  v8.Ptr = *(_QWORD *)(a1 + 8);
  v13 = 4;
  v8.Size = *(unsigned __int16 *)v8.Ptr;
  v5 = *(unsigned __int16 *)(a2 + 11);
  v8.Reserved = 2;
  v9 = a2 + 11;
  v10 = v5;
  v11 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &v7, 0, 0, 3u, &v8);
}

```

## disassembly

```asm
0x1800034d0  mov     r11, rsp
0x1800034d3  sub     rsp, 88h
0x1800034da  mov     rax, cs:__security_cookie
0x1800034e1  xor     rax, rsp
0x1800034e4  mov     [rsp+88h+var_10], rax
0x1800034e9  mov     rax, [rsp+88h+arg_20]
0x1800034f1  mov     r10, rcx
0x1800034f4  mov     [r11-20h], rax
0x1800034f8  lea     rcx, [rdx+0Bh]
0x1800034fc  movzx   eax, byte ptr [rdx]
0x1800034ff  xor     r9d, r9d; RelatedActivityId
0x180003502  shl     eax, 18h
0x180003505  xor     r8d, r8d; ActivityId
0x180003508  mov     [rsp+88h+var_50], eax
0x18000350c  movzx   eax, word ptr [rdx+1]
0x180003510  mov     [rsp+88h+var_4C], eax
0x180003514  mov     rax, [rdx+3]
0x180003518  lea     rdx, [r11-50h]; EventDescriptor
0x18000351c  mov     [r11-48h], rax
0x180003520  mov     rax, [r10+8]
0x180003524  mov     [r11-40h], rax
0x180003528  mov     qword ptr [r11-18h], 4
0x180003530  movzx   eax, word ptr [rax]
0x180003533  mov     [rsp+88h+var_38], eax
0x180003537  movzx   eax, word ptr [rcx]
0x18000353a  mov     [rsp+88h+var_34], 2
0x180003542  mov     [r11-30h], rcx
0x180003546  lea     rcx, _TraceLoggingMetadata
0x18000354d  mov     [rsp+88h+var_28], eax
0x180003551  lea     rax, _TraceLoggingMetadataEnd
0x180003558  sub     eax, ecx
0x18000355a  mov     [rsp+88h+var_24], 1
0x180003562  mov     [rsp+88h+var_58], eax
0x180003566  mov     eax, [rsp+88h+var_58]
0x18000356a  mov     rcx, [r10+20h]; RegHandle
0x18000356e  lea     rax, [r11-40h]
0x180003572  mov     [r11-60h], rax
0x180003576  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x18000357e  call    cs:__imp_EventWriteTransfer
0x180003585  nop     dword ptr [rax+rax+00h]
0x18000358a  mov     rcx, [rsp+88h+var_10]
0x18000358f  xor     rcx, rsp; StackCookie
0x180003592  call    __security_check_cookie
0x180003597  add     rsp, 88h
0x18000359e  retn
```
