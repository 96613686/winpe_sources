# PcpQueryIfRegistryHiveExists

- ea: `0x14001fae4`
- end: `0x14001fc10`
- name: `PcpQueryIfRegistryHiveExists`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001fc20`
- `0x14001fd60`

## callees

- `0x14000eb54`
- `0x14001fae4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001fb1f`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fbf1`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fb1f`
- `ntoskrnl!ZwQueryValueKey` at `0x14001fbf1`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14001fb7b`
- `ntoskrnl!ZwNotifyChangeKey` at `0x14001fb7b`

## pseudocode

```c
bool __fastcall PcpQueryIfRegistryHiveExists(_BYTE *a1)
{
  NTSTATUS v2; // eax
  ULONG ResultLength; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  ResultLength = 0;
  if ( ZwQueryValueKey(
         PcgPolicyKeyHandle,
         (PUNICODE_STRING)&PcgRegistryKeySoftwareHive,
         KeyValuePartialInformation,
         0,
         0,
         &ResultLength) == -1073741789 )
    return 1;
  v2 = ZwNotifyChangeKey(
         PcgPolicyKeyHandle,
         0,
         PcgPolicyNotifyCallbackWorkItem,
         (PVOID)1,
         &PcgPolicyIosb,
         4u,
         0,
         0,
         0,
         1u);
  if ( v2 >= 0 )
  {
    *a1 = 1;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_67a0081011b8336ab20862c5401e156e_Traceguids, (unsigned int)v2);
  }
  return ZwQueryValueKey(
           PcgPolicyKeyHandle,
           (PUNICODE_STRING)&PcgRegistryKeySoftwareHive,
           KeyValuePartialInformation,
           0,
           0,
           &ResultLength) == -1073741789;
}

```

## disassembly

```asm
0x14001fae4  push    rbx
0x14001fae6  sub     rsp, 50h
0x14001faea  xor     r9d, r9d; KeyValueInformation
0x14001faed  mov     byte ptr [rcx], 0
0x14001faf0  lea     rax, [rsp+58h+arg_0]
0x14001faf5  mov     [rsp+58h+arg_0], 0
0x14001fafd  mov     rbx, rcx
0x14001fb00  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14001fb05  mov     rcx, cs:PcgPolicyKeyHandle; KeyHandle
0x14001fb0c  lea     rdx, PcgRegistryKeySoftwareHive; ValueName
0x14001fb13  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001fb17  mov     [rsp+58h+Length], 0; Length
0x14001fb1f  call    cs:__imp_ZwQueryValueKey
0x14001fb26  nop     dword ptr [rax+rax+00h]
0x14001fb2b  cmp     eax, 0C0000023h
0x14001fb30  jz      loc_14001FC07
0x14001fb36  mov     rcx, cs:PcgPolicyKeyHandle; KeyHandle
0x14001fb3d  lea     rax, PcgPolicyIosb
0x14001fb44  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x14001fb49  lea     r8, PcgPolicyNotifyCallbackWorkItem; ApcRoutine
0x14001fb50  mov     [rsp+58h+BufferSize], 0; BufferSize
0x14001fb58  mov     r9d, 1; ApcContext
0x14001fb5e  mov     [rsp+58h+Buffer], 0; Buffer
0x14001fb67  xor     edx, edx; Event
0x14001fb69  mov     [rsp+58h+WatchTree], 0; WatchTree
0x14001fb6e  mov     dword ptr [rsp+58h+ResultLength], 4; CompletionFilter
0x14001fb76  mov     qword ptr [rsp+58h+Length], rax; IoStatusBlock
0x14001fb7b  call    cs:__imp_ZwNotifyChangeKey
0x14001fb82  nop     dword ptr [rax+rax+00h]
0x14001fb87  test    eax, eax
0x14001fb89  jns     short loc_14001FBC7
0x14001fb8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb92  lea     rdx, WPP_GLOBAL_Control
0x14001fb99  cmp     rcx, rdx
0x14001fb9c  jz      short loc_14001FBCA
0x14001fb9e  cmp     byte ptr [rcx+29h], 2
0x14001fba2  jb      short loc_14001FBCA
0x14001fba4  test    dword ptr [rcx+2Ch], 800h
0x14001fbab  jz      short loc_14001FBCA
0x14001fbad  mov     rcx, [rcx+18h]
0x14001fbb1  lea     r8, WPP_67a0081011b8336ab20862c5401e156e_Traceguids
0x14001fbb8  mov     edx, 0Ch
0x14001fbbd  mov     r9d, eax
0x14001fbc0  call    WPP_SF_D
0x14001fbc5  jmp     short loc_14001FBCA
0x14001fbc7  mov     byte ptr [rbx], 1
0x14001fbca  mov     rcx, cs:PcgPolicyKeyHandle; KeyHandle
0x14001fbd1  lea     rax, [rsp+58h+arg_0]
0x14001fbd6  xor     r9d, r9d; KeyValueInformation
0x14001fbd9  mov     [rsp+58h+ResultLength], rax; ResultLength
0x14001fbde  lea     rdx, PcgRegistryKeySoftwareHive; ValueName
0x14001fbe5  mov     [rsp+58h+Length], 0; Length
0x14001fbed  lea     r8d, [r9+2]; KeyValueInformationClass
0x14001fbf1  call    cs:__imp_ZwQueryValueKey
0x14001fbf8  nop     dword ptr [rax+rax+00h]
0x14001fbfd  cmp     eax, 0C0000023h
0x14001fc02  setz    al
0x14001fc05  jmp     short loc_14001FC09
0x14001fc07  mov     al, 1
0x14001fc09  add     rsp, 50h
0x14001fc0d  pop     rbx
0x14001fc0e  retn
```
