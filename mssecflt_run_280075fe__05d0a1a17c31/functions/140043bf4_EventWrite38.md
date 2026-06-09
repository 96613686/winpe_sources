# EventWrite38

- ea: `0x140043bf4`
- end: `0x140043cc8`
- name: `EventWrite38`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140041530`

## callees

- `0x140008714`
- `0x14000876c`
- `0x140043bf4`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140043ca8`
- `ntoskrnl!EtwWrite` at `0x140043ca8`

## pseudocode

```c
__int64 EventWrite38(__int64 a1, int a2, ...)
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
  __int64 v12; // [rsp+70h] [rbp+28h] BYREF
  va_list va2; // [rsp+70h] [rbp+28h]
  va_list va3; // [rsp+78h] [rbp+30h] BYREF

  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  v7 = a2;
  v6 = a1;
  UserData = SecGetEtwDescriptorBuffer(6u);
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
  UserData[5].Next = (struct _SLIST_ENTRY *)va3;
  *((_QWORD *)&UserData[4].Next + 1) = 8;
  *((_QWORD *)&UserData[5].Next + 1) = 8;
  v5 = EtwWrite(Microsoft_Windows_SECHandle, &Event38, 0, 6u, (PEVENT_DATA_DESCRIPTOR)UserData);
  SecReleaseEtwDescriptorBuffer(v3);
  return v5;
}

```

## disassembly

```asm
0x140043bf4  mov     rax, rsp
0x140043bf7  mov     [rax+20h], r9
0x140043bfb  mov     [rax+18h], r8
0x140043bff  mov     [rax+10h], edx
0x140043c02  mov     [rax+8], rcx
0x140043c06  push    rbx
0x140043c07  push    rdi
0x140043c08  sub     rsp, 38h
0x140043c0c  mov     ebx, 6
0x140043c11  mov     ecx, ebx
0x140043c13  call    SecGetEtwDescriptorBuffer
0x140043c18  mov     rdi, rax
0x140043c1b  test    rax, rax
0x140043c1e  jnz     short loc_140043C2A
0x140043c20  mov     eax, 0C000009Ah
0x140043c25  jmp     loc_140043CC0
0x140043c2a  lea     rax, [rsp+48h+arg_0]
0x140043c2f  mov     qword ptr [rdi+8], 8
0x140043c37  mov     [rdi], rax
0x140043c3a  lea     rdx, Event38; EventDescriptor
0x140043c41  lea     rax, [rsp+48h+arg_8]
0x140043c46  mov     qword ptr [rdi+18h], 4
0x140043c4e  mov     [rdi+10h], rax
0x140043c52  mov     r9d, ebx; UserDataCount
0x140043c55  lea     rax, [rsp+48h+arg_10]
0x140043c5a  mov     qword ptr [rdi+28h], 8
0x140043c62  mov     [rdi+20h], rax
0x140043c66  xor     r8d, r8d; ActivityId
0x140043c69  lea     rax, [rsp+48h+arg_18]
0x140043c6e  mov     qword ptr [rdi+38h], 8
0x140043c76  mov     [rdi+30h], rax
0x140043c7a  lea     rax, [rsp+48h+arg_20]
0x140043c7f  mov     [rdi+40h], rax
0x140043c83  lea     rax, [rsp+48h+arg_28]
0x140043c88  mov     [rdi+50h], rax
0x140043c8c  mov     qword ptr [rdi+48h], 8
0x140043c94  mov     qword ptr [rdi+58h], 8
0x140043c9c  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140043ca3  mov     [rsp+48h+UserData], rdi; UserData
0x140043ca8  call    cs:__imp_EtwWrite
0x140043caf  nop     dword ptr [rax+rax+00h]
0x140043cb4  mov     rcx, rdi; ListEntry
0x140043cb7  mov     ebx, eax
0x140043cb9  call    SecReleaseEtwDescriptorBuffer
0x140043cbe  mov     eax, ebx
0x140043cc0  add     rsp, 38h
0x140043cc4  pop     rdi
0x140043cc5  pop     rbx
0x140043cc6  retn
```
