# KeRegDeleteValue

- ea: `0x18004b510`
- end: `0x18004b55b`
- name: `KeRegDeleteValue`
- size: `75`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, const WCHAR *)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18004b4b0`
- `0x180072d68`
- `0x180072fc0`
- `0x180073e84`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18004b526`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004b526`
- `ntoskrnl!ZwDeleteValueKey` at `0x18004b53a`
- `ntoskrnl!ZwDeleteValueKey` at `0x18004b53a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004b548`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x18004b548`

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
0x18004b510  push    rbx
0x18004b512  sub     rsp, 30h
0x18004b516  mov     rbx, rcx
0x18004b519  xorps   xmm0, xmm0
0x18004b51c  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18004b521  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18004b526  call    cs:__imp_RtlInitUnicodeString
0x18004b52d  nop     dword ptr [rax+rax+00h]
0x18004b532  lea     rdx, [rsp+38h+DestinationString]; ValueName
0x18004b537  mov     rcx, rbx; KeyHandle
0x18004b53a  call    cs:__imp_ZwDeleteValueKey
0x18004b541  nop     dword ptr [rax+rax+00h]
0x18004b546  mov     ecx, eax; Status
0x18004b548  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18004b54f  nop     dword ptr [rax+rax+00h]
0x18004b554  add     rsp, 30h
0x18004b558  pop     rbx
0x18004b559  retn
```
