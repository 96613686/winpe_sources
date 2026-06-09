# _tlgWriteAgg

- ea: `0x1800279f4`
- end: `0x180027aca`
- name: `_tlgWriteAgg`
- size: `214`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001eb28`

## callees

- `0x1800273c4`
- `0x180027588`
- `0x1800279f4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x180027ab7`
- `ntoskrnl!EtwWriteTransfer` at `0x180027ab7`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int64 v5; // rax
  unsigned __int16 *v6; // rdx
  NTSTATUS result; // eax
  char AggregateFieldTypes; // al
  int v9; // ecx
  int v10; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  UserData->Ptr = (unsigned __int64)off_1800310E0;
  UserData->Size = *(unsigned __int16 *)off_1800310E0;
  UserData->Reserved = 2;
  UserData[1].Ptr = (unsigned __int64)v6;
  UserData[1].Size = *v6;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180031100 == TlgAggregateInternalRegisteredProviderEtwCallback )
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
      return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800279f4  mov     [rsp+arg_18], r9d
0x1800279f9  push    rbx
0x1800279fa  sub     rsp, 40h
0x1800279fe  movzx   eax, byte ptr [rdx]
0x180027a01  mov     rbx, [rsp+48h+arg_20]
0x180027a06  shl     eax, 18h
0x180027a09  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180027a0d  movzx   eax, word ptr [rdx+1]
0x180027a11  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180027a15  mov     rax, [rdx+3]
0x180027a19  add     rdx, 0Bh
0x180027a1d  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180027a22  mov     rax, cs:off_1800310E0
0x180027a29  mov     [rbx], rax
0x180027a2c  mov     rax, cs:off_1800310E0
0x180027a33  movzx   ecx, word ptr [rax]
0x180027a36  mov     [rbx+8], ecx
0x180027a39  lea     rcx, _TraceLoggingMetadata
0x180027a40  mov     dword ptr [rbx+0Ch], 2
0x180027a47  mov     [rbx+10h], rdx
0x180027a4b  movzx   eax, word ptr [rdx]
0x180027a4e  mov     [rbx+18h], eax
0x180027a51  lea     rax, _TraceLoggingMetadataEnd
0x180027a58  sub     eax, ecx
0x180027a5a  mov     dword ptr [rbx+1Ch], 1
0x180027a61  mov     [rsp+48h+arg_18], eax
0x180027a65  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180027a6c  mov     eax, [rsp+48h+arg_18]
0x180027a70  cmp     cs:qword_180031100, rcx
0x180027a77  mov     eax, 0C000000Dh
0x180027a7c  jnz     short loc_180027AC3
0x180027a7e  mov     rdx, rbx
0x180027a81  call    ExtractAggregateFieldTypes
0x180027a86  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180027a8b  test    al, al
0x180027a8d  jz      short loc_180027A9D
0x180027a8f  mov     r9, rbx
0x180027a92  mov     byte ptr [rsp+48h+UserDataCount], al
0x180027a96  call    InsertEventEntryInLookUpTable
0x180027a9b  jmp     short loc_180027AC3
0x180027a9d  mov     rcx, cs:RegHandle; RegHandle
0x180027aa4  xor     r9d, r9d; RelatedActivityId
0x180027aa7  mov     [rsp+48h+UserData], rbx; UserData
0x180027aac  xor     r8d, r8d; ActivityId
0x180027aaf  mov     [rsp+48h+UserDataCount], 7; UserDataCount
0x180027ab7  call    cs:__imp_EtwWriteTransfer
0x180027abe  nop     dword ptr [rax+rax+00h]
0x180027ac3  add     rsp, 40h
0x180027ac7  pop     rbx
0x180027ac8  retn
```
