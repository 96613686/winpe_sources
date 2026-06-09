# _tlgWriteAgg

- ea: `0x18001b9d0`
- end: `0x18001bab5`
- name: `_tlgWriteAgg`
- size: `229`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001398`
- `0x1800014c4`

## callees

- `0x1800137b0`
- `0x180013838`
- `0x18001b9d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ba98`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ba98`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v7; // rax
  unsigned __int16 *v8; // rdx
  ULONG result; // eax
  char AggregateFieldTypes; // al
  int v11; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v7 = *(_QWORD *)(a2 + 3);
  v8 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v7;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v8;
  UserData[1].Size = *v8;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, UserData);
    if ( AggregateFieldTypes )
    {
      LOBYTE(v11) = a4;
      return InsertEventEntryInLookUpTable(
               a1,
               (unsigned int)&EventDescriptor,
               v11,
               (_DWORD)UserData,
               AggregateFieldTypes);
    }
    else
    {
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b9d0  mov     [rsp+arg_0], rbx
0x18001b9d5  mov     [rsp+arg_8], rsi
0x18001b9da  push    rdi
0x18001b9db  sub     rsp, 40h
0x18001b9df  movzx   eax, byte ptr [rdx]
0x18001b9e2  mov     rdi, rcx
0x18001b9e5  mov     rbx, [rsp+48h+arg_20]
0x18001b9ea  mov     esi, r9d
0x18001b9ed  shl     eax, 18h
0x18001b9f0  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18001b9f4  movzx   eax, word ptr [rdx+1]
0x18001b9f8  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001b9fc  mov     rax, [rdx+3]
0x18001ba00  add     rdx, 0Bh
0x18001ba04  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001ba09  mov     rax, [rcx+8]
0x18001ba0d  mov     [rbx], rax
0x18001ba10  mov     rax, [rcx+8]
0x18001ba14  movzx   ecx, word ptr [rax]
0x18001ba17  mov     [rbx+8], ecx
0x18001ba1a  lea     rcx, _TraceLoggingMetadata
0x18001ba21  mov     dword ptr [rbx+0Ch], 2
0x18001ba28  mov     [rbx+10h], rdx
0x18001ba2c  movzx   eax, word ptr [rdx]
0x18001ba2f  mov     [rbx+18h], eax
0x18001ba32  lea     rax, _TraceLoggingMetadataEnd
0x18001ba39  sub     eax, ecx
0x18001ba3b  mov     dword ptr [rbx+1Ch], 1
0x18001ba42  mov     dword ptr [rsp+48h+arg_20], eax
0x18001ba46  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18001ba4d  mov     eax, dword ptr [rsp+48h+arg_20]
0x18001ba51  mov     eax, 0C000000Dh
0x18001ba56  cmp     [rdi+28h], rcx
0x18001ba5a  jnz     short loc_18001BAA4
0x18001ba5c  mov     rdx, rbx
0x18001ba5f  call    ExtractAggregateFieldTypes
0x18001ba64  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18001ba69  test    al, al
0x18001ba6b  jz      short loc_18001BA81
0x18001ba6d  mov     r9, rbx
0x18001ba70  mov     byte ptr [rsp+48h+UserDataCount], al
0x18001ba74  mov     r8b, sil
0x18001ba77  mov     rcx, rdi
0x18001ba7a  call    InsertEventEntryInLookUpTable
0x18001ba7f  jmp     short loc_18001BAA4
0x18001ba81  mov     rcx, [rdi+20h]; RegHandle
0x18001ba85  xor     r9d, r9d; RelatedActivityId
0x18001ba88  movzx   eax, sil
0x18001ba8c  xor     r8d, r8d; ActivityId
0x18001ba8f  mov     [rsp+48h+UserData], rbx; UserData
0x18001ba94  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001ba98  call    cs:__imp_EventWriteTransfer
0x18001ba9f  nop     dword ptr [rax+rax+00h]
0x18001baa4  mov     rbx, [rsp+48h+arg_0]
0x18001baa9  mov     rsi, [rsp+48h+arg_8]
0x18001baae  add     rsp, 40h
0x18001bab2  pop     rdi
0x18001bab3  retn
```
