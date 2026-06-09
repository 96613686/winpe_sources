# CscIsOSSetupRunning

- ea: `0x14009055c`
- end: `0x1400906a3`
- name: `CscIsOSSetupRunning`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, installer_update`

## callers

- `0x140090740`

## callees

- `0x14002f010`
- `0x14002f440`
- `0x14009055c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140090677`
- `ntoskrnl!ZwClose` at `0x140090677`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400905c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140090620`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400905c4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140090620`
- `ntoskrnl!ZwQueryValueKey` at `0x14009064f`
- `ntoskrnl!ZwQueryValueKey` at `0x14009064f`
- `ntoskrnl!ZwOpenKey` at `0x140090605`
- `ntoskrnl!ZwOpenKey` at `0x140090605`

## string_xrefs

- `0x1400905b4`: `\Registry\Machine\System\Setup`

## pseudocode

```c
bool CscIsOSSetupRunning()
{
  bool v0; // bl
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-80h] BYREF
  _DWORD KeyValueInformation[32]; // [rsp+90h] [rbp-70h] BYREF

  v0 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  ResultLength = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\Setup");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"SystemSetupInProgress");
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x80u, &ResultLength) >= 0
      && KeyValueInformation[1] == 4
      && KeyValueInformation[2] == 4 )
    {
      v0 = KeyValueInformation[3] == 1;
    }
    ZwClose(KeyHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x14009055c  mov     [rsp-8+arg_0], rbx
0x140090561  push    rbp
0x140090562  lea     rbp, [rsp-20h]
0x140090567  sub     rsp, 120h
0x14009056e  mov     rax, cs:__security_cookie
0x140090575  xor     rax, rsp
0x140090578  mov     [rbp+20h+var_10], rax
0x14009057c  xorps   xmm0, xmm0
0x14009057f  lea     rcx, [rbp+20h+KeyValueInformation]; void *
0x140090583  xorps   xmm1, xmm1
0x140090586  xor     ebx, ebx
0x140090588  movups  xmmword ptr [rsp+120h+ObjectAttributes.ObjectName], xmm0
0x14009058d  xor     eax, eax
0x14009058f  mov     [rsp+120h+KeyHandle], rbx
0x140090594  xor     edx, edx; Val
0x140090596  mov     r8d, 80h; Size
0x14009059c  movups  xmmword ptr [rsp+120h+ObjectAttributes+1Ch], xmm0
0x1400905a1  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1400905a6  movups  xmmword ptr [rbp+20h+ValueName.Length], xmm1
0x1400905aa  movups  xmmword ptr [rsp+120h+ObjectAttributes.Length], xmm0
0x1400905af  call    memset
0x1400905b4  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\Setup"
0x1400905bb  mov     [rsp+120h+var_F0], ebx
0x1400905bf  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1400905c4  call    cs:__imp_RtlInitUnicodeString
0x1400905cb  nop     dword ptr [rax+rax+00h]
0x1400905d0  lea     rax, [rsp+120h+DestinationString]
0x1400905d5  mov     [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x1400905dd  xorps   xmm0, xmm0
0x1400905e0  mov     [rsp+120h+ObjectAttributes.ObjectName], rax
0x1400905e5  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x1400905ea  mov     [rsp+120h+ObjectAttributes.RootDirectory], rbx
0x1400905ef  lea     edx, [rbx+1]; DesiredAccess
0x1400905f2  mov     [rsp+120h+ObjectAttributes.Attributes], 240h
0x1400905fa  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1400905ff  movdqu  xmmword ptr [rsp+120h+ObjectAttributes.SecurityDescriptor], xmm0
0x140090605  call    cs:__imp_ZwOpenKey
0x14009060c  nop     dword ptr [rax+rax+00h]
0x140090611  test    eax, eax
0x140090613  js      short loc_140090683
0x140090615  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x14009061c  lea     rcx, [rbp+20h+ValueName]; DestinationString
0x140090620  call    cs:__imp_RtlInitUnicodeString
0x140090627  nop     dword ptr [rax+rax+00h]
0x14009062c  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140090631  lea     rax, [rsp+120h+var_F0]
0x140090636  mov     [rsp+120h+ResultLength], rax; ResultLength
0x14009063b  lea     r9, [rbp+20h+KeyValueInformation]; KeyValueInformation
0x14009063f  lea     r8d, [rbx+2]; KeyValueInformationClass
0x140090643  mov     [rsp+120h+Length], 80h; Length
0x14009064b  lea     rdx, [rbp+20h+ValueName]; ValueName
0x14009064f  call    cs:__imp_ZwQueryValueKey
0x140090656  nop     dword ptr [rax+rax+00h]
0x14009065b  test    eax, eax
0x14009065d  js      short loc_140090672
0x14009065f  cmp     [rbp+20h+var_8C], 4
0x140090663  jnz     short loc_140090672
0x140090665  cmp     [rbp+20h+var_88], 4
0x140090669  jnz     short loc_140090672
0x14009066b  cmp     [rbp+20h+var_84], 1
0x14009066f  setz    bl
0x140090672  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140090677  call    cs:__imp_ZwClose
0x14009067e  nop     dword ptr [rax+rax+00h]
0x140090683  mov     al, bl
0x140090685  mov     rcx, [rbp+20h+var_10]
0x140090689  xor     rcx, rsp; StackCookie
0x14009068c  call    __security_check_cookie
0x140090691  mov     rbx, [rsp+120h+arg_0]
0x140090699  add     rsp, 120h
0x1400906a0  pop     rbp
0x1400906a1  retn
```
