# HidpGetRetainWWIrpEnabledFromRegistry

- ea: `0x1800419a8`
- end: `0x180041b3d`
- name: `HidpGetRetainWWIrpEnabledFromRegistry`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003a590`

## callees

- `0x18000ddc8`
- `0x1800419a8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180041a64`
- `ntoskrnl!ZwQueryValueKey` at `0x180041a64`
- `ntoskrnl!ZwClose` at `0x180041a9f`
- `ntoskrnl!ZwClose` at `0x180041a9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041a8f`
- `ntoskrnl!ExAllocatePool2` at `0x180041a32`
- `ntoskrnl!ExAllocatePool2` at `0x180041a32`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800419e0`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800419e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041a0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x180041a0f`

## pseudocode

```c
int __fastcall HidpGetRetainWWIrpEnabledFromRegistry(__int64 a1, struct _DEVICE_OBJECT *a2)
{
  char v3; // di
  NTSTATUS v4; // edx
  int v5; // r8d
  unsigned int *Pool2; // rbx
  _UNKNOWN **v7; // rax
  char v9; // [rsp+48h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  ULONG Length; // [rsp+80h] [rbp+20h] BYREF
  void *DeviceRegKey; // [rsp+90h] [rbp+30h] BYREF

  *(_BYTE *)(a1 + 621) = 0;
  DeviceRegKey = 0;
  v3 = 1;
  v4 = IoOpenDeviceRegistryKey(a2, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    v7 = &WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = v4;
      LOBYTE(v4) = v3;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LODWORD(v7) = WPP_RECORDER_AND_TRACE_SF_qL(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v4,
                      v5,
                      *(_QWORD *)(a1 + 704),
                      2,
                      3,
                      13,
                      (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
                      *(_QWORD *)(a1 + 32),
                      v9);
    }
  }
  else
  {
    Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RetainWWIrpWhenDeviceAbsent");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length) >= 0
        && Pool2[3] == 4 )
      {
        *(_BYTE *)(a1 + 621) = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    LODWORD(v7) = ZwClose(DeviceRegKey);
  }
  return (int)v7;
}

```

## disassembly

```asm
0x1800419a8  mov     [rsp-18h+arg_8], rbx
0x1800419ad  push    rbp
0x1800419ae  push    rsi
0x1800419af  push    rdi
0x1800419b0  mov     rbp, rsp
0x1800419b3  sub     rsp, 60h
0x1800419b7  mov     rax, rdx
0x1800419ba  mov     byte ptr [rcx+26Dh], 0
0x1800419c1  mov     rsi, rcx
0x1800419c4  mov     [rbp+DeviceRegKey], 0
0x1800419cc  mov     edi, 1
0x1800419d1  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x1800419d5  mov     edx, edi; DevInstKeyType
0x1800419d7  mov     rcx, rax; DeviceObject
0x1800419da  mov     r8d, 1F0000h; DesiredAccess
0x1800419e0  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800419e7  nop     dword ptr [rax+rax+00h]
0x1800419ec  mov     edx, eax
0x1800419ee  test    eax, eax
0x1800419f0  js      loc_180041AAD
0x1800419f6  xorps   xmm0, xmm0
0x1800419f9  mov     [rbp+arg_0], 0
0x180041a00  lea     rdx, aRetainwwirpwhe; "RetainWWIrpWhenDeviceAbsent"
0x180041a07  lea     rcx, [rbp+DestinationString]; DestinationString
0x180041a0b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180041a0f  call    cs:__imp_RtlInitUnicodeString
0x180041a16  nop     dword ptr [rax+rax+00h]
0x180041a1b  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180041a1f  mov     ecx, 100h
0x180041a24  add     eax, 1Ch
0x180041a27  mov     r8d, 43646948h
0x180041a2d  mov     edx, eax
0x180041a2f  mov     [rbp+arg_0], eax
0x180041a32  call    cs:__imp_ExAllocatePool2
0x180041a39  nop     dword ptr [rax+rax+00h]
0x180041a3e  mov     rbx, rax
0x180041a41  test    rax, rax
0x180041a44  jz      short loc_180041A9B
0x180041a46  mov     ecx, [rbp+arg_0]
0x180041a49  lea     rax, [rbp+arg_0]
0x180041a4d  mov     [rsp+60h+ResultLength], rax; ResultLength
0x180041a52  lea     rdx, [rbp+DestinationString]; ValueName
0x180041a56  mov     [rsp+60h+Length], ecx; Length
0x180041a5a  mov     r9, rbx; KeyValueInformation
0x180041a5d  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x180041a61  mov     r8d, edi; KeyValueInformationClass
0x180041a64  call    cs:__imp_ZwQueryValueKey
0x180041a6b  nop     dword ptr [rax+rax+00h]
0x180041a70  test    eax, eax
0x180041a72  js      short loc_180041A8A
0x180041a74  cmp     dword ptr [rbx+0Ch], 4
0x180041a78  jnz     short loc_180041A8A
0x180041a7a  mov     eax, [rbx+8]
0x180041a7d  cmp     dword ptr [rax+rbx], 0
0x180041a81  setnz   al
0x180041a84  mov     [rsi+26Dh], al
0x180041a8a  xor     edx, edx; Tag
0x180041a8c  mov     rcx, rbx; P
0x180041a8f  call    cs:__imp_ExFreePoolWithTag
0x180041a96  nop     dword ptr [rax+rax+00h]
0x180041a9b  mov     rcx, [rbp+DeviceRegKey]; Handle
0x180041a9f  call    cs:__imp_ZwClose
0x180041aa6  nop     dword ptr [rax+rax+00h]
0x180041aab  jmp     short loc_180041B2C
0x180041aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180041ab4  lea     rax, WPP_GLOBAL_Control
0x180041abb  cmp     rcx, rax
0x180041abe  jz      short loc_180041ACD
0x180041ac0  mov     eax, [rcx+2Ch]
0x180041ac3  test    al, 4
0x180041ac5  jz      short loc_180041ACD
0x180041ac7  cmp     byte ptr [rcx+29h], 2
0x180041acb  jnb     short loc_180041AD0
0x180041acd  xor     dil, dil
0x180041ad0  lea     rax, WPP_RECORDER_INITIALIZED
0x180041ad7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180041ade  setnz   r8b
0x180041ae2  test    dil, dil
0x180041ae5  jnz     short loc_180041AEC
0x180041ae7  test    r8b, r8b
0x180041aea  jz      short loc_180041B2C
0x180041aec  mov     rax, [rsi+20h]
0x180041af0  mov     r9, [rsi+2C0h]
0x180041af7  mov     rcx, [rcx+18h]
0x180041afb  mov     dword ptr [rsp+60h+var_18], edx
0x180041aff  mov     dl, dil
0x180041b02  mov     [rsp+60h+var_20], rax
0x180041b07  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x180041b0e  mov     [rsp+60h+var_28], rax
0x180041b13  mov     [rsp+60h+var_30], 0Dh
0x180041b1a  mov     dword ptr [rsp+60h+ResultLength], 3
0x180041b22  mov     byte ptr [rsp+60h+Length], 2
0x180041b27  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180041b2c  mov     rbx, [rsp+60h+arg_8]
0x180041b34  add     rsp, 60h
0x180041b38  pop     rdi
0x180041b39  pop     rsi
0x180041b3a  pop     rbp
0x180041b3b  retn
```
