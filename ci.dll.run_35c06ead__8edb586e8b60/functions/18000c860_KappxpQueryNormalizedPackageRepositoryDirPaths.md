# KappxpQueryNormalizedPackageRepositoryDirPaths

- ea: `0x18000c860`
- end: `0x18000cb32`
- name: `KappxpQueryNormalizedPackageRepositoryDirPaths`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c810`

## callees

- `0x18000c860`
- `0x18001f880`
- `0x18001f924`
- `0x18002c0d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000c8fb`
- `ntoskrnl!ExAllocatePool2` at `0x18000c8fb`
- `ntoskrnl!ZwQueryValueKey` at `0x18000ca52`
- `ntoskrnl!ZwQueryValueKey` at `0x18000ca52`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c971`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000c971`
- `ntoskrnl!ZwClose` at `0x18000ca65`
- `ntoskrnl!ZwClose` at `0x18000cad5`
- `ntoskrnl!ZwClose` at `0x18000ca65`
- `ntoskrnl!ZwClose` at `0x18000cad5`
- `ntoskrnl!ZwOpenKey` at `0x18000c95a`
- `ntoskrnl!ZwOpenKey` at `0x18000ca17`
- `ntoskrnl!ZwOpenKey` at `0x18000c95a`
- `ntoskrnl!ZwOpenKey` at `0x18000ca17`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c9b2`
- `ntoskrnl!ZwEnumerateKey` at `0x18000c9b2`

## string_xrefs

- `0x18000c899`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Appx\CodeIntegrity\Roots`

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
0x18000c860  mov     [rsp-8+arg_8], rbx
0x18000c865  mov     [rsp-8+arg_10], rsi
0x18000c86a  push    rbp
0x18000c86b  push    rdi
0x18000c86c  push    r14
0x18000c86e  lea     rbp, [rsp-200h]
0x18000c876  sub     rsp, 300h
0x18000c87d  mov     rax, cs:__security_cookie
0x18000c884  xor     rax, rsp
0x18000c887  mov     [rbp+210h+var_20], rax
0x18000c88e  xorps   xmm0, xmm0
0x18000c891  mov     [rbp+210h+var_290], 0AA00A8h
0x18000c899  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18000c8a0  mov     qword ptr [rbp+210h+ValueName.Length], 0A0008h
0x18000c8a8  mov     [rbp+210h+var_288], rax
0x18000c8ac  mov     r14, rcx
0x18000c8af  lea     rax, aPath; "Path"
0x18000c8b6  xorps   xmm1, xmm1
0x18000c8b9  mov     [rbp+210h+ValueName.Buffer], rax
0x18000c8bd  mov     edi, 58707041h
0x18000c8c2  xor     eax, eax
0x18000c8c4  mov     edx, 8
0x18000c8c9  movups  xmmword ptr [rsp+310h+ObjectAttributes.ObjectName], xmm0
0x18000c8ce  mov     r8d, edi
0x18000c8d1  mov     [rsp+310h+KeyHandle], rax
0x18000c8d6  mov     ecx, 100h
0x18000c8db  mov     [rsp+310h+Handle], rax
0x18000c8e0  mov     [rsp+310h+var_2E0], eax
0x18000c8e4  mov     [rsp+310h+var_2C8], rax
0x18000c8e9  movups  xmmword ptr [rsp+310h+ObjectAttributes.Length], xmm0
0x18000c8ee  movups  xmmword ptr [rsp+310h+ObjectAttributes+1Ch], xmm0
0x18000c8f3  movups  [rbp+210h+var_280], xmm0
0x18000c8f7  movups  [rbp+210h+var_260], xmm1
0x18000c8fb  call    cs:__imp_ExAllocatePool2
0x18000c902  nop     dword ptr [rax+rax+00h]
0x18000c907  mov     rsi, rax
0x18000c90a  test    rax, rax
0x18000c90d  jnz     short loc_18000C919
0x18000c90f  mov     eax, 0C0000017h
0x18000c914  jmp     loc_18000CB01
0x18000c919  mov     qword ptr [rax], 0
0x18000c920  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x18000c925  lea     rax, [rbp+210h+var_290]
0x18000c929  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x18000c931  xorps   xmm0, xmm0
0x18000c934  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x18000c939  mov     edx, 2000000h; DesiredAccess
0x18000c93e  mov     [rsp+310h+ObjectAttributes.RootDirectory], 0
0x18000c947  lea     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18000c94c  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x18000c954  movdqu  xmmword ptr [rsp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c95a  call    cs:__imp_ZwOpenKey
0x18000c961  nop     dword ptr [rax+rax+00h]
0x18000c966  mov     ebx, eax
0x18000c968  test    eax, eax
0x18000c96a  jns     short loc_18000C984
0x18000c96c  mov     edx, edi; Tag
0x18000c96e  mov     rcx, rsi; P
0x18000c971  call    cs:__imp_ExFreePoolWithTag
0x18000c978  nop     dword ptr [rax+rax+00h]
0x18000c97d  mov     eax, ebx
0x18000c97f  jmp     loc_18000CB01
0x18000c984  xor     edi, edi
0x18000c986  mov     [rsp+310h+var_2E0], edi
0x18000c98a  test    ebx, ebx
0x18000c98c  jnz     loc_18000CAD0
0x18000c992  mov     rcx, [rsp+310h+KeyHandle]; KeyHandle
0x18000c997  lea     rax, [rsp+310h+var_2E0]
0x18000c99c  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18000c9a1  lea     r9, [rbp+210h+KeyInformation]; KeyInformation
0x18000c9a5  xor     r8d, r8d; KeyInformationClass
0x18000c9a8  mov     [rsp+310h+Length], 1Eh; Length
0x18000c9b0  mov     edx, edi; Index
0x18000c9b2  call    cs:__imp_ZwEnumerateKey
0x18000c9b9  nop     dword ptr [rax+rax+00h]
0x18000c9be  mov     ebx, eax
0x18000c9c0  test    eax, eax
0x18000c9c2  js      loc_18000CAD0
0x18000c9c8  mov     rax, [rbp+210h+var_244]
0x18000c9cc  lea     r8, [rsp+310h+ObjectAttributes]; ObjectAttributes
0x18000c9d1  mov     word ptr [rbp+210h+var_280], ax
0x18000c9d5  lea     rcx, [rsp+310h+Handle]; KeyHandle
0x18000c9da  mov     word ptr [rbp+210h+var_280+2], ax
0x18000c9de  xorps   xmm0, xmm0
0x18000c9e1  lea     rax, [rbp+210h+var_244+4]
0x18000c9e5  mov     [rsp+310h+ObjectAttributes.Length], 30h ; '0'
0x18000c9ed  mov     qword ptr [rbp+210h+var_280+8], rax
0x18000c9f1  mov     edx, 2000000h; DesiredAccess
0x18000c9f6  mov     rax, [rsp+310h+KeyHandle]
0x18000c9fb  mov     [rsp+310h+ObjectAttributes.RootDirectory], rax
0x18000ca00  lea     rax, [rbp+210h+var_280]
0x18000ca04  mov     [rsp+310h+ObjectAttributes.ObjectName], rax
0x18000ca09  mov     [rsp+310h+ObjectAttributes.Attributes], 240h
0x18000ca11  movdqu  xmmword ptr [rsp+310h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ca17  call    cs:__imp_ZwOpenKey
0x18000ca1e  nop     dword ptr [rax+rax+00h]
0x18000ca23  mov     ebx, eax
0x18000ca25  test    eax, eax
0x18000ca27  js      loc_18000CAD0
0x18000ca2d  mov     rcx, [rsp+310h+Handle]; KeyHandle
0x18000ca32  lea     rax, [rsp+310h+var_2E0]
0x18000ca37  mov     [rsp+310h+ResultLength], rax; ResultLength
0x18000ca3c  lea     r9, [rbp+210h+KeyValueInformation]; KeyValueInformation
0x18000ca40  mov     r8d, 1; KeyValueInformationClass
0x18000ca46  mov     [rsp+310h+Length], 210h; Length
0x18000ca4e  lea     rdx, [rbp+210h+ValueName]; ValueName
0x18000ca52  call    cs:__imp_ZwQueryValueKey
0x18000ca59  nop     dword ptr [rax+rax+00h]
0x18000ca5e  mov     rcx, [rsp+310h+Handle]; Handle
0x18000ca63  mov     ebx, eax
0x18000ca65  call    cs:__imp_ZwClose
0x18000ca6c  nop     dword ptr [rax+rax+00h]
0x18000ca71  test    ebx, ebx
0x18000ca73  js      short loc_18000CAD0
0x18000ca75  cmp     [rbp+210h+var_22C], 1
0x18000ca79  jnz     short loc_18000CACB
0x18000ca7b  mov     rax, [rbp+210h+var_224]
0x18000ca7f  cmp     eax, 4
0x18000ca82  jb      short loc_18000CACB
0x18000ca84  sub     ax, 2
0x18000ca88  lea     rcx, [rbp+210h+KeyValueInformation]
0x18000ca8c  mov     word ptr [rbp+210h+var_260], ax
0x18000ca90  lea     rdx, [rsp+310h+var_2C8]
0x18000ca95  mov     word ptr [rbp+210h+var_260+2], ax
0x18000ca99  mov     eax, [rbp+210h+var_228]
0x18000ca9c  add     rcx, rax
0x18000ca9f  mov     qword ptr [rbp+210h+var_260+8], rcx
0x18000caa3  lea     rcx, [rbp+210h+var_260]
0x18000caa7  call    KappxpGeneratePackageRootDirectoryEntry
0x18000caac  mov     ebx, eax
0x18000caae  test    eax, eax
0x18000cab0  js      short loc_18000CAD0
0x18000cab2  mov     rax, [rsi]
0x18000cab5  mov     rcx, [rsp+310h+var_2C8]
0x18000caba  add     rcx, 10h
0x18000cabe  inc     edi
0x18000cac0  mov     [rcx], rax
0x18000cac3  mov     [rsi], rcx
0x18000cac6  jmp     loc_18000C98A
0x18000cacb  mov     ebx, 0C000090Bh
0x18000cad0  mov     rcx, [rsp+310h+KeyHandle]; Handle
0x18000cad5  call    cs:__imp_ZwClose
0x18000cadc  nop     dword ptr [rax+rax+00h]
0x18000cae1  xor     edi, edi
0x18000cae3  cmp     ebx, 8000001Ah
0x18000cae9  cmovnz  edi, ebx
0x18000caec  cmp     qword ptr [rsi], 0
0x18000caf0  jnz     short loc_18000CB29
0x18000caf2  mov     edi, 0C0000034h
0x18000caf7  mov     rcx, rsi; P
0x18000cafa  call    KappxpFreeRepositoryList
0x18000caff  mov     eax, edi
0x18000cb01  mov     rcx, [rbp+210h+var_20]
0x18000cb08  xor     rcx, rsp; StackCookie
0x18000cb0b  call    __security_check_cookie
0x18000cb10  lea     r11, [rsp+310h+var_10]
0x18000cb18  mov     rbx, [r11+28h]
0x18000cb1c  mov     rsi, [r11+30h]
0x18000cb20  mov     rsp, r11
0x18000cb23  pop     r14
0x18000cb25  pop     rdi
0x18000cb26  pop     rbp
0x18000cb27  retn
0x18000cb29  test    edi, edi
0x18000cb2b  js      short loc_18000CAF7
0x18000cb2d  mov     [r14], rsi
0x18000cb30  jmp     short loc_18000CAFF
```
