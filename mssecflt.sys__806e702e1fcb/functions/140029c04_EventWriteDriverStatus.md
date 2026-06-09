# EventWriteDriverStatus

- ea: `0x140029c04`
- end: `0x140029c75`
- name: `EventWriteDriverStatus`
- size: `113`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140029cf0`

## callees

- `0x140011650`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x140029c56`
- `ntoskrnl!EtwWrite` at `0x140029c56`

## pseudocode

```c
NTSTATUS __fastcall EventWriteDriverStatus(PCEVENT_DESCRIPTOR EventDescriptor)
{
  __int64 v2; // [rsp+30h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+38h] [rbp-20h] BYREF

  v2 = MEMORY[0xFFFFF78000000014];
  v3.Ptr = (ULONGLONG)&v2;
  *(_QWORD *)&v3.Size = 8;
  return EtwWrite(Microsoft_Windows_SECHandle, EventDescriptor, 0, 1u, &v3);
}

```

## disassembly

```asm
0x140029c04  mov     r11, rsp
0x140029c07  sub     rsp, 58h
0x140029c0b  mov     rax, cs:__security_cookie
0x140029c12  xor     rax, rsp
0x140029c15  mov     [rsp+58h+var_10], rax
0x140029c1a  mov     rdx, rcx; EventDescriptor
0x140029c1d  mov     rax, 0FFFFF78000000014h
0x140029c27  mov     r9d, 1; UserDataCount
0x140029c2d  xor     r8d, r8d; ActivityId
0x140029c30  mov     rax, [rax]
0x140029c33  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x140029c3a  mov     [r11-28h], rax
0x140029c3e  lea     rax, [r11-28h]
0x140029c42  mov     [r11-20h], rax
0x140029c46  lea     rax, [r11-20h]
0x140029c4a  mov     [r11-38h], rax
0x140029c4e  mov     qword ptr [r11-18h], 8
0x140029c56  call    cs:__imp_EtwWrite
0x140029c5d  nop     dword ptr [rax+rax+00h]
0x140029c62  mov     rcx, [rsp+58h+var_10]
0x140029c67  xor     rcx, rsp; StackCookie
0x140029c6a  call    __security_check_cookie
0x140029c6f  add     rsp, 58h
0x140029c73  retn
```
