# CipIsDeveloperModeEnabled

- ea: `0x1800e2be0`
- end: `0x1800e2e3f`
- name: `CipIsDeveloperModeEnabled`
- size: `607`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e6d64`
- `0x1800e7584`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18005abe8`
- `0x1800e2be0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800e2d2c`
- `ntoskrnl!ZwClose` at `0x1800e2d2c`
- `ntoskrnl!ZwOpenKey` at `0x1800e2d15`
- `ntoskrnl!ZwOpenKey` at `0x1800e2d15`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e2d3d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1800e2d3d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e2c6d`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1800e2c6d`

## string_xrefs

- `0x1800e2c46`: `\REGISTRY\Machine\SYSTEM\CurrentControlSet\Control\CI\Developer\DeveloperUnlock`
- `0x1800e2d6e`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e2db3`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModelUnlock`
- `0x1800e2df9`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows\Appx`

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
0x1800e2be0  push    rbp
0x1800e2be2  push    rbx
0x1800e2be3  push    rsi
0x1800e2be4  push    rdi
0x1800e2be5  lea     rbp, [rsp-1B8h]
0x1800e2bed  sub     rsp, 2B8h
0x1800e2bf4  mov     rax, cs:__security_cookie
0x1800e2bfb  xor     rax, rsp
0x1800e2bfe  mov     [rbp+1D0h+var_30], rax
0x1800e2c05  xorps   xmm0, xmm0
0x1800e2c08  mov     rdi, rcx
0x1800e2c0b  mov     ebx, 20Ah
0x1800e2c10  lea     rcx, [rbp+1D0h+var_240]; void *
0x1800e2c14  xor     esi, esi
0x1800e2c16  mov     r8d, ebx; Size
0x1800e2c19  xor     edx, edx; Val
0x1800e2c1b  mov     [rsp+2D0h+KeyHandle], rsi
0x1800e2c20  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x1800e2c25  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x1800e2c2a  movups  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2c2e  movups  [rsp+2D0h+var_280], xmm0
0x1800e2c33  call    memset
0x1800e2c38  lea     rax, [rsp+2D0h+var_28C]
0x1800e2c3d  mov     [rsp+2D0h+var_28C], esi
0x1800e2c41  mov     [rsp+2D0h+var_2A0], rax
0x1800e2c46  lea     r8, aRegistryMachin_18; "\\REGISTRY\\Machine\\SYSTEM\\CurrentCon"...
0x1800e2c4d  lea     rax, [rbp+1D0h+var_240]
0x1800e2c51  mov     [rsp+2D0h+var_2A8], ebx
0x1800e2c55  xor     r9d, r9d
0x1800e2c58  mov     [rsp+2D0h+var_2B0], rax
0x1800e2c5d  xor     edx, edx
0x1800e2c5f  mov     [rsp+2D0h+var_290], esi
0x1800e2c63  lea     rcx, aCideveloper; "CIDeveloper"
0x1800e2c6a  mov     [rdi], sil
0x1800e2c6d  call    cs:__imp_RtlGetPersistedStateLocation
0x1800e2c74  nop     dword ptr [rax+rax+00h]
0x1800e2c79  mov     ebx, eax
0x1800e2c7b  test    eax, eax
0x1800e2c7d  js      loc_1800E2E21
0x1800e2c83  xorps   xmm0, xmm0
0x1800e2c86  lea     rax, [rbp+1D0h+var_240]
0x1800e2c8a  movups  [rsp+2D0h+var_280], xmm0
0x1800e2c8f  mov     ecx, 7FFFh
0x1800e2c94  lea     edx, [rsi+2]
0x1800e2c97  cmp     [rax], si
0x1800e2c9a  jz      short loc_1800E2CA5
0x1800e2c9c  add     rax, rdx
0x1800e2c9f  sub     rcx, 1
0x1800e2ca3  jnz     short loc_1800E2C97
0x1800e2ca5  mov     rax, rcx
0x1800e2ca8  neg     rax
0x1800e2cab  sbb     ebx, ebx
0x1800e2cad  not     ebx
0x1800e2caf  and     ebx, 0C000000Dh
0x1800e2cb5  test    rcx, rcx
0x1800e2cb8  jz      loc_1800E2E21
0x1800e2cbe  add     cx, cx
0x1800e2cc1  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x1800e2cc9  mov     eax, 0FFFEh
0x1800e2cce  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rsi
0x1800e2cd3  sub     ax, cx
0x1800e2cd6  mov     [rsp+2D0h+ObjectAttributes.Attributes], 240h
0x1800e2cde  mov     word ptr [rsp+2D0h+var_280], ax
0x1800e2ce3  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x1800e2ce8  add     ax, dx
0x1800e2ceb  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800e2cf0  mov     word ptr [rsp+2D0h+var_280+2], ax
0x1800e2cf5  xorps   xmm0, xmm0
0x1800e2cf8  lea     rax, [rbp+1D0h+var_240]
0x1800e2cfc  mov     edx, 20019h; DesiredAccess
0x1800e2d01  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x1800e2d06  lea     rax, [rsp+2D0h+var_280]
0x1800e2d0b  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x1800e2d10  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2d15  call    cs:__imp_ZwOpenKey
0x1800e2d1c  nop     dword ptr [rax+rax+00h]
0x1800e2d21  mov     ebx, eax
0x1800e2d23  test    eax, eax
0x1800e2d25  js      short loc_1800E2D3D
0x1800e2d27  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1800e2d2c  call    cs:__imp_ZwClose
0x1800e2d33  nop     dword ptr [rax+rax+00h]
0x1800e2d38  jmp     loc_1800E2E1E
0x1800e2d3d  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800e2d44  nop     dword ptr [rax+rax+00h]
0x1800e2d49  test    al, al
0x1800e2d4b  jz      short loc_1800E2D92
0x1800e2d4d  lea     rax, [rsp+2D0h+var_28C]
0x1800e2d52  xor     r9d, r9d
0x1800e2d55  mov     [rsp+2D0h+var_2A0], rax
0x1800e2d5a  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2d61  lea     rax, [rsp+2D0h+var_290]
0x1800e2d66  mov     [rsp+2D0h+var_2A8], 4
0x1800e2d6e  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e2d75  mov     [rsp+2D0h+var_2B0], rax
0x1800e2d7a  xor     ecx, ecx
0x1800e2d7c  call    CipGetRegistryValue
0x1800e2d81  mov     ebx, eax
0x1800e2d83  test    eax, eax
0x1800e2d85  js      short loc_1800E2D92
0x1800e2d87  cmp     [rsp+2D0h+var_290], 1
0x1800e2d8c  jz      loc_1800E2E1E
0x1800e2d92  lea     rax, [rsp+2D0h+var_28C]
0x1800e2d97  xor     r9d, r9d
0x1800e2d9a  mov     [rsp+2D0h+var_2A0], rax
0x1800e2d9f  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2da6  lea     rax, [rsp+2D0h+var_290]
0x1800e2dab  mov     [rsp+2D0h+var_2A8], 4
0x1800e2db3  lea     rdx, aRegistryMachin_12; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800e2dba  mov     [rsp+2D0h+var_2B0], rax
0x1800e2dbf  lea     rcx, aAppmodelunlock; "AppModelUnlock"
0x1800e2dc6  call    CipGetRegistryValue
0x1800e2dcb  mov     ebx, eax
0x1800e2dcd  test    eax, eax
0x1800e2dcf  js      short loc_1800E2DD8
0x1800e2dd1  cmp     [rsp+2D0h+var_290], 1
0x1800e2dd6  jz      short loc_1800E2E1E
0x1800e2dd8  lea     rax, [rsp+2D0h+var_28C]
0x1800e2ddd  xor     r9d, r9d
0x1800e2de0  mov     [rsp+2D0h+var_2A0], rax
0x1800e2de5  lea     r8, aAllowdevelopme; "AllowDevelopmentWithoutDevLicense"
0x1800e2dec  lea     rax, [rsp+2D0h+var_290]
0x1800e2df1  mov     [rsp+2D0h+var_2A8], 4
0x1800e2df9  lea     rdx, aRegistryMachin_24; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1800e2e00  mov     [rsp+2D0h+var_2B0], rax
0x1800e2e05  lea     rcx, aAppxpolicies; "AppxPolicies"
0x1800e2e0c  call    CipGetRegistryValue
0x1800e2e11  mov     ebx, eax
0x1800e2e13  test    eax, eax
0x1800e2e15  js      short loc_1800E2E21
0x1800e2e17  cmp     [rsp+2D0h+var_290], 1
0x1800e2e1c  jnz     short loc_1800E2E21
0x1800e2e1e  mov     byte ptr [rdi], 1
0x1800e2e21  mov     eax, ebx
0x1800e2e23  mov     rcx, [rbp+1D0h+var_30]
0x1800e2e2a  xor     rcx, rsp; StackCookie
0x1800e2e2d  call    __security_check_cookie
0x1800e2e32  add     rsp, 2B8h
0x1800e2e39  pop     rdi
0x1800e2e3a  pop     rsi
0x1800e2e3b  pop     rbx
0x1800e2e3c  pop     rbp
0x1800e2e3d  retn
```
