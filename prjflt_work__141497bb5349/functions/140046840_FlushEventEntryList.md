# FlushEventEntryList

- ea: `0x140046840`
- end: `0x1400468d7`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a9b0`

## callees

- `0x14000a90c`
- `0x140046840`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400468a6`
- `ntoskrnl!EtwWriteTransfer` at `0x1400468a6`

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
      EtwWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
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
0x140046840  test    rdx, rdx
0x140046843  jz      locret_1400468D5
0x140046849  mov     [rsp+arg_0], rbx
0x14004684e  mov     [rsp+arg_8], rsi
0x140046853  push    rdi
0x140046854  sub     rsp, 30h
0x140046858  mov     rdi, rdx
0x14004685b  mov     rsi, rcx
0x14004685e  movzx   eax, byte ptr [rdi+2Dh]
0x140046862  mov     edx, 2
0x140046867  add     eax, edx
0x140046869  cmp     eax, edx
0x14004686b  jbe     short loc_140046889
0x14004686d  mov     rax, [rdi+10h]
0x140046871  movsxd  rcx, edx
0x140046874  inc     edx
0x140046876  add     rcx, rcx
0x140046879  mov     byte ptr [rax+rcx*8+0Dh], 0
0x14004687e  movzx   eax, byte ptr [rdi+2Dh]
0x140046882  add     eax, 2
0x140046885  cmp     edx, eax
0x140046887  jl      short loc_14004686D
0x140046889  movzx   edx, byte ptr [rdi+2Ch]
0x14004688d  xor     r9d, r9d; RelatedActivityId
0x140046890  mov     rax, [rdi+10h]
0x140046894  xor     r8d, r8d; ActivityId
0x140046897  mov     [rsp+38h+UserData], rax; UserData
0x14004689c  mov     rcx, rsi; RegHandle
0x14004689f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1400468a3  mov     rdx, rdi; EventDescriptor
0x1400468a6  call    cs:__imp_EtwWriteTransfer
0x1400468ad  nop     dword ptr [rax+rax+00h]
0x1400468b2  mov     rbx, [rdi+18h]
0x1400468b6  mov     rcx, rdi
0x1400468b9  call    DestroyEventEntry
0x1400468be  mov     rdi, rbx
0x1400468c1  test    rbx, rbx
0x1400468c4  jnz     short loc_14004685E
0x1400468c6  mov     rbx, [rsp+38h+arg_0]
0x1400468cb  mov     rsi, [rsp+38h+arg_8]
0x1400468d0  add     rsp, 30h
0x1400468d4  pop     rdi
0x1400468d5  retn
```
