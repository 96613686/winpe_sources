# CipIsDeveloperModeEnabled

- ea: `0x1800e2bb0`
- end: `0x1800e2e0f`
- name: `CipIsDeveloperModeEnabled`
- size: `607`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e72e4`
- `0x1800e7db8`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18005ab10`
- `0x1800e2bb0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800e2cfc`
- `ntoskrnl!ZwClose` at `0x1800e2cfc`
- `ntoskrnl!ZwOpenKey` at `0x1800e2ce5`
- `ntoskrnl!ZwOpenKey` at `0x1800e2ce5`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e2d0d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e2d0d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e2c3d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e2c3d`

## string_xrefs

- `0x1800e2c16`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlock`
- `0x1800e2d3e`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e2d83`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e2dc9`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\Appx`

## pseudocode

```c
__int64 __fastcall CipIsDeveloperModeEnabled(_BYTE *a1)
{
  signed int PersistedStateLocation; // ebx
  _WORD *v3; // rax
  __int64 v4; // rcx
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  int v7; // [rsp+44h] [rbp-BCh] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v9; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v11[528]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = 0;
  memset(v11, 0, 0x20Au);
  v7 = 0;
  v6 = 0;
  *a1 = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"CIDeveloper",
                             0,
                             L"\\REGISTRY\\Machine\\SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlock",
                             0,
                             v11,
                             522,
                             &v7);
  if ( PersistedStateLocation >= 0 )
  {
    v3 = v11;
    v9 = 0;
    v4 = 0x7FFF;
    do
    {
      if ( !*v3 )
        break;
      ++v3;
      --v4;
    }
    while ( v4 );
    PersistedStateLocation = v4 == 0 ? 0xC000000D : 0;
    if ( v4 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      LOWORD(v9) = -2 - 2 * v4;
      WORD1(v9) = -2 * v4;
      *((_QWORD *)&v9 + 1) = v11;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v9;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      PersistedStateLocation = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( PersistedStateLocation >= 0 )
      {
        ZwClose(KeyHandle);
LABEL_15:
        *a1 = 1;
        return (unsigned int)PersistedStateLocation;
      }
      if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
      {
        PersistedStateLocation = CipGetRegistryValue(
                                   0,
                                   L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock",
                                   (__int64)L"AllowDevelopmentWithoutDevLicense",
                                   0,
                                   (__int64)&v6,
                                   4,
                                   (__int64)&v7);
        if ( PersistedStateLocation >= 0 && v6 == 1 )
          goto LABEL_15;
      }
      PersistedStateLocation = CipGetRegistryValue(
                                 (__int64)L"AppModelUnlock",
                                 L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModelUnlock",
                                 (__int64)L"AllowDevelopmentWithoutDevLicense",
                                 0,
                                 (__int64)&v6,
                                 4,
                                 (__int64)&v7);
      if ( PersistedStateLocation >= 0 && v6 == 1 )
        goto LABEL_15;
      PersistedStateLocation = CipGetRegistryValue(
                                 (__int64)L"AppxPolicies",
                                 L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows\\Appx",
                                 (__int64)L"AllowDevelopmentWithoutDevLicense",
                                 0,
                                 (__int64)&v6,
                                 4,
                                 (__int64)&v7);
      if ( PersistedStateLocation >= 0 && v6 == 1 )
        goto LABEL_15;
    }
  }
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x1800e2bb0  push    rbp
0x1800e2bb2  push    rbx
0x1800e2bb3  push    rsi
0x1800e2bb4  push    rdi
0x1800e2bb5  lea     rbp, [rsp-1B8h]
0x1800e2bbd  sub     rsp, 2B8h
0x1800e2bc4  mov     rax, cs:__security_cookie
0x1800e2bcb  xor     rax, rsp
0x1800e2bce  mov     [rbp+1D0h+var_30], rax
0x1800e2bd5  xorps   xmm0, xmm0
0x1800e2bd8  mov     rdi, rcx
0x1800e2bdb  mov     ebx, 20Ah
0x1800e2be0  lea     rcx, [rbp+1D0h+var_240]; void *
0x1800e2be4  xor     esi, esi
0x1800e2be6  mov     r8d, ebx; Size
0x1800e2be9  xor     edx, edx; Val
0x1800e2beb  mov     [rsp+2D0h+KeyHandle], rsi
0x1800e2bf0  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x1800e2bf5  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x1800e2bfa  movups  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2bfe  movups  [rsp+2D0h+var_280], xmm0
0x1800e2c03  call    memset
0x1800e2c08  lea     rax, [rsp+2D0h+var_28C]
0x1800e2c0d  mov     [rsp+2D0h+var_28C], esi
0x1800e2c11  mov     [rsp+2D0h+var_2A0], rax
0x1800e2c16  lea     r8, aRegistryMachin_18; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x1800e2c1d  lea     rax, [rbp+1D0h+var_240]
0x1800e2c21  mov     [rsp+2D0h+var_2A8], ebx
0x1800e2c25  xor     r9d, r9d
0x1800e2c28  mov     [rsp+2D0h+var_2B0], rax
0x1800e2c2d  xor     edx, edx
0x1800e2c2f  mov     [rsp+2D0h+var_290], esi
0x1800e2c33  lea     rcx, aCideveloper; "CIDeveloper"
0x1800e2c3a  mov     [rdi], sil
0x1800e2c3d  call    cs:__imp_RtlGetPersistedStateLocation
0x1800e2c44  nop     dword ptr [rax+rax+00h]
0x1800e2c49  mov     ebx, eax
0x1800e2c4b  test    eax, eax
0x1800e2c4d  js      loc_1800E2DF1
0x1800e2c53  xorps   xmm0, xmm0
0x1800e2c56  lea     rax, [rbp+1D0h+var_240]
0x1800e2c5a  movups  [rsp+2D0h+var_280], xmm0
0x1800e2c5f  mov     ecx, 7FFFh
0x1800e2c64  lea     edx, [rsi+2]
0x1800e2c67  cmp     [rax], si
0x1800e2c6a  jz      short loc_1800E2C75
0x1800e2c6c  add     rax, rdx
0x1800e2c6f  sub     rcx, 1
0x1800e2c73  jnz     short loc_1800E2C67
0x1800e2c75  mov     rax, rcx
0x1800e2c78  neg     rax
0x1800e2c7b  sbb     ebx, ebx
0x1800e2c7d  not     ebx
0x1800e2c7f  and     ebx, 0C000000Dh
0x1800e2c85  test    rcx, rcx
0x1800e2c88  jz      loc_1800E2DF1
0x1800e2c8e  add     cx, cx
0x1800e2c91  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x1800e2c99  mov     eax, 0FFFEh
0x1800e2c9e  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rsi
0x1800e2ca3  sub     ax, cx
0x1800e2ca6  mov     [rsp+2D0h+ObjectAttributes.Attributes], 240h
0x1800e2cae  mov     word ptr [rsp+2D0h+var_280], ax
0x1800e2cb3  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x1800e2cb8  add     ax, dx
0x1800e2cbb  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800e2cc0  mov     word ptr [rsp+2D0h+var_280+2], ax
0x1800e2cc5  xorps   xmm0, xmm0
0x1800e2cc8  lea     rax, [rbp+1D0h+var_240]
0x1800e2ccc  mov     edx, 20019h; DesiredAccess
0x1800e2cd1  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x1800e2cd6  lea     rax, [rsp+2D0h+var_280]
0x1800e2cdb  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x1800e2ce0  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2ce5  call    cs:__imp_ZwOpenKey
0x1800e2cec  nop     dword ptr [rax+rax+00h]
0x1800e2cf1  mov     ebx, eax
0x1800e2cf3  test    eax, eax
0x1800e2cf5  js      short loc_1800E2D0D
0x1800e2cf7  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1800e2cfc  call    cs:__imp_ZwClose
0x1800e2d03  nop     dword ptr [rax+rax+00h]
0x1800e2d08  jmp     loc_1800E2DEE
0x1800e2d0d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800e2d14  nop     dword ptr [rax+rax+00h]
0x1800e2d19  test    al, al
0x1800e2d1b  jz      short loc_1800E2D62
0x1800e2d1d  lea     rax, [rsp+2D0h+var_28C]
0x1800e2d22  xor     r9d, r9d
0x1800e2d25  mov     [rsp+2D0h+var_2A0], rax
0x1800e2d2a  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2d31  lea     rax, [rsp+2D0h+var_290]
0x1800e2d36  mov     [rsp+2D0h+var_2A8], 4
0x1800e2d3e  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e2d45  mov     [rsp+2D0h+var_2B0], rax
0x1800e2d4a  xor     ecx, ecx
0x1800e2d4c  call    CipGetRegistryValue
0x1800e2d51  mov     ebx, eax
0x1800e2d53  test    eax, eax
0x1800e2d55  js      short loc_1800E2D62
0x1800e2d57  cmp     [rsp+2D0h+var_290], 1
0x1800e2d5c  jz      loc_1800E2DEE
0x1800e2d62  lea     rax, [rsp+2D0h+var_28C]
0x1800e2d67  xor     r9d, r9d
0x1800e2d6a  mov     [rsp+2D0h+var_2A0], rax
0x1800e2d6f  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2d76  lea     rax, [rsp+2D0h+var_290]
0x1800e2d7b  mov     [rsp+2D0h+var_2A8], 4
0x1800e2d83  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e2d8a  mov     [rsp+2D0h+var_2B0], rax
0x1800e2d8f  lea     rcx, aAppmodelunlock; "AppModelUnlock"
0x1800e2d96  call    CipGetRegistryValue
0x1800e2d9b  mov     ebx, eax
0x1800e2d9d  test    eax, eax
0x1800e2d9f  js      short loc_1800E2DA8
0x1800e2da1  cmp     [rsp+2D0h+var_290], 1
0x1800e2da6  jz      short loc_1800E2DEE
0x1800e2da8  lea     rax, [rsp+2D0h+var_28C]
0x1800e2dad  xor     r9d, r9d
0x1800e2db0  mov     [rsp+2D0h+var_2A0], rax
0x1800e2db5  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2dbc  lea     rax, [rsp+2D0h+var_290]
0x1800e2dc1  mov     [rsp+2D0h+var_2A8], 4
0x1800e2dc9  lea     rdx, aRegistryMachin_24; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1800e2dd0  mov     [rsp+2D0h+var_2B0], rax
0x1800e2dd5  lea     rcx, aAppxpolicies; "AppxPolicies"
0x1800e2ddc  call    CipGetRegistryValue
0x1800e2de1  mov     ebx, eax
0x1800e2de3  test    eax, eax
0x1800e2de5  js      short loc_1800E2DF1
0x1800e2de7  cmp     [rsp+2D0h+var_290], 1
0x1800e2dec  jnz     short loc_1800E2DF1
0x1800e2dee  mov     byte ptr [rdi], 1
0x1800e2df1  mov     eax, ebx
0x1800e2df3  mov     rcx, [rbp+1D0h+var_30]
0x1800e2dfa  xor     rcx, rsp; StackCookie
0x1800e2dfd  call    __security_check_cookie
0x1800e2e02  add     rsp, 2B8h
0x1800e2e09  pop     rdi
0x1800e2e0a  pop     rsi
0x1800e2e0b  pop     rbx
0x1800e2e0c  pop     rbp
0x1800e2e0d  retn
```
