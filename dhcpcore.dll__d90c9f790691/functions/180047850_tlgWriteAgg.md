# _tlgWriteAgg

- ea: `0x180047850`
- end: `0x18004791f`
- name: `_tlgWriteAgg`
- size: `207`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003191c`

## callees

- `0x180046c48`
- `0x180046e70`
- `0x180047850`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180047913`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180047913`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(__int64 a1, unsigned __int8 *a2, __int64 a3, __int64 a4, PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  ULONG result; // eax
  char AggregateFieldTypes; // al
  int v9; // ecx
  int v10; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  UserData->Ptr = (ULONGLONG)off_1800610E0;
  UserData->Size = *(unsigned __int16 *)off_1800610E0;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v6;
  UserData[1].Size = *v6;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_180061100 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, UserData);
    if ( AggregateFieldTypes )
      return InsertEventEntryInLookUpTable(
               v9,
               (unsigned int)&EventDescriptor,
               v10,
               (_DWORD)UserData,
               AggregateFieldTypes);
    else
      return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x180047850  mov     [rsp+arg_18], r9d
0x180047855  push    rbx
0x180047856  sub     rsp, 40h
0x18004785a  movzx   eax, byte ptr [rdx]
0x18004785d  mov     rbx, [rsp+48h+arg_20]
0x180047862  shl     eax, 18h
0x180047865  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180047869  movzx   eax, word ptr [rdx+1]
0x18004786d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180047871  mov     rax, [rdx+3]
0x180047875  add     rdx, 0Bh
0x180047879  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18004787e  mov     rax, cs:off_1800610E0
0x180047885  mov     [rbx], rax
0x180047888  mov     rax, cs:off_1800610E0
0x18004788f  movzx   ecx, word ptr [rax]
0x180047892  mov     [rbx+8], ecx
0x180047895  lea     rcx, _TraceLoggingMetadata
0x18004789c  mov     dword ptr [rbx+0Ch], 2
0x1800478a3  mov     [rbx+10h], rdx
0x1800478a7  movzx   eax, word ptr [rdx]
0x1800478aa  mov     [rbx+18h], eax
0x1800478ad  lea     rax, _TraceLoggingMetadataEnd
0x1800478b4  sub     eax, ecx
0x1800478b6  mov     dword ptr [rbx+1Ch], 1
0x1800478bd  mov     [rsp+48h+arg_18], eax
0x1800478c1  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1800478c8  mov     eax, [rsp+48h+arg_18]
0x1800478cc  cmp     cs:qword_180061100, rcx
0x1800478d3  mov     eax, 0C000000Dh
0x1800478d8  jnz     short loc_180047919
0x1800478da  mov     rdx, rbx
0x1800478dd  call    ExtractAggregateFieldTypes
0x1800478e2  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800478e7  test    al, al
0x1800478e9  jz      short loc_1800478F9
0x1800478eb  mov     r9, rbx
0x1800478ee  mov     byte ptr [rsp+48h+UserDataCount], al
0x1800478f2  call    InsertEventEntryInLookUpTable
0x1800478f7  jmp     short loc_180047919
0x1800478f9  mov     rcx, cs:RegHandle; RegHandle
0x180047900  xor     r9d, r9d; RelatedActivityId
0x180047903  mov     [rsp+48h+UserData], rbx; UserData
0x180047908  xor     r8d, r8d; ActivityId
0x18004790b  mov     [rsp+48h+UserDataCount], 6; UserDataCount
0x180047913  call    cs:__imp_EventWriteTransfer
0x180047919  add     rsp, 40h
0x18004791d  pop     rbx
0x18004791e  retn
```
