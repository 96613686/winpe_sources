# NetioInitNetworkRegistry

- ea: `0x14005bcc0`
- end: `0x14005bd73`
- name: `NetioInitNetworkRegistry`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400b6080`

## callees

- `0x14005bb28`
- `0x14005bbf0`
- `0x14005bcc0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005bd4e`
- `ntoskrnl!ZwClose` at `0x14005bd4e`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14005bcf0`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14005bcf0`

## string_xrefs

- `0x14005bcca`: `\Registry\Machine\Devices\Networking`
- `0x14005bce2`: `\Registry\Machine\Devices\Networking\Nsi`

## pseudocode

```c
NTSTATUS NetioInitNetworkRegistry()
{
  unsigned int i; // ebx
  NTSTATUS result; // eax
  _QWORD v2[3]; // [rsp+30h] [rbp-18h]
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF

  v2[0] = L"\\Registry\\Machine\\Devices\\Networking";
  v2[1] = L"\\Registry\\Machine\\Devices\\Networking\\Nsi";
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 0x200) == 0 )
  {
    if ( (unsigned __int8)RtlIsStateSeparationEnabled() && !(unsigned __int8)IsRunningOnXbox() )
    {
      for ( i = 0; i < 2; ++i )
      {
        Handle = 0;
        result = NetioCreateKeyEx(&Handle, 0, (const WCHAR *)v2[i], 0, 0x20019u, 0);
        if ( result < 0 )
          return result;
        if ( Handle )
          ZwClose(Handle);
      }
    }
    WPP_MAIN_CB.DeviceExtension = (PVOID)((unsigned __int64)WPP_MAIN_CB.DeviceExtension | 0x200);
  }
  return 0;
}

```

## disassembly

```asm
0x14005bcc0  mov     [rsp+arg_8], rbx
0x14005bcc5  push    rdi
0x14005bcc6  sub     rsp, 40h
0x14005bcca  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\Devices\\Networkin"...
0x14005bcd1  mov     edi, 200h
0x14005bcd6  test    cs:WPP_MAIN_CB.DeviceExtension, rdi
0x14005bcdd  mov     [rsp+48h+var_18], rax
0x14005bce2  lea     rax, aRegistryMachin_5; "\\Registry\\Machine\\Devices\\Networkin"...
0x14005bce9  mov     [rsp+48h+var_10], rax
0x14005bcee  jnz     short loc_14005BD65
0x14005bcf0  call    cs:__imp_RtlIsStateSeparationEnabled
0x14005bcf7  nop     dword ptr [rax+rax+00h]
0x14005bcfc  test    al, al
0x14005bcfe  jz      short loc_14005BD5E
0x14005bd00  call    IsRunningOnXbox
0x14005bd05  test    al, al
0x14005bd07  jnz     short loc_14005BD5E
0x14005bd09  xor     ebx, ebx
0x14005bd0b  cmp     ebx, 2
0x14005bd0e  jnb     short loc_14005BD5E
0x14005bd10  movsxd  r8, ebx
0x14005bd13  lea     rcx, [rsp+48h+Handle]; KeyHandle
0x14005bd18  mov     [rsp+48h+var_20], 0; ULONG
0x14005bd20  xor     r9d, r9d
0x14005bd23  xor     edx, edx
0x14005bd25  mov     [rsp+48h+Handle], 0
0x14005bd2e  mov     [rsp+48h+DesiredAccess], 20019h; DesiredAccess
0x14005bd36  mov     r8, [rsp+r8*8+48h+var_18]
0x14005bd3b  call    NetioCreateKeyEx
0x14005bd40  test    eax, eax
0x14005bd42  js      short loc_14005BD67
0x14005bd44  mov     rcx, [rsp+48h+Handle]; Handle
0x14005bd49  test    rcx, rcx
0x14005bd4c  jz      short loc_14005BD5A
0x14005bd4e  call    cs:__imp_ZwClose
0x14005bd55  nop     dword ptr [rax+rax+00h]
0x14005bd5a  inc     ebx
0x14005bd5c  jmp     short loc_14005BD0B
0x14005bd5e  or      cs:WPP_MAIN_CB.DeviceExtension, rdi
0x14005bd65  xor     eax, eax
0x14005bd67  mov     rbx, [rsp+48h+arg_8]
0x14005bd6c  add     rsp, 40h
0x14005bd70  pop     rdi
0x14005bd71  retn
```
