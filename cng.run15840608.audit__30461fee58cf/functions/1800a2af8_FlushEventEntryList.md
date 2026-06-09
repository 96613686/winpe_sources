# FlushEventEntryList

- ea: `0x1800a2af8`
- end: `0x1800a2b8f`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005f7d4`

## callees

- `0x18005f730`
- `0x1800a2af8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800a2b5e`
- `ntoskrnl!EtwWriteTransfer` at `0x1800a2b5e`

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
0x1800a2af8  test    rdx, rdx
0x1800a2afb  jz      locret_1800A2B8D
0x1800a2b01  mov     [rsp+arg_0], rbx
0x1800a2b06  mov     [rsp+arg_8], rsi
0x1800a2b0b  push    rdi
0x1800a2b0c  sub     rsp, 30h
0x1800a2b10  mov     rdi, rdx
0x1800a2b13  mov     rsi, rcx
0x1800a2b16  movzx   eax, byte ptr [rdi+2Dh]
0x1800a2b1a  mov     edx, 2
0x1800a2b1f  add     eax, edx
0x1800a2b21  cmp     eax, edx
0x1800a2b23  jbe     short loc_1800A2B41
0x1800a2b25  mov     rax, [rdi+10h]
0x1800a2b29  movsxd  rcx, edx
0x1800a2b2c  inc     edx
0x1800a2b2e  add     rcx, rcx
0x1800a2b31  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1800a2b36  movzx   eax, byte ptr [rdi+2Dh]
0x1800a2b3a  add     eax, 2
0x1800a2b3d  cmp     edx, eax
0x1800a2b3f  jl      short loc_1800A2B25
0x1800a2b41  movzx   edx, byte ptr [rdi+2Ch]
0x1800a2b45  xor     r9d, r9d; RelatedActivityId
0x1800a2b48  mov     rax, [rdi+10h]
0x1800a2b4c  xor     r8d, r8d; ActivityId
0x1800a2b4f  mov     [rsp+38h+UserData], rax; UserData
0x1800a2b54  mov     rcx, rsi; RegHandle
0x1800a2b57  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1800a2b5b  mov     rdx, rdi; EventDescriptor
0x1800a2b5e  call    cs:__imp_EtwWriteTransfer
0x1800a2b65  nop     dword ptr [rax+rax+00h]
0x1800a2b6a  mov     rbx, [rdi+18h]
0x1800a2b6e  mov     rcx, rdi
0x1800a2b71  call    DestroyEventEntry
0x1800a2b76  mov     rdi, rbx
0x1800a2b79  test    rbx, rbx
0x1800a2b7c  jnz     short loc_1800A2B16
0x1800a2b7e  mov     rbx, [rsp+38h+arg_0]
0x1800a2b83  mov     rsi, [rsp+38h+arg_8]
0x1800a2b88  add     rsp, 30h
0x1800a2b8c  pop     rdi
0x1800a2b8d  retn
```
