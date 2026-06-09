# FlushEventEntryList

- ea: `0x180046cd0`
- end: `0x180046d60`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046d68`

## callees

- `0x180046bc0`
- `0x180046cd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180046d36`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180046d36`

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
0x180046cd0  test    rdx, rdx
0x180046cd3  jz      locret_180046D5F
0x180046cd9  mov     [rsp+arg_0], rbx
0x180046cde  mov     [rsp+arg_8], rsi
0x180046ce3  push    rdi
0x180046ce4  sub     rsp, 30h
0x180046ce8  mov     rdi, rdx
0x180046ceb  mov     rsi, rcx
0x180046cee  movzx   eax, byte ptr [rdi+2Dh]
0x180046cf2  mov     edx, 2
0x180046cf7  add     eax, edx
0x180046cf9  cmp     eax, edx
0x180046cfb  jbe     short loc_180046D19
0x180046cfd  mov     rax, [rdi+10h]
0x180046d01  movsxd  rcx, edx
0x180046d04  inc     edx
0x180046d06  add     rcx, rcx
0x180046d09  mov     byte ptr [rax+rcx*8+0Dh], 0
0x180046d0e  movzx   eax, byte ptr [rdi+2Dh]
0x180046d12  add     eax, 2
0x180046d15  cmp     edx, eax
0x180046d17  jl      short loc_180046CFD
0x180046d19  movzx   edx, byte ptr [rdi+2Ch]
0x180046d1d  xor     r9d, r9d; RelatedActivityId
0x180046d20  mov     rax, [rdi+10h]
0x180046d24  xor     r8d, r8d; ActivityId
0x180046d27  mov     [rsp+38h+UserData], rax; UserData
0x180046d2c  mov     rcx, rsi; RegHandle
0x180046d2f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x180046d33  mov     rdx, rdi; EventDescriptor
0x180046d36  call    cs:__imp_EventWriteTransfer
0x180046d3c  mov     rbx, [rdi+18h]
0x180046d40  mov     rcx, rdi
0x180046d43  call    DestroyEventEntry
0x180046d48  mov     rdi, rbx
0x180046d4b  test    rbx, rbx
0x180046d4e  jnz     short loc_180046CEE
0x180046d50  mov     rbx, [rsp+38h+arg_0]
0x180046d55  mov     rsi, [rsp+38h+arg_8]
0x180046d5a  add     rsp, 30h
0x180046d5e  pop     rdi
0x180046d5f  retn
```
