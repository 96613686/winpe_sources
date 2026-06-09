# KeRegDeleteValue

- ea: `0x180055610`
- end: `0x18005565b`
- name: `KeRegDeleteValue`
- size: `75`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800555b0`
- `0x18007cf08`
- `0x18007d160`
- `0x18007e024`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180055626`
- `ntoskrnl!RtlInitUnicodeString` at `0x180055626`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005563a`
- `ntoskrnl!ZwDeleteValueKey` at `0x18005563a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180055648`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180055648`

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
0x180055610  push    rbx
0x180055612  sub     rsp, 30h
0x180055616  mov     rbx, rcx
0x180055619  xorps   xmm0, xmm0
0x18005561c  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180055621  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180055626  call    cs:__imp_RtlInitUnicodeString
0x18005562d  nop     dword ptr [rax+rax+00h]
0x180055632  lea     rdx, [rsp+38h+DestinationString]; ValueName
0x180055637  mov     rcx, rbx; KeyHandle
0x18005563a  call    cs:__imp_ZwDeleteValueKey
0x180055641  nop     dword ptr [rax+rax+00h]
0x180055646  mov     ecx, eax; Status
0x180055648  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18005564f  nop     dword ptr [rax+rax+00h]
0x180055654  add     rsp, 30h
0x180055658  pop     rbx
0x180055659  retn
```
