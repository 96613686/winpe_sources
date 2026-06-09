# FlushEventEntryList

- ea: `0x18000ab18`
- end: `0x18000aba8`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000abb0`

## callees

- `0x18000aa90`
- `0x18000ab18`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ab7e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ab7e`

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
0x18000ab18  test    rdx, rdx
0x18000ab1b  jz      locret_18000ABA7
0x18000ab21  mov     [rsp+arg_0], rbx
0x18000ab26  mov     [rsp+arg_8], rsi
0x18000ab2b  push    rdi
0x18000ab2c  sub     rsp, 30h
0x18000ab30  mov     rdi, rdx
0x18000ab33  mov     rsi, rcx
0x18000ab36  movzx   eax, byte ptr [rdi+2Dh]
0x18000ab3a  mov     edx, 2
0x18000ab3f  add     eax, edx
0x18000ab41  cmp     eax, edx
0x18000ab43  jbe     short loc_18000AB61
0x18000ab45  mov     rax, [rdi+10h]
0x18000ab49  movsxd  rcx, edx
0x18000ab4c  inc     edx
0x18000ab4e  add     rcx, rcx
0x18000ab51  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18000ab56  movzx   eax, byte ptr [rdi+2Dh]
0x18000ab5a  add     eax, 2
0x18000ab5d  cmp     edx, eax
0x18000ab5f  jl      short loc_18000AB45
0x18000ab61  movzx   edx, byte ptr [rdi+2Ch]
0x18000ab65  xor     r9d, r9d; RelatedActivityId
0x18000ab68  mov     rax, [rdi+10h]
0x18000ab6c  xor     r8d, r8d; ActivityId
0x18000ab6f  mov     [rsp+38h+UserData], rax; UserData
0x18000ab74  mov     rcx, rsi; RegHandle
0x18000ab77  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18000ab7b  mov     rdx, rdi; EventDescriptor
0x18000ab7e  call    cs:__imp_EventWriteTransfer
0x18000ab84  mov     rbx, [rdi+18h]
0x18000ab88  mov     rcx, rdi
0x18000ab8b  call    DestroyEventEntry
0x18000ab90  mov     rdi, rbx
0x18000ab93  test    rbx, rbx
0x18000ab96  jnz     short loc_18000AB36
0x18000ab98  mov     rbx, [rsp+38h+arg_0]
0x18000ab9d  mov     rsi, [rsp+38h+arg_8]
0x18000aba2  add     rsp, 30h
0x18000aba6  pop     rdi
0x18000aba7  retn
```
