# PmConstructDeviceLocationNetworkStorage(_DEVICE_EXTENSION *)

- ea: `0x14001f99c`
- end: `0x14001fa3e`
- name: `?PmConstructDeviceLocationNetworkStorage@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002366c`

## callees

- `0x140004504`
- `0x14001f99c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fa0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001fa0c`
- `ntoskrnl!ExAllocatePool2` at `0x14001f9bc`
- `ntoskrnl!ExAllocatePool2` at `0x14001f9bc`

## pseudocode

```c
__int64 __fastcall PmConstructDeviceLocationNetworkStorage(struct _DEVICE_EXTENSION *a1)
{
  wchar_t *Pool2; // rbx
  NTSTATUS v3; // edi

  Pool2 = (wchar_t *)ExAllocatePool2(66, 76, 1112108368);
  if ( Pool2 )
  {
    v3 = RtlStringCbPrintfW(Pool2, 8u, L"%s %u", L"Network storage on Adapter", *((_DWORD *)a1 + 104));
    if ( v3 < 0 )
      ExFreePoolWithTag(Pool2, 0);
    else
      RtlInitUnicodeString((PUNICODE_STRING)a1 + 28, Pool2);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001f99c  mov     [rsp+arg_0], rbx
0x14001f9a1  mov     [rsp+arg_8], rsi
0x14001f9a6  push    rdi
0x14001f9a7  sub     rsp, 30h
0x14001f9ab  mov     edx, 4Ch ; 'L'
0x14001f9b0  mov     rsi, rcx
0x14001f9b3  mov     r8d, 42496D50h
0x14001f9b9  lea     ecx, [rdx-0Ah]
0x14001f9bc  call    cs:__imp_ExAllocatePool2
0x14001f9c3  nop     dword ptr [rax+rax+00h]
0x14001f9c8  mov     rbx, rax
0x14001f9cb  test    rax, rax
0x14001f9ce  jnz     short loc_14001F9D7
0x14001f9d0  mov     edi, 0C000009Ah
0x14001f9d5  jmp     short loc_14001FA2B
0x14001f9d7  mov     eax, [rsi+1A0h]
0x14001f9dd  lea     r9, aNetworkStorage; "Network storage on Adapter"
0x14001f9e4  lea     r8, aSU; "%s %u"
0x14001f9eb  mov     [rsp+38h+var_18], eax
0x14001f9ef  mov     edx, 8; cbDest
0x14001f9f4  mov     rcx, rbx; pszDest
0x14001f9f7  call    RtlStringCbPrintfW
0x14001f9fc  mov     edi, eax
0x14001f9fe  test    eax, eax
0x14001fa00  js      short loc_14001FA1A
0x14001fa02  lea     rcx, [rsi+1C0h]; DestinationString
0x14001fa09  mov     rdx, rbx; SourceString
0x14001fa0c  call    cs:__imp_RtlInitUnicodeString
0x14001fa13  nop     dword ptr [rax+rax+00h]
0x14001fa18  jmp     short loc_14001FA2B
0x14001fa1a  xor     edx, edx; Tag
0x14001fa1c  mov     rcx, rbx; P
0x14001fa1f  call    cs:__imp_ExFreePoolWithTag
0x14001fa26  nop     dword ptr [rax+rax+00h]
0x14001fa2b  mov     rbx, [rsp+38h+arg_0]
0x14001fa30  mov     eax, edi
0x14001fa32  mov     rsi, [rsp+38h+arg_8]
0x14001fa37  add     rsp, 30h
0x14001fa3b  pop     rdi
0x14001fa3c  retn
```
