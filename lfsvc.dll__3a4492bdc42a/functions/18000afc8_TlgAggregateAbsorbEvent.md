# TlgAggregateAbsorbEvent

- ea: `0x18000afc8`
- end: `0x18000b0b4`
- name: `TlgAggregateAbsorbEvent`
- size: `236`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, unsigned __int8, struct _EVENT_DATA_DESCRIPTOR *UserData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b1c4`

## callees

- `0x18000acc0`
- `0x18000afc8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b09e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b09e`

## pseudocode

```c
ULONG __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // edi
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v9; // r10
  unsigned __int64 v10; // rbx
  char *v11; // rcx
  char v12; // al
  char v15; // r8
  char *v16; // rax
  char v17; // dl
  __int64 v18; // rax

  UserDataCount = a3;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, __int64, unsigned __int8, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
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
    while ( (unsigned __int64)v11 < v10 )
    {
      while ( *v11++ )
        ;
      if ( *v11 >= 0 )
        break;
      v15 = *v11 & 0x7F;
      v16 = v11 + 1;
      v11 += 2;
      if ( *v16 >= 0 )
        break;
      while ( 1 )
      {
        v17 = *v11;
        if ( *v11 >= 0 )
          break;
        if ( v17 != (char)0x80 )
          goto LABEL_15;
        ++v11;
      }
      if ( v15 != 9 || (unsigned __int8)(v17 - 113) > 2u )
        break;
      v18 = v9++;
      UserData[v18 + 2].Reserved1 = v17;
    }
LABEL_15:
    if ( v9 )
      return InsertEventEntryInLookUpTable(a1, (_DWORD)a2, (_BYTE)UserDataCount, (_DWORD)UserData, v9);
    else
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18000afc8  mov     [rsp+arg_0], rbx
0x18000afcd  mov     [rsp+arg_8], rsi
0x18000afd2  push    rdi
0x18000afd3  sub     rsp, 30h
0x18000afd7  mov     r11, rcx
0x18000afda  movzx   edi, r8b
0x18000afde  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000afe5  mov     rsi, rdx
0x18000afe8  mov     eax, 0C000000Dh
0x18000afed  cmp     [r11+28h], rcx
0x18000aff1  jnz     loc_18000B0A4
0x18000aff7  mov     rax, [r9+10h]
0x18000affb  xor     r10b, r10b
0x18000affe  mov     ebx, [r9+18h]
0x18000b002  add     rbx, rax
0x18000b005  lea     rcx, [rax+2]
0x18000b009  movzx   eax, byte ptr [rcx]
0x18000b00c  inc     rcx
0x18000b00f  test    al, al
0x18000b011  js      short loc_18000B009
0x18000b013  mov     al, [rcx]
0x18000b015  inc     rcx
0x18000b018  test    al, al
0x18000b01a  jnz     short loc_18000B013
0x18000b01c  cmp     rcx, rbx
0x18000b01f  jnb     short loc_18000B071
0x18000b021  mov     al, [rcx]
0x18000b023  inc     rcx
0x18000b026  test    al, al
0x18000b028  jnz     short loc_18000B021
0x18000b02a  mov     r8b, [rcx]
0x18000b02d  test    r8b, r8b
0x18000b030  jns     short loc_18000B071
0x18000b032  and     r8b, 7Fh
0x18000b036  lea     rax, [rcx+1]
0x18000b03a  add     rcx, 2
0x18000b03e  cmp     byte ptr [rax], 0
0x18000b041  jge     short loc_18000B071
0x18000b043  mov     dl, [rcx]
0x18000b045  test    dl, dl
0x18000b047  jns     short loc_18000B053
0x18000b049  cmp     dl, 80h
0x18000b04c  jnz     short loc_18000B071
0x18000b04e  inc     rcx
0x18000b051  jmp     short loc_18000B043
0x18000b053  cmp     r8b, 9
0x18000b057  jnz     short loc_18000B071
0x18000b059  lea     eax, [rdx-71h]
0x18000b05c  cmp     al, 2
0x18000b05e  ja      short loc_18000B071
0x18000b060  movzx   eax, r10b
0x18000b064  add     rax, rax
0x18000b067  inc     r10b
0x18000b06a  mov     [r9+rax*8+2Dh], dl
0x18000b06f  jmp     short loc_18000B01C
0x18000b071  mov     rdx, rsi; EventDescriptor
0x18000b074  test    r10b, r10b
0x18000b077  jz      short loc_18000B08B
0x18000b079  mov     r8b, dil
0x18000b07c  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x18000b081  mov     rcx, r11
0x18000b084  call    InsertEventEntryInLookUpTable
0x18000b089  jmp     short loc_18000B0A4
0x18000b08b  mov     rcx, [r11+20h]; RegHandle
0x18000b08f  xor     r8d, r8d; ActivityId
0x18000b092  mov     [rsp+38h+UserData], r9; UserData
0x18000b097  xor     r9d, r9d; RelatedActivityId
0x18000b09a  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x18000b09e  call    cs:__imp_EventWriteTransfer
0x18000b0a4  mov     rbx, [rsp+38h+arg_0]
0x18000b0a9  mov     rsi, [rsp+38h+arg_8]
0x18000b0ae  add     rsp, 30h
0x18000b0b2  pop     rdi
0x18000b0b3  retn
```
