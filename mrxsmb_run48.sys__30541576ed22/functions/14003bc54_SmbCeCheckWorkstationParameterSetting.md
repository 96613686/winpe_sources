# SmbCeCheckWorkstationParameterSetting

- ea: `0x14003bc54`
- end: `0x14003bdc5`
- name: `SmbCeCheckWorkstationParameterSetting`
- size: `369`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007fd3c`

## callees

- `0x14001c5f0`
- `0x140026978`
- `0x14003bc54`
- `0x140059dc0`
- `0x1400904c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14003bd08`
- `ntoskrnl!ZwOpenKey` at `0x14003bd08`
- `ntoskrnl!ZwClose` at `0x14003bda0`
- `ntoskrnl!ZwClose` at `0x14003bda0`

## string_xrefs

- `0x14003bca8`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x14003bd64`: `EnableSecuritySignature`

## pseudocode

```c
int SmbCeCheckWorkstationParameterSetting()
{
  int result; // eax
  int v1; // ecx
  int v2; // r8d
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  char v6; // [rsp+80h] [rbp-80h] BYREF

  v4[0] = 34078720;
  KeyHandle = 0;
  v4[1] = &v6;
  memset(&ObjectAttributes, 0, 44);
  result = MRxSmbInitRedirectedPath(
             L"LanmanWorkStationParameters",
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
             v4);
  if ( result >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( result >= 0 )
    {
      MRxSmbGetUlongRegistryParameter(KeyHandle);
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 && (byte_1400712C4 & 4) != 0 )
        McTemplateK0zq_EtwWriteTransfer(v1, (unsigned int)&EnableSecuritySignatureNonDefault, v2, 0, 0);
      return ZwClose(KeyHandle);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003bc54  push    rbp
0x14003bc56  lea     rbp, [rsp-1A0h]
0x14003bc5e  sub     rsp, 2A0h
0x14003bc65  mov     rax, cs:__security_cookie
0x14003bc6c  xor     rax, rsp
0x14003bc6f  mov     [rbp+1A0h+var_10], rax
0x14003bc76  xorps   xmm0, xmm0
0x14003bc79  mov     [rsp+2A0h+var_260], 2080000h
0x14003bc82  xor     eax, eax
0x14003bc84  mov     [rsp+2A0h+KeyHandle], 0
0x14003bc8d  lea     rax, [rbp+1A0h+var_220]
0x14003bc91  mov     [rsp+2A0h+var_270], 0
0x14003bc99  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.ObjectName], xmm0
0x14003bc9e  lea     r8, [rsp+2A0h+var_260]
0x14003bca3  mov     [rsp+2A0h+var_258], rax
0x14003bca8  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003bcaf  lea     rcx, aLanmanworkstat; "LanmanWorkStationParameters"
0x14003bcb6  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.Length], xmm0
0x14003bcbb  movups  xmmword ptr [rsp+2A0h+ObjectAttributes+1Ch], xmm0
0x14003bcc0  call    MRxSmbInitRedirectedPath
0x14003bcc5  test    eax, eax
0x14003bcc7  js      loc_14003BDAC
0x14003bccd  lea     rax, [rsp+2A0h+var_260]
0x14003bcd2  mov     [rsp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x14003bcda  xorps   xmm0, xmm0
0x14003bcdd  mov     [rsp+2A0h+ObjectAttributes.ObjectName], rax
0x14003bce2  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x14003bce7  mov     [rsp+2A0h+ObjectAttributes.RootDirectory], 0
0x14003bcf0  mov     edx, 20019h; DesiredAccess
0x14003bcf5  mov     [rsp+2A0h+ObjectAttributes.Attributes], 240h
0x14003bcfd  lea     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x14003bd02  movdqu  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003bd08  call    cs:__imp_ZwOpenKey
0x14003bd0f  nop     dword ptr [rax+rax+00h]
0x14003bd14  test    eax, eax
0x14003bd16  js      loc_14003BDAC
0x14003bd1c  mov     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x14003bd21  lea     r8, [rsp+2A0h+var_270]
0x14003bd26  lea     rdx, aDisablemultich; "DisableMultiChannel"
0x14003bd2d  call    MRxSmbGetUlongRegistryParameter
0x14003bd32  test    eax, eax
0x14003bd34  js      short loc_14003BD5A
0x14003bd36  mov     ecx, [rsp+2A0h+var_270]
0x14003bd3a  test    ecx, ecx
0x14003bd3c  jz      short loc_14003BD5A
0x14003bd3e  test    cs:byte_1400712C3, 2
0x14003bd45  jz      short loc_14003BD5A
0x14003bd47  xor     r9d, r9d
0x14003bd4a  mov     [rsp+2A0h+var_280], ecx
0x14003bd4e  lea     rdx, MultiChannelDisabled
0x14003bd55  call    McTemplateK0zq_EtwWriteTransfer
0x14003bd5a  mov     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x14003bd5f  lea     r8, [rsp+2A0h+var_270]
0x14003bd64  lea     rdx, aEnablesecurity; "EnableSecuritySignature"
0x14003bd6b  call    MRxSmbGetUlongRegistryParameter
0x14003bd70  test    eax, eax
0x14003bd72  js      short loc_14003BD9B
0x14003bd74  cmp     [rsp+2A0h+var_270], 0
0x14003bd79  jnz     short loc_14003BD9B
0x14003bd7b  test    cs:byte_1400712C4, 4
0x14003bd82  jz      short loc_14003BD9B
0x14003bd84  xor     r9d, r9d
0x14003bd87  mov     [rsp+2A0h+var_280], 0
0x14003bd8f  lea     rdx, EnableSecuritySignatureNonDefault
0x14003bd96  call    McTemplateK0zq_EtwWriteTransfer
0x14003bd9b  mov     rcx, [rsp+2A0h+KeyHandle]; Handle
0x14003bda0  call    cs:__imp_ZwClose
0x14003bda7  nop     dword ptr [rax+rax+00h]
0x14003bdac  mov     rcx, [rbp+1A0h+var_10]
0x14003bdb3  xor     rcx, rsp; StackCookie
0x14003bdb6  call    __security_check_cookie
0x14003bdbb  add     rsp, 2A0h
0x14003bdc2  pop     rbp
0x14003bdc3  retn
```
