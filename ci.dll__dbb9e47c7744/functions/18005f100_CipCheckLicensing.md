# CipCheckLicensing

- ea: `0x18005f100`
- end: `0x18005f34f`
- name: `CipCheckLicensing`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005e6d0`

## callees

- `0x18001c61c`
- `0x18002bf20`
- `0x18002c000`
- `0x18005f100`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005f259`
- `ntoskrnl!ZwCreateKey` at `0x18005f259`
- `ntoskrnl!ZwQueryValueKey` at `0x18005f2a1`
- `ntoskrnl!ZwQueryValueKey` at `0x18005f2a1`
- `ntoskrnl!ZwClose` at `0x18005f321`
- `ntoskrnl!ZwClose` at `0x18005f321`
- `ntoskrnl!ZwSetValueKey` at `0x18005f2ef`
- `ntoskrnl!ZwSetValueKey` at `0x18005f2ef`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005f1cc`
- `ntoskrnl!ZwQueryLicenseValue` at `0x18005f1cc`

## string_xrefs

- `0x18005f146`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Protected`
- `0x18005f16d`: `CodeIntegrity-AllowConfigurablePolicy-CustomKernelSigners`

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
        ((void (__fastcall *)(void *))xmmword_18004A590)(KeyHandle);
        return ZwClose(KeyHandle);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005f100  mov     [rsp-8+arg_8], rbx
0x18005f105  mov     [rsp-8+arg_10], rdi
0x18005f10a  push    rbp
0x18005f10b  lea     rbp, [rsp-57h]
0x18005f110  sub     rsp, 0E0h
0x18005f117  mov     rax, cs:__security_cookie
0x18005f11e  xor     rax, rsp
0x18005f121  mov     [rbp+57h+var_8], rax
0x18005f125  xorps   xmm0, xmm0
0x18005f128  mov     qword ptr [rbp+57h+ValueName.Length], 120010h
0x18005f130  lea     rax, aLicensed; "Licensed"
0x18005f137  mov     [rbp+57h+var_60], 80007Eh
0x18005f13f  mov     [rbp+57h+ValueName.Buffer], rax
0x18005f143  mov     rbx, rcx
0x18005f146  lea     rax, aRegistryMachin_17; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005f14d  mov     [rbp+57h+var_70], 740072h
0x18005f155  mov     [rbp+57h+var_58], rax
0x18005f159  mov     ecx, 10h
0x18005f15e  xor     eax, eax
0x18005f160  mov     [rbp+57h+var_88], 0
0x18005f167  mov     [rbp+57h+var_10], eax
0x18005f16a  mov     [rbp+57h+ResultLength], eax
0x18005f16d  lea     rax, aCodeintegrityA; "CodeIntegrity-AllowConfigurablePolicy-C"...
0x18005f174  mov     [rbp+57h+var_68], rax
0x18005f178  xor     eax, eax
0x18005f17a  mov     [rbp+57h+var_90], 0
0x18005f181  mov     [rbp+57h+var_8C], 0
0x18005f188  mov     [rbp+57h+Data], eax
0x18005f18b  mov     [rbp+57h+KeyHandle], rax
0x18005f18f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005f193  movups  [rbp+57h+KeyValueInformation], xmm0
0x18005f197  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005f19b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005f19f  test    rbx, rbx
0x18005f1a2  jz      loc_18005F32D
0x18005f1a8  mov     eax, [rbx+4]
0x18005f1ab  test    cl, al
0x18005f1ad  jnz     loc_18005F32D
0x18005f1b3  lea     rax, [rbp+57h+var_90]
0x18005f1b7  lea     r9d, [rcx-0Ch]
0x18005f1bb  mov     [rsp+0E0h+Class], rax
0x18005f1c0  lea     rcx, [rbp+57h+var_70]
0x18005f1c4  lea     r8, [rbp+57h+var_88]
0x18005f1c8  lea     rdx, [rbp+57h+var_8C]
0x18005f1cc  call    cs:__imp_ZwQueryLicenseValue
0x18005f1d3  nop     dword ptr [rax+rax+00h]
0x18005f1d8  test    eax, eax
0x18005f1da  jns     short loc_18005F1E6
0x18005f1dc  xor     dil, dil
0x18005f1df  cmp     eax, 0C0000023h
0x18005f1e4  jnz     short loc_18005F209
0x18005f1e6  cmp     [rbp+57h+var_90], 4
0x18005f1ea  jnz     short loc_18005F202
0x18005f1ec  cmp     [rbp+57h+var_8C], 4
0x18005f1f0  jnz     short loc_18005F202
0x18005f1f2  cmp     [rbp+57h+var_88], 0
0x18005f1f6  jz      short loc_18005F202
0x18005f1f8  or      [rbp+57h+Data], 1
0x18005f1fc  or      dword ptr [rbx+4], 4
0x18005f200  jmp     short loc_18005F206
0x18005f202  and     dword ptr [rbx+4], 0FFFFFFFBh
0x18005f206  mov     dil, 1
0x18005f209  lea     rax, [rbp+57h+var_60]
0x18005f20d  mov     [rsp+0E0h+Disposition], 0; Disposition
0x18005f216  xorps   xmm0, xmm0
0x18005f219  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x18005f221  xor     r9d, r9d; TitleIndex
0x18005f224  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005f228  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005f22c  mov     [rsp+0E0h+Class], 0; Class
0x18005f235  mov     edx, 20006h; DesiredAccess
0x18005f23a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005f241  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f245  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005f24d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f252  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005f259  call    cs:__imp_ZwCreateKey
0x18005f260  nop     dword ptr [rax+rax+00h]
0x18005f265  test    eax, eax
0x18005f267  js      loc_18005F32D
0x18005f26d  test    dil, dil
0x18005f270  jz      loc_18005F2FB
0x18005f276  mov     eax, [rbx+4]
0x18005f279  mov     r8d, 2; KeyValueInformationClass
0x18005f27f  test    r8b, al
0x18005f282  jnz     short loc_18005F2FB
0x18005f284  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f288  lea     rax, [rbp+57h+ResultLength]
0x18005f28c  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x18005f291  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18005f295  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005f299  mov     dword ptr [rsp+0E0h+Class], 14h; Length
0x18005f2a1  call    cs:__imp_ZwQueryValueKey
0x18005f2a8  nop     dword ptr [rax+rax+00h]
0x18005f2ad  mov     ecx, [rbp+57h+Data]
0x18005f2b0  test    eax, eax
0x18005f2b2  js      short loc_18005F2C5
0x18005f2b4  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x18005f2b8  jnz     short loc_18005F2C5
0x18005f2ba  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x18005f2be  jnz     short loc_18005F2C5
0x18005f2c0  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18005f2c3  jmp     short loc_18005F2C9
0x18005f2c5  mov     eax, ecx
0x18005f2c7  not     eax
0x18005f2c9  xor     ecx, eax
0x18005f2cb  jz      short loc_18005F2FB
0x18005f2cd  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f2d1  lea     rax, [rbp+57h+Data]
0x18005f2d5  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x18005f2dd  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005f2e1  mov     r9d, 4; Type
0x18005f2e7  mov     [rsp+0E0h+Class], rax; Data
0x18005f2ec  xor     r8d, r8d; TitleIndex
0x18005f2ef  call    cs:__imp_ZwSetValueKey
0x18005f2f6  nop     dword ptr [rax+rax+00h]
0x18005f2fb  mov     edx, [rbx+4]
0x18005f2fe  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18005f302  shr     edx, 3
0x18005f305  and     dl, 1
0x18005f308  call    CipUpdateCustomKernelSignerEnabledState
0x18005f30d  mov     rax, qword ptr cs:xmmword_18004A590
0x18005f314  mov     rcx, [rbp+57h+KeyHandle]
0x18005f318  call    _guard_dispatch_icall
0x18005f31d  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18005f321  call    cs:__imp_ZwClose
0x18005f328  nop     dword ptr [rax+rax+00h]
0x18005f32d  mov     rcx, [rbp+57h+var_8]
0x18005f331  xor     rcx, rsp; StackCookie
0x18005f334  call    __security_check_cookie
0x18005f339  lea     r11, [rsp+0E0h+var_s0]
0x18005f341  mov     rbx, [r11+18h]
0x18005f345  mov     rdi, [r11+20h]
0x18005f349  mov     rsp, r11
0x18005f34c  pop     rbp
0x18005f34d  retn
```
