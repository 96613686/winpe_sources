# FlushEventEntryList

- ea: `0x18001f700`
- end: `0x18001f790`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800215f4`

## callees

- `0x18001f700`
- `0x18001f798`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f766`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f766`

## pseudocode

```c
__int64 __fastcall FlushEventEntryList(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)
{
  PCEVENT_DESCRIPTOR v2; // rdi
  int v4; // edx
  __int64 v5; // rcx
  const EVENT_DESCRIPTOR *Keyword; // rbx
  __int64 result; // rax

  if ( EventDescriptor )
  {
    v2 = EventDescriptor;
    do
    {
      v4 = 2;
      if ( (unsigned int)BYTE5(v2[2].Keyword) + 2 > 2 )
      {
        do
        {
          v5 = v4++;
          *(_BYTE *)(*(_QWORD *)&v2[1].Id + 16 * v5 + 13) = 0;
        }
        while ( v4 < BYTE5(v2[2].Keyword) + 2 );
      }
      EventWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
      Keyword = (const EVENT_DESCRIPTOR *)v2[1].Keyword;
      result = DestroyEventEntry(v2);
      v2 = Keyword;
    }
    while ( Keyword );
  }
  return result;
}

```

## disassembly

```asm
0x18001f700  test    rdx, rdx
0x18001f703  jz      locret_18001F78F
0x18001f709  mov     [rsp+arg_0], rbx
0x18001f70e  mov     [rsp+arg_8], rsi
0x18001f713  push    rdi
0x18001f714  sub     rsp, 30h
0x18001f718  mov     rdi, rdx
0x18001f71b  mov     rsi, rcx
0x18001f71e  movzx   eax, byte ptr [rdi+2Dh]
0x18001f722  mov     edx, 2
0x18001f727  add     eax, edx
0x18001f729  cmp     eax, edx
0x18001f72b  jbe     short loc_18001F749
0x18001f72d  mov     rax, [rdi+10h]
0x18001f731  movsxd  rcx, edx
0x18001f734  inc     edx
0x18001f736  add     rcx, rcx
0x18001f739  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18001f73e  movzx   eax, byte ptr [rdi+2Dh]
0x18001f742  add     eax, 2
0x18001f745  cmp     edx, eax
0x18001f747  jl      short loc_18001F72D
0x18001f749  movzx   edx, byte ptr [rdi+2Ch]
0x18001f74d  xor     r9d, r9d; RelatedActivityId
0x18001f750  mov     rax, [rdi+10h]
0x18001f754  xor     r8d, r8d; ActivityId
0x18001f757  mov     [rsp+38h+UserData], rax; UserData
0x18001f75c  mov     rcx, rsi; RegHandle
0x18001f75f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18001f763  mov     rdx, rdi; EventDescriptor
0x18001f766  call    cs:__imp_EventWriteTransfer
0x18001f76c  mov     rbx, [rdi+18h]
0x18001f770  mov     rcx, rdi
0x18001f773  call    DestroyEventEntry
0x18001f778  mov     rdi, rbx
0x18001f77b  test    rbx, rbx
0x18001f77e  jnz     short loc_18001F71E
0x18001f780  mov     rbx, [rsp+38h+arg_0]
0x18001f785  mov     rsi, [rsp+38h+arg_8]
0x18001f78a  add     rsp, 30h
0x18001f78e  pop     rdi
0x18001f78f  retn
```
