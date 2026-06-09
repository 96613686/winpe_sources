# EventWrite36

- ea: `0x14004377c`
- end: `0x14004383f`
- name: `EventWrite36`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140041218`

## callees

- `0x140008714`
- `0x14000876c`
- `0x14004377c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14004381f`
- `ntoskrnl!EtwWrite` at `0x14004381f`

## pseudocode

```c
__int64 EventWrite36(__int64 a1, int a2, ...)
{
  PSLIST_ENTRY UserData; // rax
  struct _SLIST_ENTRY *v3; // rdi
  unsigned int v5; // ebx
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF
  va_list va; // [rsp+60h] [rbp+18h]
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF
  va_list va1; // [rsp+68h] [rbp+20h]
  va_list va2; // [rsp+70h] [rbp+28h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  v7 = a2;
  v6 = a1;
  UserData = SecGetEtwDescriptorBuffer(5u);
  v3 = UserData;
  if ( !UserData )
    return 3221225626LL;
  *((_QWORD *)&UserData->Next + 1) = 8;
  UserData->Next = (struct _SLIST_ENTRY *)&v6;
  *((_QWORD *)&UserData[1].Next + 1) = 4;
  UserData[1].Next = (struct _SLIST_ENTRY *)&v7;
  *((_QWORD *)&UserData[2].Next + 1) = 8;
  UserData[2].Next = (struct _SLIST_ENTRY *)va;
  *((_QWORD *)&UserData[3].Next + 1) = 8;
  UserData[3].Next = (struct _SLIST_ENTRY *)va1;
  UserData[4].Next = (struct _SLIST_ENTRY *)va2;
  *((_QWORD *)&UserData[4].Next + 1) = 4;
  v5 = EtwWrite(Microsoft_Windows_SECHandle, &Event36, 0, 5u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer(v3);
  return v5;
}

```

## disassembly

```asm
0x14004377c  mov     rax, rsp
0x14004377f  mov     [rax+20h], r9
0x140043783  mov     [rax+18h], r8
0x140043787  mov     [rax+10h], edx
0x14004378a  mov     [rax+8], rcx
0x14004378e  push    rbx
0x14004378f  push    rdi
0x140043790  sub     rsp, 38h
0x140043794  mov     ebx, 5
0x140043799  mov     ecx, ebx
0x14004379b  call    SecGetEtwDescriptorBuffer
0x1400437a0  mov     rdi, rax
0x1400437a3  test    rax, rax
0x1400437a6  jnz     short loc_1400437B2
0x1400437a8  mov     eax, 0C000009Ah
0x1400437ad  jmp     loc_140043837
0x1400437b2  lea     rax, [rsp+48h+arg_0]
0x1400437b7  mov     qword ptr [rdi+8], 8
0x1400437bf  mov     [rdi], rax
0x1400437c2  lea     rdx, Event36; EventDescriptor
0x1400437c9  lea     rax, [rsp+48h+arg_8]
0x1400437ce  mov     qword ptr [rdi+18h], 4
0x1400437d6  mov     [rdi+10h], rax
0x1400437da  mov     r9d, ebx; UserDataCount
0x1400437dd  lea     rax, [rsp+48h+arg_10]
0x1400437e2  mov     qword ptr [rdi+28h], 8
0x1400437ea  mov     [rdi+20h], rax
0x1400437ee  xor     r8d, r8d; ActivityId
0x1400437f1  lea     rax, [rsp+48h+arg_18]
0x1400437f6  mov     qword ptr [rdi+38h], 8
0x1400437fe  mov     [rdi+30h], rax
0x140043802  lea     rax, [rsp+48h+arg_20]
0x140043807  mov     [rdi+40h], rax
0x14004380b  mov     qword ptr [rdi+48h], 4
0x140043813  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14004381a  mov     [rsp+48h+UserData], rdi; UserData
0x14004381f  call    cs:__imp_EtwWrite
0x140043826  nop     dword ptr [rax+rax+00h]
0x14004382b  mov     rcx, rdi; ListEntry
0x14004382e  mov     ebx, eax
0x140043830  call    SecReleaseEtwDescriptorBuffer
0x140043835  mov     eax, ebx
0x140043837  add     rsp, 38h
0x14004383b  pop     rdi
0x14004383c  pop     rbx
0x14004383d  retn
```
