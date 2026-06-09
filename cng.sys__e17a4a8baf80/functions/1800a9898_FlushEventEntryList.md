# FlushEventEntryList

- ea: `0x1800a9898`
- end: `0x1800a992f`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800699a4`

## callees

- `0x180069900`
- `0x1800a9898`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1800a98fe`
- `ntoskrnl!EtwWriteTransfer` at `0x1800a98fe`

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
0x1800a9898  test    rdx, rdx
0x1800a989b  jz      locret_1800A992D
0x1800a98a1  mov     [rsp+arg_0], rbx
0x1800a98a6  mov     [rsp+arg_8], rsi
0x1800a98ab  push    rdi
0x1800a98ac  sub     rsp, 30h
0x1800a98b0  mov     rdi, rdx
0x1800a98b3  mov     rsi, rcx
0x1800a98b6  movzx   eax, byte ptr [rdi+2Dh]
0x1800a98ba  mov     edx, 2
0x1800a98bf  add     eax, edx
0x1800a98c1  cmp     eax, edx
0x1800a98c3  jbe     short loc_1800A98E1
0x1800a98c5  mov     rax, [rdi+10h]
0x1800a98c9  movsxd  rcx, edx
0x1800a98cc  inc     edx
0x1800a98ce  add     rcx, rcx
0x1800a98d1  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1800a98d6  movzx   eax, byte ptr [rdi+2Dh]
0x1800a98da  add     eax, 2
0x1800a98dd  cmp     edx, eax
0x1800a98df  jl      short loc_1800A98C5
0x1800a98e1  movzx   edx, byte ptr [rdi+2Ch]
0x1800a98e5  xor     r9d, r9d; RelatedActivityId
0x1800a98e8  mov     rax, [rdi+10h]
0x1800a98ec  xor     r8d, r8d; ActivityId
0x1800a98ef  mov     [rsp+38h+UserData], rax; UserData
0x1800a98f4  mov     rcx, rsi; RegHandle
0x1800a98f7  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1800a98fb  mov     rdx, rdi; EventDescriptor
0x1800a98fe  call    cs:__imp_EtwWriteTransfer
0x1800a9905  nop     dword ptr [rax+rax+00h]
0x1800a990a  mov     rbx, [rdi+18h]
0x1800a990e  mov     rcx, rdi
0x1800a9911  call    DestroyEventEntry
0x1800a9916  mov     rdi, rbx
0x1800a9919  test    rbx, rbx
0x1800a991c  jnz     short loc_1800A98B6
0x1800a991e  mov     rbx, [rsp+38h+arg_0]
0x1800a9923  mov     rsi, [rsp+38h+arg_8]
0x1800a9928  add     rsp, 30h
0x1800a992c  pop     rdi
0x1800a992d  retn
```
