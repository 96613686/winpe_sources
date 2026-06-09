# PcpRegistryNotificationCallback

- ea: `0x14001fc20`
- end: `0x14001fd4f`
- name: `PcpRegistryNotificationCallback`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b5e0`
- `0x14000eb54`
- `0x14001fae4`
- `0x14001fc20`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001fcf8`
- `ntoskrnl!ZwClose` at `0x14001fcf8`
- `ntoskrnl!KeSetEvent` at `0x14001fcba`
- `ntoskrnl!KeSetEvent` at `0x14001fd1b`
- `ntoskrnl!KeSetEvent` at `0x14001fd37`
- `ntoskrnl!KeSetEvent` at `0x14001fcba`
- `ntoskrnl!KeSetEvent` at `0x14001fd1b`
- `ntoskrnl!KeSetEvent` at `0x14001fd37`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fc47`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fc47`

## pseudocode

```c
LONG PcpRegistryNotificationCallback()
{
  NTSTATUS v0; // eax
  char v1; // di
  char v2; // bl
  LONG result; // eax
  char v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v0 = KeWaitForSingleObject(&PcgRegistryStateLock, Executive, 0, 0, 0);
  if ( v0 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_67a0081011b8336ab20862c5401e156e_Traceguids,
        (unsigned int)v0);
    }
    return KeSetEvent(&PcgRegistryCompletionEvent, 0, 0);
  }
  if ( !PcgPolicyKeyHandle )
  {
    KeSetEvent(&PcgRegistryStateLock, 0, 0);
    return KeSetEvent(&PcgRegistryCompletionEvent, 0, 0);
  }
  v1 = 0;
  v2 = 1;
  if ( PcpQueryIfRegistryHiveExists(&v4) )
  {
    PcpProcessSettingsChange();
    v1 = 1;
  }
  if ( !v4 || (v2 = 0, v1) )
  {
    ZwClose(PcgPolicyKeyHandle);
    PcgPolicyKeyHandle = 0;
  }
  result = KeSetEvent(&PcgRegistryStateLock, 0, 0);
  if ( v2 )
    return KeSetEvent(&PcgRegistryCompletionEvent, 0, 0);
  return result;
}

```

## disassembly

```asm
0x14001fc20  mov     [rsp+arg_0], rbx
0x14001fc25  push    rdi
0x14001fc26  sub     rsp, 30h
0x14001fc2a  xor     r9d, r9d; Alertable
0x14001fc2d  mov     [rsp+38h+arg_8], 0
0x14001fc32  xor     r8d, r8d; WaitMode
0x14001fc35  mov     [rsp+38h+Timeout], 0; Timeout
0x14001fc3e  xor     edx, edx; WaitReason
0x14001fc40  lea     rcx, PcgRegistryStateLock; Object
0x14001fc47  call    cs:__imp_KeWaitForSingleObject
0x14001fc4e  nop     dword ptr [rax+rax+00h]
0x14001fc53  test    eax, eax
0x14001fc55  jns     short loc_14001FCA4
0x14001fc57  mov     r10, cs:WPP_GLOBAL_Control
0x14001fc5e  lea     rcx, WPP_GLOBAL_Control
0x14001fc65  cmp     r10, rcx
0x14001fc68  jz      loc_14001FD2B
0x14001fc6e  cmp     byte ptr [r10+29h], 2
0x14001fc73  jb      loc_14001FD2B
0x14001fc79  test    dword ptr [r10+2Ch], 800h
0x14001fc81  jz      loc_14001FD2B
0x14001fc87  mov     rcx, [r10+18h]
0x14001fc8b  lea     r8, WPP_67a0081011b8336ab20862c5401e156e_Traceguids
0x14001fc92  mov     edx, 0Bh
0x14001fc97  mov     r9d, eax
0x14001fc9a  call    WPP_SF_D
0x14001fc9f  jmp     loc_14001FD2B
0x14001fca4  cmp     cs:PcgPolicyKeyHandle, 0
0x14001fcac  jnz     short loc_14001FCC8
0x14001fcae  xor     r8d, r8d; Wait
0x14001fcb1  lea     rcx, PcgRegistryStateLock; Event
0x14001fcb8  xor     edx, edx; Increment
0x14001fcba  call    cs:__imp_KeSetEvent
0x14001fcc1  nop     dword ptr [rax+rax+00h]
0x14001fcc6  jmp     short loc_14001FD2B
0x14001fcc8  lea     rcx, [rsp+38h+arg_8]
0x14001fccd  xor     dil, dil
0x14001fcd0  call    PcpQueryIfRegistryHiveExists
0x14001fcd5  mov     bl, 1
0x14001fcd7  test    al, al
0x14001fcd9  jz      short loc_14001FCE3
0x14001fcdb  call    PcpProcessSettingsChange
0x14001fce0  mov     dil, bl
0x14001fce3  cmp     [rsp+38h+arg_8], 0
0x14001fce8  jz      short loc_14001FCF1
0x14001fcea  xor     bl, bl
0x14001fcec  test    dil, dil
0x14001fcef  jz      short loc_14001FD0F
0x14001fcf1  mov     rcx, cs:PcgPolicyKeyHandle; Handle
0x14001fcf8  call    cs:__imp_ZwClose
0x14001fcff  nop     dword ptr [rax+rax+00h]
0x14001fd04  mov     cs:PcgPolicyKeyHandle, 0
0x14001fd0f  xor     r8d, r8d; Wait
0x14001fd12  lea     rcx, PcgRegistryStateLock; Event
0x14001fd19  xor     edx, edx; Increment
0x14001fd1b  call    cs:__imp_KeSetEvent
0x14001fd22  nop     dword ptr [rax+rax+00h]
0x14001fd27  test    bl, bl
0x14001fd29  jz      short loc_14001FD43
0x14001fd2b  xor     r8d, r8d; Wait
0x14001fd2e  lea     rcx, PcgRegistryCompletionEvent; Event
0x14001fd35  xor     edx, edx; Increment
0x14001fd37  call    cs:__imp_KeSetEvent
0x14001fd3e  nop     dword ptr [rax+rax+00h]
0x14001fd43  mov     rbx, [rsp+38h+arg_0]
0x14001fd48  add     rsp, 30h
0x14001fd4c  pop     rdi
0x14001fd4d  retn
```
