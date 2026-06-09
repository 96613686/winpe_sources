# FlushEventEntryList

- ea: `0x18003c0a4`
- end: `0x18003c13b`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c40c`

## callees

- `0x18003c014`
- `0x18003c0a4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003c10a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003c10a`

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
0x18003c0a4  test    rdx, rdx
0x18003c0a7  jz      locret_18003C139
0x18003c0ad  mov     [rsp+arg_0], rbx
0x18003c0b2  mov     [rsp+arg_8], rsi
0x18003c0b7  push    rdi
0x18003c0b8  sub     rsp, 30h
0x18003c0bc  mov     rdi, rdx
0x18003c0bf  mov     rsi, rcx
0x18003c0c2  movzx   eax, byte ptr [rdi+2Dh]
0x18003c0c6  mov     edx, 2
0x18003c0cb  add     eax, edx
0x18003c0cd  cmp     eax, edx
0x18003c0cf  jbe     short loc_18003C0ED
0x18003c0d1  mov     rax, [rdi+10h]
0x18003c0d5  movsxd  rcx, edx
0x18003c0d8  inc     edx
0x18003c0da  add     rcx, rcx
0x18003c0dd  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18003c0e2  movzx   eax, byte ptr [rdi+2Dh]
0x18003c0e6  add     eax, 2
0x18003c0e9  cmp     edx, eax
0x18003c0eb  jl      short loc_18003C0D1
0x18003c0ed  movzx   edx, byte ptr [rdi+2Ch]
0x18003c0f1  xor     r9d, r9d; RelatedActivityId
0x18003c0f4  mov     rax, [rdi+10h]
0x18003c0f8  xor     r8d, r8d; ActivityId
0x18003c0fb  mov     [rsp+38h+UserData], rax; UserData
0x18003c100  mov     rcx, rsi; RegHandle
0x18003c103  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18003c107  mov     rdx, rdi; EventDescriptor
0x18003c10a  call    cs:__imp_EventWriteTransfer
0x18003c111  nop     dword ptr [rax+rax+00h]
0x18003c116  mov     rbx, [rdi+18h]
0x18003c11a  mov     rcx, rdi
0x18003c11d  call    DestroyEventEntry
0x18003c122  mov     rdi, rbx
0x18003c125  test    rbx, rbx
0x18003c128  jnz     short loc_18003C0C2
0x18003c12a  mov     rbx, [rsp+38h+arg_0]
0x18003c12f  mov     rsi, [rsp+38h+arg_8]
0x18003c134  add     rsp, 30h
0x18003c138  pop     rdi
0x18003c139  retn
```
