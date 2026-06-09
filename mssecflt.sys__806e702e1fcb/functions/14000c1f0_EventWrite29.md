# EventWrite29

- ea: `0x14000c1f0`
- end: `0x14000c2a2`
- name: `EventWrite29`
- size: `178`
- prototype: `__int64 __fastcall(int, int, int, int, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000a8f8`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14000c1f0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000c282`
- `ntoskrnl!EtwWrite` at `0x14000c282`

## pseudocode

```c
__int64 __fastcall EventWrite29(__int64 a1, __int64 a2, __int64 a3, int a4, PCEVENT_DESCRIPTOR EventDescriptor)
{
  const EVENT_DESCRIPTOR *v5; // rbx
  PSLIST_ENTRY UserData; // rax
  struct _SLIST_ENTRY *v7; // rdi
  unsigned int v9; // ebx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a3;
  v11 = a2;
  v10 = a1;
  v5 = EventDescriptor;
  UserData = SecGetEtwDescriptorBuffer(4u);
  v7 = UserData;
  if ( !UserData )
    return 3221225626LL;
  *((_QWORD *)&UserData->Next + 1) = 8;
  UserData->Next = (struct _SLIST_ENTRY *)&v10;
  *((_QWORD *)&UserData[1].Next + 1) = 8;
  UserData[1].Next = (struct _SLIST_ENTRY *)&v11;
  *((_QWORD *)&UserData[2].Next + 1) = 8;
  UserData[2].Next = (struct _SLIST_ENTRY *)&v12;
  *((_QWORD *)&UserData[3].Next + 1) = 4;
  UserData[3].Next = (struct _SLIST_ENTRY *)&v13;
  v9 = EtwWrite(Microsoft_Windows_SECHandle, v5, 0, 4u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer(v7);
  return v9;
}

```

## disassembly

```asm
0x14000c1f0  mov     rax, rsp
0x14000c1f3  mov     [rax+20h], r9d
0x14000c1f7  mov     [rax+18h], r8
0x14000c1fb  mov     [rax+10h], rdx
0x14000c1ff  mov     [rax+8], rcx
0x14000c203  push    rbx
0x14000c204  push    rdi
0x14000c205  sub     rsp, 38h
0x14000c209  mov     rbx, [rsp+48h+EventDescriptor]
0x14000c20e  mov     ecx, 4
0x14000c213  call    SecGetEtwDescriptorBuffer
0x14000c218  mov     rdi, rax
0x14000c21b  test    rax, rax
0x14000c21e  jnz     short loc_14000C227
0x14000c220  mov     eax, 0C000009Ah
0x14000c225  jmp     short loc_14000C29A
0x14000c227  lea     rax, [rsp+48h+arg_0]
0x14000c22c  mov     qword ptr [rdi+8], 8
0x14000c234  mov     [rdi], rax
0x14000c237  mov     r9d, 4; UserDataCount
0x14000c23d  lea     rax, [rsp+48h+arg_8]
0x14000c242  mov     qword ptr [rdi+18h], 8
0x14000c24a  mov     [rdi+10h], rax
0x14000c24e  xor     r8d, r8d; ActivityId
0x14000c251  lea     rax, [rsp+48h+arg_10]
0x14000c256  mov     qword ptr [rdi+28h], 8
0x14000c25e  mov     [rdi+20h], rax
0x14000c262  mov     rdx, rbx; EventDescriptor
0x14000c265  lea     rax, [rsp+48h+arg_18]
0x14000c26a  mov     qword ptr [rdi+38h], 4
0x14000c272  mov     [rdi+30h], rax
0x14000c276  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14000c27d  mov     [rsp+48h+UserData], rdi; UserData
0x14000c282  call    cs:__imp_EtwWrite
0x14000c289  nop     dword ptr [rax+rax+00h]
0x14000c28e  mov     rcx, rdi; ListEntry
0x14000c291  mov     ebx, eax
0x14000c293  call    SecReleaseEtwDescriptorBuffer
0x14000c298  mov     eax, ebx
0x14000c29a  add     rsp, 38h
0x14000c29e  pop     rdi
0x14000c29f  pop     rbx
0x14000c2a0  retn
```
