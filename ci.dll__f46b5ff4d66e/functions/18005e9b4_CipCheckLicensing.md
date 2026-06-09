# CipCheckLicensing

- ea: `0x18005e9b4`
- end: `0x18005ec03`
- name: `CipCheckLicensing`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005dfd0`

## callees

- `0x18001c73c`
- `0x18002bef0`
- `0x18002bfd0`
- `0x18005e9b4`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005eb0d`
- `ntoskrnl!ZwCreateKey` at `0x18005eb0d`
- `ntoskrnl!ZwQueryValueKey` at `0x18005eb55`
- `ntoskrnl!ZwQueryValueKey` at `0x18005eb55`
- `ntoskrnl!ZwClose` at `0x18005ebd5`
- `ntoskrnl!ZwClose` at `0x18005ebd5`
- `ntoskrnl!ZwSetValueKey` at `0x18005eba3`
- `ntoskrnl!ZwSetValueKey` at `0x18005eba3`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005ea80`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005ea80`

## string_xrefs

- `0x18005e9fa`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Protected`
- `0x18005ea21`: `CodeIntegrity-AllowConfigurablePolicy-CustomKernelSigners`

## pseudocode

```c
int __fastcall CipCheckLicensing(__int64 a1)
{
  int result; // eax
  int v3; // eax
  char v4; // di
  int v5; // eax
  int Data; // [rsp+40h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  int v8; // [rsp+50h] [rbp-39h] BYREF
  int v9; // [rsp+54h] [rbp-35h] BYREF
  int v10; // [rsp+58h] [rbp-31h] BYREF
  ULONG ResultLength; // [rsp+5Ch] [rbp-2Dh] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v13[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v14[2]; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+C0h] [rbp+37h] BYREF
  int v17; // [rsp+D0h] [rbp+47h]

  *(_QWORD *)&ValueName.Length = 1179664;
  v14[0] = 8388734;
  ValueName.Buffer = L"Licensed";
  v13[0] = 7602290;
  v14[1] = L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Protected";
  v10 = 0;
  v17 = 0;
  ResultLength = 0;
  v13[1] = L"CodeIntegrity-AllowConfigurablePolicy-CustomKernelSigners";
  result = 0;
  v8 = 0;
  v9 = 0;
  Data = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    result = *(_DWORD *)(a1 + 4);
    if ( (result & 0x10) == 0 )
    {
      v3 = ZwQueryLicenseValue(v13, &v9, &v10, 4, &v8);
      if ( v3 >= 0 || (v4 = 0, v3 == -1073741789) )
      {
        if ( v8 == 4 && v9 == 4 && v10 )
        {
          Data |= 1u;
          *(_DWORD *)(a1 + 4) |= 4u;
        }
        else
        {
          *(_DWORD *)(a1 + 4) &= ~4u;
        }
        v4 = 1;
      }
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Attributes = 576;
      result = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
      if ( result >= 0 )
      {
        if ( v4 && (*(_DWORD *)(a1 + 4) & 2) == 0 )
        {
          if ( ZwQueryValueKey(
                 KeyHandle,
                 &ValueName,
                 KeyValuePartialInformation,
                 &KeyValueInformation,
                 0x14u,
                 &ResultLength) >= 0
            && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
          {
            v5 = HIDWORD(KeyValueInformation);
          }
          else
          {
            v5 = ~Data;
          }
          if ( v5 != Data )
            ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
        }
        CipUpdateCustomKernelSignerEnabledState(KeyHandle);
        ((void (__fastcall *)(void *))xmmword_180049630)(KeyHandle);
        return ZwClose(KeyHandle);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005e9b4  mov     [rsp-8+arg_8], rbx
0x18005e9b9  mov     [rsp-8+arg_10], rdi
0x18005e9be  push    rbp
0x18005e9bf  lea     rbp, [rsp-57h]
0x18005e9c4  sub     rsp, 0E0h
0x18005e9cb  mov     rax, cs:__security_cookie
0x18005e9d2  xor     rax, rsp
0x18005e9d5  mov     [rbp+57h+var_8], rax
0x18005e9d9  xorps   xmm0, xmm0
0x18005e9dc  mov     qword ptr [rbp+57h+ValueName.Length], 120010h
0x18005e9e4  lea     rax, aLicensed; "Licensed"
0x18005e9eb  mov     [rbp+57h+var_60], 80007Eh
0x18005e9f3  mov     [rbp+57h+ValueName.Buffer], rax
0x18005e9f7  mov     rbx, rcx
0x18005e9fa  lea     rax, aRegistryMachin_18; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005ea01  mov     [rbp+57h+var_70], 740072h
0x18005ea09  mov     [rbp+57h+var_58], rax
0x18005ea0d  mov     ecx, 10h
0x18005ea12  xor     eax, eax
0x18005ea14  mov     [rbp+57h+var_88], 0
0x18005ea1b  mov     [rbp+57h+var_10], eax
0x18005ea1e  mov     [rbp+57h+ResultLength], eax
0x18005ea21  lea     rax, aCodeintegrityA; "CodeIntegrity-AllowConfigurablePolicy-C"...
0x18005ea28  mov     [rbp+57h+var_68], rax
0x18005ea2c  xor     eax, eax
0x18005ea2e  mov     [rbp+57h+var_90], 0
0x18005ea35  mov     [rbp+57h+var_8C], 0
0x18005ea3c  mov     [rbp+57h+Data], eax
0x18005ea3f  mov     [rbp+57h+KeyHandle], rax
0x18005ea43  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005ea47  movups  [rbp+57h+KeyValueInformation], xmm0
0x18005ea4b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005ea4f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005ea53  test    rbx, rbx
0x18005ea56  jz      loc_18005EBE1
0x18005ea5c  mov     eax, [rbx+4]
0x18005ea5f  test    cl, al
0x18005ea61  jnz     loc_18005EBE1
0x18005ea67  lea     rax, [rbp+57h+var_90]
0x18005ea6b  lea     r9d, [rcx-0Ch]
0x18005ea6f  mov     [rsp+0E0h+Class], rax
0x18005ea74  lea     rcx, [rbp+57h+var_70]
0x18005ea78  lea     r8, [rbp+57h+var_88]
0x18005ea7c  lea     rdx, [rbp+57h+var_8C]
0x18005ea80  call    cs:__imp_ZwQueryLicenseValue
0x18005ea87  nop     dword ptr [rax+rax+00h]
0x18005ea8c  test    eax, eax
0x18005ea8e  jns     short loc_18005EA9A
0x18005ea90  xor     dil, dil
0x18005ea93  cmp     eax, 0C0000023h
0x18005ea98  jnz     short loc_18005EABD
0x18005ea9a  cmp     [rbp+57h+var_90], 4
0x18005ea9e  jnz     short loc_18005EAB6
0x18005eaa0  cmp     [rbp+57h+var_8C], 4
0x18005eaa4  jnz     short loc_18005EAB6
0x18005eaa6  cmp     [rbp+57h+var_88], 0
0x18005eaaa  jz      short loc_18005EAB6
0x18005eaac  or      [rbp+57h+Data], 1
0x18005eab0  or      dword ptr [rbx+4], 4
0x18005eab4  jmp     short loc_18005EABA
0x18005eab6  and     dword ptr [rbx+4], 0FFFFFFFBh
0x18005eaba  mov     dil, 1
0x18005eabd  lea     rax, [rbp+57h+var_60]
0x18005eac1  mov     [rsp+0E0h+Disposition], 0; Disposition
0x18005eaca  xorps   xmm0, xmm0
0x18005eacd  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x18005ead5  xor     r9d, r9d; TitleIndex
0x18005ead8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005eadc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005eae0  mov     [rsp+0E0h+Class], 0; Class
0x18005eae9  mov     edx, 20006h; DesiredAccess
0x18005eaee  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005eaf5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005eaf9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005eb01  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005eb06  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005eb0d  call    cs:__imp_ZwCreateKey
0x18005eb14  nop     dword ptr [rax+rax+00h]
0x18005eb19  test    eax, eax
0x18005eb1b  js      loc_18005EBE1
0x18005eb21  test    dil, dil
0x18005eb24  jz      loc_18005EBAF
0x18005eb2a  mov     eax, [rbx+4]
0x18005eb2d  mov     r8d, 2; KeyValueInformationClass
0x18005eb33  test    r8b, al
0x18005eb36  jnz     short loc_18005EBAF
0x18005eb38  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005eb3c  lea     rax, [rbp+57h+ResultLength]
0x18005eb40  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x18005eb45  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18005eb49  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005eb4d  mov     dword ptr [rsp+0E0h+Class], 14h; Length
0x18005eb55  call    cs:__imp_ZwQueryValueKey
0x18005eb5c  nop     dword ptr [rax+rax+00h]
0x18005eb61  mov     ecx, [rbp+57h+Data]
0x18005eb64  test    eax, eax
0x18005eb66  js      short loc_18005EB79
0x18005eb68  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x18005eb6c  jnz     short loc_18005EB79
0x18005eb6e  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x18005eb72  jnz     short loc_18005EB79
0x18005eb74  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18005eb77  jmp     short loc_18005EB7D
0x18005eb79  mov     eax, ecx
0x18005eb7b  not     eax
0x18005eb7d  xor     ecx, eax
0x18005eb7f  jz      short loc_18005EBAF
0x18005eb81  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005eb85  lea     rax, [rbp+57h+Data]
0x18005eb89  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x18005eb91  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005eb95  mov     r9d, 4; Type
0x18005eb9b  mov     [rsp+0E0h+Class], rax; Data
0x18005eba0  xor     r8d, r8d; TitleIndex
0x18005eba3  call    cs:__imp_ZwSetValueKey
0x18005ebaa  nop     dword ptr [rax+rax+00h]
0x18005ebaf  mov     edx, [rbx+4]
0x18005ebb2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005ebb6  shr     edx, 3
0x18005ebb9  and     dl, 1
0x18005ebbc  call    CipUpdateCustomKernelSignerEnabledState
0x18005ebc1  mov     rax, qword ptr cs:xmmword_180049630
0x18005ebc8  mov     rcx, [rbp+57h+KeyHandle]
0x18005ebcc  call    _guard_dispatch_icall
0x18005ebd1  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18005ebd5  call    cs:__imp_ZwClose
0x18005ebdc  nop     dword ptr [rax+rax+00h]
0x18005ebe1  mov     rcx, [rbp+57h+var_8]
0x18005ebe5  xor     rcx, rsp; StackCookie
0x18005ebe8  call    __security_check_cookie
0x18005ebed  lea     r11, [rsp+0E0h+var_s0]
0x18005ebf5  mov     rbx, [r11+18h]
0x18005ebf9  mov     rdi, [r11+20h]
0x18005ebfd  mov     rsp, r11
0x18005ec00  pop     rbp
0x18005ec01  retn
```
