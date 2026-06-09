# CscLicensingRegisterPolicyChange

- ea: `0x14009141c`
- end: `0x1400914eb`
- name: `CscLicensingRegisterPolicyChange`
- size: `207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140090740`

## callees

- `0x14005213c`
- `0x14008d930`
- `0x14009141c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140091449`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091449`
- `ntoskrnl!ExRegisterCallback` at `0x1400914af`
- `ntoskrnl!ExRegisterCallback` at `0x1400914af`
- `ntoskrnl!ExCreateCallback` at `0x14009148c`
- `ntoskrnl!ExCreateCallback` at `0x14009148c`

## pseudocode

```c
__int64 CscLicensingRegisterPolicyChange()
{
  NTSTATUS v0; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Callback\\LicensingData");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 80;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ExCreateCallback((PCALLBACK_OBJECT *)&g_CscPolicyData + 1, &ObjectAttributes, 0, 1u);
  if ( v0 < 0 )
    goto LABEL_4;
  g_CscPolicyData = ExRegisterCallback((PCALLBACK_OBJECT)*(&g_CscPolicyData + 1), CscLicensingPolicyChangeCallback, 0);
  if ( !g_CscPolicyData )
  {
    v0 = -1073741823;
LABEL_4:
    CscLicensingPolicyCleanup();
  }
  CscLicensingPolicyChangeCallback(0, 0, 0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14009141c  mov     [rsp-8+arg_0], rbx
0x140091421  push    rbp
0x140091422  mov     rbp, rsp
0x140091425  sub     rsp, 60h
0x140091429  xorps   xmm0, xmm0
0x14009142c  lea     rdx, aCallbackLicens; "\\Callback\\LicensingData"
0x140091433  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140091437  xor     eax, eax
0x140091439  lea     rcx, [rbp+DestinationString]; DestinationString
0x14009143d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140091441  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140091445  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140091449  call    cs:__imp_RtlInitUnicodeString
0x140091450  nop     dword ptr [rax+rax+00h]
0x140091455  lea     rax, [rbp+DestinationString]
0x140091459  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140091460  xorps   xmm0, xmm0
0x140091463  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140091467  mov     r9b, 1; AllowMultipleCallbacks
0x14009146a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140091472  xor     r8d, r8d; Create
0x140091475  mov     [rbp+ObjectAttributes.Attributes], 50h ; 'P'
0x14009147c  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x140091480  lea     rcx, g_CscPolicyData+8; CallbackObject
0x140091487  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14009148c  call    cs:__imp_ExCreateCallback
0x140091493  nop     dword ptr [rax+rax+00h]
0x140091498  mov     ebx, eax
0x14009149a  test    eax, eax
0x14009149c  js      short loc_1400914CC
0x14009149e  mov     rcx, qword ptr cs:g_CscPolicyData+8; CallbackObject
0x1400914a5  lea     rdx, CscLicensingPolicyChangeCallback; CallbackFunction
0x1400914ac  xor     r8d, r8d; CallbackContext
0x1400914af  call    cs:__imp_ExRegisterCallback
0x1400914b6  nop     dword ptr [rax+rax+00h]
0x1400914bb  mov     qword ptr cs:g_CscPolicyData, rax
0x1400914c2  test    rax, rax
0x1400914c5  jnz     short loc_1400914D1
0x1400914c7  mov     ebx, 0C0000001h
0x1400914cc  call    CscLicensingPolicyCleanup
0x1400914d1  xor     r8d, r8d; Argument2
0x1400914d4  xor     edx, edx; Argument1
0x1400914d6  xor     ecx, ecx; CallbackContext
0x1400914d8  call    CscLicensingPolicyChangeCallback
0x1400914dd  mov     eax, ebx
0x1400914df  mov     rbx, [rsp+60h+arg_0]
0x1400914e4  add     rsp, 60h
0x1400914e8  pop     rbp
0x1400914e9  retn
```
