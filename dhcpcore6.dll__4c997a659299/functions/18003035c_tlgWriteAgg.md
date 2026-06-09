# _tlgWriteAgg

- ea: `0x18003035c`
- end: `0x180030432`
- name: `_tlgWriteAgg`
- size: `214`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020824`

## callees

- `0x18002fb60`
- `0x18002fda0`
- `0x18003035c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003041f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003041f`

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
  UserData->Ptr = (ULONGLONG)off_180042050;
  UserData->Size = *(unsigned __int16 *)off_180042050;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v6;
  UserData[1].Size = *v6;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180042070 == TlgAggregateInternalRegisteredProviderEtwCallback )
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
0x18003035c  mov     [rsp+arg_18], r9d
0x180030361  push    rbx
0x180030362  sub     rsp, 40h
0x180030366  movzx   eax, byte ptr [rdx]
0x180030369  mov     rbx, [rsp+48h+arg_20]
0x18003036e  shl     eax, 18h
0x180030371  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180030375  movzx   eax, word ptr [rdx+1]
0x180030379  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18003037d  mov     rax, [rdx+3]
0x180030381  add     rdx, 0Bh
0x180030385  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18003038a  mov     rax, cs:off_180042050
0x180030391  mov     [rbx], rax
0x180030394  mov     rax, cs:off_180042050
0x18003039b  movzx   ecx, word ptr [rax]
0x18003039e  mov     [rbx+8], ecx
0x1800303a1  lea     rcx, _TraceLoggingMetadata
0x1800303a8  mov     dword ptr [rbx+0Ch], 2
0x1800303af  mov     [rbx+10h], rdx
0x1800303b3  movzx   eax, word ptr [rdx]
0x1800303b6  mov     [rbx+18h], eax
0x1800303b9  lea     rax, _TraceLoggingMetadataEnd
0x1800303c0  sub     eax, ecx
0x1800303c2  mov     dword ptr [rbx+1Ch], 1
0x1800303c9  mov     [rsp+48h+arg_18], eax
0x1800303cd  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1800303d4  mov     eax, [rsp+48h+arg_18]
0x1800303d8  cmp     cs:qword_180042070, rcx
0x1800303df  mov     eax, 0C000000Dh
0x1800303e4  jnz     short loc_18003042B
0x1800303e6  mov     rdx, rbx
0x1800303e9  call    ExtractAggregateFieldTypes
0x1800303ee  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800303f3  test    al, al
0x1800303f5  jz      short loc_180030405
0x1800303f7  mov     r9, rbx
0x1800303fa  mov     byte ptr [rsp+48h+UserDataCount], al
0x1800303fe  call    InsertEventEntryInLookUpTable
0x180030403  jmp     short loc_18003042B
0x180030405  mov     rcx, cs:RegHandle; RegHandle
0x18003040c  xor     r9d, r9d; RelatedActivityId
0x18003040f  mov     [rsp+48h+UserData], rbx; UserData
0x180030414  xor     r8d, r8d; ActivityId
0x180030417  mov     [rsp+48h+UserDataCount], 6; UserDataCount
0x18003041f  call    cs:__imp_EventWriteTransfer
0x180030426  nop     dword ptr [rax+rax+00h]
0x18003042b  add     rsp, 40h
0x18003042f  pop     rbx
0x180030430  retn
```
