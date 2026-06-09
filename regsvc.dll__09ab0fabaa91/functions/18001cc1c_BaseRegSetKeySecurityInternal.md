# BaseRegSetKeySecurityInternal

- ea: `0x18001cc1c`
- end: `0x18001cca6`
- name: `BaseRegSetKeySecurityInternal`
- size: `138`
- prototype: `ULONG __fastcall(HANDLE Handle, SECURITY_INFORMATION SecurityInformation, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019ff0`

## callees

- `0x18001cc1c`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x18001cc73`
- `ntdll!NtSetSecurityObject` at `0x18001cc73`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001cc61`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001cc61`
- `ntdll!RtlNtStatusToDosError` at `0x18001cc89`
- `ntdll!RtlNtStatusToDosError` at `0x18001cc89`

## pseudocode

```c
ULONG __fastcall BaseRegSetKeySecurityInternal(HANDLE Handle, SECURITY_INFORMATION SecurityInformation, __int64 a3)
{
  NTSTATUS v6; // eax

  if ( !a3 || !*(_QWORD *)a3 )
    return 87;
  if ( Handle == (HANDLE)-2147483644LL || Handle == (HANDLE)-2147483568LL || Handle == (HANDLE)-2147483552LL )
  {
    v6 = -1073741816;
  }
  else if ( RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)a3, *(_DWORD *)(a3 + 8), SecurityInformation) )
  {
    v6 = NtSetSecurityObject(Handle, SecurityInformation, *(PSECURITY_DESCRIPTOR *)a3);
  }
  else
  {
    v6 = -1073741811;
  }
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x18001cc1c  mov     [rsp+arg_0], rbx
0x18001cc21  mov     [rsp+arg_8], rsi
0x18001cc26  push    rdi
0x18001cc27  sub     rsp, 20h
0x18001cc2b  mov     rdi, r8
0x18001cc2e  mov     esi, edx
0x18001cc30  mov     rbx, rcx
0x18001cc33  test    r8, r8
0x18001cc36  jz      short loc_18001CC91
0x18001cc38  mov     rcx, [r8]; SecurityDescriptorInput
0x18001cc3b  test    rcx, rcx
0x18001cc3e  jz      short loc_18001CC91
0x18001cc40  cmp     rbx, 0FFFFFFFF80000004h
0x18001cc47  jz      short loc_18001CC82
0x18001cc49  cmp     rbx, 0FFFFFFFF80000050h
0x18001cc50  jz      short loc_18001CC82
0x18001cc52  cmp     rbx, 0FFFFFFFF80000060h
0x18001cc59  jz      short loc_18001CC82
0x18001cc5b  mov     r8d, edx; RequiredInformation
0x18001cc5e  mov     edx, [rdi+8]; SecurityDescriptorLength
0x18001cc61  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001cc67  test    al, al
0x18001cc69  jz      short loc_18001CC7B
0x18001cc6b  mov     r8, [rdi]; SecurityDescriptor
0x18001cc6e  mov     edx, esi; SecurityInformation
0x18001cc70  mov     rcx, rbx; Handle
0x18001cc73  call    cs:__imp_NtSetSecurityObject
0x18001cc79  jmp     short loc_18001CC87
0x18001cc7b  mov     eax, 0C000000Dh
0x18001cc80  jmp     short loc_18001CC87
0x18001cc82  mov     eax, 0C0000008h
0x18001cc87  mov     ecx, eax; Status
0x18001cc89  call    cs:__imp_RtlNtStatusToDosError
0x18001cc8f  jmp     short loc_18001CC96
0x18001cc91  mov     eax, 57h ; 'W'
0x18001cc96  mov     rbx, [rsp+28h+arg_0]
0x18001cc9b  mov     rsi, [rsp+28h+arg_8]
0x18001cca0  add     rsp, 20h
0x18001cca4  pop     rdi
0x18001cca5  retn
```
