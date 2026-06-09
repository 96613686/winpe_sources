# FlushEventEntryList

- ea: `0x18002fbe8`
- end: `0x18002fc7f`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fc88`

## callees

- `0x18002fac4`
- `0x18002fbe8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fc4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fc4e`

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
0x18002fbe8  test    rdx, rdx
0x18002fbeb  jz      locret_18002FC7D
0x18002fbf1  mov     [rsp+arg_0], rbx
0x18002fbf6  mov     [rsp+arg_8], rsi
0x18002fbfb  push    rdi
0x18002fbfc  sub     rsp, 30h
0x18002fc00  mov     rdi, rdx
0x18002fc03  mov     rsi, rcx
0x18002fc06  movzx   eax, byte ptr [rdi+2Dh]
0x18002fc0a  mov     edx, 2
0x18002fc0f  add     eax, edx
0x18002fc11  cmp     eax, edx
0x18002fc13  jbe     short loc_18002FC31
0x18002fc15  mov     rax, [rdi+10h]
0x18002fc19  movsxd  rcx, edx
0x18002fc1c  inc     edx
0x18002fc1e  add     rcx, rcx
0x18002fc21  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18002fc26  movzx   eax, byte ptr [rdi+2Dh]
0x18002fc2a  add     eax, 2
0x18002fc2d  cmp     edx, eax
0x18002fc2f  jl      short loc_18002FC15
0x18002fc31  movzx   edx, byte ptr [rdi+2Ch]
0x18002fc35  xor     r9d, r9d; RelatedActivityId
0x18002fc38  mov     rax, [rdi+10h]
0x18002fc3c  xor     r8d, r8d; ActivityId
0x18002fc3f  mov     [rsp+38h+UserData], rax; UserData
0x18002fc44  mov     rcx, rsi; RegHandle
0x18002fc47  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18002fc4b  mov     rdx, rdi; EventDescriptor
0x18002fc4e  call    cs:__imp_EventWriteTransfer
0x18002fc55  nop     dword ptr [rax+rax+00h]
0x18002fc5a  mov     rbx, [rdi+18h]
0x18002fc5e  mov     rcx, rdi
0x18002fc61  call    DestroyEventEntry
0x18002fc66  mov     rdi, rbx
0x18002fc69  test    rbx, rbx
0x18002fc6c  jnz     short loc_18002FC06
0x18002fc6e  mov     rbx, [rsp+38h+arg_0]
0x18002fc73  mov     rsi, [rsp+38h+arg_8]
0x18002fc78  add     rsp, 30h
0x18002fc7c  pop     rdi
0x18002fc7d  retn
```
