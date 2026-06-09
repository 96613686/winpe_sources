# FlushEventEntryList

- ea: `0x180017b44`
- end: `0x180017bd4`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017bdc`

## callees

- `0x1800179e8`
- `0x180017b44`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017baa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017baa`

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
0x180017b44  test    rdx, rdx
0x180017b47  jz      locret_180017BD3
0x180017b4d  mov     [rsp+arg_0], rbx
0x180017b52  mov     [rsp+arg_8], rsi
0x180017b57  push    rdi
0x180017b58  sub     rsp, 30h
0x180017b5c  mov     rdi, rdx
0x180017b5f  mov     rsi, rcx
0x180017b62  movzx   eax, byte ptr [rdi+2Dh]
0x180017b66  mov     edx, 2
0x180017b6b  add     eax, edx
0x180017b6d  cmp     eax, edx
0x180017b6f  jbe     short loc_180017B8D
0x180017b71  mov     rax, [rdi+10h]
0x180017b75  movsxd  rcx, edx
0x180017b78  inc     edx
0x180017b7a  add     rcx, rcx
0x180017b7d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180017b82  movzx   eax, byte ptr [rdi+2Dh]
0x180017b86  add     eax, 2
0x180017b89  cmp     edx, eax
0x180017b8b  jl      short loc_180017B71
0x180017b8d  movzx   edx, byte ptr [rdi+2Ch]
0x180017b91  xor     r9d, r9d; RelatedActivityId
0x180017b94  mov     rax, [rdi+10h]
0x180017b98  xor     r8d, r8d; ActivityId
0x180017b9b  mov     [rsp+38h+UserData], rax; UserData
0x180017ba0  mov     rcx, rsi; RegHandle
0x180017ba3  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x180017ba7  mov     rdx, rdi; EventDescriptor
0x180017baa  call    cs:__imp_EventWriteTransfer
0x180017bb0  mov     rbx, [rdi+18h]
0x180017bb4  mov     rcx, rdi
0x180017bb7  call    DestroyEventEntry
0x180017bbc  mov     rdi, rbx
0x180017bbf  test    rbx, rbx
0x180017bc2  jnz     short loc_180017B62
0x180017bc4  mov     rbx, [rsp+38h+arg_0]
0x180017bc9  mov     rsi, [rsp+38h+arg_8]
0x180017bce  add     rsp, 30h
0x180017bd2  pop     rdi
0x180017bd3  retn
```
