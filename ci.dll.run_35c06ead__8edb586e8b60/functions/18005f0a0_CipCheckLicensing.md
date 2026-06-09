# CipCheckLicensing

- ea: `0x18005f0a0`
- end: `0x18005f2ef`
- name: `CipCheckLicensing`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e670`

## callees

- `0x18001c67c`
- `0x18002c0d0`
- `0x18002c1b0`
- `0x18005f0a0`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005f1f9`
- `ntoskrnl!ZwCreateKey` at `0x18005f1f9`
- `ntoskrnl!ZwQueryValueKey` at `0x18005f241`
- `ntoskrnl!ZwQueryValueKey` at `0x18005f241`
- `ntoskrnl!ZwClose` at `0x18005f2c1`
- `ntoskrnl!ZwClose` at `0x18005f2c1`
- `ntoskrnl!ZwSetValueKey` at `0x18005f28f`
- `ntoskrnl!ZwSetValueKey` at `0x18005f28f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005f16c`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005f16c`

## string_xrefs

- `0x18005f0e6`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Protected`
- `0x18005f10d`: `CodeIntegrity-AllowConfigurablePolicy-CustomKernelSigners`

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
        ((void (__fastcall *)(void *))xmmword_18004A630)(KeyHandle);
        return ZwClose(KeyHandle);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f0a0  mov     [rsp-8+arg_8], rbx
0x18005f0a5  mov     [rsp-8+arg_10], rdi
0x18005f0aa  push    rbp
0x18005f0ab  lea     rbp, [rsp-57h]
0x18005f0b0  sub     rsp, 0E0h
0x18005f0b7  mov     rax, cs:__security_cookie
0x18005f0be  xor     rax, rsp
0x18005f0c1  mov     [rbp+57h+var_8], rax
0x18005f0c5  xorps   xmm0, xmm0
0x18005f0c8  mov     qword ptr [rbp+57h+ValueName.Length], 120010h
0x18005f0d0  lea     rax, aLicensed; "Licensed"
0x18005f0d7  mov     [rbp+57h+var_60], 80007Eh
0x18005f0df  mov     [rbp+57h+ValueName.Buffer], rax
0x18005f0e3  mov     rbx, rcx
0x18005f0e6  lea     rax, aRegistryMachin_17; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005f0ed  mov     [rbp+57h+var_70], 740072h
0x18005f0f5  mov     [rbp+57h+var_58], rax
0x18005f0f9  mov     ecx, 10h
0x18005f0fe  xor     eax, eax
0x18005f100  mov     [rbp+57h+var_88], 0
0x18005f107  mov     [rbp+57h+var_10], eax
0x18005f10a  mov     [rbp+57h+ResultLength], eax
0x18005f10d  lea     rax, aCodeintegrityA; "CodeIntegrity-AllowConfigurablePolicy-C"...
0x18005f114  mov     [rbp+57h+var_68], rax
0x18005f118  xor     eax, eax
0x18005f11a  mov     [rbp+57h+var_90], 0
0x18005f121  mov     [rbp+57h+var_8C], 0
0x18005f128  mov     [rbp+57h+Data], eax
0x18005f12b  mov     [rbp+57h+KeyHandle], rax
0x18005f12f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005f133  movups  [rbp+57h+KeyValueInformation], xmm0
0x18005f137  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005f13b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005f13f  test    rbx, rbx
0x18005f142  jz      loc_18005F2CD
0x18005f148  mov     eax, [rbx+4]
0x18005f14b  test    cl, al
0x18005f14d  jnz     loc_18005F2CD
0x18005f153  lea     rax, [rbp+57h+var_90]
0x18005f157  lea     r9d, [rcx-0Ch]
0x18005f15b  mov     [rsp+0E0h+Class], rax
0x18005f160  lea     rcx, [rbp+57h+var_70]
0x18005f164  lea     r8, [rbp+57h+var_88]
0x18005f168  lea     rdx, [rbp+57h+var_8C]
0x18005f16c  call    cs:__imp_ZwQueryLicenseValue
0x18005f173  nop     dword ptr [rax+rax+00h]
0x18005f178  test    eax, eax
0x18005f17a  jns     short loc_18005F186
0x18005f17c  xor     dil, dil
0x18005f17f  cmp     eax, 0C0000023h
0x18005f184  jnz     short loc_18005F1A9
0x18005f186  cmp     [rbp+57h+var_90], 4
0x18005f18a  jnz     short loc_18005F1A2
0x18005f18c  cmp     [rbp+57h+var_8C], 4
0x18005f190  jnz     short loc_18005F1A2
0x18005f192  cmp     [rbp+57h+var_88], 0
0x18005f196  jz      short loc_18005F1A2
0x18005f198  or      [rbp+57h+Data], 1
0x18005f19c  or      dword ptr [rbx+4], 4
0x18005f1a0  jmp     short loc_18005F1A6
0x18005f1a2  and     dword ptr [rbx+4], 0FFFFFFFBh
0x18005f1a6  mov     dil, 1
0x18005f1a9  lea     rax, [rbp+57h+var_60]
0x18005f1ad  mov     [rsp+0E0h+Disposition], 0; Disposition
0x18005f1b6  xorps   xmm0, xmm0
0x18005f1b9  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x18005f1c1  xor     r9d, r9d; TitleIndex
0x18005f1c4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005f1c8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005f1cc  mov     [rsp+0E0h+Class], 0; Class
0x18005f1d5  mov     edx, 20006h; DesiredAccess
0x18005f1da  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005f1e1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f1e5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005f1ed  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f1f2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005f1f9  call    cs:__imp_ZwCreateKey
0x18005f200  nop     dword ptr [rax+rax+00h]
0x18005f205  test    eax, eax
0x18005f207  js      loc_18005F2CD
0x18005f20d  test    dil, dil
0x18005f210  jz      loc_18005F29B
0x18005f216  mov     eax, [rbx+4]
0x18005f219  mov     r8d, 2; KeyValueInformationClass
0x18005f21f  test    r8b, al
0x18005f222  jnz     short loc_18005F29B
0x18005f224  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f228  lea     rax, [rbp+57h+ResultLength]
0x18005f22c  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x18005f231  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18005f235  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005f239  mov     dword ptr [rsp+0E0h+Class], 14h; Length
0x18005f241  call    cs:__imp_ZwQueryValueKey
0x18005f248  nop     dword ptr [rax+rax+00h]
0x18005f24d  mov     ecx, [rbp+57h+Data]
0x18005f250  test    eax, eax
0x18005f252  js      short loc_18005F265
0x18005f254  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x18005f258  jnz     short loc_18005F265
0x18005f25a  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x18005f25e  jnz     short loc_18005F265
0x18005f260  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18005f263  jmp     short loc_18005F269
0x18005f265  mov     eax, ecx
0x18005f267  not     eax
0x18005f269  xor     ecx, eax
0x18005f26b  jz      short loc_18005F29B
0x18005f26d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f271  lea     rax, [rbp+57h+Data]
0x18005f275  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x18005f27d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005f281  mov     r9d, 4; Type
0x18005f287  mov     [rsp+0E0h+Class], rax; Data
0x18005f28c  xor     r8d, r8d; TitleIndex
0x18005f28f  call    cs:__imp_ZwSetValueKey
0x18005f296  nop     dword ptr [rax+rax+00h]
0x18005f29b  mov     edx, [rbx+4]
0x18005f29e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f2a2  shr     edx, 3
0x18005f2a5  and     dl, 1
0x18005f2a8  call    CipUpdateCustomKernelSignerEnabledState
0x18005f2ad  mov     rax, qword ptr cs:xmmword_18004A630
0x18005f2b4  mov     rcx, [rbp+57h+KeyHandle]
0x18005f2b8  call    _guard_dispatch_icall
0x18005f2bd  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18005f2c1  call    cs:__imp_ZwClose
0x18005f2c8  nop     dword ptr [rax+rax+00h]
0x18005f2cd  mov     rcx, [rbp+57h+var_8]
0x18005f2d1  xor     rcx, rsp; StackCookie
0x18005f2d4  call    __security_check_cookie
0x18005f2d9  lea     r11, [rsp+0E0h+var_s0]
0x18005f2e1  mov     rbx, [r11+18h]
0x18005f2e5  mov     rdi, [r11+20h]
0x18005f2e9  mov     rsp, r11
0x18005f2ec  pop     rbp
0x18005f2ed  retn
```
