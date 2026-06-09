# KappxpQueryNormalizedPackageRepositoryDirPaths

- ea: `0x18000c850`
- end: `0x18000cb22`
- name: `KappxpQueryNormalizedPackageRepositoryDirPaths`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c800`

## callees

- `0x18000c850`
- `0x18001f7b0`
- `0x18001f854`
- `0x18002bf20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000c8eb`
- `ntoskrnl!ExAllocatePool2` at `0x18000c8eb`
- `ntoskrnl!ZwQueryValueKey` at `0x18000ca42`
- `ntoskrnl!ZwQueryValueKey` at `0x18000ca42`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c961`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c961`
- `ntoskrnl!ZwClose` at `0x18000ca55`
- `ntoskrnl!ZwClose` at `0x18000cac5`
- `ntoskrnl!ZwClose` at `0x18000ca55`
- `ntoskrnl!ZwClose` at `0x18000cac5`
- `ntoskrnl!ZwOpenKey` at `0x18000c94a`
- `ntoskrnl!ZwOpenKey` at `0x18000ca07`
- `ntoskrnl!ZwOpenKey` at `0x18000c94a`
- `ntoskrnl!ZwOpenKey` at `0x18000ca07`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c9a2`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c9a2`

## string_xrefs

- `0x18000c889`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Appx\CodeIntegrity\Roots`

## pseudocode

```c
__int64 __fastcall KappxpQueryNormalizedPackageRepositoryDirPaths(_QWORD *a1)
{
  _QWORD *Pool2; // rax
  _QWORD *v3; // rsi
  NTSTATUS v5; // ebx
  ULONG v6; // edi
  __int64 v7; // rcx
  int v8; // edi
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v15; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v17; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE KeyInformation[12]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v19; // [rsp+CCh] [rbp-34h]
  __int64 v20; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v22; // [rsp+E4h] [rbp-1Ch]
  int v23; // [rsp+E8h] [rbp-18h]
  __int64 v24; // [rsp+ECh] [rbp-14h]

  v14[0] = 11141288;
  *(_QWORD *)&ValueName.Length = 655368;
  v14[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Appx\\CodeIntegrity\\Roots";
  ValueName.Buffer = L"Path";
  KeyHandle = 0;
  Handle = 0;
  ResultLength = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, 44);
  v15 = 0;
  v17 = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8, 1483763777);
  v3 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *Pool2 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
  if ( v5 < 0 )
  {
    ExFreePoolWithTag(v3, 0x58707041u);
    return (unsigned int)v5;
  }
  v6 = 0;
  ResultLength = 0;
  while ( !v5 )
  {
    v5 = ZwEnumerateKey(KeyHandle, v6, KeyBasicInformation, KeyInformation, 0x1Eu, &ResultLength);
    if ( v5 < 0 )
      break;
    LOWORD(v15) = v19;
    WORD1(v15) = v19;
    ObjectAttributes.Length = 48;
    *((_QWORD *)&v15 + 1) = &v20;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v15;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenKey(&Handle, 0x2000000u, &ObjectAttributes);
    if ( v5 < 0 )
      break;
    v5 = ZwQueryValueKey(Handle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x210u, &ResultLength);
    ZwClose(Handle);
    if ( v5 < 0 )
      break;
    if ( v22 != 1 || (unsigned int)v24 < 4 )
    {
      v5 = -1073739509;
      break;
    }
    LOWORD(v17) = v24 - 2;
    WORD1(v17) = v24 - 2;
    *((_QWORD *)&v17 + 1) = &KeyValueInformation[v23];
    v5 = KappxpGeneratePackageRootDirectoryEntry(&v17, &v12);
    if ( v5 < 0 )
      break;
    v7 = v12 + 16;
    ++v6;
    *(_QWORD *)(v12 + 16) = *v3;
    *v3 = v7;
  }
  ZwClose(KeyHandle);
  v8 = 0;
  if ( v5 != -2147483622 )
    v8 = v5;
  if ( *v3 )
  {
    if ( v8 >= 0 )
    {
      *a1 = v3;
      return (unsigned int)v8;
    }
  }
  else
  {
    v8 = -1073741772;
  }
  KappxpFreeRepositoryList(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c850  mov     [rsp-8+arg_8], rbx
0x18000c855  mov     [rsp-8+arg_10], rsi
0x18000c85a  push    rbp
0x18000c85b  push    rdi
0x18000c85c  push    r14
0x18000c85e  lea     rbp, [rsp-200h]
0x18000c866  sub     rsp, 300h
0x18000c86d  mov     rax, cs:__security_cookie
0x18000c874  xor     rax, rsp
0x18000c877  mov     [rbp+210h+var_20], rax
0x18000c87e  xorps   xmm0, xmm0
0x18000c881  mov     [rbp+210h+var_290], 0AA00A8h
0x18000c889  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18000c890  mov     qword ptr [rbp+210h+ValueName.Length], 0A0008h
0x18000c898  mov     [rbp+210h+var_288], rax
0x18000c89c  mov     r14, rcx
0x18000c89f  lea     rax, aPath; "Path"
0x18000c8a6  xorps   xmm1, xmm1
0x18000c8a9  mov     [rbp+210h+ValueName.Buffer], rax
0x18000c8ad  mov     edi, 58707041h
0x18000c8b2  xor     eax, eax
0x18000c8b4  mov     edx, 8
0x18000c8b9  movups  xmmword ptr [rsp+310h+ObjectAttributes.ObjectName], xmm0
0x18000c8be  mov     r8d, edi
0x18000c8c1  mov     [rsp+310h+KeyHandle], rax
0x18000c8c6  mov     ecx, 100h
0x18000c8cb  mov     [rsp+310h+Handle], rax
0x18000c8d0  mov     [rsp+310h+var_2E0], eax
0x18000c8d4  mov     [rsp+310h+var_2C8], rax
0x18000c8d9  movups  xmmword ptr [rsp+310h+ObjectAttributes.Length], xmm0
0x18000c8de  movups  xmmword ptr [rsp+310h+ObjectAttributes+1Ch], xmm0
0x18000c8e3  movups  [rbp+210h+var_280], xmm0
0x18000c8e7  movups  [rbp+210h+var_260], xmm1
0x18000c8eb  call    cs:__imp_ExAllocatePool2
0x18000c8f2  nop     dword ptr [rax+rax+00h]
0x18000c8f7  mov     rsi, rax
0x18000c8fa  test    rax, rax
0x18000c8fd  jnz     short loc_18000C909
0x18000c8ff  mov     eax, 0C0000017h
0x18000c904  jmp     loc_18000CAF1
0x18000c909  mov     qword ptr [rax], 0
0x18000c910  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x18000c915  lea     rax, [rbp+210h+var_290]
0x18000c919  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x18000c921  xorps   xmm0, xmm0
0x18000c924  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x18000c929  mov     edx, 2000000h; DesiredAccess
0x18000c92e  mov     [rsp+310h+ObjectAttributes.RootDirectory], 0
0x18000c937  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18000c93c  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x18000c944  movdqu  xmmword ptr [rsp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c94a  call    cs:__imp_ZwOpenKey
0x18000c951  nop     dword ptr [rax+rax+00h]
0x18000c956  mov     ebx, eax
0x18000c958  test    eax, eax
0x18000c95a  jns     short loc_18000C974
0x18000c95c  mov     edx, edi; Tag
0x18000c95e  mov     rcx, rsi; P
0x18000c961  call    cs:__imp_ExFreePoolWithTag
0x18000c968  nop     dword ptr [rax+rax+00h]
0x18000c96d  mov     eax, ebx
0x18000c96f  jmp     loc_18000CAF1
0x18000c974  xor     edi, edi
0x18000c976  mov     [rsp+310h+var_2E0], edi
0x18000c97a  test    ebx, ebx
0x18000c97c  jnz     loc_18000CAC0
0x18000c982  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18000c987  lea     rax, [rsp+310h+var_2E0]
0x18000c98c  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18000c991  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x18000c995  xor     r8d, r8d; KeyInformationClass
0x18000c998  mov     [rsp+310h+Length], 1Eh; Length
0x18000c9a0  mov     edx, edi; Index
0x18000c9a2  call    cs:__imp_ZwEnumerateKey
0x18000c9a9  nop     dword ptr [rax+rax+00h]
0x18000c9ae  mov     ebx, eax
0x18000c9b0  test    eax, eax
0x18000c9b2  js      loc_18000CAC0
0x18000c9b8  mov     rax, [rbp+210h+var_244]
0x18000c9bc  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x18000c9c1  mov     word ptr [rbp+210h+var_280], ax
0x18000c9c5  lea     rcx, [rsp+310h+Handle]; KeyHandle
0x18000c9ca  mov     word ptr [rbp+210h+var_280+2], ax
0x18000c9ce  xorps   xmm0, xmm0
0x18000c9d1  lea     rax, [rbp+210h+var_244+4]
0x18000c9d5  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x18000c9dd  mov     qword ptr [rbp+210h+var_280+8], rax
0x18000c9e1  mov     edx, 2000000h; DesiredAccess
0x18000c9e6  mov     rax, [rsp+310h+KeyHandle]
0x18000c9eb  mov     [rsp+310h+ObjectAttributes.RootDirectory], rax
0x18000c9f0  lea     rax, [rbp+210h+var_280]
0x18000c9f4  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x18000c9f9  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x18000ca01  movdqu  xmmword ptr [rsp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ca07  call    cs:__imp_ZwOpenKey
0x18000ca0e  nop     dword ptr [rax+rax+00h]
0x18000ca13  mov     ebx, eax
0x18000ca15  test    eax, eax
0x18000ca17  js      loc_18000CAC0
0x18000ca1d  mov     rcx, [rsp+310h+Handle]; KeyHandle
0x18000ca22  lea     rax, [rsp+310h+var_2E0]
0x18000ca27  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18000ca2c  lea     r9, [rbp+210h+KeyValueInformation]; KeyValueInformation
0x18000ca30  mov     r8d, 1; KeyValueInformationClass
0x18000ca36  mov     [rsp+310h+Length], 210h; Length
0x18000ca3e  lea     rdx, [rbp+210h+ValueName]; ValueName
0x18000ca42  call    cs:__imp_ZwQueryValueKey
0x18000ca49  nop     dword ptr [rax+rax+00h]
0x18000ca4e  mov     rcx, [rsp+310h+Handle]; Handle
0x18000ca53  mov     ebx, eax
0x18000ca55  call    cs:__imp_ZwClose
0x18000ca5c  nop     dword ptr [rax+rax+00h]
0x18000ca61  test    ebx, ebx
0x18000ca63  js      short loc_18000CAC0
0x18000ca65  cmp     [rbp+210h+var_22C], 1
0x18000ca69  jnz     short loc_18000CABB
0x18000ca6b  mov     rax, [rbp+210h+var_224]
0x18000ca6f  cmp     eax, 4
0x18000ca72  jb      short loc_18000CABB
0x18000ca74  sub     ax, 2
0x18000ca78  lea     rcx, [rbp+210h+KeyValueInformation]
0x18000ca7c  mov     word ptr [rbp+210h+var_260], ax
0x18000ca80  lea     rdx, [rsp+310h+var_2C8]
0x18000ca85  mov     word ptr [rbp+210h+var_260+2], ax
0x18000ca89  mov     eax, [rbp+210h+var_228]
0x18000ca8c  add     rcx, rax
0x18000ca8f  mov     qword ptr [rbp+210h+var_260+8], rcx
0x18000ca93  lea     rcx, [rbp+210h+var_260]
0x18000ca97  call    KappxpGeneratePackageRootDirectoryEntry
0x18000ca9c  mov     ebx, eax
0x18000ca9e  test    eax, eax
0x18000caa0  js      short loc_18000CAC0
0x18000caa2  mov     rax, [rsi]
0x18000caa5  mov     rcx, [rsp+310h+var_2C8]
0x18000caaa  add     rcx, 10h
0x18000caae  inc     edi
0x18000cab0  mov     [rcx], rax
0x18000cab3  mov     [rsi], rcx
0x18000cab6  jmp     loc_18000C97A
0x18000cabb  mov     ebx, 0C000090Bh
0x18000cac0  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x18000cac5  call    cs:__imp_ZwClose
0x18000cacc  nop     dword ptr [rax+rax+00h]
0x18000cad1  xor     edi, edi
0x18000cad3  cmp     ebx, 8000001Ah
0x18000cad9  cmovnz  edi, ebx
0x18000cadc  cmp     qword ptr [rsi], 0
0x18000cae0  jnz     short loc_18000CB19
0x18000cae2  mov     edi, 0C0000034h
0x18000cae7  mov     rcx, rsi; P
0x18000caea  call    KappxpFreeRepositoryList
0x18000caef  mov     eax, edi
0x18000caf1  mov     rcx, [rbp+210h+var_20]
0x18000caf8  xor     rcx, rsp; StackCookie
0x18000cafb  call    __security_check_cookie
0x18000cb00  lea     r11, [rsp+310h+var_10]
0x18000cb08  mov     rbx, [r11+28h]
0x18000cb0c  mov     rsi, [r11+30h]
0x18000cb10  mov     rsp, r11
0x18000cb13  pop     r14
0x18000cb15  pop     rdi
0x18000cb16  pop     rbp
0x18000cb17  retn
0x18000cb19  test    edi, edi
0x18000cb1b  js      short loc_18000CAE7
0x18000cb1d  mov     [r14], rsi
0x18000cb20  jmp     short loc_18000CAEF
```
