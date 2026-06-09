# FlushEventEntryList

- ea: `0x1800a4928`
- end: `0x1800a49bf`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800600c4`

## callees

- `0x180060020`
- `0x1800a4928`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800a498e`
- `ntoskrnl!EtwWriteTransfer` at `0x1800a498e`

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
0x1800a4928  test    rdx, rdx
0x1800a492b  jz      locret_1800A49BD
0x1800a4931  mov     [rsp+arg_0], rbx
0x1800a4936  mov     [rsp+arg_8], rsi
0x1800a493b  push    rdi
0x1800a493c  sub     rsp, 30h
0x1800a4940  mov     rdi, rdx
0x1800a4943  mov     rsi, rcx
0x1800a4946  movzx   eax, byte ptr [rdi+2Dh]
0x1800a494a  mov     edx, 2
0x1800a494f  add     eax, edx
0x1800a4951  cmp     eax, edx
0x1800a4953  jbe     short loc_1800A4971
0x1800a4955  mov     rax, [rdi+10h]
0x1800a4959  movsxd  rcx, edx
0x1800a495c  inc     edx
0x1800a495e  add     rcx, rcx
0x1800a4961  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1800a4966  movzx   eax, byte ptr [rdi+2Dh]
0x1800a496a  add     eax, 2
0x1800a496d  cmp     edx, eax
0x1800a496f  jl      short loc_1800A4955
0x1800a4971  movzx   edx, byte ptr [rdi+2Ch]
0x1800a4975  xor     r9d, r9d; RelatedActivityId
0x1800a4978  mov     rax, [rdi+10h]
0x1800a497c  xor     r8d, r8d; ActivityId
0x1800a497f  mov     [rsp+38h+UserData], rax; UserData
0x1800a4984  mov     rcx, rsi; RegHandle
0x1800a4987  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1800a498b  mov     rdx, rdi; EventDescriptor
0x1800a498e  call    cs:__imp_EtwWriteTransfer
0x1800a4995  nop     dword ptr [rax+rax+00h]
0x1800a499a  mov     rbx, [rdi+18h]
0x1800a499e  mov     rcx, rdi
0x1800a49a1  call    DestroyEventEntry
0x1800a49a6  mov     rdi, rbx
0x1800a49a9  test    rbx, rbx
0x1800a49ac  jnz     short loc_1800A4946
0x1800a49ae  mov     rbx, [rsp+38h+arg_0]
0x1800a49b3  mov     rsi, [rsp+38h+arg_8]
0x1800a49b8  add     rsp, 30h
0x1800a49bc  pop     rdi
0x1800a49bd  retn
```
