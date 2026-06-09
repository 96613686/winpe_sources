# TlgAggregateAbsorbEvent

- ea: `0x18006061c`
- end: `0x18006070f`
- name: `TlgAggregateAbsorbEvent`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180060764`

## callees

- `0x1800601e4`
- `0x18006061c`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800606f2`
- `ntoskrnl!EtwWriteTransfer` at `0x1800606f2`

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
0x18006061c  mov     [rsp+arg_0], rbx
0x180060621  mov     [rsp+arg_8], rsi
0x180060626  push    rdi
0x180060627  sub     rsp, 30h
0x18006062b  mov     r11, rcx
0x18006062e  movzx   edi, r8b
0x180060632  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180060639  mov     rsi, rdx
0x18006063c  mov     eax, 0C000000Dh
0x180060641  cmp     [r11+28h], rcx
0x180060645  jnz     loc_1800606FE
0x18006064b  mov     rax, [r9+10h]
0x18006064f  xor     r10b, r10b
0x180060652  mov     ebx, [r9+18h]
0x180060656  add     rbx, rax
0x180060659  lea     rcx, [rax+2]
0x18006065d  movzx   eax, byte ptr [rcx]
0x180060660  inc     rcx
0x180060663  test    al, al
0x180060665  js      short loc_18006065D
0x180060667  mov     al, [rcx]
0x180060669  inc     rcx
0x18006066c  test    al, al
0x18006066e  jnz     short loc_180060667
0x180060670  cmp     rcx, rbx
0x180060673  jnb     short loc_1800606C5
0x180060675  mov     al, [rcx]
0x180060677  inc     rcx
0x18006067a  test    al, al
0x18006067c  jnz     short loc_180060675
0x18006067e  mov     r8b, [rcx]
0x180060681  test    r8b, r8b
0x180060684  jns     short loc_1800606C5
0x180060686  and     r8b, 7Fh
0x18006068a  lea     rax, [rcx+1]
0x18006068e  add     rcx, 2
0x180060692  cmp     byte ptr [rax], 0
0x180060695  jge     short loc_1800606C5
0x180060697  mov     dl, [rcx]
0x180060699  test    dl, dl
0x18006069b  jns     short loc_1800606A7
0x18006069d  cmp     dl, 80h
0x1800606a0  jnz     short loc_1800606C5
0x1800606a2  inc     rcx
0x1800606a5  jmp     short loc_180060697
0x1800606a7  cmp     r8b, 9
0x1800606ab  jnz     short loc_1800606C5
0x1800606ad  lea     eax, [rdx-71h]
0x1800606b0  cmp     al, 2
0x1800606b2  ja      short loc_1800606C5
0x1800606b4  movzx   eax, r10b
0x1800606b8  add     rax, rax
0x1800606bb  inc     r10b
0x1800606be  mov     [r9+rax*8+2Dh], dl
0x1800606c3  jmp     short loc_180060670
0x1800606c5  mov     rdx, rsi; EventDescriptor
0x1800606c8  test    r10b, r10b
0x1800606cb  jz      short loc_1800606DF
0x1800606cd  mov     r8b, dil
0x1800606d0  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x1800606d5  mov     rcx, r11
0x1800606d8  call    InsertEventEntryInLookUpTable
0x1800606dd  jmp     short loc_1800606FE
0x1800606df  mov     rcx, [r11+20h]; RegHandle
0x1800606e3  xor     r8d, r8d; ActivityId
0x1800606e6  mov     [rsp+38h+UserData], r9; UserData
0x1800606eb  xor     r9d, r9d; RelatedActivityId
0x1800606ee  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x1800606f2  call    cs:__imp_EtwWriteTransfer
0x1800606f9  nop     dword ptr [rax+rax+00h]
0x1800606fe  mov     rbx, [rsp+38h+arg_0]
0x180060703  mov     rsi, [rsp+38h+arg_8]
0x180060708  add     rsp, 30h
0x18006070c  pop     rdi
0x18006070d  retn
```
