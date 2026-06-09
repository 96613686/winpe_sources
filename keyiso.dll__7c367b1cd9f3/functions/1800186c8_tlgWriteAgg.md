# _tlgWriteAgg

- ea: `0x1800186c8`
- end: `0x180018799`
- name: `_tlgWriteAgg`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a798`
- `0x18000a8e8`

## callees

- `0x180017a70`
- `0x180017cb0`
- `0x1800186c8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001878e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001878e`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(__int64 a1, unsigned __int8 *a2, __int64 a3, __int64 a4, __int64 a5)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  ULONG result; // eax
  char AggregateFieldTypes; // al
  int v9; // ecx
  int v10; // r8d
  struct _EVENT_DATA_DESCRIPTOR *UserData; // r11
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  *(_QWORD *)a5 = off_180025130;
  *(_DWORD *)(a5 + 8) = *(unsigned __int16 *)off_180025130;
  *(_DWORD *)(a5 + 12) = 2;
  *(_QWORD *)(a5 + 16) = v6;
  *(_DWORD *)(a5 + 24) = *v6;
  *(_DWORD *)(a5 + 28) = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180025150 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, a5);
    if ( AggregateFieldTypes )
      return InsertEventEntryInLookUpTable(
               v9,
               (unsigned int)&EventDescriptor,
               v10,
               (_DWORD)UserData,
               AggregateFieldTypes);
    else
      return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800186c8  mov     [rsp+arg_18], r9d
0x1800186cd  sub     rsp, 48h
0x1800186d1  movzx   eax, byte ptr [rdx]
0x1800186d4  mov     r11, [rsp+48h+arg_20]
0x1800186d9  shl     eax, 18h
0x1800186dc  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800186e0  movzx   eax, word ptr [rdx+1]
0x1800186e4  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800186e8  mov     rax, [rdx+3]
0x1800186ec  add     rdx, 0Bh
0x1800186f0  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800186f5  mov     rax, cs:off_180025130
0x1800186fc  mov     [r11], rax
0x1800186ff  mov     rax, cs:off_180025130
0x180018706  movzx   ecx, word ptr [rax]
0x180018709  mov     [r11+8], ecx
0x18001870d  lea     rcx, _TraceLoggingMetadata
0x180018714  mov     dword ptr [r11+0Ch], 2
0x18001871c  mov     [r11+10h], rdx
0x180018720  movzx   eax, word ptr [rdx]
0x180018723  mov     [r11+18h], eax
0x180018727  lea     rax, _TraceLoggingMetadataEnd
0x18001872e  sub     eax, ecx
0x180018730  mov     dword ptr [r11+1Ch], 1
0x180018738  mov     [rsp+48h+arg_18], eax
0x18001873c  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180018743  mov     eax, [rsp+48h+arg_18]
0x180018747  cmp     cs:qword_180025150, rcx
0x18001874e  mov     eax, 0C000000Dh
0x180018753  jnz     short loc_180018794
0x180018755  mov     rdx, r11
0x180018758  call    ExtractAggregateFieldTypes
0x18001875d  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180018762  test    al, al
0x180018764  jz      short loc_180018774
0x180018766  mov     r9, r11
0x180018769  mov     byte ptr [rsp+48h+UserDataCount], al
0x18001876d  call    InsertEventEntryInLookUpTable
0x180018772  jmp     short loc_180018794
0x180018774  mov     rcx, cs:RegHandle; RegHandle
0x18001877b  xor     r9d, r9d; RelatedActivityId
0x18001877e  mov     [rsp+48h+UserData], r11; UserData
0x180018783  xor     r8d, r8d; ActivityId
0x180018786  mov     [rsp+48h+UserDataCount], 5; UserDataCount
0x18001878e  call    cs:__imp_EventWriteTransfer
0x180018794  add     rsp, 48h
0x180018798  retn
```
