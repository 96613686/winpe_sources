# FlushEventEntryList

- ea: `0x18001a1bc`
- end: `0x18001a24c`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a104`

## callees

- `0x18001a1bc`
- `0x18001e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a222`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a222`

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
0x18001a1bc  test    rdx, rdx
0x18001a1bf  jz      locret_18001A24B
0x18001a1c5  mov     [rsp+arg_0], rbx
0x18001a1ca  mov     [rsp+arg_8], rsi
0x18001a1cf  push    rdi
0x18001a1d0  sub     rsp, 30h
0x18001a1d4  mov     rdi, rdx
0x18001a1d7  mov     rsi, rcx
0x18001a1da  movzx   eax, byte ptr [rdi+2Dh]
0x18001a1de  mov     edx, 2
0x18001a1e3  add     eax, edx
0x18001a1e5  cmp     eax, edx
0x18001a1e7  jbe     short loc_18001A205
0x18001a1e9  mov     rax, [rdi+10h]
0x18001a1ed  movsxd  rcx, edx
0x18001a1f0  inc     edx
0x18001a1f2  add     rcx, rcx
0x18001a1f5  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18001a1fa  movzx   eax, byte ptr [rdi+2Dh]
0x18001a1fe  add     eax, 2
0x18001a201  cmp     edx, eax
0x18001a203  jl      short loc_18001A1E9
0x18001a205  movzx   edx, byte ptr [rdi+2Ch]
0x18001a209  xor     r9d, r9d; RelatedActivityId
0x18001a20c  mov     rax, [rdi+10h]
0x18001a210  xor     r8d, r8d; ActivityId
0x18001a213  mov     [rsp+38h+UserData], rax; UserData
0x18001a218  mov     rcx, rsi; RegHandle
0x18001a21b  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18001a21f  mov     rdx, rdi; EventDescriptor
0x18001a222  call    cs:__imp_EventWriteTransfer
0x18001a228  mov     rbx, [rdi+18h]
0x18001a22c  mov     rcx, rdi
0x18001a22f  call    DestroyEventEntry
0x18001a234  mov     rdi, rbx
0x18001a237  test    rbx, rbx
0x18001a23a  jnz     short loc_18001A1DA
0x18001a23c  mov     rbx, [rsp+38h+arg_0]
0x18001a241  mov     rsi, [rsp+38h+arg_8]
0x18001a246  add     rsp, 30h
0x18001a24a  pop     rdi
0x18001a24b  retn
```
