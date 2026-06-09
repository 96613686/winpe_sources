# _tlgWriteAgg

- ea: `0x1400081a4`
- end: `0x14000828d`
- name: `_tlgWriteAgg`
- size: `233`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a22c`
- `0x14000b7e8`
- `0x14000bad4`
- `0x140015378`
- `0x1400155e0`
- `0x1400159b0`
- `0x140015c28`
- `0x140015e40`
- `0x1400160dc`
- `0x14001663c`
- `0x140016b38`
- `0x140016f6c`

## callees

- `0x1400081a4`
- `0x140008294`
- `0x14000831c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000827f`
- `ntoskrnl!EtwWriteTransfer` at `0x14000827f`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v7; // rax
  unsigned __int16 *v8; // rdx
  NTSTATUS result; // eax
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
      return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400081a4  mov     r11, rsp
0x1400081a7  mov     [r11+8], rbx
0x1400081ab  mov     [r11+10h], rsi
0x1400081af  mov     [r11+18h], r8
0x1400081b3  push    rdi
0x1400081b4  sub     rsp, 40h
0x1400081b8  movzx   eax, byte ptr [rdx]
0x1400081bb  mov     rdi, rcx
0x1400081be  mov     rbx, [rsp+48h+arg_20]
0x1400081c3  mov     esi, r9d
0x1400081c6  shl     eax, 18h
0x1400081c9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400081cd  movzx   eax, word ptr [rdx+1]
0x1400081d1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400081d5  mov     rax, [rdx+3]
0x1400081d9  add     rdx, 0Bh
0x1400081dd  mov     [r11-10h], rax
0x1400081e1  mov     rax, [rcx+8]
0x1400081e5  mov     [rbx], rax
0x1400081e8  mov     rax, [rcx+8]
0x1400081ec  movzx   ecx, word ptr [rax]
0x1400081ef  mov     [rbx+8], ecx
0x1400081f2  lea     rcx, _TraceLoggingMetadata
0x1400081f9  mov     dword ptr [rbx+0Ch], 2
0x140008200  mov     [rbx+10h], rdx
0x140008204  movzx   eax, word ptr [rdx]
0x140008207  mov     [rbx+18h], eax
0x14000820a  lea     rax, _TraceLoggingMetadataEnd
0x140008211  sub     eax, ecx
0x140008213  mov     dword ptr [rbx+1Ch], 1
0x14000821a  mov     [rsp+48h+arg_10], eax
0x14000821e  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140008225  mov     eax, [rsp+48h+arg_10]
0x140008229  mov     eax, 0C000000Dh
0x14000822e  cmp     [rdi+28h], rcx
0x140008232  jnz     short loc_140008257
0x140008234  mov     rdx, rbx
0x140008237  call    ExtractAggregateFieldTypes
0x14000823c  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140008241  test    al, al
0x140008243  jz      short loc_140008268
0x140008245  mov     r9, rbx
0x140008248  mov     byte ptr [rsp+48h+UserDataCount], al
0x14000824c  mov     r8b, sil
0x14000824f  mov     rcx, rdi
0x140008252  call    InsertEventEntryInLookUpTable
0x140008257  mov     rbx, [rsp+48h+arg_0]
0x14000825c  mov     rsi, [rsp+48h+arg_8]
0x140008261  add     rsp, 40h
0x140008265  pop     rdi
0x140008266  retn
0x140008268  mov     rcx, [rdi+20h]; RegHandle
0x14000826c  xor     r9d, r9d; RelatedActivityId
0x14000826f  movzx   eax, sil
0x140008273  xor     r8d, r8d; ActivityId
0x140008276  mov     [rsp+48h+UserData], rbx; UserData
0x14000827b  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14000827f  call    cs:__imp_EtwWriteTransfer
0x140008286  nop     dword ptr [rax+rax+00h]
0x14000828b  jmp     short loc_140008257
```
