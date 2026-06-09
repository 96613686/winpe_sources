# _tlgWriteAgg

- ea: `0x18001ca5c`
- end: `0x18001cba2`
- name: `_tlgWriteAgg`
- size: `326`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180012c28`
- `0x180018564`
- `0x18001a308`

## callees

- `0x18000232a`
- `0x18001beb0`
- `0x18001ca5c`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  int v6; // r8d
  ULONGLONG v7; // rax
  unsigned __int16 *v8; // rdx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v11; // r9
  unsigned __int64 v12; // r10
  char *v13; // rcx
  char v14; // al
  char v17; // al
  char v18; // dl
  __int64 v19; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)UserData;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v7 = *(_QWORD *)(a2 + 3);
  v8 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v7;
  UserData->Ptr = (ULONGLONG)off_18002A1A8;
  UserData->Size = *(unsigned __int16 *)off_18002A1A8;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v8;
  UserData[1].Size = *v8;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_18002A1C8 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v11 = 0;
    v12 = Ptr + UserData[1].Size;
    v13 = (char *)(Ptr + 2);
    do
      v14 = *v13++;
    while ( v14 < 0 );
    while ( *v13++ )
      ;
    while ( (unsigned __int64)v13 < v12 )
    {
      while ( *v13++ )
        ;
      if ( *v13 >= 0 )
        break;
      v17 = *v13 & 0x7F;
      if ( v13[1] >= 0 )
        break;
      for ( v13 += 2; ; ++v13 )
      {
        v18 = *v13;
        if ( *v13 >= 0 )
          break;
        if ( v18 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v17 != 9 || (unsigned __int8)(v18 - 113) > 2u )
        break;
      v19 = v11++;
      UserData[v19 + 2].Reserved1 = v18;
    }
LABEL_17:
    if ( v11 )
    {
      LOBYTE(v6) = a4;
      return InsertEventEntryInLookUpTable((_DWORD)v13, (unsigned int)&EventDescriptor, v6, (_DWORD)UserData, v11);
    }
    else
    {
      return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ca5c  mov     [rsp+arg_10], r8
0x18001ca61  sub     rsp, 48h
0x18001ca65  movzx   eax, byte ptr [rdx]
0x18001ca68  mov     r11d, r9d
0x18001ca6b  mov     r8, [rsp+48h+arg_20]
0x18001ca70  shl     eax, 18h
0x18001ca73  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18001ca77  movzx   eax, word ptr [rdx+1]
0x18001ca7b  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001ca7f  mov     rax, [rdx+3]
0x18001ca83  add     rdx, 0Bh
0x18001ca87  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18001ca8c  mov     rax, cs:off_18002A1A8
0x18001ca93  mov     [r8], rax
0x18001ca96  mov     rax, cs:off_18002A1A8
0x18001ca9d  movzx   ecx, word ptr [rax]
0x18001caa0  mov     [r8+8], ecx
0x18001caa4  lea     rcx, _TraceLoggingMetadata
0x18001caab  mov     dword ptr [r8+0Ch], 2
0x18001cab3  mov     [r8+10h], rdx
0x18001cab7  movzx   eax, word ptr [rdx]
0x18001caba  mov     [r8+18h], eax
0x18001cabe  lea     rax, _TraceLoggingMetadataEnd
0x18001cac5  sub     eax, ecx
0x18001cac7  mov     dword ptr [r8+1Ch], 1
0x18001cacf  mov     dword ptr [rsp+48h+arg_10], eax
0x18001cad3  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18001cada  mov     eax, dword ptr [rsp+48h+arg_10]
0x18001cade  cmp     cs:qword_18002A1C8, rcx
0x18001cae5  mov     eax, 0C000000Dh
0x18001caea  jnz     loc_18001CB9C
0x18001caf0  mov     rax, [r8+10h]
0x18001caf4  xor     r9b, r9b
0x18001caf7  mov     r10d, [r8+18h]
0x18001cafb  add     r10, rax
0x18001cafe  lea     rcx, [rax+2]
0x18001cb02  movzx   eax, byte ptr [rcx]
0x18001cb05  inc     rcx
0x18001cb08  test    al, al
0x18001cb0a  js      short loc_18001CB02
0x18001cb0c  mov     al, [rcx]
0x18001cb0e  inc     rcx
0x18001cb11  test    al, al
0x18001cb13  jnz     short loc_18001CB0C
0x18001cb15  jmp     short loc_18001CB5C
0x18001cb17  mov     al, [rcx]
0x18001cb19  inc     rcx
0x18001cb1c  test    al, al
0x18001cb1e  jnz     short loc_18001CB17
0x18001cb20  mov     al, [rcx]
0x18001cb22  test    al, al
0x18001cb24  jns     short loc_18001CB61
0x18001cb26  and     al, 7Fh
0x18001cb28  cmp     byte ptr [rcx+1], 0
0x18001cb2c  jge     short loc_18001CB61
0x18001cb2e  add     rcx, 2
0x18001cb32  jmp     short loc_18001CB3C
0x18001cb34  cmp     dl, 80h
0x18001cb37  jnz     short loc_18001CB61
0x18001cb39  inc     rcx
0x18001cb3c  mov     dl, [rcx]
0x18001cb3e  test    dl, dl
0x18001cb40  js      short loc_18001CB34
0x18001cb42  cmp     al, 9
0x18001cb44  jnz     short loc_18001CB61
0x18001cb46  lea     eax, [rdx-71h]
0x18001cb49  cmp     al, 2
0x18001cb4b  ja      short loc_18001CB61
0x18001cb4d  movzx   eax, r9b
0x18001cb51  add     rax, rax
0x18001cb54  inc     r9b
0x18001cb57  mov     [r8+rax*8+2Dh], dl
0x18001cb5c  cmp     rcx, r10
0x18001cb5f  jb      short loc_18001CB17
0x18001cb61  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18001cb66  test    r9b, r9b
0x18001cb69  jz      short loc_18001CB7D
0x18001cb6b  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x18001cb70  mov     r9, r8
0x18001cb73  mov     r8b, r11b
0x18001cb76  call    InsertEventEntryInLookUpTable
0x18001cb7b  jmp     short loc_18001CB9C
0x18001cb7d  mov     rcx, cs:RegHandle; RegHandle
0x18001cb84  xor     r9d, r9d; RelatedActivityId
0x18001cb87  mov     [rsp+48h+UserData], r8; UserData
0x18001cb8c  xor     r8d, r8d; ActivityId
0x18001cb8f  movzx   eax, r11b
0x18001cb93  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18001cb97  call    EventWriteTransfer_0
0x18001cb9c  add     rsp, 48h
0x18001cba0  retn
```
