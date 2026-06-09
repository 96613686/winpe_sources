# TlgAggregateAbsorbEvent

- ea: `0x180069efc`
- end: `0x180069fef`
- name: `TlgAggregateAbsorbEvent`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006a044`

## callees

- `0x180069ac4`
- `0x180069efc`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x180069fd2`
- `ntoskrnl!EtwWriteTransfer` at `0x180069fd2`

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
0x180069efc  mov     [rsp+arg_0], rbx
0x180069f01  mov     [rsp+arg_8], rsi
0x180069f06  push    rdi
0x180069f07  sub     rsp, 30h
0x180069f0b  mov     r11, rcx
0x180069f0e  movzx   edi, r8b
0x180069f12  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180069f19  mov     rsi, rdx
0x180069f1c  mov     eax, 0C000000Dh
0x180069f21  cmp     [r11+28h], rcx
0x180069f25  jnz     loc_180069FDE
0x180069f2b  mov     rax, [r9+10h]
0x180069f2f  xor     r10b, r10b
0x180069f32  mov     ebx, [r9+18h]
0x180069f36  add     rbx, rax
0x180069f39  lea     rcx, [rax+2]
0x180069f3d  movzx   eax, byte ptr [rcx]
0x180069f40  inc     rcx
0x180069f43  test    al, al
0x180069f45  js      short loc_180069F3D
0x180069f47  mov     al, [rcx]
0x180069f49  inc     rcx
0x180069f4c  test    al, al
0x180069f4e  jnz     short loc_180069F47
0x180069f50  cmp     rcx, rbx
0x180069f53  jnb     short loc_180069FA5
0x180069f55  mov     al, [rcx]
0x180069f57  inc     rcx
0x180069f5a  test    al, al
0x180069f5c  jnz     short loc_180069F55
0x180069f5e  mov     r8b, [rcx]
0x180069f61  test    r8b, r8b
0x180069f64  jns     short loc_180069FA5
0x180069f66  and     r8b, 7Fh
0x180069f6a  lea     rax, [rcx+1]
0x180069f6e  add     rcx, 2
0x180069f72  cmp     byte ptr [rax], 0
0x180069f75  jge     short loc_180069FA5
0x180069f77  mov     dl, [rcx]
0x180069f79  test    dl, dl
0x180069f7b  jns     short loc_180069F87
0x180069f7d  cmp     dl, 80h
0x180069f80  jnz     short loc_180069FA5
0x180069f82  inc     rcx
0x180069f85  jmp     short loc_180069F77
0x180069f87  cmp     r8b, 9
0x180069f8b  jnz     short loc_180069FA5
0x180069f8d  lea     eax, [rdx-71h]
0x180069f90  cmp     al, 2
0x180069f92  ja      short loc_180069FA5
0x180069f94  movzx   eax, r10b
0x180069f98  add     rax, rax
0x180069f9b  inc     r10b
0x180069f9e  mov     [r9+rax*8+2Dh], dl
0x180069fa3  jmp     short loc_180069F50
0x180069fa5  mov     rdx, rsi; EventDescriptor
0x180069fa8  test    r10b, r10b
0x180069fab  jz      short loc_180069FBF
0x180069fad  mov     r8b, dil
0x180069fb0  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x180069fb5  mov     rcx, r11
0x180069fb8  call    InsertEventEntryInLookUpTable
0x180069fbd  jmp     short loc_180069FDE
0x180069fbf  mov     rcx, [r11+20h]; RegHandle
0x180069fc3  xor     r8d, r8d; ActivityId
0x180069fc6  mov     [rsp+38h+UserData], r9; UserData
0x180069fcb  xor     r9d, r9d; RelatedActivityId
0x180069fce  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x180069fd2  call    cs:__imp_EtwWriteTransfer
0x180069fd9  nop     dword ptr [rax+rax+00h]
0x180069fde  mov     rbx, [rsp+38h+arg_0]
0x180069fe3  mov     rsi, [rsp+38h+arg_8]
0x180069fe8  add     rsp, 30h
0x180069fec  pop     rdi
0x180069fed  retn
```
