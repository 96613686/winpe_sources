# _tlgWriteAgg

- ea: `0x180015408`
- end: `0x180015544`
- name: `_tlgWriteAgg`
- size: `316`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, __int64, unsigned __int8, struct _EVENT_DATA_DESCRIPTOR *UserData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000df84`

## callees

- `0x180003478`
- `0x180014a70`
- `0x180015408`

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
      return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015408  push    rbx
0x18001540a  sub     rsp, 40h
0x18001540e  movzx   eax, byte ptr [rdx]
0x180015411  mov     r11, rcx
0x180015414  mov     r8, [rsp+48h+arg_20]
0x180015419  mov     ebx, r9d
0x18001541c  shl     eax, 18h
0x18001541f  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180015423  movzx   eax, word ptr [rdx+1]
0x180015427  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18001542b  mov     rax, [rdx+3]
0x18001542f  add     rdx, 0Bh
0x180015433  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180015438  mov     rax, [rcx+8]
0x18001543c  mov     [r8], rax
0x18001543f  mov     rax, [rcx+8]
0x180015443  movzx   ecx, word ptr [rax]
0x180015446  mov     [r8+8], ecx
0x18001544a  lea     rcx, _TraceLoggingMetadata
0x180015451  mov     dword ptr [r8+0Ch], 2
0x180015459  mov     [r8+10h], rdx
0x18001545d  movzx   eax, word ptr [rdx]
0x180015460  mov     [r8+18h], eax
0x180015464  lea     rax, _TraceLoggingMetadataEnd
0x18001546b  sub     eax, ecx
0x18001546d  mov     dword ptr [r8+1Ch], 1
0x180015475  mov     dword ptr [rsp+48h+arg_20], eax
0x180015479  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180015480  mov     eax, dword ptr [rsp+48h+arg_20]
0x180015484  mov     eax, 0C000000Dh
0x180015489  cmp     [r11+28h], rcx
0x18001548d  jnz     loc_18001553E
0x180015493  mov     rax, [r8+10h]
0x180015497  xor     r9b, r9b
0x18001549a  mov     r10d, [r8+18h]
0x18001549e  add     r10, rax
0x1800154a1  lea     rcx, [rax+2]
0x1800154a5  movzx   eax, byte ptr [rcx]
0x1800154a8  inc     rcx
0x1800154ab  test    al, al
0x1800154ad  js      short loc_1800154A5
0x1800154af  mov     al, [rcx]
0x1800154b1  inc     rcx
0x1800154b4  test    al, al
0x1800154b6  jnz     short loc_1800154AF
0x1800154b8  jmp     short loc_1800154FF
0x1800154ba  mov     al, [rcx]
0x1800154bc  inc     rcx
0x1800154bf  test    al, al
0x1800154c1  jnz     short loc_1800154BA
0x1800154c3  mov     al, [rcx]
0x1800154c5  test    al, al
0x1800154c7  jns     short loc_180015504
0x1800154c9  and     al, 7Fh
0x1800154cb  cmp     byte ptr [rcx+1], 0
0x1800154cf  jge     short loc_180015504
0x1800154d1  add     rcx, 2
0x1800154d5  jmp     short loc_1800154DF
0x1800154d7  cmp     dl, 80h
0x1800154da  jnz     short loc_180015504
0x1800154dc  inc     rcx
0x1800154df  mov     dl, [rcx]
0x1800154e1  test    dl, dl
0x1800154e3  js      short loc_1800154D7
0x1800154e5  cmp     al, 9
0x1800154e7  jnz     short loc_180015504
0x1800154e9  lea     eax, [rdx-71h]
0x1800154ec  cmp     al, 2
0x1800154ee  ja      short loc_180015504
0x1800154f0  movzx   eax, r9b
0x1800154f4  add     rax, rax
0x1800154f7  inc     r9b
0x1800154fa  mov     [r8+rax*8+2Dh], dl
0x1800154ff  cmp     rcx, r10
0x180015502  jb      short loc_1800154BA
0x180015504  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180015509  test    r9b, r9b
0x18001550c  jz      short loc_180015523
0x18001550e  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x180015513  mov     rcx, r11
0x180015516  mov     r9, r8
0x180015519  mov     r8b, bl
0x18001551c  call    InsertEventEntryInLookUpTable
0x180015521  jmp     short loc_18001553E
0x180015523  mov     rcx, [r11+20h]; RegHandle
0x180015527  xor     r9d, r9d; RelatedActivityId
0x18001552a  mov     [rsp+48h+UserData], r8; UserData
0x18001552f  xor     r8d, r8d; ActivityId
0x180015532  movzx   eax, bl
0x180015535  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180015539  call    EventWriteTransfer_0
0x18001553e  add     rsp, 40h
0x180015542  pop     rbx
0x180015543  retn
```
