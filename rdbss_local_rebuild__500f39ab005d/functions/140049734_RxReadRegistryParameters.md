# RxReadRegistryParameters

- ea: `0x140049734`
- end: `0x14004999a`
- name: `RxReadRegistryParameters`
- size: `614`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140049680`
- `0x14008321c`

## callees

- `0x140025c20`
- `0x140049124`
- `0x140049734`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140049791`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400497fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004985a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400498d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049791`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400497fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004985a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400498d9`
- `ntoskrnl!ZwClose` at `0x1400498b8`
- `ntoskrnl!ZwClose` at `0x14004996d`
- `ntoskrnl!ZwClose` at `0x1400498b8`
- `ntoskrnl!ZwClose` at `0x14004996d`
- `ntoskrnl!ZwOpenKey` at `0x1400497d7`
- `ntoskrnl!ZwOpenKey` at `0x140049920`
- `ntoskrnl!ZwOpenKey` at `0x1400497d7`
- `ntoskrnl!ZwOpenKey` at `0x140049920`
- `ntoskrnl!ZwQueryValueKey` at `0x14004982d`
- `ntoskrnl!ZwQueryValueKey` at `0x14004988c`
- `ntoskrnl!ZwQueryValueKey` at `0x14004982d`
- `ntoskrnl!ZwQueryValueKey` at `0x14004988c`

## string_xrefs

- `0x140049768`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x1400497ef`: `DisableByteRangeLockingOnReadOnlyFiles`
- `0x140049946`: `AllowLowIntegrityNetworkAccess`
- `0x1400498c4`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
int __fastcall RxReadRegistryParameters(char a1)
{
  int result; // eax
  bool v3; // al
  bool v4; // al
  ULONG Length; // [rsp+20h] [rbp-E0h]
  ULONG ResultLength; // [rsp+28h] [rbp-D8h]
  ULONG v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh]
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING ValueName; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v15; // [rsp+A4h] [rbp-5Ch]
  int v16; // [rsp+ACh] [rbp-54h]

  KeyHandle = 0;
  v7 = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( !a1 )
    {
      RtlInitUnicodeString(&ValueName, L"DisableByteRangeLockingOnReadOnlyFiles");
      if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x40u, &v7) >= 0
        && v15 == 4 )
      {
        DisableByteRangeLockingOnReadOnlyFiles = v16 != 0;
      }
    }
    RtlInitUnicodeString(&ValueName, L"DisableTransitiveOplocks");
    v3 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x40u, &v7) >= 0
      && v15 == 4
      && v16 != 0;
    RxDisableTransitiveOplocks = v3;
    ZwClose(KeyHandle);
    Handle = 0;
    RtlInitUnicodeString(&ValueName, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &ValueName;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    if ( result >= 0 )
    {
      v8 = 0;
      v4 = (int)RxGetUlongRegistryParameter(Handle, Length, ResultLength) >= 0 && v8 == 0;
      RxDisallowLowIntegrity = v4;
      return ZwClose(Handle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140049734  mov     [rsp-8+arg_0], rbx
0x140049739  push    rbp
0x14004973a  lea     rbp, [rsp-0F0h]
0x140049742  sub     rsp, 1F0h
0x140049749  mov     rax, cs:__security_cookie
0x140049750  xor     rax, rsp
0x140049753  mov     [rbp+0F0h+var_10], rax
0x14004975a  xorps   xmm0, xmm0
0x14004975d  mov     [rsp+1F0h+KeyHandle], 0
0x140049766  mov     bl, cl
0x140049768  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004976f  xor     eax, eax
0x140049771  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x140049775  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x14004977a  mov     [rsp+1F0h+var_1C0], eax
0x14004977e  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x140049783  movups  xmmword ptr [rsp+1F0h+ValueName.Length], xmm0
0x140049788  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x14004978d  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x140049791  call    cs:__imp_RtlInitUnicodeString
0x140049798  nop     dword ptr [rax+rax+00h]
0x14004979d  lea     rax, [rbp+0F0h+DestinationString]
0x1400497a1  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x1400497a9  xorps   xmm0, xmm0
0x1400497ac  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x1400497b1  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1400497b6  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x1400497bf  mov     edx, 20019h; DesiredAccess
0x1400497c4  mov     [rsp+1F0h+ObjectAttributes.Attributes], 240h
0x1400497cc  lea     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x1400497d1  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400497d7  call    cs:__imp_ZwOpenKey
0x1400497de  nop     dword ptr [rax+rax+00h]
0x1400497e3  test    eax, eax
0x1400497e5  js      loc_140049979
0x1400497eb  test    bl, bl
0x1400497ed  jnz     short loc_14004984E
0x1400497ef  lea     rdx, aDisablebyteran; "DisableByteRangeLockingOnReadOnlyFiles"
0x1400497f6  lea     rcx, [rsp+1F0h+ValueName]; DestinationString
0x1400497fb  call    cs:__imp_RtlInitUnicodeString
0x140049802  nop     dword ptr [rax+rax+00h]
0x140049807  mov     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x14004980c  lea     rax, [rsp+1F0h+var_1C0]
0x140049811  mov     [rsp+1F0h+ResultLength], rax; ResultLength
0x140049816  lea     r9, [rbp+0F0h+KeyValueInformation]; KeyValueInformation
0x14004981a  mov     r8d, 2; KeyValueInformationClass
0x140049820  mov     [rsp+1F0h+Length], 40h ; '@'; Length
0x140049828  lea     rdx, [rsp+1F0h+ValueName]; ValueName
0x14004982d  call    cs:__imp_ZwQueryValueKey
0x140049834  nop     dword ptr [rax+rax+00h]
0x140049839  test    eax, eax
0x14004983b  js      short loc_14004984E
0x14004983d  cmp     [rbp+0F0h+var_14C], 4
0x140049841  jnz     short loc_14004984E
0x140049843  cmp     [rbp+0F0h+var_144], 0
0x140049847  setnz   cs:DisableByteRangeLockingOnReadOnlyFiles
0x14004984e  lea     rdx, aDisabletransit; "DisableTransitiveOplocks"
0x140049855  lea     rcx, [rsp+1F0h+ValueName]; DestinationString
0x14004985a  call    cs:__imp_RtlInitUnicodeString
0x140049861  nop     dword ptr [rax+rax+00h]
0x140049866  mov     rcx, [rsp+1F0h+KeyHandle]; KeyHandle
0x14004986b  lea     rax, [rsp+1F0h+var_1C0]
0x140049870  mov     [rsp+1F0h+ResultLength], rax; ULONG
0x140049875  lea     r9, [rbp+0F0h+KeyValueInformation]; KeyValueInformation
0x140049879  mov     r8d, 2; KeyValueInformationClass
0x14004987f  mov     [rsp+1F0h+Length], 40h ; '@'; int
0x140049887  lea     rdx, [rsp+1F0h+ValueName]; ValueName
0x14004988c  call    cs:__imp_ZwQueryValueKey
0x140049893  nop     dword ptr [rax+rax+00h]
0x140049898  test    eax, eax
0x14004989a  js      short loc_1400498AB
0x14004989c  cmp     [rbp+0F0h+var_14C], 4
0x1400498a0  jnz     short loc_1400498AB
0x1400498a2  cmp     [rbp+0F0h+var_144], 0
0x1400498a6  setnz   al
0x1400498a9  jmp     short loc_1400498AD
0x1400498ab  xor     al, al
0x1400498ad  mov     rcx, [rsp+1F0h+KeyHandle]; Handle
0x1400498b2  mov     cs:RxDisableTransitiveOplocks, al
0x1400498b8  call    cs:__imp_ZwClose
0x1400498bf  nop     dword ptr [rax+rax+00h]
0x1400498c4  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400498cb  mov     [rsp+1F0h+Handle], 0
0x1400498d4  lea     rcx, [rsp+1F0h+ValueName]; DestinationString
0x1400498d9  call    cs:__imp_RtlInitUnicodeString
0x1400498e0  nop     dword ptr [rax+rax+00h]
0x1400498e5  lea     rax, [rsp+1F0h+ValueName]
0x1400498ea  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x1400498f2  xorps   xmm0, xmm0
0x1400498f5  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x1400498fa  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1400498ff  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x140049908  mov     edx, 20019h; DesiredAccess
0x14004990d  mov     [rsp+1F0h+ObjectAttributes.Attributes], 240h
0x140049915  lea     rcx, [rsp+1F0h+Handle]; KeyHandle
0x14004991a  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140049920  call    cs:__imp_ZwOpenKey
0x140049927  nop     dword ptr [rax+rax+00h]
0x14004992c  test    eax, eax
0x14004992e  js      short loc_140049979
0x140049930  mov     rcx, [rsp+1F0h+Handle]; KeyHandle
0x140049935  lea     r9, [rbp+0F0h+var_110]
0x140049939  lea     r8, [rsp+1F0h+var_1BC]
0x14004993e  mov     [rsp+1F0h+var_1BC], 0
0x140049946  lea     rdx, aAllowlowintegr; "AllowLowIntegrityNetworkAccess"
0x14004994d  call    RxGetUlongRegistryParameter
0x140049952  test    eax, eax
0x140049954  js      short loc_140049960
0x140049956  cmp     [rsp+1F0h+var_1BC], 0
0x14004995b  setz    al
0x14004995e  jmp     short loc_140049962
0x140049960  xor     al, al
0x140049962  mov     rcx, [rsp+1F0h+Handle]; Handle
0x140049967  mov     cs:RxDisallowLowIntegrity, al
0x14004996d  call    cs:__imp_ZwClose
0x140049974  nop     dword ptr [rax+rax+00h]
0x140049979  mov     rcx, [rbp+0F0h+var_10]
0x140049980  xor     rcx, rsp; StackCookie
0x140049983  call    __security_check_cookie
0x140049988  mov     rbx, [rsp+1F0h+arg_0]
0x140049990  add     rsp, 1F0h
0x140049997  pop     rbp
0x140049998  retn
```
