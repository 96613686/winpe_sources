# HidpGetWinRtInterfaceRestrictionLevel

- ea: `0x180042530`
- end: `0x1800426df`
- name: `HidpGetWinRtInterfaceRestrictionLevel`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180042f24`

## callees

- `0x180013860`
- `0x180042530`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180042684`
- `ntoskrnl!ZwQueryValueKey` at `0x180042684`
- `ntoskrnl!ZwClose` at `0x1800426c2`
- `ntoskrnl!ZwClose` at `0x1800426c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800426b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800426b2`
- `ntoskrnl!ExAllocatePool2` at `0x180042652`
- `ntoskrnl!ExAllocatePool2` at `0x180042652`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180042563`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x180042563`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004262f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18004262f`

## pseudocode

```c
int __fastcall HidpGetWinRtInterfaceRestrictionLevel(__int64 a1)
{
  __int64 v1; // rbx
  char v3; // di
  int result; // eax
  int v5; // edx
  int v6; // r8d
  unsigned int *Pool2; // rbx
  int v8; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG Length; // [rsp+90h] [rbp+20h] BYREF
  void *DeviceRegKey; // [rsp+98h] [rbp+28h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  DeviceRegKey = 0;
  v3 = 1;
  result = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 48), 1u, 0x1F0000u, &DeviceRegKey);
  if ( result >= 0 )
  {
    Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"WinRtInterfaceRestrictionLevel");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length) >= 0
        && Pool2[3] == 4 )
      {
        v8 = 0;
        if ( *(unsigned int *)((char *)Pool2 + Pool2[2]) <= 1 )
          v8 = *(unsigned int *)((char *)Pool2 + Pool2[2]);
        *(_DWORD *)(a1 + 344) = v8;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    return ZwClose(DeviceRegKey);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v3;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      return WPP_RECORDER_AND_TRACE_SF_qdqL(
               WPP_GLOBAL_Control->AttachedDevice,
               v5,
               v6,
               *(_QWORD *)(v1 + 704),
               2,
               3,
               27,
               (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
               *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL),
               *(_DWORD *)(a1 + 8),
               *(_QWORD *)(a1 + 48),
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180042530  mov     [rsp-18h+arg_10], rbx
0x180042535  push    rbp
0x180042536  push    rsi
0x180042537  push    rdi
0x180042538  mov     rbp, rsp
0x18004253b  sub     rsp, 70h
0x18004253f  mov     rbx, [rcx+40h]
0x180042543  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x180042547  mov     rsi, rcx
0x18004254a  mov     [rbp+DeviceRegKey], 0
0x180042552  mov     rcx, [rcx+30h]; DeviceObject
0x180042556  mov     edi, 1
0x18004255b  mov     edx, edi; DevInstKeyType
0x18004255d  mov     r8d, 1F0000h; DesiredAccess
0x180042563  call    cs:__imp_IoOpenDeviceRegistryKey
0x18004256a  nop     dword ptr [rax+rax+00h]
0x18004256f  test    eax, eax
0x180042571  jns     loc_180042616
0x180042577  mov     r11, cs:WPP_GLOBAL_Control
0x18004257e  lea     rcx, WPP_GLOBAL_Control
0x180042585  cmp     r11, rcx
0x180042588  jz      short loc_18004259A
0x18004258a  mov     ecx, [r11+2Ch]
0x18004258e  test    cl, 4
0x180042591  jz      short loc_18004259A
0x180042593  cmp     byte ptr [r11+29h], 2
0x180042598  jnb     short loc_18004259D
0x18004259a  xor     dil, dil
0x18004259d  lea     rcx, WPP_RECORDER_INITIALIZED
0x1800425a4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1800425ab  setnz   r8b
0x1800425af  test    dil, dil
0x1800425b2  jnz     short loc_1800425BD
0x1800425b4  test    r8b, r8b
0x1800425b7  jz      loc_1800426CE
0x1800425bd  mov     r10, [rsi+40h]
0x1800425c1  mov     dl, dil
0x1800425c4  mov     r9, [rbx+2C0h]
0x1800425cb  mov     rcx, [r11+18h]
0x1800425cf  mov     [rsp+70h+var_18], eax
0x1800425d3  mov     rax, [rsi+30h]
0x1800425d7  mov     [rsp+70h+var_20], rax
0x1800425dc  mov     eax, [rsi+8]
0x1800425df  mov     [rsp+70h+var_28], eax
0x1800425e3  mov     rax, [r10+20h]
0x1800425e7  mov     [rsp+70h+var_30], rax
0x1800425ec  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x1800425f3  mov     [rsp+70h+var_38], rax
0x1800425f8  mov     [rsp+70h+var_40], 1Bh
0x1800425ff  mov     dword ptr [rsp+70h+ResultLength], 3
0x180042607  mov     byte ptr [rsp+70h+Length], 2
0x18004260c  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x180042611  jmp     loc_1800426CE
0x180042616  xorps   xmm0, xmm0
0x180042619  mov     [rbp+arg_0], 0
0x180042620  lea     rdx, aWinrtinterface; "WinRtInterfaceRestrictionLevel"
0x180042627  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004262b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004262f  call    cs:__imp_RtlInitUnicodeString
0x180042636  nop     dword ptr [rax+rax+00h]
0x18004263b  movzx   eax, [rbp+DestinationString.MaximumLength]
0x18004263f  mov     ecx, 100h
0x180042644  add     eax, 1Ch
0x180042647  mov     r8d, 43646948h
0x18004264d  mov     edx, eax
0x18004264f  mov     [rbp+arg_0], eax
0x180042652  call    cs:__imp_ExAllocatePool2
0x180042659  nop     dword ptr [rax+rax+00h]
0x18004265e  mov     rbx, rax
0x180042661  test    rax, rax
0x180042664  jz      short loc_1800426BE
0x180042666  mov     ecx, [rbp+arg_0]
0x180042669  lea     rax, [rbp+arg_0]
0x18004266d  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180042672  lea     rdx, [rbp+DestinationString]; ValueName
0x180042676  mov     [rsp+70h+Length], ecx; Length
0x18004267a  mov     r9, rbx; KeyValueInformation
0x18004267d  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180042681  mov     r8d, edi; KeyValueInformationClass
0x180042684  call    cs:__imp_ZwQueryValueKey
0x18004268b  nop     dword ptr [rax+rax+00h]
0x180042690  test    eax, eax
0x180042692  js      short loc_1800426AD
0x180042694  cmp     dword ptr [rbx+0Ch], 4
0x180042698  jnz     short loc_1800426AD
0x18004269a  mov     eax, [rbx+8]
0x18004269d  mov     ecx, [rax+rbx]
0x1800426a0  xor     eax, eax
0x1800426a2  cmp     ecx, edi
0x1800426a4  cmovbe  eax, ecx
0x1800426a7  mov     [rsi+158h], eax
0x1800426ad  xor     edx, edx; Tag
0x1800426af  mov     rcx, rbx; P
0x1800426b2  call    cs:__imp_ExFreePoolWithTag
0x1800426b9  nop     dword ptr [rax+rax+00h]
0x1800426be  mov     rcx, [rbp+DeviceRegKey]; Handle
0x1800426c2  call    cs:__imp_ZwClose
0x1800426c9  nop     dword ptr [rax+rax+00h]
0x1800426ce  mov     rbx, [rsp+70h+arg_10]
0x1800426d6  add     rsp, 70h
0x1800426da  pop     rdi
0x1800426db  pop     rsi
0x1800426dc  pop     rbp
0x1800426dd  retn
```
