# FlushEventEntryList

- ea: `0x14001d720`
- end: `0x14001d7af`
- name: `FlushEventEntryList`
- size: `143`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001d7b8`

## callees

- `0x140010c98`
- `0x14001d698`
- `0x14001d720`

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
      EventWriteTransfer_0(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
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
0x14001d720  test    rdx, rdx
0x14001d723  jz      locret_14001D7AE
0x14001d729  mov     [rsp+arg_0], rbx
0x14001d72e  mov     [rsp+arg_8], rsi
0x14001d733  push    rdi
0x14001d734  sub     rsp, 30h
0x14001d738  mov     rdi, rdx
0x14001d73b  mov     rsi, rcx
0x14001d73e  movzx   eax, byte ptr [rdi+2Dh]
0x14001d742  mov     edx, 2
0x14001d747  add     eax, edx
0x14001d749  cmp     eax, edx
0x14001d74b  jbe     short loc_14001D769
0x14001d74d  mov     rax, [rdi+10h]
0x14001d751  movsxd  rcx, edx
0x14001d754  inc     edx
0x14001d756  add     rcx, rcx
0x14001d759  mov     byte ptr [rax+rcx*8+0Dh], 0
0x14001d75e  movzx   eax, byte ptr [rdi+2Dh]
0x14001d762  add     eax, 2
0x14001d765  cmp     edx, eax
0x14001d767  jl      short loc_14001D74D
0x14001d769  movzx   edx, byte ptr [rdi+2Ch]
0x14001d76d  xor     r9d, r9d; RelatedActivityId
0x14001d770  mov     rax, [rdi+10h]
0x14001d774  xor     r8d, r8d; ActivityId
0x14001d777  mov     [rsp+38h+UserData], rax; UserData
0x14001d77c  mov     rcx, rsi; RegHandle
0x14001d77f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x14001d783  mov     rdx, rdi; EventDescriptor
0x14001d786  call    EventWriteTransfer_0
0x14001d78b  mov     rbx, [rdi+18h]
0x14001d78f  mov     rcx, rdi
0x14001d792  call    DestroyEventEntry
0x14001d797  mov     rdi, rbx
0x14001d79a  test    rbx, rbx
0x14001d79d  jnz     short loc_14001D73E
0x14001d79f  mov     rbx, [rsp+38h+arg_0]
0x14001d7a4  mov     rsi, [rsp+38h+arg_8]
0x14001d7a9  add     rsp, 30h
0x14001d7ad  pop     rdi
0x14001d7ae  retn
```
