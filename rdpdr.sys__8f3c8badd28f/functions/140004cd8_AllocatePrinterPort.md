# AllocatePrinterPort

- ea: `0x140004cd8`
- end: `0x140004ea9`
- name: `AllocatePrinterPort`
- size: `465`
- prototype: `__int64 __fastcall(int, __int64, __int64, _DWORD *, PHANDLE DeviceInterfaceRegKey, PUNICODE_STRING SymbolicLinkName)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x1400294a0`

## callees

- `0x14000327c`
- `0x140004cd8`
- `0x140004eb0`
- `0x14001b6c8`
- `0x14002bca0`
- `0x14002c5d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004e17`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004e4a`
- `ntoskrnl!ZwClose` at `0x140004e5f`
- `ntoskrnl!ZwClose` at `0x140004e5f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e02`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e8a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e02`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e8a`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140004d62`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140004d62`

## pseudocode

```c
__int64 __fastcall AllocatePrinterPort(
        int a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        PHANDLE DeviceInterfaceRegKey,
        PUNICODE_STRING SymbolicLinkName)
{
  unsigned int NextFreePortInPortArray; // ebx
  BOOL v7; // edi
  int IsAvailableForUse; // ebp
  unsigned int v11; // r12d
  KIRQL v12; // al

  NextFreePortInPortArray = 0;
  v7 = 0;
  *a4 = 32 * a1;
  IsAvailableForUse = 0;
  while ( !NextFreePortInPortArray )
  {
    NextFreePortInPortArray = FindNextFreePortInPortArray((unsigned int)*a4, a4);
    if ( !NextFreePortInPortArray )
    {
      if ( (unsigned int)GeneratePortName((unsigned int)*a4, a2) )
        NextFreePortInPortArray = CreatePrintPortInterface((__int64)SymbolicLinkName, a2);
      else
        NextFreePortInPortArray = -1073741670;
    }
    v11 = NextFreePortInPortArray;
    v7 = NextFreePortInPortArray == 0;
    if ( NextFreePortInPortArray )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          31,
          WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids,
          NextFreePortInPortArray);
LABEL_13:
      *DeviceInterfaceRegKey = (void *)-1LL;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids,
          NextFreePortInPortArray);
      goto LABEL_16;
    }
    NextFreePortInPortArray = IoOpenDeviceInterfaceRegistryKey(SymbolicLinkName, 0xF003Fu, DeviceInterfaceRegKey);
    if ( NextFreePortInPortArray )
      goto LABEL_13;
    IsAvailableForUse = PortIsAvailableForUse(*DeviceInterfaceRegKey);
LABEL_16:
    if ( IsAvailableForUse && !NextFreePortInPortArray )
      return NextFreePortInPortArray;
    if ( !v11 )
    {
      RtlFreeUnicodeString(SymbolicLinkName);
      v7 = 0;
    }
    v12 = KeAcquireSpinLockRaiseToDpc(&PortAllocLock);
    *((_DWORD *)&WPP_MAIN_CB.Dpc.DpcListEntry.Next->Next + ((unsigned __int64)(unsigned int)*a4 >> 5)) &= ~(1 << *a4);
    KeReleaseSpinLock(&PortAllocLock, v12);
    if ( *DeviceInterfaceRegKey != (void *)-1LL )
    {
      ZwClose(*DeviceInterfaceRegKey);
      *DeviceInterfaceRegKey = (void *)-1LL;
    }
    if ( IsAvailableForUse )
    {
      if ( !NextFreePortInPortArray )
        return NextFreePortInPortArray;
      break;
    }
  }
  if ( v7 )
    RtlFreeUnicodeString(SymbolicLinkName);
  return NextFreePortInPortArray;
}

```

## disassembly

```asm
0x140004cd8  push    rbx
0x140004cda  push    rbp
0x140004cdb  push    rdi
0x140004cdc  push    r12
0x140004cde  push    r13
0x140004ce0  push    r14
0x140004ce2  push    r15
0x140004ce4  sub     rsp, 20h
0x140004ce8  mov     r14, [rsp+58h+DeviceInterfaceRegKey]
0x140004cf0  xor     ebx, ebx
0x140004cf2  shl     ecx, 5
0x140004cf5  xor     edi, edi
0x140004cf7  mov     [r9], ecx
0x140004cfa  xor     ebp, ebp
0x140004cfc  mov     r15, r9
0x140004cff  mov     r13, rdx
0x140004d02  test    ebx, ebx
0x140004d04  jnz     loc_140004E7E
0x140004d0a  mov     ecx, [r15]
0x140004d0d  mov     rdx, r15
0x140004d10  call    FindNextFreePortInPortArray
0x140004d15  mov     ebx, eax
0x140004d17  test    eax, eax
0x140004d19  jnz     short loc_140004D43
0x140004d1b  mov     ecx, [r15]
0x140004d1e  mov     rdx, r13
0x140004d21  call    GeneratePortName
0x140004d26  test    eax, eax
0x140004d28  jnz     short loc_140004D31
0x140004d2a  mov     ebx, 0C000009Ah
0x140004d2f  jmp     short loc_140004D43
0x140004d31  mov     rcx, [rsp+58h+SymbolicLinkName]
0x140004d39  mov     rdx, r13
0x140004d3c  call    CreatePrintPortInterface
0x140004d41  mov     ebx, eax
0x140004d43  xor     edi, edi
0x140004d45  mov     r12d, ebx
0x140004d48  test    ebx, ebx
0x140004d4a  setz    dil
0x140004d4e  test    ebx, ebx
0x140004d50  jnz     short loc_140004D80
0x140004d52  mov     rcx, [rsp+58h+SymbolicLinkName]; SymbolicLinkName
0x140004d5a  mov     r8, r14; DeviceInterfaceRegKey
0x140004d5d  mov     edx, 0F003Fh; DesiredAccess
0x140004d62  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x140004d69  nop     dword ptr [rax+rax+00h]
0x140004d6e  mov     ebx, eax
0x140004d70  test    eax, eax
0x140004d72  jnz     short loc_140004DB1
0x140004d74  mov     rcx, [r14]; KeyHandle
0x140004d77  call    PortIsAvailableForUse
0x140004d7c  mov     ebp, eax
0x140004d7e  jmp     short loc_140004DE9
0x140004d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d87  lea     rax, WPP_GLOBAL_Control
0x140004d8e  cmp     rcx, rax
0x140004d91  jz      short loc_140004DB8
0x140004d93  cmp     byte ptr [rcx+29h], 4
0x140004d97  jb      short loc_140004DB8
0x140004d99  mov     rcx, [rcx+18h]
0x140004d9d  lea     r8, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids
0x140004da4  mov     edx, 1Fh
0x140004da9  mov     r9d, ebx
0x140004dac  call    WPP_SF_d
0x140004db1  lea     rax, WPP_GLOBAL_Control
0x140004db8  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140004dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dc6  cmp     rcx, rax
0x140004dc9  jz      short loc_140004DE9
0x140004dcb  cmp     byte ptr [rcx+29h], 4
0x140004dcf  jb      short loc_140004DE9
0x140004dd1  mov     rcx, [rcx+18h]
0x140004dd5  lea     r8, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids
0x140004ddc  mov     edx, 20h ; ' '
0x140004de1  mov     r9d, ebx
0x140004de4  call    WPP_SF_d
0x140004de9  test    ebp, ebp
0x140004deb  jz      short loc_140004DF5
0x140004ded  test    ebx, ebx
0x140004def  jz      loc_140004E96
0x140004df5  test    r12d, r12d
0x140004df8  jnz     short loc_140004E10
0x140004dfa  mov     rcx, [rsp+58h+SymbolicLinkName]; UnicodeString
0x140004e02  call    cs:__imp_RtlFreeUnicodeString
0x140004e09  nop     dword ptr [rax+rax+00h]
0x140004e0e  xor     edi, edi
0x140004e10  lea     rcx, ?PortAllocLock@@3_KA; SpinLock
0x140004e17  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004e1e  nop     dword ptr [rax+rax+00h]
0x140004e23  mov     ecx, [r15]
0x140004e26  mov     edx, 1
0x140004e2b  mov     r8, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next
0x140004e32  mov     r9d, ecx
0x140004e35  shl     edx, cl
0x140004e37  lea     rcx, ?PortAllocLock@@3_KA; SpinLock
0x140004e3e  not     edx
0x140004e40  shr     r9, 5
0x140004e44  and     [r8+r9*4], edx
0x140004e48  mov     dl, al; NewIrql
0x140004e4a  call    cs:__imp_KeReleaseSpinLock
0x140004e51  nop     dword ptr [rax+rax+00h]
0x140004e56  mov     rcx, [r14]; Handle
0x140004e59  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004e5d  jz      short loc_140004E72
0x140004e5f  call    cs:__imp_ZwClose
0x140004e66  nop     dword ptr [rax+rax+00h]
0x140004e6b  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140004e72  test    ebp, ebp
0x140004e74  jz      loc_140004D02
0x140004e7a  test    ebx, ebx
0x140004e7c  jz      short loc_140004E96
0x140004e7e  test    edi, edi
0x140004e80  jz      short loc_140004E96
0x140004e82  mov     rcx, [rsp+58h+SymbolicLinkName]; UnicodeString
0x140004e8a  call    cs:__imp_RtlFreeUnicodeString
0x140004e91  nop     dword ptr [rax+rax+00h]
0x140004e96  mov     eax, ebx
0x140004e98  add     rsp, 20h
0x140004e9c  pop     r15
0x140004e9e  pop     r14
0x140004ea0  pop     r13
0x140004ea2  pop     r12
0x140004ea4  pop     rdi
0x140004ea5  pop     rbp
0x140004ea6  pop     rbx
0x140004ea7  retn
```
