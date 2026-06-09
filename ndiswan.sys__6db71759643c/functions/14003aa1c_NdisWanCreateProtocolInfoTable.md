# NdisWanCreateProtocolInfoTable

- ea: `0x14003aa1c`
- end: `0x14003aac7`
- name: `NdisWanCreateProtocolInfoTable`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140039008`

## callees

- `0x140006d9c`
- `0x14000a2c0`
- `0x14003aa1c`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14003aa9e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003aa9e`
- `ntoskrnl!ExAllocatePool2` at `0x14003aa32`
- `ntoskrnl!ExAllocatePool2` at `0x14003aa32`

## pseudocode

```c
__int64 NdisWanCreateProtocolInfoTable()
{
  __int64 Pool2; // rax
  __int64 v1; // rbx

  Pool2 = ExAllocatePool2(64, 688, 1315856727);
  v1 = Pool2;
  if ( Pool2 )
  {
    ProtocolInfoTable = (PKSPIN_LOCK)Pool2;
    *(_DWORD *)(Pool2 + 16) = 688;
    *(_DWORD *)(Pool2 + 20) = 32;
    KeInitializeSpinLock((PKSPIN_LOCK)Pool2);
    ProtocolInfoTable[5] = v1 + 48;
    NdisWanResetProtocolInfoTable();
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, 688);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14003aa1c  push    rbx
0x14003aa1e  sub     rsp, 20h
0x14003aa22  mov     edx, 2B0h
0x14003aa27  mov     ecx, 40h ; '@'
0x14003aa2c  mov     r8d, 4E6E6157h
0x14003aa32  call    cs:__imp_ExAllocatePool2
0x14003aa39  nop     dword ptr [rax+rax+00h]
0x14003aa3e  mov     rbx, rax
0x14003aa41  test    rax, rax
0x14003aa44  jnz     short loc_14003AA86
0x14003aa46  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aa4d  lea     rax, WPP_GLOBAL_Control
0x14003aa54  cmp     rcx, rax
0x14003aa57  jz      short loc_14003AA7F
0x14003aa59  mov     eax, [rcx+2Ch]
0x14003aa5c  test    al, 40h
0x14003aa5e  jz      short loc_14003AA7F
0x14003aa60  cmp     byte ptr [rcx+29h], 2
0x14003aa64  jb      short loc_14003AA7F
0x14003aa66  mov     rcx, [rcx+18h]
0x14003aa6a  lea     edx, [rbx+22h]
0x14003aa6d  mov     r9d, 2B0h
0x14003aa73  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14003aa7a  call    WPP_SF_d
0x14003aa7f  mov     eax, 0C000009Ah
0x14003aa84  jmp     short loc_14003AAC0
0x14003aa86  mov     rcx, rbx; SpinLock
0x14003aa89  mov     cs:ProtocolInfoTable, rbx
0x14003aa90  mov     dword ptr [rax+10h], 2B0h
0x14003aa97  mov     dword ptr [rax+14h], 20h ; ' '
0x14003aa9e  call    cs:__imp_KeInitializeSpinLock
0x14003aaa5  nop     dword ptr [rax+rax+00h]
0x14003aaaa  mov     rax, cs:ProtocolInfoTable
0x14003aab1  lea     rcx, [rbx+30h]
0x14003aab5  mov     [rax+28h], rcx
0x14003aab9  call    NdisWanResetProtocolInfoTable
0x14003aabe  xor     eax, eax
0x14003aac0  add     rsp, 20h
0x14003aac4  pop     rbx
0x14003aac5  retn
```
