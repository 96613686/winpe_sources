# FlushEventEntryList

- ea: `0x140054688`
- end: `0x14005471f`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022d90`

## callees

- `0x1400369e8`
- `0x140054688`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400546ee`
- `ntoskrnl!EtwWriteTransfer` at `0x1400546ee`

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
0x140054688  test    rdx, rdx
0x14005468b  jz      locret_14005471D
0x140054691  mov     [rsp+arg_0], rbx
0x140054696  mov     [rsp+arg_8], rsi
0x14005469b  push    rdi
0x14005469c  sub     rsp, 30h
0x1400546a0  mov     rdi, rdx
0x1400546a3  mov     rsi, rcx
0x1400546a6  movzx   eax, byte ptr [rdi+2Dh]
0x1400546aa  mov     edx, 2
0x1400546af  add     eax, edx
0x1400546b1  cmp     eax, edx
0x1400546b3  jbe     short loc_1400546D1
0x1400546b5  mov     rax, [rdi+10h]
0x1400546b9  movsxd  rcx, edx
0x1400546bc  inc     edx
0x1400546be  add     rcx, rcx
0x1400546c1  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1400546c6  movzx   eax, byte ptr [rdi+2Dh]
0x1400546ca  add     eax, 2
0x1400546cd  cmp     edx, eax
0x1400546cf  jl      short loc_1400546B5
0x1400546d1  movzx   edx, byte ptr [rdi+2Ch]
0x1400546d5  xor     r9d, r9d; RelatedActivityId
0x1400546d8  mov     rax, [rdi+10h]
0x1400546dc  xor     r8d, r8d; ActivityId
0x1400546df  mov     [rsp+38h+UserData], rax; UserData
0x1400546e4  mov     rcx, rsi; RegHandle
0x1400546e7  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x1400546eb  mov     rdx, rdi; EventDescriptor
0x1400546ee  call    cs:__imp_EtwWriteTransfer
0x1400546f5  nop     dword ptr [rax+rax+00h]
0x1400546fa  mov     rbx, [rdi+18h]
0x1400546fe  mov     rcx, rdi
0x140054701  call    DestroyEventEntry
0x140054706  mov     rdi, rbx
0x140054709  test    rbx, rbx
0x14005470c  jnz     short loc_1400546A6
0x14005470e  mov     rbx, [rsp+38h+arg_0]
0x140054713  mov     rsi, [rsp+38h+arg_8]
0x140054718  add     rsp, 30h
0x14005471c  pop     rdi
0x14005471d  retn
```
