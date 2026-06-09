# FlushEventEntryList

- ea: `0x18003cae0`
- end: `0x18003cb77`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027468`

## callees

- `0x18002733c`
- `0x18003cae0`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x18003cb46`
- `ntoskrnl!EtwWriteTransfer` at `0x18003cb46`

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
0x18003cae0  test    rdx, rdx
0x18003cae3  jz      locret_18003CB75
0x18003cae9  mov     [rsp+arg_0], rbx
0x18003caee  mov     [rsp+arg_8], rsi
0x18003caf3  push    rdi
0x18003caf4  sub     rsp, 30h
0x18003caf8  mov     rdi, rdx
0x18003cafb  mov     rsi, rcx
0x18003cafe  movzx   eax, byte ptr [rdi+2Dh]
0x18003cb02  mov     edx, 2
0x18003cb07  add     eax, edx
0x18003cb09  cmp     eax, edx
0x18003cb0b  jbe     short loc_18003CB29
0x18003cb0d  mov     rax, [rdi+10h]
0x18003cb11  movsxd  rcx, edx
0x18003cb14  inc     edx
0x18003cb16  add     rcx, rcx
0x18003cb19  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18003cb1e  movzx   eax, byte ptr [rdi+2Dh]
0x18003cb22  add     eax, 2
0x18003cb25  cmp     edx, eax
0x18003cb27  jl      short loc_18003CB0D
0x18003cb29  movzx   edx, byte ptr [rdi+2Ch]
0x18003cb2d  xor     r9d, r9d; RelatedActivityId
0x18003cb30  mov     rax, [rdi+10h]
0x18003cb34  xor     r8d, r8d; ActivityId
0x18003cb37  mov     [rsp+38h+UserData], rax; UserData
0x18003cb3c  mov     rcx, rsi; RegHandle
0x18003cb3f  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18003cb43  mov     rdx, rdi; EventDescriptor
0x18003cb46  call    cs:__imp_EtwWriteTransfer
0x18003cb4d  nop     dword ptr [rax+rax+00h]
0x18003cb52  mov     rbx, [rdi+18h]
0x18003cb56  mov     rcx, rdi
0x18003cb59  call    DestroyEventEntry
0x18003cb5e  mov     rdi, rbx
0x18003cb61  test    rbx, rbx
0x18003cb64  jnz     short loc_18003CAFE
0x18003cb66  mov     rbx, [rsp+38h+arg_0]
0x18003cb6b  mov     rsi, [rsp+38h+arg_8]
0x18003cb70  add     rsp, 30h
0x18003cb74  pop     rdi
0x18003cb75  retn
```
