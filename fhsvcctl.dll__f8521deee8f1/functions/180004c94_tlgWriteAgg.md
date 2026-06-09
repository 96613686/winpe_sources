# _tlgWriteAgg

- ea: `0x180004c94`
- end: `0x180004dd1`
- name: `_tlgWriteAgg`
- size: `317`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, unsigned __int8, struct _EVENT_DATA_DESCRIPTOR *UserData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a00`

## callees

- `0x180004120`
- `0x180004c94`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180004dc5`
- `ADVAPI32!EventWriteTransfer` at `0x180004dc5`

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
  ULONGLONG v8; // rax
  unsigned __int16 *v9; // rdx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v12; // r9
  unsigned __int64 v13; // r10
  char *v14; // rcx
  char v15; // al
  char v18; // al
  char v19; // dl
  __int64 v20; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)UserData;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v8 = *(_QWORD *)(a2 + 3);
  v9 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v8;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v9;
  UserData[1].Size = *v9;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v12 = 0;
    v13 = Ptr + UserData[1].Size;
    v14 = (char *)(Ptr + 2);
    do
      v15 = *v14++;
    while ( v15 < 0 );
    while ( *v14++ )
      ;
    while ( (unsigned __int64)v14 < v13 )
    {
      while ( *v14++ )
        ;
      if ( *v14 >= 0 )
        break;
      v18 = *v14 & 0x7F;
      if ( v14[1] >= 0 )
        break;
      for ( v14 += 2; ; ++v14 )
      {
        v19 = *v14;
        if ( *v14 >= 0 )
          break;
        if ( v19 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v18 != 9 || (unsigned __int8)(v19 - 113) > 2u )
        break;
      v20 = v12++;
      UserData[v20 + 2].Reserved1 = v19;
    }
LABEL_17:
    if ( v12 )
    {
      LOBYTE(v6) = a4;
      return InsertEventEntryInLookUpTable(a1, (unsigned int)&EventDescriptor, v6, (_DWORD)UserData, v12);
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
0x180004c94  push    rbx
0x180004c96  sub     rsp, 40h
0x180004c9a  movzx   eax, byte ptr [rdx]
0x180004c9d  mov     r11, rcx
0x180004ca0  mov     r8, [rsp+48h+arg_20]
0x180004ca5  mov     ebx, r9d
0x180004ca8  shl     eax, 18h
0x180004cab  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180004caf  movzx   eax, word ptr [rdx+1]
0x180004cb3  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180004cb7  mov     rax, [rdx+3]
0x180004cbb  add     rdx, 0Bh
0x180004cbf  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180004cc4  mov     rax, [rcx+8]
0x180004cc8  mov     [r8], rax
0x180004ccb  mov     rax, [rcx+8]
0x180004ccf  movzx   ecx, word ptr [rax]
0x180004cd2  mov     [r8+8], ecx
0x180004cd6  lea     rcx, _TraceLoggingMetadata
0x180004cdd  mov     dword ptr [r8+0Ch], 2
0x180004ce5  mov     [r8+10h], rdx
0x180004ce9  movzx   eax, word ptr [rdx]
0x180004cec  mov     [r8+18h], eax
0x180004cf0  lea     rax, _TraceLoggingMetadataEnd
0x180004cf7  sub     eax, ecx
0x180004cf9  mov     dword ptr [r8+1Ch], 1
0x180004d01  mov     dword ptr [rsp+48h+arg_20], eax
0x180004d05  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180004d0c  mov     eax, dword ptr [rsp+48h+arg_20]
0x180004d10  mov     eax, 0C000000Dh
0x180004d15  cmp     [r11+28h], rcx
0x180004d19  jnz     loc_180004DCB
0x180004d1f  mov     rax, [r8+10h]
0x180004d23  xor     r9b, r9b
0x180004d26  mov     r10d, [r8+18h]
0x180004d2a  add     r10, rax
0x180004d2d  lea     rcx, [rax+2]
0x180004d31  movzx   eax, byte ptr [rcx]
0x180004d34  inc     rcx
0x180004d37  test    al, al
0x180004d39  js      short loc_180004D31
0x180004d3b  mov     al, [rcx]
0x180004d3d  inc     rcx
0x180004d40  test    al, al
0x180004d42  jnz     short loc_180004D3B
0x180004d44  jmp     short loc_180004D8B
0x180004d46  mov     al, [rcx]
0x180004d48  inc     rcx
0x180004d4b  test    al, al
0x180004d4d  jnz     short loc_180004D46
0x180004d4f  mov     al, [rcx]
0x180004d51  test    al, al
0x180004d53  jns     short loc_180004D90
0x180004d55  and     al, 7Fh
0x180004d57  cmp     byte ptr [rcx+1], 0
0x180004d5b  jge     short loc_180004D90
0x180004d5d  add     rcx, 2
0x180004d61  jmp     short loc_180004D6B
0x180004d63  cmp     dl, 80h
0x180004d66  jnz     short loc_180004D90
0x180004d68  inc     rcx
0x180004d6b  mov     dl, [rcx]
0x180004d6d  test    dl, dl
0x180004d6f  js      short loc_180004D63
0x180004d71  cmp     al, 9
0x180004d73  jnz     short loc_180004D90
0x180004d75  lea     eax, [rdx-71h]
0x180004d78  cmp     al, 2
0x180004d7a  ja      short loc_180004D90
0x180004d7c  movzx   eax, r9b
0x180004d80  add     rax, rax
0x180004d83  inc     r9b
0x180004d86  mov     [r8+rax*8+2Dh], dl
0x180004d8b  cmp     rcx, r10
0x180004d8e  jb      short loc_180004D46
0x180004d90  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180004d95  test    r9b, r9b
0x180004d98  jz      short loc_180004DAF
0x180004d9a  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x180004d9f  mov     rcx, r11
0x180004da2  mov     r9, r8
0x180004da5  mov     r8b, bl
0x180004da8  call    InsertEventEntryInLookUpTable
0x180004dad  jmp     short loc_180004DCB
0x180004daf  mov     rcx, [r11+20h]; RegHandle
0x180004db3  xor     r9d, r9d; RelatedActivityId
0x180004db6  mov     [rsp+48h+UserData], r8; UserData
0x180004dbb  xor     r8d, r8d; ActivityId
0x180004dbe  movzx   eax, bl
0x180004dc1  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180004dc5  call    cs:__imp_EventWriteTransfer
0x180004dcb  add     rsp, 40h
0x180004dcf  pop     rbx
0x180004dd0  retn
```
