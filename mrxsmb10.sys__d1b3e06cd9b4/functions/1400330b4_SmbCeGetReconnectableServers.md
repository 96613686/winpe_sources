# SmbCeGetReconnectableServers

- ea: `0x1400330b4`
- end: `0x140033306`
- name: `SmbCeGetReconnectableServers`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14003108c`

## callees

- `0x14000dfa8`
- `0x140016560`
- `0x140031adc`
- `0x1400330b4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140033152`
- `ntoskrnl!ZwOpenKey` at `0x140033152`
- `ntoskrnl!ZwClose` at `0x1400332d6`
- `ntoskrnl!ZwClose` at `0x1400332d6`
- `ntoskrnl!ZwQueryValueKey` at `0x1400331a0`
- `ntoskrnl!ZwQueryValueKey` at `0x140033215`
- `ntoskrnl!ZwQueryValueKey` at `0x1400331a0`
- `ntoskrnl!ZwQueryValueKey` at `0x140033215`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033113`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033171`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033113`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033171`
- `ntoskrnl!ExAllocatePool2` at `0x1400331e3`
- `ntoskrnl!ExAllocatePool2` at `0x1400331e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003328d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003328d`

## string_xrefs

- `0x1400330f1`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`

## pseudocode

```c
NTSTATUS SmbCeGetReconnectableServers()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  int UlongRegistryParameter; // ebx
  ULONG Length; // edi
  __int64 Pool2; // rbx
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  int v6; // [rsp+34h] [rbp-15h]
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp+37h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  v6 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ReconnectableServers");
    v1 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x10u,
           &ResultLength);
    UlongRegistryParameter = 0;
    if ( v1 != -2147483643 )
      UlongRegistryParameter = v1;
    if ( UlongRegistryParameter >= 0 )
    {
      Length = DWORD2(KeyValueInformation) + 16;
      if ( (unsigned int)(DWORD2(KeyValueInformation) + 16) <= 0xFFFF
        && (Pool2 = ExAllocatePool2(258, Length, 1934454099)) != 0 )
      {
        if ( ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               (PVOID)Pool2,
               Length,
               &ResultLength) >= 0
          && *(_DWORD *)(Pool2 + 4) == 7 )
        {
          if ( *(_DWORD *)(Pool2 + 8) )
          {
            stru_140020320.Length = *(_WORD *)(Pool2 + 8);
            stru_140020320.MaximumLength = stru_140020320.Length;
            stru_140020320.Buffer = (PWSTR)(Pool2 + 12);
            byte_140020330 = 0;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
          }
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
        UlongRegistryParameter = MRxSmbGetUlongRegistryParameter(KeyHandle);
        if ( UlongRegistryParameter < 0 )
          qword_140020338 = 600000000;
        else
          qword_140020338 = 10000000LL * v6;
      }
      else
      {
        UlongRegistryParameter = -1073741670;
      }
    }
    ZwClose(KeyHandle);
    return UlongRegistryParameter;
  }
  return result;
}

```

## disassembly

```asm
0x1400330b4  mov     [rsp-8+arg_0], rbx
0x1400330b9  mov     [rsp-8+arg_8], rdi
0x1400330be  push    rbp
0x1400330bf  lea     rbp, [rsp-57h]
0x1400330c4  sub     rsp, 0A0h
0x1400330cb  mov     rax, cs:__security_cookie
0x1400330d2  xor     rax, rsp
0x1400330d5  mov     [rbp+57h+var_10], rax
0x1400330d9  xorps   xmm0, xmm0
0x1400330dc  mov     [rbp+57h+KeyHandle], 0
0x1400330e4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400330e8  xor     eax, eax
0x1400330ea  mov     [rbp+57h+var_70], 0
0x1400330f1  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400330f8  mov     [rbp+57h+var_6C], 0
0x1400330ff  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140033103  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140033107  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003310b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14003310f  movups  [rbp+57h+KeyValueInformation], xmm0
0x140033113  call    cs:__imp_RtlInitUnicodeString
0x14003311a  nop     dword ptr [rax+rax+00h]
0x14003311f  lea     rax, [rbp+57h+DestinationString]
0x140033123  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14003312a  xorps   xmm0, xmm0
0x14003312d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140033131  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140033135  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14003313d  mov     edx, 20019h; DesiredAccess
0x140033142  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140033149  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14003314d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140033152  call    cs:__imp_ZwOpenKey
0x140033159  nop     dword ptr [rax+rax+00h]
0x14003315e  test    eax, eax
0x140033160  js      loc_1400332E4
0x140033166  lea     rdx, aReconnectables; "ReconnectableServers"
0x14003316d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140033171  call    cs:__imp_RtlInitUnicodeString
0x140033178  nop     dword ptr [rax+rax+00h]
0x14003317d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140033181  lea     rax, [rbp+57h+var_70]
0x140033185  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14003318a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14003318e  mov     r8d, 2; KeyValueInformationClass
0x140033194  mov     [rsp+0A0h+Length], 10h; Length
0x14003319c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400331a0  call    cs:__imp_ZwQueryValueKey
0x1400331a7  nop     dword ptr [rax+rax+00h]
0x1400331ac  xor     ebx, ebx
0x1400331ae  cmp     eax, 80000005h
0x1400331b3  cmovnz  ebx, eax
0x1400331b6  test    ebx, ebx
0x1400331b8  js      loc_1400332D2
0x1400331be  mov     edi, dword ptr [rbp+57h+KeyValueInformation+8]
0x1400331c1  add     edi, 10h
0x1400331c4  cmp     edi, 0FFFFh
0x1400331ca  jbe     short loc_1400331D6
0x1400331cc  mov     ebx, 0C000009Ah
0x1400331d1  jmp     loc_1400332D2
0x1400331d6  mov     edx, edi
0x1400331d8  mov     ecx, 102h
0x1400331dd  mov     r8d, 734D6D53h
0x1400331e3  call    cs:__imp_ExAllocatePool2
0x1400331ea  nop     dword ptr [rax+rax+00h]
0x1400331ef  mov     rbx, rax
0x1400331f2  test    rax, rax
0x1400331f5  jz      short loc_1400331CC
0x1400331f7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400331fb  lea     rax, [rbp+57h+var_70]
0x1400331ff  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x140033204  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140033208  mov     r9, rbx; KeyValueInformation
0x14003320b  mov     [rsp+0A0h+Length], edi; Length
0x14003320f  mov     r8d, 2; KeyValueInformationClass
0x140033215  call    cs:__imp_ZwQueryValueKey
0x14003321c  nop     dword ptr [rax+rax+00h]
0x140033221  test    eax, eax
0x140033223  js      short loc_140033257
0x140033225  cmp     dword ptr [rbx+4], 7
0x140033229  jnz     short loc_140033257
0x14003322b  cmp     dword ptr [rbx+8], 0
0x14003322f  jbe     short loc_140033299
0x140033231  movzx   eax, word ptr [rbx+8]
0x140033235  mov     cs:stru_140020320.Length, ax
0x14003323c  mov     cs:stru_140020320.MaximumLength, ax
0x140033243  lea     rax, [rbx+0Ch]
0x140033247  mov     cs:stru_140020320.Buffer, rax
0x14003324e  mov     cs:byte_140020330, 0
0x140033255  jmp     short loc_140033299
0x140033257  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003325e  lea     rax, WPP_GLOBAL_Control
0x140033265  cmp     rcx, rax
0x140033268  jz      short loc_140033288
0x14003326a  test    dword ptr [rcx+2Ch], 200h
0x140033271  jz      short loc_140033288
0x140033273  mov     rcx, [rcx+18h]
0x140033277  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x14003327e  mov     edx, 15h
0x140033283  call    WPP_SF_
0x140033288  xor     edx, edx; Tag
0x14003328a  mov     rcx, rbx; P
0x14003328d  call    cs:__imp_ExFreePoolWithTag
0x140033294  nop     dword ptr [rax+rax+00h]
0x140033299  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14003329d  lea     r8, [rbp+57h+var_6C]
0x1400332a1  lea     rdx, aReconnecttimeo; "ReconnectTimeout"
0x1400332a8  call    MRxSmbGetUlongRegistryParameter
0x1400332ad  mov     ebx, eax
0x1400332af  test    eax, eax
0x1400332b1  js      short loc_1400332C7
0x1400332b3  movsxd  rcx, [rbp+57h+var_6C]
0x1400332b7  imul    rdx, rcx, 989680h
0x1400332be  mov     cs:qword_140020338, rdx
0x1400332c5  jmp     short loc_1400332D2
0x1400332c7  mov     cs:qword_140020338, 23C34600h
0x1400332d2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400332d6  call    cs:__imp_ZwClose
0x1400332dd  nop     dword ptr [rax+rax+00h]
0x1400332e2  mov     eax, ebx
0x1400332e4  mov     rcx, [rbp+57h+var_10]
0x1400332e8  xor     rcx, rsp; StackCookie
0x1400332eb  call    __security_check_cookie
0x1400332f0  lea     r11, [rsp+0A0h+var_s0]
0x1400332f8  mov     rbx, [r11+10h]
0x1400332fc  mov     rdi, [r11+18h]
0x140033300  mov     rsp, r11
0x140033303  pop     rbp
0x140033304  retn
```
