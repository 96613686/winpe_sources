# SmbCeGetOperatingSystemInformation

- ea: `0x14003c184`
- end: `0x14003c61e`
- name: `SmbCeGetOperatingSystemInformation`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140081b28`

## callees

- `0x14003c184`
- `0x140059dc0`
- `0x140059f00`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x14003c3a1`
- `ntoskrnl!_wcsnicmp` at `0x14003c3a1`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c324`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c374`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c426`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c542`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c324`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c374`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c426`
- `ntoskrnl!ZwQueryValueKey` at `0x14003c542`
- `ntoskrnl!ZwOpenKey` at `0x14003c2d8`
- `ntoskrnl!ZwOpenKey` at `0x14003c2d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c290`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c2f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c346`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c3d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c50d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c290`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c2f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c346`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c3d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003c50d`
- `ntoskrnl!ExAllocatePool2` at `0x14003c471`
- `ntoskrnl!ExAllocatePool2` at `0x14003c582`
- `ntoskrnl!ExAllocatePool2` at `0x14003c471`
- `ntoskrnl!ExAllocatePool2` at `0x14003c582`
- `ntoskrnl!ZwClose` at `0x14003c5eb`
- `ntoskrnl!ZwClose` at `0x14003c5eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c235`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c265`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c235`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c265`

## string_xrefs

- `0x14003c27e`: `\REGISTRY\Machine\Software\Microsoft\Windows Nt\CurrentVersion`

## pseudocode

```c
NTSTATUS SmbCeGetOperatingSystemInformation()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  unsigned int v2; // ebx
  NTSTATUS v3; // edi
  unsigned int v4; // edx
  wchar_t *Pool2; // rax
  __int64 v6; // rdx
  wchar_t *v7; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD KeyValueInformation[3]; // [rsp+80h] [rbp-80h] BYREF
  size_t v13[66]; // [rsp+B0h] [rbp-50h] BYREF
  size_t v14[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v15; // [rsp+2D0h] [rbp+1D0h]
  __int128 v16; // [rsp+2E0h] [rbp+1E0h]
  size_t v17[18]; // [rsp+2F0h] [rbp+1F0h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  *(_OWORD *)v14 = 0;
  v15 = 0;
  v16 = 0;
  memset(v13, 0, sizeof(v13));
  memset(v17, 0, sizeof(v17));
  if ( stru_140070F40.Buffer )
    ExFreePoolWithTag(stru_140070F40.Buffer, 0x6D536643u);
  stru_140070F40.Buffer = 0;
  *(_DWORD *)&stru_140070F40.Length = 0;
  if ( stru_140070F50.Buffer )
    ExFreePoolWithTag(stru_140070F50.Buffer, 0x6D536643u);
  stru_140070F50.Buffer = 0;
  *(_DWORD *)&stru_140070F50.Length = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\Machine\\Software\\Microsoft\\Windows Nt\\CurrentVersion");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"CurrentBuildNumber");
    v1 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x30u,
           &ResultLength);
    if ( v1 < 0 )
      goto LABEL_25;
    RtlInitUnicodeString(&DestinationString, L"ProductName");
    v1 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v13, 0x210u, &ResultLength);
    if ( v1 < 0 )
      goto LABEL_25;
    if ( LODWORD(v13[1]) > 0x14 && !_wcsnicmp((const wchar_t *)&v13[1] + 2, L"Microsoft ", 0xAu) )
    {
      memmove((char *)&v13[1] + 4, &v13[4], (unsigned int)(LODWORD(v13[1]) - 20));
      LODWORD(v13[1]) -= 20;
    }
    RtlInitUnicodeString(&DestinationString, L"CSDVersion");
    v2 = LODWORD(v13[1]) + DWORD2(KeyValueInformation[0]);
    if ( (unsigned int)(LODWORD(v13[1]) + DWORD2(KeyValueInformation[0])) >= LODWORD(v13[1]) && v2 <= 0xFFFF )
    {
      v3 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v17, 0x90u, &ResultLength);
      if ( v3 < 0 || (v4 = v2 + LODWORD(v17[1]), v2 + LODWORD(v17[1]) >= v2) && (v2 += LODWORD(v17[1]), v4 <= 0xFFFF) )
      {
        stru_140070F40.MaximumLength = v2;
        stru_140070F40.Length = v2;
        Pool2 = (wchar_t *)ExAllocatePool2(258, v2, 1834182211);
        stru_140070F40.Buffer = Pool2;
        if ( !Pool2 )
          goto LABEL_23;
        memmove(Pool2, (char *)&v13[1] + 4, LODWORD(v13[1]));
        *(wchar_t *)((char *)stru_140070F40.Buffer + LODWORD(v13[1]) - 2) = 32;
        memmove(
          (char *)stru_140070F40.Buffer + LODWORD(v13[1]),
          (char *)KeyValueInformation + 12,
          DWORD2(KeyValueInformation[0]));
        if ( v3 >= 0 )
        {
          *(wchar_t *)((char *)stru_140070F40.Buffer + DWORD2(KeyValueInformation[0]) + LODWORD(v13[1]) - 2) = 32;
          memmove(
            (char *)stru_140070F40.Buffer + DWORD2(KeyValueInformation[0]) + LODWORD(v13[1]),
            (char *)&v17[1] + 4,
            LODWORD(v17[1]));
        }
        RtlInitUnicodeString(&DestinationString, L"CurrentVersion");
        v1 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v14, 0x30u, &ResultLength);
        if ( v1 < 0 )
          goto LABEL_25;
        v6 = (unsigned int)(LODWORD(v13[1]) + LODWORD(v14[1]));
        if ( (unsigned int)v6 <= 0xFFFF )
        {
          stru_140070F50.MaximumLength = LOWORD(v13[1]) + LOWORD(v14[1]);
          stru_140070F50.Length = LOWORD(v13[1]) + LOWORD(v14[1]);
          v7 = (wchar_t *)ExAllocatePool2(258, v6, 1834182211);
          stru_140070F50.Buffer = v7;
          if ( v7 )
          {
            memmove(v7, (char *)&v13[1] + 4, LODWORD(v13[1]));
            *(wchar_t *)((char *)stru_140070F50.Buffer + LODWORD(v13[1]) - 2) = 32;
            memmove((char *)stru_140070F50.Buffer + LODWORD(v13[1]), (char *)&v14[1] + 4, LODWORD(v14[1]));
LABEL_25:
            ZwClose(KeyHandle);
            return v1;
          }
LABEL_23:
          v1 = -1073741670;
          goto LABEL_25;
        }
      }
    }
    v1 = -1073741811;
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x14003c184  mov     [rsp-8+arg_0], rbx
0x14003c189  mov     [rsp-8+arg_8], rdi
0x14003c18e  push    rbp
0x14003c18f  lea     rbp, [rsp-290h]
0x14003c197  sub     rsp, 390h
0x14003c19e  mov     rax, cs:__security_cookie
0x14003c1a5  xor     rax, rsp
0x14003c1a8  mov     [rbp+290h+var_10], rax
0x14003c1af  xorps   xmm0, xmm0
0x14003c1b2  mov     [rsp+390h+KeyHandle], 0
0x14003c1bb  xorps   xmm1, xmm1
0x14003c1be  mov     [rsp+390h+var_360], 0
0x14003c1c6  movups  xmmword ptr [rsp+390h+ObjectAttributes.ObjectName], xmm0
0x14003c1cb  mov     edi, 210h
0x14003c1d0  lea     rcx, [rbp+290h+var_2E0]; void *
0x14003c1d4  mov     r8d, edi; Size
0x14003c1d7  xor     eax, eax
0x14003c1d9  xor     edx, edx; Val
0x14003c1db  movups  xmmword ptr [rsp+390h+ObjectAttributes+1Ch], xmm0
0x14003c1e0  movups  xmmword ptr [rsp+390h+DestinationString.Length], xmm0
0x14003c1e5  movups  xmmword ptr [rsp+390h+ObjectAttributes.Length], xmm0
0x14003c1ea  movups  [rbp+290h+KeyValueInformation], xmm0
0x14003c1ee  movups  [rbp+290h+var_300], xmm0
0x14003c1f2  movups  [rbp+290h+var_2F0], xmm0
0x14003c1f6  movups  xmmword ptr [rbp+290h+var_D0], xmm1
0x14003c1fd  movups  [rbp+290h+var_C0], xmm1
0x14003c204  movups  [rbp+290h+var_B0], xmm1
0x14003c20b  call    memset
0x14003c210  xor     edx, edx; Val
0x14003c212  lea     rcx, [rbp+290h+var_A0]; void *
0x14003c219  mov     r8d, 90h; Size
0x14003c21f  call    memset
0x14003c224  mov     rcx, cs:stru_140070F40.Buffer; P
0x14003c22b  test    rcx, rcx
0x14003c22e  jz      short loc_14003C241
0x14003c230  mov     edx, 6D536643h; Tag
0x14003c235  call    cs:__imp_ExFreePoolWithTag
0x14003c23c  nop     dword ptr [rax+rax+00h]
0x14003c241  mov     rcx, cs:stru_140070F50.Buffer; P
0x14003c248  xor     eax, eax
0x14003c24a  mov     cs:stru_140070F40.Buffer, 0
0x14003c255  mov     dword ptr cs:stru_140070F40.Length, eax
0x14003c25b  test    rcx, rcx
0x14003c25e  jz      short loc_14003C271
0x14003c260  mov     edx, 6D536643h; Tag
0x14003c265  call    cs:__imp_ExFreePoolWithTag
0x14003c26c  nop     dword ptr [rax+rax+00h]
0x14003c271  xor     eax, eax
0x14003c273  mov     cs:stru_140070F50.Buffer, 0
0x14003c27e  lea     rdx, aRegistryMachin_7; "\\REGISTRY\\Machine\\Software\\Microsof"...
0x14003c285  mov     dword ptr cs:stru_140070F50.Length, eax
0x14003c28b  lea     rcx, [rsp+390h+DestinationString]; DestinationString
0x14003c290  call    cs:__imp_RtlInitUnicodeString
0x14003c297  nop     dword ptr [rax+rax+00h]
0x14003c29c  lea     rax, [rsp+390h+DestinationString]
0x14003c2a1  mov     [rsp+390h+ObjectAttributes.RootDirectory], 0
0x14003c2aa  xorps   xmm0, xmm0
0x14003c2ad  mov     [rsp+390h+ObjectAttributes.ObjectName], rax
0x14003c2b2  mov     ebx, 30h ; '0'
0x14003c2b7  mov     [rsp+390h+ObjectAttributes.Attributes], 240h
0x14003c2bf  lea     r8, [rsp+390h+ObjectAttributes]; ObjectAttributes
0x14003c2c4  mov     [rsp+390h+ObjectAttributes.Length], ebx
0x14003c2c8  mov     edx, 20019h; DesiredAccess
0x14003c2cd  lea     rcx, [rsp+390h+KeyHandle]; KeyHandle
0x14003c2d2  movdqu  xmmword ptr [rsp+390h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c2d8  call    cs:__imp_ZwOpenKey
0x14003c2df  nop     dword ptr [rax+rax+00h]
0x14003c2e4  test    eax, eax
0x14003c2e6  js      loc_14003C5F9
0x14003c2ec  lea     rdx, aCurrentbuildnu; "CurrentBuildNumber"
0x14003c2f3  lea     rcx, [rsp+390h+DestinationString]; DestinationString
0x14003c2f8  call    cs:__imp_RtlInitUnicodeString
0x14003c2ff  nop     dword ptr [rax+rax+00h]
0x14003c304  mov     rcx, [rsp+390h+KeyHandle]; KeyHandle
0x14003c309  lea     rax, [rsp+390h+var_360]
0x14003c30e  mov     [rsp+390h+ResultLength], rax; ResultLength
0x14003c313  lea     r9, [rbp+290h+KeyValueInformation]; KeyValueInformation
0x14003c317  lea     r8d, [rbx-2Eh]; KeyValueInformationClass
0x14003c31b  mov     [rsp+390h+Length], ebx; Length
0x14003c31f  lea     rdx, [rsp+390h+DestinationString]; ValueName
0x14003c324  call    cs:__imp_ZwQueryValueKey
0x14003c32b  nop     dword ptr [rax+rax+00h]
0x14003c330  mov     ebx, eax
0x14003c332  test    eax, eax
0x14003c334  js      loc_14003C5E6
0x14003c33a  lea     rdx, aProductname; "ProductName"
0x14003c341  lea     rcx, [rsp+390h+DestinationString]; DestinationString
0x14003c346  call    cs:__imp_RtlInitUnicodeString
0x14003c34d  nop     dword ptr [rax+rax+00h]
0x14003c352  mov     rcx, [rsp+390h+KeyHandle]; KeyHandle
0x14003c357  lea     rax, [rsp+390h+var_360]
0x14003c35c  mov     [rsp+390h+ResultLength], rax; ResultLength
0x14003c361  lea     r9, [rbp+290h+var_2E0]; KeyValueInformation
0x14003c365  mov     r8d, 2; KeyValueInformationClass
0x14003c36b  mov     [rsp+390h+Length], edi; Length
0x14003c36f  lea     rdx, [rsp+390h+DestinationString]; ValueName
0x14003c374  call    cs:__imp_ZwQueryValueKey
0x14003c37b  nop     dword ptr [rax+rax+00h]
0x14003c380  mov     ebx, eax
0x14003c382  test    eax, eax
0x14003c384  js      loc_14003C5E6
0x14003c38a  cmp     dword ptr [rbp+290h+Size], 14h
0x14003c38e  jbe     short loc_14003C3CA
0x14003c390  mov     r8d, 0Ah; MaxCount
0x14003c396  lea     rdx, aMicrosoft; "Microsoft "
0x14003c39d  lea     rcx, [rbp+290h+Size+4]; Str1
0x14003c3a1  call    cs:__imp__wcsnicmp
0x14003c3a8  nop     dword ptr [rax+rax+00h]
0x14003c3ad  test    eax, eax
0x14003c3af  jnz     short loc_14003C3CA
0x14003c3b1  mov     r8d, dword ptr [rbp+290h+Size]
0x14003c3b5  lea     rdx, [rbp+290h+Src]; Src
0x14003c3b9  add     r8d, 0FFFFFFECh; Size
0x14003c3bd  lea     rcx, [rbp+290h+Size+4]; void *
0x14003c3c1  call    memmove
0x14003c3c6  add     dword ptr [rbp+290h+Size], 0FFFFFFECh
0x14003c3ca  lea     rdx, aCsdversion; "CSDVersion"
0x14003c3d1  lea     rcx, [rsp+390h+DestinationString]; DestinationString
0x14003c3d6  call    cs:__imp_RtlInitUnicodeString
0x14003c3dd  nop     dword ptr [rax+rax+00h]
0x14003c3e2  mov     ebx, dword ptr [rbp+290h+KeyValueInformation+8]
0x14003c3e5  add     ebx, dword ptr [rbp+290h+Size]
0x14003c3e8  cmp     ebx, dword ptr [rbp+290h+Size]
0x14003c3eb  jb      loc_14003C5E1
0x14003c3f1  cmp     ebx, 0FFFFh
0x14003c3f7  ja      loc_14003C5E1
0x14003c3fd  mov     rcx, [rsp+390h+KeyHandle]; KeyHandle
0x14003c402  lea     rax, [rsp+390h+var_360]
0x14003c407  mov     [rsp+390h+ResultLength], rax; ResultLength
0x14003c40c  lea     r9, [rbp+290h+var_A0]; KeyValueInformation
0x14003c413  mov     r8d, 2; KeyValueInformationClass
0x14003c419  mov     [rsp+390h+Length], 90h; Length
0x14003c421  lea     rdx, [rsp+390h+DestinationString]; ValueName
0x14003c426  call    cs:__imp_ZwQueryValueKey
0x14003c42d  nop     dword ptr [rax+rax+00h]
0x14003c432  mov     edi, eax
0x14003c434  test    eax, eax
0x14003c436  js      short loc_14003C456
0x14003c438  mov     edx, dword ptr [rbp+290h+var_98]
0x14003c43e  add     edx, ebx
0x14003c440  cmp     edx, ebx
0x14003c442  jb      loc_14003C5E1
0x14003c448  mov     ebx, edx
0x14003c44a  cmp     edx, 0FFFFh
0x14003c450  ja      loc_14003C5E1
0x14003c456  mov     edx, ebx
0x14003c458  mov     ecx, 102h
0x14003c45d  mov     r8d, 6D536643h
0x14003c463  mov     cs:stru_140070F40.MaximumLength, bx
0x14003c46a  mov     cs:stru_140070F40.Length, bx
0x14003c471  call    cs:__imp_ExAllocatePool2
0x14003c478  nop     dword ptr [rax+rax+00h]
0x14003c47d  mov     cs:stru_140070F40.Buffer, rax
0x14003c484  test    rax, rax
0x14003c487  jz      loc_14003C5DA
0x14003c48d  mov     r8d, dword ptr [rbp+290h+Size]; Size
0x14003c491  lea     rdx, [rbp+290h+Size+4]; Src
0x14003c495  mov     rcx, rax; void *
0x14003c498  call    memmove
0x14003c49d  mov     ecx, dword ptr [rbp+290h+Size]
0x14003c4a0  lea     rdx, [rbp+290h+KeyValueInformation+0Ch]; Src
0x14003c4a4  mov     rax, cs:stru_140070F40.Buffer
0x14003c4ab  mov     ebx, 20h ; ' '
0x14003c4b0  mov     [rcx+rax-2], bx
0x14003c4b5  mov     ecx, dword ptr [rbp+290h+Size]
0x14003c4b8  add     rcx, cs:stru_140070F40.Buffer; void *
0x14003c4bf  mov     r8d, dword ptr [rbp+290h+KeyValueInformation+8]; Size
0x14003c4c3  call    memmove
0x14003c4c8  test    edi, edi
0x14003c4ca  js      short loc_14003C501
0x14003c4cc  mov     ecx, dword ptr [rbp+290h+KeyValueInformation+8]
0x14003c4cf  add     rcx, cs:stru_140070F40.Buffer
0x14003c4d6  mov     edx, dword ptr [rbp+290h+Size]
0x14003c4d9  mov     [rdx+rcx-2], bx
0x14003c4de  mov     edx, dword ptr [rbp+290h+KeyValueInformation+8]
0x14003c4e1  add     rdx, cs:stru_140070F40.Buffer
0x14003c4e8  mov     ecx, dword ptr [rbp+290h+Size]
0x14003c4eb  mov     r8d, dword ptr [rbp+290h+var_98]; Size
0x14003c4f2  add     rcx, rdx; void *
0x14003c4f5  lea     rdx, [rbp+290h+var_98+4]; Src
0x14003c4fc  call    memmove
0x14003c501  lea     rdx, aCurrentversion; "CurrentVersion"
0x14003c508  lea     rcx, [rsp+390h+DestinationString]; DestinationString
0x14003c50d  call    cs:__imp_RtlInitUnicodeString
0x14003c514  nop     dword ptr [rax+rax+00h]
0x14003c519  mov     rcx, [rsp+390h+KeyHandle]; KeyHandle
0x14003c51e  lea     rax, [rsp+390h+var_360]
0x14003c523  mov     [rsp+390h+ResultLength], rax; ResultLength
0x14003c528  lea     r9, [rbp+290h+var_D0]; KeyValueInformation
0x14003c52f  mov     r8d, 2; KeyValueInformationClass
0x14003c535  mov     [rsp+390h+Length], 30h ; '0'; Length
0x14003c53d  lea     rdx, [rsp+390h+DestinationString]; ValueName
0x14003c542  call    cs:__imp_ZwQueryValueKey
0x14003c549  nop     dword ptr [rax+rax+00h]
0x14003c54e  mov     ebx, eax
0x14003c550  test    eax, eax
0x14003c552  js      loc_14003C5E6
0x14003c558  mov     edx, dword ptr [rbp+290h+var_D0+8]
0x14003c55e  add     edx, dword ptr [rbp+290h+Size]
0x14003c561  cmp     edx, 0FFFFh
0x14003c567  ja      short loc_14003C5E1
0x14003c569  mov     ecx, 102h
0x14003c56e  mov     cs:stru_140070F50.MaximumLength, dx
0x14003c575  mov     r8d, 6D536643h
0x14003c57b  mov     cs:stru_140070F50.Length, dx
0x14003c582  call    cs:__imp_ExAllocatePool2
0x14003c589  nop     dword ptr [rax+rax+00h]
0x14003c58e  mov     cs:stru_140070F50.Buffer, rax
0x14003c595  test    rax, rax
0x14003c598  jz      short loc_14003C5DA
0x14003c59a  mov     r8d, dword ptr [rbp+290h+Size]; Size
0x14003c59e  lea     rdx, [rbp+290h+Size+4]; Src
0x14003c5a2  mov     rcx, rax; void *
0x14003c5a5  call    memmove
0x14003c5aa  mov     ecx, dword ptr [rbp+290h+Size]
0x14003c5ad  lea     rdx, [rbp+290h+var_D0+0Ch]; Src
0x14003c5b4  mov     rax, cs:stru_140070F50.Buffer
0x14003c5bb  mov     word ptr [rcx+rax-2], 20h ; ' '
0x14003c5c2  mov     ecx, dword ptr [rbp+290h+Size]
0x14003c5c5  add     rcx, cs:stru_140070F50.Buffer; void *
0x14003c5cc  mov     r8d, dword ptr [rbp+290h+var_D0+8]; Size
0x14003c5d3  call    memmove
0x14003c5d8  jmp     short loc_14003C5E6
0x14003c5da  mov     ebx, 0C000009Ah
0x14003c5df  jmp     short loc_14003C5E6
0x14003c5e1  mov     ebx, 0C000000Dh
0x14003c5e6  mov     rcx, [rsp+390h+KeyHandle]; Handle
0x14003c5eb  call    cs:__imp_ZwClose
0x14003c5f2  nop     dword ptr [rax+rax+00h]
0x14003c5f7  mov     eax, ebx
0x14003c5f9  mov     rcx, [rbp+290h+var_10]
0x14003c600  xor     rcx, rsp; StackCookie
0x14003c603  call    __security_check_cookie
0x14003c608  lea     r11, [rsp+390h+var_s0]
0x14003c610  mov     rbx, [r11+10h]
0x14003c614  mov     rdi, [r11+18h]
0x14003c618  mov     rsp, r11
0x14003c61b  pop     rbp
0x14003c61c  retn
```
