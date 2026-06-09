# ClasspInitializeHotplugInfo

- ea: `0x1400597c0`
- end: `0x1400598e9`
- name: `ClasspInitializeHotplugInfo`
- size: `297`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1400579b4`

## callees

- `0x1400597c0`
- `0x14005f690`

## import_xrefs

- `ntoskrnl!IoGetDeviceProperty` at `0x140059844`
- `ntoskrnl!IoGetDeviceProperty` at `0x140059844`

## string_xrefs

- `0x1400598ab`: `WriteCacheEnableOverride`

## pseudocode

```c
NTSTATUS __fastcall ClasspInitializeHotplugInfo(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)
{
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rdi
  NTSTATUS result; // eax
  ULONG v4; // ecx
  ULONG PropertyBuffer; // [rsp+50h] [rbp+20h] BYREF
  ULONG v6; // [rsp+58h] [rbp+28h] BYREF
  ULONG ResultLength; // [rsp+60h] [rbp+30h] BYREF
  ULONG ParameterValue; // [rsp+68h] [rbp+38h] BYREF

  PrivateFdoData = FdoExtension->PrivateFdoData;
  PropertyBuffer = 0;
  ResultLength = 0;
  v6 = 0;
  PrivateFdoData->HotplugInfo = 0;
  PrivateFdoData->HotplugInfo.Size = 8;
  PrivateFdoData->HotplugInfo.MediaRemovable = FdoExtension->DeviceDescriptor->RemovableMedia != 0;
  PrivateFdoData->HotplugInfo.MediaHotplug = FdoExtension->PrivateFdoData->HackFlags & 1;
  result = IoGetDeviceProperty(FdoExtension->LowerPdo, DevicePropertyRemovalPolicy, 4u, &PropertyBuffer, &ResultLength);
  if ( result >= 0 )
  {
    if ( ResultLength == 4 )
    {
      v4 = PropertyBuffer;
      if ( PropertyBuffer - 2 <= 1 )
      {
        ParameterValue = 0;
        ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"UserRemovalPolicy", &ParameterValue);
        v4 = ParameterValue;
        if ( ParameterValue - 2 > 1 )
          v4 = PropertyBuffer;
        else
          PropertyBuffer = ParameterValue;
      }
      PrivateFdoData->HotplugInfo.DeviceHotplug = v4 == 3;
      v6 = 0;
      ClassGetDeviceParameter(FdoExtension, (PWSTR)L"Classpnp", (PWSTR)L"WriteCacheEnableOverride", &v6);
      PrivateFdoData->HotplugInfo.WriteCacheEnableOverride = v6 != 0;
      return 0;
    }
    else
    {
      return -1073741823;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400597c0  push    rbp
0x1400597c2  push    rbx
0x1400597c3  push    rdi
0x1400597c4  mov     rbp, rsp
0x1400597c7  sub     rsp, 30h
0x1400597cb  mov     rdi, [rcx+478h]
0x1400597d2  lea     r9, [rbp+PropertyBuffer]; PropertyBuffer
0x1400597d6  xor     eax, eax
0x1400597d8  mov     [rbp+PropertyBuffer], 0
0x1400597df  mov     [rbp+arg_10], 0
0x1400597e6  mov     rbx, rcx
0x1400597e9  mov     [rbp+arg_8], 0
0x1400597f0  mov     edx, 13h; DeviceProperty
0x1400597f5  mov     [rdi+530h], rax
0x1400597fc  mov     dword ptr [rdi+530h], 8
0x140059806  mov     rax, [rcx+208h]
0x14005980d  lea     r8d, [rdx-0Fh]; BufferLength
0x140059811  cmp     byte ptr [rax+0Ah], 0
0x140059815  setnz   al
0x140059818  mov     [rdi+534h], al
0x14005981e  mov     rax, [rcx+478h]
0x140059825  mov     cl, [rax+528h]
0x14005982b  lea     rax, [rbp+arg_10]
0x14005982f  and     cl, 1
0x140059832  mov     [rsp+30h+ResultLength], rax; ResultLength
0x140059837  mov     [rdi+535h], cl
0x14005983d  mov     rcx, [rbx+200h]; DeviceObject
0x140059844  call    cs:__imp_IoGetDeviceProperty
0x14005984b  nop     dword ptr [rax+rax+00h]
0x140059850  test    eax, eax
0x140059852  js      loc_1400598E0
0x140059858  cmp     [rbp+arg_10], 4
0x14005985c  jz      short loc_140059865
0x14005985e  mov     eax, 0C0000001h
0x140059863  jmp     short loc_1400598E0
0x140059865  mov     ecx, [rbp+PropertyBuffer]
0x140059868  lea     eax, [rcx-2]
0x14005986b  cmp     eax, 1
0x14005986e  ja      short loc_1400598A4
0x140059870  lea     r9, [rbp+ParameterValue]; ParameterValue
0x140059874  mov     [rbp+ParameterValue], 0
0x14005987b  lea     r8, aUserremovalpol; "UserRemovalPolicy"
0x140059882  mov     rcx, rbx; FdoExtension
0x140059885  lea     rdx, SubkeyName; "Classpnp"
0x14005988c  call    ClassGetDeviceParameter
0x140059891  mov     ecx, [rbp+ParameterValue]
0x140059894  lea     eax, [rcx-2]
0x140059897  cmp     eax, 1
0x14005989a  ja      short loc_1400598A1
0x14005989c  mov     [rbp+PropertyBuffer], ecx
0x14005989f  jmp     short loc_1400598A4
0x1400598a1  mov     ecx, [rbp+PropertyBuffer]
0x1400598a4  cmp     ecx, 3
0x1400598a7  lea     r9, [rbp+arg_8]; ParameterValue
0x1400598ab  lea     r8, aWritecacheenab; "WriteCacheEnableOverride"
0x1400598b2  mov     rcx, rbx; FdoExtension
0x1400598b5  setz    al
0x1400598b8  lea     rdx, SubkeyName; "Classpnp"
0x1400598bf  mov     [rdi+536h], al
0x1400598c5  mov     [rbp+arg_8], 0
0x1400598cc  call    ClassGetDeviceParameter
0x1400598d1  cmp     [rbp+arg_8], 0
0x1400598d5  setnz   al
0x1400598d8  mov     [rdi+537h], al
0x1400598de  xor     eax, eax
0x1400598e0  add     rsp, 30h
0x1400598e4  pop     rdi
0x1400598e5  pop     rbx
0x1400598e6  pop     rbp
0x1400598e7  retn
```
