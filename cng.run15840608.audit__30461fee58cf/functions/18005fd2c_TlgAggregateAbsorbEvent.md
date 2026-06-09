# TlgAggregateAbsorbEvent

- ea: `0x18005fd2c`
- end: `0x18005fe1f`
- name: `TlgAggregateAbsorbEvent`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005fe74`

## callees

- `0x18005f8f4`
- `0x18005fd2c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18005fe02`
- `ntoskrnl!EtwWriteTransfer` at `0x18005fe02`

## pseudocode

```c
NTSTATUS __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // edi
  NTSTATUS result; // eax
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
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
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
      return EtwWriteTransfer(*(_QWORD *)(a1 + 32), a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18005fd2c  mov     [rsp+arg_0], rbx
0x18005fd31  mov     [rsp+arg_8], rsi
0x18005fd36  push    rdi
0x18005fd37  sub     rsp, 30h
0x18005fd3b  mov     r11, rcx
0x18005fd3e  movzx   edi, r8b
0x18005fd42  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18005fd49  mov     rsi, rdx
0x18005fd4c  mov     eax, 0C000000Dh
0x18005fd51  cmp     [r11+28h], rcx
0x18005fd55  jnz     loc_18005FE0E
0x18005fd5b  mov     rax, [r9+10h]
0x18005fd5f  xor     r10b, r10b
0x18005fd62  mov     ebx, [r9+18h]
0x18005fd66  add     rbx, rax
0x18005fd69  lea     rcx, [rax+2]
0x18005fd6d  movzx   eax, byte ptr [rcx]
0x18005fd70  inc     rcx
0x18005fd73  test    al, al
0x18005fd75  js      short loc_18005FD6D
0x18005fd77  mov     al, [rcx]
0x18005fd79  inc     rcx
0x18005fd7c  test    al, al
0x18005fd7e  jnz     short loc_18005FD77
0x18005fd80  cmp     rcx, rbx
0x18005fd83  jnb     short loc_18005FDD5
0x18005fd85  mov     al, [rcx]
0x18005fd87  inc     rcx
0x18005fd8a  test    al, al
0x18005fd8c  jnz     short loc_18005FD85
0x18005fd8e  mov     r8b, [rcx]
0x18005fd91  test    r8b, r8b
0x18005fd94  jns     short loc_18005FDD5
0x18005fd96  and     r8b, 7Fh
0x18005fd9a  lea     rax, [rcx+1]
0x18005fd9e  add     rcx, 2
0x18005fda2  cmp     byte ptr [rax], 0
0x18005fda5  jge     short loc_18005FDD5
0x18005fda7  mov     dl, [rcx]
0x18005fda9  test    dl, dl
0x18005fdab  jns     short loc_18005FDB7
0x18005fdad  cmp     dl, 80h
0x18005fdb0  jnz     short loc_18005FDD5
0x18005fdb2  inc     rcx
0x18005fdb5  jmp     short loc_18005FDA7
0x18005fdb7  cmp     r8b, 9
0x18005fdbb  jnz     short loc_18005FDD5
0x18005fdbd  lea     eax, [rdx-71h]
0x18005fdc0  cmp     al, 2
0x18005fdc2  ja      short loc_18005FDD5
0x18005fdc4  movzx   eax, r10b
0x18005fdc8  add     rax, rax
0x18005fdcb  inc     r10b
0x18005fdce  mov     [r9+rax*8+2Dh], dl
0x18005fdd3  jmp     short loc_18005FD80
0x18005fdd5  mov     rdx, rsi; EventDescriptor
0x18005fdd8  test    r10b, r10b
0x18005fddb  jz      short loc_18005FDEF
0x18005fddd  mov     r8b, dil
0x18005fde0  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x18005fde5  mov     rcx, r11
0x18005fde8  call    InsertEventEntryInLookUpTable
0x18005fded  jmp     short loc_18005FE0E
0x18005fdef  mov     rcx, [r11+20h]; RegHandle
0x18005fdf3  xor     r8d, r8d; ActivityId
0x18005fdf6  mov     [rsp+38h+UserData], r9; UserData
0x18005fdfb  xor     r9d, r9d; RelatedActivityId
0x18005fdfe  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x18005fe02  call    cs:__imp_EtwWriteTransfer
0x18005fe09  nop     dword ptr [rax+rax+00h]
0x18005fe0e  mov     rbx, [rsp+38h+arg_0]
0x18005fe13  mov     rsi, [rsp+38h+arg_8]
0x18005fe18  add     rsp, 30h
0x18005fe1c  pop     rdi
0x18005fe1d  retn
```
