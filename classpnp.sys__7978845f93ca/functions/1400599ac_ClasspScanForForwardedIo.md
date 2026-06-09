# ClasspScanForForwardedIo

- ea: `0x1400599ac`
- end: `0x140059af6`
- name: `ClasspScanForForwardedIo`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400579b4`

## callees

- `0x14003e430`
- `0x1400599ac`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140059ab7`
- `ntoskrnl!ObfDereferenceObject` at `0x140059ace`
- `ntoskrnl!ObfDereferenceObject` at `0x140059ab7`
- `ntoskrnl!ObfDereferenceObject` at `0x140059ace`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400599ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400599ed`
- `ntoskrnl!ZwClose` at `0x140059a8d`
- `ntoskrnl!ZwClose` at `0x140059a8d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140059a2d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140059a2d`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x140059aa1`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x140059aa1`
- `ntoskrnl!ObfReferenceObject` at `0x140059a00`
- `ntoskrnl!ObfReferenceObject` at `0x140059a00`
- `ntoskrnl!ZwQueryValueKey` at `0x140059a64`
- `ntoskrnl!ZwQueryValueKey` at `0x140059a64`

## pseudocode

```c
char __fastcall ClasspScanForForwardedIo(__int64 a1)
{
  char v2; // di
  struct _DEVICE_OBJECT *v3; // rbx
  PDEVICE_OBJECT LowerDeviceObject; // rsi
  ULONG ResultLength; // [rsp+30h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-28h] BYREF
  int v10; // [rsp+54h] [rbp-24h]
  int v11; // [rsp+58h] [rbp-20h]
  char v12; // [rsp+5Ch] [rbp-1Ch]

  KeyHandle = 0;
  ResultLength = 0;
  v2 = 1;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"StorageSupportedFeatures");
  v3 = *(struct _DEVICE_OBJECT **)(a1 + 16);
  ObfReferenceObject(v3);
  while ( v3 )
  {
    if ( (int)IoOpenDriverRegistryKey(v3->DriverObject, 0, 131097, 0, &KeyHandle) < 0 )
    {
      ObfDereferenceObject(v3);
      return 0;
    }
    if ( ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x10u,
           &ResultLength) < 0
      || v10 != 4
      || v11 != 4
      || (v12 & 2) == 0 )
    {
      v2 = 0;
    }
    ZwClose(KeyHandle);
    if ( v2 )
      LowerDeviceObject = IoGetLowerDeviceObject(v3);
    else
      LowerDeviceObject = 0;
    ObfDereferenceObject(v3);
    v3 = LowerDeviceObject;
  }
  return v2;
}

```

## disassembly

```asm
0x1400599ac  push    rbp
0x1400599ae  push    rbx
0x1400599af  push    rsi
0x1400599b0  push    rdi
0x1400599b1  mov     rbp, rsp
0x1400599b4  sub     rsp, 78h
0x1400599b8  mov     rax, cs:__security_cookie
0x1400599bf  xor     rax, rsp
0x1400599c2  mov     [rbp+var_18], rax
0x1400599c6  mov     rbx, rcx
0x1400599c9  mov     [rbp+KeyHandle], 0
0x1400599d1  xorps   xmm0, xmm0
0x1400599d4  mov     [rbp+var_48], 0
0x1400599db  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400599df  mov     dil, 1
0x1400599e2  lea     rdx, aStoragesupport; "StorageSupportedFeatures"
0x1400599e9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400599ed  call    cs:__imp_RtlInitUnicodeString
0x1400599f4  nop     dword ptr [rax+rax+00h]
0x1400599f9  mov     rbx, [rbx+10h]
0x1400599fd  mov     rcx, rbx; Object
0x140059a00  call    cs:__imp_ObfReferenceObject
0x140059a07  nop     dword ptr [rax+rax+00h]
0x140059a0c  test    rbx, rbx
0x140059a0f  jz      loc_140059ADD
0x140059a15  mov     rcx, [rbx+8]
0x140059a19  lea     rax, [rbp+KeyHandle]
0x140059a1d  xor     r9d, r9d
0x140059a20  mov     qword ptr [rsp+78h+Length], rax
0x140059a25  xor     edx, edx
0x140059a27  mov     r8d, 20019h
0x140059a2d  call    cs:__imp_IoOpenDriverRegistryKey
0x140059a34  nop     dword ptr [rax+rax+00h]
0x140059a39  test    eax, eax
0x140059a3b  js      loc_140059ACB
0x140059a41  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140059a45  lea     rax, [rbp+var_48]
0x140059a49  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140059a4e  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x140059a52  mov     r8d, 2; KeyValueInformationClass
0x140059a58  mov     [rsp+78h+Length], 10h; Length
0x140059a60  lea     rdx, [rbp+DestinationString]; ValueName
0x140059a64  call    cs:__imp_ZwQueryValueKey
0x140059a6b  nop     dword ptr [rax+rax+00h]
0x140059a70  test    eax, eax
0x140059a72  js      short loc_140059A86
0x140059a74  cmp     [rbp+var_24], 4
0x140059a78  jnz     short loc_140059A86
0x140059a7a  cmp     [rbp+var_20], 4
0x140059a7e  jnz     short loc_140059A86
0x140059a80  test    [rbp+var_1C], 2
0x140059a84  jnz     short loc_140059A89
0x140059a86  xor     dil, dil
0x140059a89  mov     rcx, [rbp+KeyHandle]; Handle
0x140059a8d  call    cs:__imp_ZwClose
0x140059a94  nop     dword ptr [rax+rax+00h]
0x140059a99  test    dil, dil
0x140059a9c  jz      short loc_140059AB2
0x140059a9e  mov     rcx, rbx; DeviceObject
0x140059aa1  call    cs:__imp_IoGetLowerDeviceObject
0x140059aa8  nop     dword ptr [rax+rax+00h]
0x140059aad  mov     rsi, rax
0x140059ab0  jmp     short loc_140059AB4
0x140059ab2  xor     esi, esi
0x140059ab4  mov     rcx, rbx; Object
0x140059ab7  call    cs:__imp_ObfDereferenceObject
0x140059abe  nop     dword ptr [rax+rax+00h]
0x140059ac3  mov     rbx, rsi
0x140059ac6  jmp     loc_140059A0C
0x140059acb  mov     rcx, rbx; Object
0x140059ace  call    cs:__imp_ObfDereferenceObject
0x140059ad5  nop     dword ptr [rax+rax+00h]
0x140059ada  xor     dil, dil
0x140059add  mov     al, dil
0x140059ae0  mov     rcx, [rbp+var_18]
0x140059ae4  xor     rcx, rsp; StackCookie
0x140059ae7  call    __security_check_cookie
0x140059aec  add     rsp, 78h
0x140059af0  pop     rdi
0x140059af1  pop     rsi
0x140059af2  pop     rbx
0x140059af3  pop     rbp
0x140059af4  retn
```
