# _tlgWriteAgg

- ea: `0x14001b4c0`
- end: `0x14001b626`
- name: `_tlgWriteAgg`
- size: `358`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, __int64, unsigned __int8, unsigned __int8 *UserData)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140024f20`
- `0x140025b70`
- `0x140026bd0`
- `0x140053130`

## callees

- `0x14001b4c0`
- `0x14001b630`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001b60c`
- `ntoskrnl!EtwWriteTransfer` at `0x14001b60c`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        unsigned __int8 *UserData)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  ULONGLONG v7; // rax
  unsigned __int8 v8; // r11
  ULONGLONG v9; // r10
  char *v10; // rax
  char v11; // cl
  __int64 v12; // rcx
  char v13; // dl
  int v15; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  *(_QWORD *)UserData = off_140046058;
  *((_DWORD *)UserData + 2) = (unsigned __int16)*off_140046058;
  *((_DWORD *)UserData + 3) = 2;
  *((_QWORD *)UserData + 2) = v6;
  *((_DWORD *)UserData + 6) = *v6;
  *((_DWORD *)UserData + 7) = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_140046078 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  v7 = *((_QWORD *)UserData + 2);
  v8 = 0;
  v9 = v7 + *((unsigned int *)UserData + 6);
  v10 = (char *)(v7 + 2);
  do
    v11 = *v10++;
  while ( v11 < 0 );
  do
    v12 = (unsigned __int8)*v10++;
  while ( (_BYTE)v12 );
  while ( (unsigned __int64)v10 < v9 )
  {
    do
      v12 = (unsigned __int8)*v10++;
    while ( (_BYTE)v12 );
    if ( *v10 >= 0 )
      break;
    v12 = (__int64)(v10 + 1);
    v13 = *v10 & 0x7F;
    v10 += 2;
    if ( *(char *)v12 >= 0 )
      break;
    while ( 1 )
    {
      v15 = (unsigned __int8)*v10;
      if ( (v15 & 0x80u) == 0 )
        break;
      if ( (_BYTE)v15 != 0x80 )
        goto LABEL_9;
      ++v10;
    }
    if ( v13 != 9 )
      break;
    v12 = (unsigned int)(v15 - 113);
    if ( (unsigned __int8)(v15 - 113) > 2u )
      break;
    v12 = 2LL * v8++;
    UserData[8 * v12 + 45] = v15;
  }
LABEL_9:
  if ( v8 )
    return InsertEventEntryInLookUpTable(v12, (__int128 *)&EventDescriptor, a4, UserData, v8);
  else
    return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, a4, (PEVENT_DATA_DESCRIPTOR)UserData);
}

```

## disassembly

```asm
0x14001b4c0  mov     [rsp+arg_10], r8
0x14001b4c5  push    rbx
0x14001b4c6  sub     rsp, 40h
0x14001b4ca  movzx   eax, byte ptr [rdx]
0x14001b4cd  mov     ebx, r9d
0x14001b4d0  mov     r9, [rsp+48h+arg_20]
0x14001b4d5  shl     eax, 18h
0x14001b4d8  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14001b4dc  movzx   eax, word ptr [rdx+1]
0x14001b4e0  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14001b4e4  mov     rax, [rdx+3]
0x14001b4e8  add     rdx, 0Bh
0x14001b4ec  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14001b4f1  mov     rax, cs:off_140046058
0x14001b4f8  mov     [r9], rax
0x14001b4fb  mov     rax, cs:off_140046058
0x14001b502  movzx   ecx, word ptr [rax]
0x14001b505  mov     [r9+8], ecx
0x14001b509  lea     rcx, _TraceLoggingMetadata
0x14001b510  mov     dword ptr [r9+0Ch], 2
0x14001b518  mov     [r9+10h], rdx
0x14001b51c  movzx   eax, word ptr [rdx]
0x14001b51f  mov     [r9+18h], eax
0x14001b523  lea     rax, _TraceLoggingMetadataEnd
0x14001b52a  sub     eax, ecx
0x14001b52c  mov     dword ptr [r9+1Ch], 1
0x14001b534  mov     dword ptr [rsp+48h+arg_10], eax
0x14001b538  mov     eax, dword ptr [rsp+48h+arg_10]
0x14001b53c  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14001b543  cmp     cs:qword_140046078, rax
0x14001b54a  jnz     loc_14001B61F
0x14001b550  mov     rax, [r9+10h]
0x14001b554  xor     r11b, r11b
0x14001b557  mov     r10d, [r9+18h]
0x14001b55b  add     r10, rax
0x14001b55e  add     rax, 2
0x14001b562  movzx   ecx, byte ptr [rax]
0x14001b565  inc     rax
0x14001b568  test    cl, cl
0x14001b56a  js      short loc_14001B562
0x14001b56c  nop     dword ptr [rax+00h]
0x14001b570  movzx   ecx, byte ptr [rax]
0x14001b573  inc     rax
0x14001b576  test    cl, cl
0x14001b578  jnz     short loc_14001B570
0x14001b57a  cmp     rax, r10
0x14001b57d  jnb     short loc_14001B5A1
0x14001b57f  nop
0x14001b580  movzx   ecx, byte ptr [rax]
0x14001b583  inc     rax
0x14001b586  test    cl, cl
0x14001b588  jnz     short loc_14001B580
0x14001b58a  movzx   edx, byte ptr [rax]
0x14001b58d  test    dl, dl
0x14001b58f  jns     short loc_14001B5A1
0x14001b591  lea     rcx, [rax+1]
0x14001b595  and     dl, 7Fh
0x14001b598  add     rax, 2
0x14001b59c  cmp     byte ptr [rcx], 0
0x14001b59f  jl      short loc_14001B5C0
0x14001b5a1  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14001b5a6  test    r11b, r11b
0x14001b5a9  jz      short loc_14001B5F3
0x14001b5ab  movzx   r8d, bl
0x14001b5af  mov     byte ptr [rsp+48h+UserDataCount], r11b
0x14001b5b4  call    InsertEventEntryInLookUpTable
0x14001b5b9  add     rsp, 40h
0x14001b5bd  pop     rbx
0x14001b5be  retn
0x14001b5c0  movzx   r8d, byte ptr [rax]
0x14001b5c4  test    r8b, r8b
0x14001b5c7  jns     short loc_14001B5D4
0x14001b5c9  cmp     r8b, 80h
0x14001b5cd  jnz     short loc_14001B5A1
0x14001b5cf  inc     rax
0x14001b5d2  jmp     short loc_14001B5C0
0x14001b5d4  cmp     dl, 9
0x14001b5d7  jnz     short loc_14001B5A1
0x14001b5d9  lea     ecx, [r8-71h]
0x14001b5dd  cmp     cl, 2
0x14001b5e0  ja      short loc_14001B5A1
0x14001b5e2  movzx   ecx, r11b
0x14001b5e6  add     rcx, rcx
0x14001b5e9  inc     r11b
0x14001b5ec  mov     [r9+rcx*8+2Dh], r8b
0x14001b5f1  jmp     short loc_14001B57A
0x14001b5f3  mov     rcx, cs:RegHandle; RegHandle
0x14001b5fa  xor     r8d, r8d; ActivityId
0x14001b5fd  mov     [rsp+48h+UserData], r9; UserData
0x14001b602  xor     r9d, r9d; RelatedActivityId
0x14001b605  movzx   eax, bl
0x14001b608  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14001b60c  call    cs:__imp_EtwWriteTransfer
0x14001b613  nop     dword ptr [rax+rax+00h]
0x14001b618  add     rsp, 40h
0x14001b61c  pop     rbx
0x14001b61d  retn
0x14001b61f  mov     eax, 0C000000Dh
0x14001b624  jmp     short loc_14001B5B9
```
