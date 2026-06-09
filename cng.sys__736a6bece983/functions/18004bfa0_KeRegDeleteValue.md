# KeRegDeleteValue

- ea: `0x18004bfa0`
- end: `0x18004bfeb`
- name: `KeRegDeleteValue`
- size: `75`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18004bf40`
- `0x180073768`
- `0x1800739c0`
- `0x180074884`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004bfb6`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004bfb6`
- `ntoskrnl!ZwDeleteValueKey` at `0x18004bfca`
- `ntoskrnl!ZwDeleteValueKey` at `0x18004bfca`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004bfd8`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004bfd8`

## pseudocode

```c
ULONG __fastcall KeRegDeleteValue(HANDLE KeyHandle, const WCHAR *a2)
{
  NTSTATUS v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v3 = ZwDeleteValueKey(KeyHandle, &DestinationString);
  return RtlNtStatusToDosErrorNoTeb(v3);
}

```

## disassembly

```asm
0x18004bfa0  push    rbx
0x18004bfa2  sub     rsp, 30h
0x18004bfa6  mov     rbx, rcx
0x18004bfa9  xorps   xmm0, xmm0
0x18004bfac  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18004bfb1  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18004bfb6  call    cs:__imp_RtlInitUnicodeString
0x18004bfbd  nop     dword ptr [rax+rax+00h]
0x18004bfc2  lea     rdx, [rsp+38h+DestinationString]; ValueName
0x18004bfc7  mov     rcx, rbx; KeyHandle
0x18004bfca  call    cs:__imp_ZwDeleteValueKey
0x18004bfd1  nop     dword ptr [rax+rax+00h]
0x18004bfd6  mov     ecx, eax; Status
0x18004bfd8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004bfdf  nop     dword ptr [rax+rax+00h]
0x18004bfe4  add     rsp, 30h
0x18004bfe8  pop     rbx
0x18004bfe9  retn
```
