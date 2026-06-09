# SmbCeGetServersWithExtendedSessTimeout

- ea: `0x14003c624`
- end: `0x14003c86d`
- name: `SmbCeGetServersWithExtendedSessTimeout`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14007fd3c`

## callees

- `0x14001c5f0`
- `0x140039fa8`
- `0x14003c624`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14003c737`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c7af`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c737`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c7af`
- `ntoskrnl!ZwOpenKey` at `0x14003c6e5`
- `ntoskrnl!ZwOpenKey` at `0x14003c6e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c705`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c705`
- `ntoskrnl!ExAllocatePool2` at `0x14003c77a`
- `ntoskrnl!ExAllocatePool2` at `0x14003c77a`
- `ntoskrnl!ZwClose` at `0x14003c83a`
- `ntoskrnl!ZwClose` at `0x14003c83a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c829`

## string_xrefs

- `0x14003c681`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`

## pseudocode

```c
NTSTATUS SmbCeGetServersWithExtendedSessTimeout()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // eax
  NTSTATUS v2; // ebx
  ULONG Length; // ebx
  __int64 Pool2; // rdi
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-80h] BYREF
  char v10; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&DestinationString.Length = 34078720;
  KeyHandle = 0;
  DestinationString.Buffer = (wchar_t *)&v10;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  result = MRxSmbInitRedirectedPath(
             L"LanmanWorkStationParameters",
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
             &DestinationString);
  if ( result >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( result >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ServersWithExtendedSessTimeout");
      v1 = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
      v2 = 0;
      if ( v1 != -2147483643 )
        v2 = v1;
      if ( v2 >= 0 )
      {
        Length = DWORD2(KeyValueInformation) + 16;
        if ( (unsigned int)(DWORD2(KeyValueInformation) + 16) <= 0xFFFF
          && (Pool2 = ExAllocatePool2(258, Length, 1834182211)) != 0 )
        {
          v2 = ZwQueryValueKey(
                 KeyHandle,
                 &DestinationString,
                 KeyValuePartialInformation,
                 (PVOID)Pool2,
                 Length,
                 &ResultLength);
          if ( v2 >= 0 && *(_DWORD *)(Pool2 + 8) && *(_DWORD *)(Pool2 + 4) == 7 )
          {
            stru_140070F90.Length = *(_WORD *)(Pool2 + 8);
            stru_140070F90.MaximumLength = stru_140070F90.Length;
            stru_140070F90.Buffer = (wchar_t *)(Pool2 + 12);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids);
            }
            ExFreePoolWithTag((PVOID)Pool2, 0x6D536643u);
          }
        }
        else
        {
          v2 = -1073741670;
        }
      }
      ZwClose(KeyHandle);
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c624  mov     [rsp-8+arg_0], rbx
0x14003c629  mov     [rsp-8+arg_8], rdi
0x14003c62e  push    rbp
0x14003c62f  lea     rbp, [rsp-1B0h]
0x14003c637  sub     rsp, 2B0h
0x14003c63e  mov     rax, cs:__security_cookie
0x14003c645  xor     rax, rsp
0x14003c648  mov     [rbp+1B0h+var_10], rax
0x14003c64f  xorps   xmm0, xmm0
0x14003c652  mov     qword ptr [rsp+2B0h+DestinationString.Length], 2080000h
0x14003c65b  lea     rax, [rbp+1B0h+var_220]
0x14003c65f  mov     [rsp+2B0h+KeyHandle], 0
0x14003c668  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x14003c66d  lea     r8, [rsp+2B0h+DestinationString]
0x14003c672  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x14003c677  xor     eax, eax
0x14003c679  mov     [rsp+2B0h+var_280], 0
0x14003c681  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14003c688  lea     rcx, aLanmanworkstat; "LanmanWorkStationParameters"
0x14003c68f  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x14003c694  movups  xmmword ptr [rsp+2B0h+ObjectAttributes+1Ch], xmm0
0x14003c699  movups  [rbp+1B0h+KeyValueInformation], xmm0
0x14003c69d  call    MRxSmbInitRedirectedPath
0x14003c6a2  test    eax, eax
0x14003c6a4  js      loc_14003C848
0x14003c6aa  lea     rax, [rsp+2B0h+DestinationString]
0x14003c6af  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x14003c6b7  xorps   xmm0, xmm0
0x14003c6ba  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x14003c6bf  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x14003c6c4  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], 0
0x14003c6cd  mov     edx, 20019h; DesiredAccess
0x14003c6d2  mov     [rsp+2B0h+ObjectAttributes.Attributes], 240h
0x14003c6da  lea     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x14003c6df  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c6e5  call    cs:__imp_ZwOpenKey
0x14003c6ec  nop     dword ptr [rax+rax+00h]
0x14003c6f1  test    eax, eax
0x14003c6f3  js      loc_14003C848
0x14003c6f9  lea     rdx, aServerswithext; "ServersWithExtendedSessTimeout"
0x14003c700  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x14003c705  call    cs:__imp_RtlInitUnicodeString
0x14003c70c  nop     dword ptr [rax+rax+00h]
0x14003c711  mov     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x14003c716  lea     rax, [rsp+2B0h+var_280]
0x14003c71b  mov     [rsp+2B0h+ResultLength], rax; ResultLength
0x14003c720  lea     r9, [rbp+1B0h+KeyValueInformation]; KeyValueInformation
0x14003c724  mov     r8d, 2; KeyValueInformationClass
0x14003c72a  mov     [rsp+2B0h+Length], 10h; Length
0x14003c732  lea     rdx, [rsp+2B0h+DestinationString]; ValueName
0x14003c737  call    cs:__imp_ZwQueryValueKey
0x14003c73e  nop     dword ptr [rax+rax+00h]
0x14003c743  xor     ebx, ebx
0x14003c745  cmp     eax, 80000005h
0x14003c74a  cmovnz  ebx, eax
0x14003c74d  test    ebx, ebx
0x14003c74f  js      loc_14003C835
0x14003c755  mov     ebx, dword ptr [rbp+1B0h+KeyValueInformation+8]
0x14003c758  add     ebx, 10h
0x14003c75b  cmp     ebx, 0FFFFh
0x14003c761  jbe     short loc_14003C76D
0x14003c763  mov     ebx, 0C000009Ah
0x14003c768  jmp     loc_14003C835
0x14003c76d  mov     edx, ebx
0x14003c76f  mov     ecx, 102h
0x14003c774  mov     r8d, 6D536643h
0x14003c77a  call    cs:__imp_ExAllocatePool2
0x14003c781  nop     dword ptr [rax+rax+00h]
0x14003c786  mov     rdi, rax
0x14003c789  test    rax, rax
0x14003c78c  jz      short loc_14003C763
0x14003c78e  mov     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x14003c793  lea     rax, [rsp+2B0h+var_280]
0x14003c798  mov     [rsp+2B0h+ResultLength], rax; ResultLength
0x14003c79d  lea     rdx, [rsp+2B0h+DestinationString]; ValueName
0x14003c7a2  mov     r9, rdi; KeyValueInformation
0x14003c7a5  mov     [rsp+2B0h+Length], ebx; Length
0x14003c7a9  mov     r8d, 2; KeyValueInformationClass
0x14003c7af  call    cs:__imp_ZwQueryValueKey
0x14003c7b6  nop     dword ptr [rax+rax+00h]
0x14003c7bb  mov     ebx, eax
0x14003c7bd  test    eax, eax
0x14003c7bf  js      short loc_14003C7EC
0x14003c7c1  cmp     dword ptr [rdi+8], 0
0x14003c7c5  jbe     short loc_14003C7EC
0x14003c7c7  cmp     dword ptr [rdi+4], 7
0x14003c7cb  jnz     short loc_14003C7EC
0x14003c7cd  movzx   ecx, word ptr [rdi+8]
0x14003c7d1  mov     cs:stru_140070F90.Length, cx
0x14003c7d8  mov     cs:stru_140070F90.MaximumLength, cx
0x14003c7df  lea     rcx, [rdi+0Ch]
0x14003c7e3  mov     cs:stru_140070F90.Buffer, rcx
0x14003c7ea  jmp     short loc_14003C835
0x14003c7ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c7f3  lea     rax, WPP_GLOBAL_Control
0x14003c7fa  cmp     rcx, rax
0x14003c7fd  jz      short loc_14003C821
0x14003c7ff  mov     eax, [rcx+2Ch]
0x14003c802  test    al, 2
0x14003c804  jz      short loc_14003C821
0x14003c806  cmp     byte ptr [rcx+29h], 2
0x14003c80a  jb      short loc_14003C821
0x14003c80c  mov     rcx, [rcx+18h]
0x14003c810  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14003c817  mov     edx, 34h ; '4'
0x14003c81c  call    WPP_SF_
0x14003c821  mov     edx, 6D536643h; Tag
0x14003c826  mov     rcx, rdi; P
0x14003c829  call    cs:__imp_ExFreePoolWithTag
0x14003c830  nop     dword ptr [rax+rax+00h]
0x14003c835  mov     rcx, [rsp+2B0h+KeyHandle]; Handle
0x14003c83a  call    cs:__imp_ZwClose
0x14003c841  nop     dword ptr [rax+rax+00h]
0x14003c846  mov     eax, ebx
0x14003c848  mov     rcx, [rbp+1B0h+var_10]
0x14003c84f  xor     rcx, rsp; StackCookie
0x14003c852  call    __security_check_cookie
0x14003c857  lea     r11, [rsp+2B0h+var_s0]
0x14003c85f  mov     rbx, [r11+10h]
0x14003c863  mov     rdi, [r11+18h]
0x14003c867  mov     rsp, r11
0x14003c86a  pop     rbp
0x14003c86b  retn
```
