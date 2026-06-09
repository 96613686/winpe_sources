# _tlgWriteAgg

- ea: `0x1800081d4`
- end: `0x18000831c`
- name: `_tlgWriteAgg`
- size: `328`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006a64`
- `0x180006b9c`
- `0x180006cb4`

## callees

- `0x180007670`
- `0x1800081d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008311`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008311`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(__int64 a1, unsigned __int8 *a2, __int64 a3, __int64 a4, PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v9; // r9
  ULONGLONG v10; // r10
  char *v11; // rcx
  char v12; // al
  char v15; // al
  UCHAR v16; // dl
  __int64 v17; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  UserData->Ptr = (ULONGLONG)off_18000D008;
  UserData->Size = (unsigned __int16)*off_18000D008;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v6;
  UserData[1].Size = *v6;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_18000D028 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v9 = 0;
    v10 = Ptr + UserData[1].Size;
    v11 = (char *)(Ptr + 2);
    do
      v12 = *v11++;
    while ( v12 < 0 );
    while ( *v11++ )
      ;
    if ( (unsigned __int64)v11 >= v10 )
      return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, UserData);
    do
    {
      while ( *v11++ )
        ;
      if ( *v11 >= 0 )
        break;
      v15 = *v11 & 0x7F;
      if ( v11[1] >= 0 )
        break;
      for ( v11 += 2; ; ++v11 )
      {
        v16 = *v11;
        if ( *v11 >= 0 )
          break;
        if ( v16 != 0x80 )
          goto LABEL_16;
      }
      if ( v15 != 9 )
        break;
      if ( (unsigned __int8)(v16 - 113) > 2u )
        break;
      v17 = v9++;
      UserData[v17 + 2].Reserved1 = v16;
    }
    while ( (unsigned __int64)v11 < v10 );
LABEL_16:
    if ( v9 )
      return InsertEventEntryInLookUpTable(
               (_DWORD)v11,
               (unsigned int)&EventDescriptor,
               (_DWORD)UserData,
               (_DWORD)UserData,
               v9);
    else
      return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800081d4  mov     [rsp+arg_18], r9d
0x1800081d9  sub     rsp, 48h
0x1800081dd  movzx   eax, byte ptr [rdx]
0x1800081e0  mov     r8, [rsp+48h+arg_20]
0x1800081e5  shl     eax, 18h
0x1800081e8  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800081ec  movzx   eax, word ptr [rdx+1]
0x1800081f0  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800081f4  mov     rax, [rdx+3]
0x1800081f8  add     rdx, 0Bh
0x1800081fc  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180008201  mov     rax, cs:off_18000D008
0x180008208  mov     [r8], rax
0x18000820b  mov     rax, cs:off_18000D008
0x180008212  movzx   ecx, word ptr [rax]
0x180008215  mov     [r8+8], ecx
0x180008219  lea     rcx, _TraceLoggingMetadata
0x180008220  mov     dword ptr [r8+0Ch], 2
0x180008228  mov     [r8+10h], rdx
0x18000822c  movzx   eax, word ptr [rdx]
0x18000822f  mov     [r8+18h], eax
0x180008233  lea     rax, _TraceLoggingMetadataEnd
0x18000823a  sub     eax, ecx
0x18000823c  mov     dword ptr [r8+1Ch], 1
0x180008244  mov     [rsp+48h+arg_18], eax
0x180008248  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000824f  mov     eax, [rsp+48h+arg_18]
0x180008253  cmp     cs:qword_18000D028, rcx
0x18000825a  mov     eax, 0C000000Dh
0x18000825f  jnz     loc_180008317
0x180008265  mov     rax, [r8+10h]
0x180008269  xor     r9b, r9b
0x18000826c  mov     r10d, [r8+18h]
0x180008270  add     r10, rax
0x180008273  lea     rcx, [rax+2]
0x180008277  movzx   eax, byte ptr [rcx]
0x18000827a  inc     rcx
0x18000827d  test    al, al
0x18000827f  js      short loc_180008277
0x180008281  mov     al, [rcx]
0x180008283  inc     rcx
0x180008286  test    al, al
0x180008288  jnz     short loc_180008281
0x18000828a  cmp     rcx, r10
0x18000828d  jnb     short loc_1800082F2
0x18000828f  mov     al, [rcx]
0x180008291  inc     rcx
0x180008294  test    al, al
0x180008296  jnz     short loc_18000828F
0x180008298  mov     al, [rcx]
0x18000829a  test    al, al
0x18000829c  jns     short loc_1800082D9
0x18000829e  and     al, 7Fh
0x1800082a0  cmp     byte ptr [rcx+1], 0
0x1800082a4  jge     short loc_1800082D9
0x1800082a6  add     rcx, 2
0x1800082aa  jmp     short loc_1800082B4
0x1800082ac  cmp     dl, 80h
0x1800082af  jnz     short loc_1800082D9
0x1800082b1  inc     rcx
0x1800082b4  mov     dl, [rcx]
0x1800082b6  test    dl, dl
0x1800082b8  js      short loc_1800082AC
0x1800082ba  cmp     al, 9
0x1800082bc  jnz     short loc_1800082D9
0x1800082be  lea     eax, [rdx-71h]
0x1800082c1  cmp     al, 2
0x1800082c3  ja      short loc_1800082D9
0x1800082c5  movzx   eax, r9b
0x1800082c9  inc     r9b
0x1800082cc  add     rax, rax
0x1800082cf  mov     [r8+rax*8+2Dh], dl
0x1800082d4  cmp     rcx, r10
0x1800082d7  jb      short loc_18000828F
0x1800082d9  test    r9b, r9b
0x1800082dc  jz      short loc_1800082F2
0x1800082de  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x1800082e3  lea     rdx, [rsp+48h+EventDescriptor]
0x1800082e8  mov     r9, r8
0x1800082eb  call    InsertEventEntryInLookUpTable
0x1800082f0  jmp     short loc_180008317
0x1800082f2  mov     rcx, cs:RegHandle; RegHandle
0x1800082f9  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800082fe  mov     [rsp+48h+UserData], r8; UserData
0x180008303  xor     r9d, r9d; RelatedActivityId
0x180008306  xor     r8d, r8d; ActivityId
0x180008309  mov     [rsp+48h+UserDataCount], 7; UserDataCount
0x180008311  call    cs:__imp_EventWriteTransfer
0x180008317  add     rsp, 48h
0x18000831b  retn
```
