# CipIsDeveloperModeEnabled

- ea: `0x1800e1bf0`
- end: `0x1800e1e4f`
- name: `CipIsDeveloperModeEnabled`
- size: `607`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e2208`
- `0x1800e24c0`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x180059ed0`
- `0x1800e1bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800e1d3c`
- `ntoskrnl!ZwClose` at `0x1800e1d3c`
- `ntoskrnl!ZwOpenKey` at `0x1800e1d25`
- `ntoskrnl!ZwOpenKey` at `0x1800e1d25`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e1c7d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e1c7d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e1d4d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e1d4d`

## string_xrefs

- `0x1800e1c56`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlock`
- `0x1800e1d7e`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e1dc3`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e1e09`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\Appx`

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
0x1800e1bf0  push    rbp
0x1800e1bf2  push    rbx
0x1800e1bf3  push    rsi
0x1800e1bf4  push    rdi
0x1800e1bf5  lea     rbp, [rsp-1B8h]
0x1800e1bfd  sub     rsp, 2B8h
0x1800e1c04  mov     rax, cs:__security_cookie
0x1800e1c0b  xor     rax, rsp
0x1800e1c0e  mov     [rbp+1D0h+var_30], rax
0x1800e1c15  xorps   xmm0, xmm0
0x1800e1c18  mov     rdi, rcx
0x1800e1c1b  mov     ebx, 20Ah
0x1800e1c20  lea     rcx, [rbp+1D0h+var_240]; void *
0x1800e1c24  xor     esi, esi
0x1800e1c26  mov     r8d, ebx; Size
0x1800e1c29  xor     edx, edx; Val
0x1800e1c2b  mov     [rsp+2D0h+KeyHandle], rsi
0x1800e1c30  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x1800e1c35  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x1800e1c3a  movups  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e1c3e  movups  [rsp+2D0h+var_280], xmm0
0x1800e1c43  call    memset
0x1800e1c48  lea     rax, [rsp+2D0h+var_28C]
0x1800e1c4d  mov     [rsp+2D0h+var_28C], esi
0x1800e1c51  mov     [rsp+2D0h+var_2A0], rax
0x1800e1c56  lea     r8, aRegistryMachin_19; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x1800e1c5d  lea     rax, [rbp+1D0h+var_240]
0x1800e1c61  mov     [rsp+2D0h+var_2A8], ebx
0x1800e1c65  xor     r9d, r9d
0x1800e1c68  mov     [rsp+2D0h+var_2B0], rax
0x1800e1c6d  xor     edx, edx
0x1800e1c6f  mov     [rsp+2D0h+var_290], esi
0x1800e1c73  lea     rcx, aCideveloper; "CIDeveloper"
0x1800e1c7a  mov     [rdi], sil
0x1800e1c7d  call    cs:__imp_RtlGetPersistedStateLocation
0x1800e1c84  nop     dword ptr [rax+rax+00h]
0x1800e1c89  mov     ebx, eax
0x1800e1c8b  test    eax, eax
0x1800e1c8d  js      loc_1800E1E31
0x1800e1c93  xorps   xmm0, xmm0
0x1800e1c96  lea     rax, [rbp+1D0h+var_240]
0x1800e1c9a  movups  [rsp+2D0h+var_280], xmm0
0x1800e1c9f  mov     ecx, 7FFFh
0x1800e1ca4  lea     edx, [rsi+2]
0x1800e1ca7  cmp     [rax], si
0x1800e1caa  jz      short loc_1800E1CB5
0x1800e1cac  add     rax, rdx
0x1800e1caf  sub     rcx, 1
0x1800e1cb3  jnz     short loc_1800E1CA7
0x1800e1cb5  mov     rax, rcx
0x1800e1cb8  neg     rax
0x1800e1cbb  sbb     ebx, ebx
0x1800e1cbd  not     ebx
0x1800e1cbf  and     ebx, 0C000000Dh
0x1800e1cc5  test    rcx, rcx
0x1800e1cc8  jz      loc_1800E1E31
0x1800e1cce  add     cx, cx
0x1800e1cd1  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x1800e1cd9  mov     eax, 0FFFEh
0x1800e1cde  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rsi
0x1800e1ce3  sub     ax, cx
0x1800e1ce6  mov     [rsp+2D0h+ObjectAttributes.Attributes], 240h
0x1800e1cee  mov     word ptr [rsp+2D0h+var_280], ax
0x1800e1cf3  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x1800e1cf8  add     ax, dx
0x1800e1cfb  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800e1d00  mov     word ptr [rsp+2D0h+var_280+2], ax
0x1800e1d05  xorps   xmm0, xmm0
0x1800e1d08  lea     rax, [rbp+1D0h+var_240]
0x1800e1d0c  mov     edx, 20019h; DesiredAccess
0x1800e1d11  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x1800e1d16  lea     rax, [rsp+2D0h+var_280]
0x1800e1d1b  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x1800e1d20  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e1d25  call    cs:__imp_ZwOpenKey
0x1800e1d2c  nop     dword ptr [rax+rax+00h]
0x1800e1d31  mov     ebx, eax
0x1800e1d33  test    eax, eax
0x1800e1d35  js      short loc_1800E1D4D
0x1800e1d37  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1800e1d3c  call    cs:__imp_ZwClose
0x1800e1d43  nop     dword ptr [rax+rax+00h]
0x1800e1d48  jmp     loc_1800E1E2E
0x1800e1d4d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800e1d54  nop     dword ptr [rax+rax+00h]
0x1800e1d59  test    al, al
0x1800e1d5b  jz      short loc_1800E1DA2
0x1800e1d5d  lea     rax, [rsp+2D0h+var_28C]
0x1800e1d62  xor     r9d, r9d
0x1800e1d65  mov     [rsp+2D0h+var_2A0], rax
0x1800e1d6a  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e1d71  lea     rax, [rsp+2D0h+var_290]
0x1800e1d76  mov     [rsp+2D0h+var_2A8], 4
0x1800e1d7e  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e1d85  mov     [rsp+2D0h+var_2B0], rax
0x1800e1d8a  xor     ecx, ecx
0x1800e1d8c  call    CipGetRegistryValue
0x1800e1d91  mov     ebx, eax
0x1800e1d93  test    eax, eax
0x1800e1d95  js      short loc_1800E1DA2
0x1800e1d97  cmp     [rsp+2D0h+var_290], 1
0x1800e1d9c  jz      loc_1800E1E2E
0x1800e1da2  lea     rax, [rsp+2D0h+var_28C]
0x1800e1da7  xor     r9d, r9d
0x1800e1daa  mov     [rsp+2D0h+var_2A0], rax
0x1800e1daf  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e1db6  lea     rax, [rsp+2D0h+var_290]
0x1800e1dbb  mov     [rsp+2D0h+var_2A8], 4
0x1800e1dc3  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e1dca  mov     [rsp+2D0h+var_2B0], rax
0x1800e1dcf  lea     rcx, aAppmodelunlock; "AppModelUnlock"
0x1800e1dd6  call    CipGetRegistryValue
0x1800e1ddb  mov     ebx, eax
0x1800e1ddd  test    eax, eax
0x1800e1ddf  js      short loc_1800E1DE8
0x1800e1de1  cmp     [rsp+2D0h+var_290], 1
0x1800e1de6  jz      short loc_1800E1E2E
0x1800e1de8  lea     rax, [rsp+2D0h+var_28C]
0x1800e1ded  xor     r9d, r9d
0x1800e1df0  mov     [rsp+2D0h+var_2A0], rax
0x1800e1df5  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e1dfc  lea     rax, [rsp+2D0h+var_290]
0x1800e1e01  mov     [rsp+2D0h+var_2A8], 4
0x1800e1e09  lea     rdx, aRegistryMachin_25; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1800e1e10  mov     [rsp+2D0h+var_2B0], rax
0x1800e1e15  lea     rcx, aAppxpolicies; "AppxPolicies"
0x1800e1e1c  call    CipGetRegistryValue
0x1800e1e21  mov     ebx, eax
0x1800e1e23  test    eax, eax
0x1800e1e25  js      short loc_1800E1E31
0x1800e1e27  cmp     [rsp+2D0h+var_290], 1
0x1800e1e2c  jnz     short loc_1800E1E31
0x1800e1e2e  mov     byte ptr [rdi], 1
0x1800e1e31  mov     eax, ebx
0x1800e1e33  mov     rcx, [rbp+1D0h+var_30]
0x1800e1e3a  xor     rcx, rsp; StackCookie
0x1800e1e3d  call    __security_check_cookie
0x1800e1e42  add     rsp, 2B8h
0x1800e1e49  pop     rdi
0x1800e1e4a  pop     rsi
0x1800e1e4b  pop     rbx
0x1800e1e4c  pop     rbp
0x1800e1e4d  retn
```
