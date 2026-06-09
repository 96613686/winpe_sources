# FlushEventEntryList

- ea: `0x1800499e0`
- end: `0x180049a77`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180049a80`

## callees

- `0x180049944`
- `0x1800499e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180049a46`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180049a46`

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
0x1800499e0  test    rdx, rdx
0x1800499e3  jz      locret_180049A75
0x1800499e9  mov     [rsp+arg_0], rbx
0x1800499ee  mov     [rsp+arg_8], rsi
0x1800499f3  push    rdi
0x1800499f4  sub     rsp, 30h
0x1800499f8  mov     rdi, rdx
0x1800499fb  mov     rsi, rcx
0x1800499fe  movzx   eax, byte ptr [rdi+2Dh]
0x180049a02  mov     edx, 2
0x180049a07  add     eax, edx
0x180049a09  cmp     eax, edx
0x180049a0b  jbe     short loc_180049A29
0x180049a0d  mov     rax, [rdi+10h]
0x180049a11  movsxd  rcx, edx
0x180049a14  inc     edx
0x180049a16  add     rcx, rcx
0x180049a19  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180049a1e  movzx   eax, byte ptr [rdi+2Dh]
0x180049a22  add     eax, 2
0x180049a25  cmp     edx, eax
0x180049a27  jl      short loc_180049A0D
0x180049a29  movzx   edx, byte ptr [rdi+2Ch]
0x180049a2d  xor     r9d, r9d; RelatedActivityId
0x180049a30  mov     rax, [rdi+10h]
0x180049a34  xor     r8d, r8d; ActivityId
0x180049a37  mov     [rsp+38h+UserData], rax; UserData
0x180049a3c  mov     rcx, rsi; RegHandle
0x180049a3f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x180049a43  mov     rdx, rdi; EventDescriptor
0x180049a46  call    cs:__imp_EventWriteTransfer
0x180049a4d  nop     dword ptr [rax+rax+00h]
0x180049a52  mov     rbx, [rdi+18h]
0x180049a56  mov     rcx, rdi
0x180049a59  call    DestroyEventEntry
0x180049a5e  mov     rdi, rbx
0x180049a61  test    rbx, rbx
0x180049a64  jnz     short loc_1800499FE
0x180049a66  mov     rbx, [rsp+38h+arg_0]
0x180049a6b  mov     rsi, [rsp+38h+arg_8]
0x180049a70  add     rsp, 30h
0x180049a74  pop     rdi
0x180049a75  retn
```
