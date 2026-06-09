# TlgAggregateAbsorbEvent

- ea: `0x1800183e0`
- end: `0x1800184c2`
- name: `TlgAggregateAbsorbEvent`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018350`

## callees

- `0x1800183e0`
- `0x1800184c8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800184b1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800184b1`

## pseudocode

```c
ULONG __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // ebx
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v8; // r10
  unsigned __int64 v9; // r11
  char *v10; // rcx
  char v11; // al
  char v14; // r8
  char *v15; // rax
  char v16; // dl
  __int64 v17; // rax

  UserDataCount = a3;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_18002A0A0 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v8 = 0;
    v9 = Ptr + UserData[1].Size;
    v10 = (char *)(Ptr + 2);
    do
      v11 = *v10++;
    while ( v11 < 0 );
    while ( *v10++ )
      ;
    while ( (unsigned __int64)v10 < v9 )
    {
      while ( *v10++ )
        ;
      if ( *v10 >= 0 )
        break;
      v14 = *v10 & 0x7F;
      v15 = v10 + 1;
      v10 += 2;
      if ( *v15 >= 0 )
        break;
      while ( 1 )
      {
        v16 = *v10;
        if ( *v10 >= 0 )
          break;
        if ( v16 != (char)0x80 )
          goto LABEL_15;
        ++v10;
      }
      if ( v14 != 9 || (unsigned __int8)(v16 - 113) > 2u )
        break;
      v17 = v8++;
      UserData[v17 + 2].Reserved1 = v16;
    }
LABEL_15:
    if ( v8 )
      return InsertEventEntryInLookUpTable((_DWORD)v10, (_DWORD)a2, (_BYTE)UserDataCount, (_DWORD)UserData, v8);
    else
      return EventWriteTransfer(RegHandle, a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x1800183e0  mov     [rsp+arg_0], rbx
0x1800183e5  push    rdi
0x1800183e6  sub     rsp, 30h
0x1800183ea  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x1800183f1  movzx   ebx, r8b
0x1800183f5  cmp     cs:qword_18002A0A0, rcx
0x1800183fc  mov     rdi, rdx
0x1800183ff  mov     eax, 0C000000Dh
0x180018404  jnz     loc_1800184B7
0x18001840a  mov     rax, [r9+10h]
0x18001840e  xor     r10b, r10b
0x180018411  mov     r11d, [r9+18h]
0x180018415  add     r11, rax
0x180018418  lea     rcx, [rax+2]
0x18001841c  movzx   eax, byte ptr [rcx]
0x18001841f  inc     rcx
0x180018422  test    al, al
0x180018424  js      short loc_18001841C
0x180018426  mov     al, [rcx]
0x180018428  inc     rcx
0x18001842b  test    al, al
0x18001842d  jnz     short loc_180018426
0x18001842f  cmp     rcx, r11
0x180018432  jnb     short loc_180018484
0x180018434  mov     al, [rcx]
0x180018436  inc     rcx
0x180018439  test    al, al
0x18001843b  jnz     short loc_180018434
0x18001843d  mov     r8b, [rcx]
0x180018440  test    r8b, r8b
0x180018443  jns     short loc_180018484
0x180018445  and     r8b, 7Fh
0x180018449  lea     rax, [rcx+1]
0x18001844d  add     rcx, 2
0x180018451  cmp     byte ptr [rax], 0
0x180018454  jge     short loc_180018484
0x180018456  mov     dl, [rcx]
0x180018458  test    dl, dl
0x18001845a  jns     short loc_180018466
0x18001845c  cmp     dl, 80h
0x18001845f  jnz     short loc_180018484
0x180018461  inc     rcx
0x180018464  jmp     short loc_180018456
0x180018466  cmp     r8b, 9
0x18001846a  jnz     short loc_180018484
0x18001846c  lea     eax, [rdx-71h]
0x18001846f  cmp     al, 2
0x180018471  ja      short loc_180018484
0x180018473  movzx   eax, r10b
0x180018477  add     rax, rax
0x18001847a  inc     r10b
0x18001847d  mov     [r9+rax*8+2Dh], dl
0x180018482  jmp     short loc_18001842F
0x180018484  mov     rdx, rdi; EventDescriptor
0x180018487  test    r10b, r10b
0x18001848a  jz      short loc_18001849B
0x18001848c  mov     r8b, bl
0x18001848f  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x180018494  call    InsertEventEntryInLookUpTable
0x180018499  jmp     short loc_1800184B7
0x18001849b  mov     rcx, cs:RegHandle; RegHandle
0x1800184a2  xor     r8d, r8d; ActivityId
0x1800184a5  mov     [rsp+38h+UserData], r9; UserData
0x1800184aa  xor     r9d, r9d; RelatedActivityId
0x1800184ad  mov     [rsp+38h+UserDataCount], ebx; UserDataCount
0x1800184b1  call    cs:__imp_EventWriteTransfer
0x1800184b7  mov     rbx, [rsp+38h+arg_0]
0x1800184bc  add     rsp, 30h
0x1800184c0  pop     rdi
0x1800184c1  retn
```
