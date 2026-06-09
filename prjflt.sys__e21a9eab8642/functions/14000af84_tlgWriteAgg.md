# _tlgWriteAgg

- ea: `0x14000af84`
- end: `0x14000b0d1`
- name: `_tlgWriteAgg`
- size: `333`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140005e8c`
- `0x1400063fc`
- `0x140028d9c`
- `0x1400370c0`
- `0x140037418`

## callees

- `0x14000aad0`
- `0x14000af84`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000b0bf`
- `ntoskrnl!EtwWriteTransfer` at `0x14000b0bf`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  NTSTATUS result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v10; // r9
  unsigned __int64 v11; // r10
  char *v12; // rcx
  char v13; // al
  char v16; // al
  char v17; // dl
  __int64 v18; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = (ULONGLONG)off_14001A070;
  UserData->Size = *(unsigned __int16 *)off_14001A070;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_14001A090 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v10 = 0;
    v11 = Ptr + UserData[1].Size;
    v12 = (char *)(Ptr + 2);
    do
      v13 = *v12++;
    while ( v13 < 0 );
    while ( *v12++ )
      ;
    while ( (unsigned __int64)v12 < v11 )
    {
      while ( *v12++ )
        ;
      if ( *v12 >= 0 )
        break;
      v16 = *v12 & 0x7F;
      if ( v12[1] >= 0 )
        break;
      for ( v12 += 2; ; ++v12 )
      {
        v17 = *v12;
        if ( *v12 >= 0 )
          break;
        if ( v17 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v16 != 9 || (unsigned __int8)(v17 - 113) > 2u )
        break;
      v18 = v10++;
      UserData[v18 + 2].Reserved1 = v17;
    }
LABEL_17:
    if ( v10 )
      return InsertEventEntryInLookUpTable((__int64)v12, (__int128 *)&EventDescriptor, a4, (__int64)UserData, v10);
    else
      return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, a4, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x14000af84  mov     [rsp+arg_10], r8
0x14000af89  sub     rsp, 48h
0x14000af8d  movzx   eax, byte ptr [rdx]
0x14000af90  mov     r11d, r9d
0x14000af93  mov     r8, [rsp+48h+arg_20]
0x14000af98  shl     eax, 18h
0x14000af9b  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000af9f  movzx   eax, word ptr [rdx+1]
0x14000afa3  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000afa7  mov     rax, [rdx+3]
0x14000afab  add     rdx, 0Bh
0x14000afaf  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000afb4  mov     rax, cs:off_14001A070
0x14000afbb  mov     [r8], rax
0x14000afbe  mov     rax, cs:off_14001A070
0x14000afc5  movzx   ecx, word ptr [rax]
0x14000afc8  mov     [r8+8], ecx
0x14000afcc  lea     rcx, _TraceLoggingMetadata
0x14000afd3  mov     dword ptr [r8+0Ch], 2
0x14000afdb  mov     [r8+10h], rdx
0x14000afdf  movzx   eax, word ptr [rdx]
0x14000afe2  mov     [r8+18h], eax
0x14000afe6  lea     rax, _TraceLoggingMetadataEnd
0x14000afed  sub     eax, ecx
0x14000afef  mov     dword ptr [r8+1Ch], 1
0x14000aff7  mov     dword ptr [rsp+48h+arg_10], eax
0x14000affb  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14000b002  mov     eax, dword ptr [rsp+48h+arg_10]
0x14000b006  cmp     cs:qword_14001A090, rcx
0x14000b00d  mov     eax, 0C000000Dh
0x14000b012  jnz     loc_14000B0CB
0x14000b018  mov     rax, [r8+10h]
0x14000b01c  xor     r9b, r9b
0x14000b01f  mov     r10d, [r8+18h]
0x14000b023  add     r10, rax
0x14000b026  lea     rcx, [rax+2]
0x14000b02a  movzx   eax, byte ptr [rcx]
0x14000b02d  inc     rcx
0x14000b030  test    al, al
0x14000b032  js      short loc_14000B02A
0x14000b034  mov     al, [rcx]
0x14000b036  inc     rcx
0x14000b039  test    al, al
0x14000b03b  jnz     short loc_14000B034
0x14000b03d  jmp     short loc_14000B084
0x14000b03f  mov     al, [rcx]
0x14000b041  inc     rcx
0x14000b044  test    al, al
0x14000b046  jnz     short loc_14000B03F
0x14000b048  mov     al, [rcx]
0x14000b04a  test    al, al
0x14000b04c  jns     short loc_14000B089
0x14000b04e  and     al, 7Fh
0x14000b050  cmp     byte ptr [rcx+1], 0
0x14000b054  jge     short loc_14000B089
0x14000b056  add     rcx, 2
0x14000b05a  jmp     short loc_14000B064
0x14000b05c  cmp     dl, 80h
0x14000b05f  jnz     short loc_14000B089
0x14000b061  inc     rcx
0x14000b064  mov     dl, [rcx]
0x14000b066  test    dl, dl
0x14000b068  js      short loc_14000B05C
0x14000b06a  cmp     al, 9
0x14000b06c  jnz     short loc_14000B089
0x14000b06e  lea     eax, [rdx-71h]
0x14000b071  cmp     al, 2
0x14000b073  ja      short loc_14000B089
0x14000b075  movzx   eax, r9b
0x14000b079  add     rax, rax
0x14000b07c  inc     r9b
0x14000b07f  mov     [r8+rax*8+2Dh], dl
0x14000b084  cmp     rcx, r10
0x14000b087  jb      short loc_14000B03F
0x14000b089  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14000b08e  test    r9b, r9b
0x14000b091  jz      short loc_14000B0A5
0x14000b093  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x14000b098  mov     r9, r8
0x14000b09b  mov     r8b, r11b
0x14000b09e  call    InsertEventEntryInLookUpTable
0x14000b0a3  jmp     short loc_14000B0CB
0x14000b0a5  mov     rcx, cs:RegHandle; RegHandle
0x14000b0ac  xor     r9d, r9d; RelatedActivityId
0x14000b0af  mov     [rsp+48h+UserData], r8; UserData
0x14000b0b4  xor     r8d, r8d; ActivityId
0x14000b0b7  movzx   eax, r11b
0x14000b0bb  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14000b0bf  call    cs:__imp_EtwWriteTransfer
0x14000b0c6  nop     dword ptr [rax+rax+00h]
0x14000b0cb  add     rsp, 48h
0x14000b0cf  retn
```
