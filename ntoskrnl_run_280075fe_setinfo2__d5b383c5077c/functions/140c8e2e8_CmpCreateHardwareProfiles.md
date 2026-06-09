# CmpCreateHardwareProfiles

- ea: `0x140c8e2e8`
- end: `0x140c8eb5d`
- name: `CmpCreateHardwareProfiles`
- size: `2165`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140c8ce24`

## callees

- `0x14048eb48`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1407282c4`
- `0x1407f864c`
- `0x1407fbf98`
- `0x1407fc114`
- `0x140873c20`
- `0x140c8d9a0`
- `0x140c8dbd0`
- `0x140c8e2e8`

## string_xrefs

- `0x140c8e936`: `\Registry\Machine\%wZ\CurrentControlSet\Hardware Profiles\%04d`
- `0x140c8e9dc`: `\Registry\Machine\%wZ\CurrentControlSet\%wZ`
- `0x140c8ea61`: `\Registry\Machine\%wZ\CurrentControlSet\%wZ`

## pseudocode

```c
__int64 __fastcall CmpCreateHardwareProfiles(__int64 a1)
{
  int v2; // eax
  HANDLE v3; // r14
  NTSTATUS v4; // ebx
  NTSTATUS v5; // eax
  __int64 v6; // rdi
  char v7; // si
  __int16 v8; // dx
  int v9; // r8d
  ULONG Class; // [rsp+20h] [rbp-E0h]
  unsigned int Data; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v14[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v15; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v19; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v21; // [rsp+B0h] [rbp-50h] BYREF
  ULONG ResultLength; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE v23; // [rsp+C0h] [rbp-40h] BYREF
  UNICODE_STRING String1; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v25; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD KeyValueInformation[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[256]; // [rsp+160h] [rbp+60h] BYREF
  int v28; // [rsp+260h] [rbp+160h] BYREF

  Handle = 0;
  ResultLength = 0;
  Disposition = 0;
  v25 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v19 = 0;
  String1 = 0;
  v21 = 0;
  DestinationString = 0;
  v15 = 0;
  Data = 0;
  v2 = CmpOpenDevicesControlSet(a1, &v25, &String1);
  v3 = v25;
  v4 = v2;
  if ( v2 >= 0 )
  {
    ObjectAttributes.RootDirectory = v25;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"$&";
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v4 = v5;
    if ( v5 == -1073741772 )
    {
      if ( !CmStateSeparationEnabled )
        goto LABEL_44;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&CmpControlString;
      ObjectAttributes.RootDirectory = v3;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( v4 < 0 )
        goto LABEL_44;
      ZwClose(Handle);
      Handle = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)L"$&";
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = v3;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( v4 < 0 )
        goto LABEL_44;
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)L"\"$";
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( v4 < 0 )
        goto LABEL_44;
      Data = 0;
      *(_QWORD *)&DestinationString.Length = 0x1000000;
      DestinationString.Buffer = (wchar_t *)v27;
      RtlUnicodeStringPrintf(&DestinationString, L"%04d", 0);
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwCreateKey(&v19, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
      ZwClose(Handle);
      Handle = 0;
      if ( v4 < 0 )
        goto LABEL_44;
      ZwClose(v19);
      v19 = 0;
      v4 = ZwSetValueKey(KeyHandle, (PUNICODE_STRING)&CmpCurrentConfigString, 0, 4u, &Data, 4u);
      if ( v4 < 0 )
        goto LABEL_44;
    }
    else
    {
      if ( v5 < 0 )
        goto LABEL_44;
      v4 = ZwQueryValueKey(
             KeyHandle,
             (PUNICODE_STRING)&CmpCurrentConfigString,
             KeyValueFullInformation,
             KeyValueInformation,
             0x80u,
             &ResultLength);
      if ( v4 < 0 || KeyValueInformation[1] != 4 )
        goto LABEL_44;
      Data = *(_DWORD *)((char *)KeyValueInformation + KeyValueInformation[2]);
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"\"$";
    ObjectAttributes.RootDirectory = v3;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwOpenKey(&v21, 0x20019u, &ObjectAttributes);
    if ( v4 == -1073741772 )
    {
      if ( !CmStateSeparationEnabled )
        goto LABEL_44;
      v4 = ZwCreateKey(&v21, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
    }
    if ( v4 >= 0 )
    {
      *(_QWORD *)&DestinationString.Length = 0x1000000;
      DestinationString.Buffer = (wchar_t *)v27;
      RtlUnicodeStringPrintf(&DestinationString, L"%04d", Data);
      ObjectAttributes.RootDirectory = v21;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v4 = ZwOpenKey(&v19, 0x2001Fu, &ObjectAttributes);
      if ( v4 == -1073741772 )
      {
        if ( !CmStateSeparationEnabled )
          goto LABEL_44;
        v4 = ZwCreateKey(&v19, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
      }
      if ( v4 >= 0 )
      {
        v6 = *(_QWORD *)(a1 + 240);
        v7 = 0;
        v8 = *(_WORD *)(v6 + 8);
        if ( v8 == 3 )
        {
          v8 = 1;
          *(_WORD *)(v6 + 8) = 1;
        }
        if ( *(_WORD *)(v6 + 4) == 1 )
          goto LABEL_30;
        if ( *(_WORD *)(v6 + 4) == 2 )
        {
LABEL_31:
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&CmpStrCurrentDockInfoString;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwCreateKey(&v15, 0x2001Fu, &ObjectAttributes, 0, 0, 1u, &Disposition) >= 0 )
          {
            CmpAddDockingInfo((int)v15);
            ZwClose(v15);
            v15 = 0;
          }
          if ( *(_WORD *)(v6 + 8) == 1 )
            v7 = 1;
          goto LABEL_35;
        }
        if ( *(_WORD *)(v6 + 4) != 3 )
        {
LABEL_35:
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)L"24";
          ObjectAttributes.RootDirectory = v3;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwOpenKey(&v15, 0xF003Fu, &ObjectAttributes) >= 0 )
          {
            CmDeleteKeyRecursive((int)v15, 0, (int)&v28, 256, Class);
            ZwClose(v15);
            v15 = 0;
          }
          v4 = ZwCreateKey(&v15, 0x20u, &ObjectAttributes, 0, 0, 3u, &Disposition);
          if ( v4 >= 0 )
          {
            *(_QWORD *)&DestinationString.Length = 0x1000000;
            DestinationString.Buffer = (wchar_t *)v27;
            RtlUnicodeStringPrintf(
              &DestinationString,
              L"\\Registry\\Machine\\%wZ\\CurrentControlSet\\Hardware Profiles\\%04d",
              &String1,
              Data);
            v4 = ZwSetValueKey(v15, &CmSymbolicLinkValueName, 0, 6u, DestinationString.Buffer, DestinationString.Length);
            if ( !RtlEqualUnicodeString(&String1, &CmpSystemHiveNameString, 1u) )
            {
              ZwClose(v15);
              v15 = 0;
              *(_QWORD *)&DestinationString.Length = 0x1000000;
              DestinationString.Buffer = (wchar_t *)v27;
              RtlUnicodeStringPrintf(
                &DestinationString,
                L"\\Registry\\Machine\\%wZ\\CurrentControlSet\\%wZ",
                &CmpSystemHiveNameString,
                L"24");
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &DestinationString;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.Attributes = 576;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              v4 = ZwCreateKey(&v15, 0x20u, &ObjectAttributes, 0, 0, 3u, &Disposition);
              if ( v4 >= 0 )
              {
                *(_QWORD *)&DestinationString.Length = 0x1000000;
                DestinationString.Buffer = (wchar_t *)v27;
                RtlUnicodeStringPrintf(
                  &DestinationString,
                  L"\\Registry\\Machine\\%wZ\\CurrentControlSet\\%wZ",
                  &String1,
                  L"24");
                v4 = ZwSetValueKey(
                       v15,
                       &CmSymbolicLinkValueName,
                       0,
                       6u,
                       DestinationString.Buffer,
                       DestinationString.Length);
              }
            }
          }
          if ( v7 )
          {
            v23 = 0;
            v14[0] = 0;
            LODWORD(v25) = 131073;
            WORD2(v25) = 0;
            v4 = CmSetAcpiHwProfile(
                   (unsigned int)&v25,
                   (unsigned int)CmpHwprofileDefaultSelect,
                   v9,
                   (unsigned int)&v23,
                   (__int64)v14);
            if ( v4 >= 0 )
              ZwClose(v23);
          }
          goto LABEL_44;
        }
        LOWORD(Class) = v8;
        v4 = CmpCloneHwProfile(KeyHandle, v21, v19, Data, Class, &v19, &Data);
        if ( v4 < 0 )
        {
          v19 = 0;
          goto LABEL_44;
        }
        v4 = ZwSetValueKey(KeyHandle, (PUNICODE_STRING)&CmpCurrentConfigString, 0, 4u, &Data, 4u);
        if ( v4 >= 0 )
        {
LABEL_30:
          CmpAddAliasEntry(KeyHandle, v6 + 4, Data);
          goto LABEL_31;
        }
      }
    }
  }
LABEL_44:
  if ( v3 )
    ZwClose(v3);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v19 )
    ZwClose(v19);
  if ( v21 )
    ZwClose(v21);
  if ( v15 )
    ZwClose(v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140c8e2e8  push    rbp
0x140c8e2ea  push    rbx
0x140c8e2eb  push    rsi
0x140c8e2ec  push    rdi
0x140c8e2ed  push    r12
0x140c8e2ef  push    r13
0x140c8e2f1  push    r14
0x140c8e2f3  push    r15
0x140c8e2f5  lea     rbp, [rsp-278h]
0x140c8e2fd  sub     rsp, 378h
0x140c8e304  mov     rax, cs:__security_cookie
0x140c8e30b  xor     rax, rsp
0x140c8e30e  mov     [rbp+2B0h+var_50], rax
0x140c8e315  xor     r12d, r12d
0x140c8e318  lea     r8, [rbp+2B0h+String1]
0x140c8e31c  xorps   xmm0, xmm0
0x140c8e31f  mov     [rbp+2B0h+Handle], r12
0x140c8e323  xorps   xmm1, xmm1
0x140c8e326  mov     [rbp+2B0h+ResultLength], r12d
0x140c8e32a  movups  xmmword ptr [rsp+3B0h+ObjectAttributes.ObjectName], xmm0
0x140c8e32f  xor     eax, eax
0x140c8e331  mov     [rsp+3B0h+var_36C], r12d
0x140c8e336  lea     rdx, [rbp+2B0h+var_2D8]
0x140c8e33a  mov     [rbp+2B0h+var_2D8], r12
0x140c8e33e  movups  xmmword ptr [rbp+2B0h+ObjectAttributes+1Ch], xmm0
0x140c8e342  mov     rdi, rcx
0x140c8e345  mov     [rbp+2B0h+KeyHandle], r12
0x140c8e349  movups  xmmword ptr [rsp+3B0h+ObjectAttributes.Length], xmm0
0x140c8e34e  mov     [rbp+2B0h+var_310], r12
0x140c8e352  movups  xmmword ptr [rbp+2B0h+String1.Length], xmm0
0x140c8e356  mov     [rbp+2B0h+var_300], r12
0x140c8e35a  movups  xmmword ptr [rsp+3B0h+DestinationString.Length], xmm1
0x140c8e35f  mov     [rsp+3B0h+var_360], r12
0x140c8e364  mov     [rsp+3B0h+Data], r12d
0x140c8e369  call    CmpOpenDevicesControlSet
0x140c8e36e  mov     r14, [rbp+2B0h+var_2D8]
0x140c8e372  mov     ebx, eax
0x140c8e374  test    eax, eax
0x140c8e376  js      loc_140C8EAF1
0x140c8e37c  lea     rax, CmpControlIdConfigDbString; "$&"
0x140c8e383  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], r14
0x140c8e388  xorps   xmm0, xmm0
0x140c8e38b  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e390  mov     esi, 20019h
0x140c8e395  lea     r13d, [r12+30h]
0x140c8e39a  mov     r15d, 240h
0x140c8e3a0  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e3a5  mov     edx, esi; DesiredAccess
0x140c8e3a7  mov     [rbp+2B0h+ObjectAttributes.Attributes], r15d
0x140c8e3ab  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e3b0  lea     rcx, [rbp+2B0h+KeyHandle]; KeyHandle
0x140c8e3b4  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e3b9  call    ZwOpenKey
0x140c8e3be  mov     ebx, eax
0x140c8e3c0  cmp     eax, 0C0000034h
0x140c8e3c5  jnz     loc_140C8E5BB
0x140c8e3cb  cmp     cs:CmStateSeparationEnabled, r12d
0x140c8e3d2  jz      loc_140C8EAF1
0x140c8e3d8  lea     rax, CmpControlString
0x140c8e3df  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e3e4  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e3e9  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e3ee  lea     rax, [rsp+3B0h+var_36C]
0x140c8e3f3  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], r14
0x140c8e3f8  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e3fd  lea     rcx, [rbp+2B0h+Handle]; KeyHandle
0x140c8e401  xorps   xmm0, xmm0
0x140c8e404  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e409  xor     r9d, r9d; TitleIndex
0x140c8e40c  mov     [rsp+3B0h+Class], r12; Class
0x140c8e411  mov     edx, esi; DesiredAccess
0x140c8e413  mov     [rbp+2B0h+ObjectAttributes.Attributes], r15d
0x140c8e417  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e41c  call    ZwCreateKey
0x140c8e421  mov     ebx, eax
0x140c8e423  test    eax, eax
0x140c8e425  js      loc_140C8EAF1
0x140c8e42b  mov     rcx, [rbp+2B0h+Handle]; Handle
0x140c8e42f  call    ZwClose
0x140c8e434  lea     rax, CmpControlIdConfigDbString; "$&"
0x140c8e43b  mov     [rbp+2B0h+Handle], r12
0x140c8e43f  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e444  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e449  lea     rax, [rsp+3B0h+var_36C]
0x140c8e44e  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e453  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e458  lea     rcx, [rbp+2B0h+KeyHandle]; KeyHandle
0x140c8e45c  xorps   xmm0, xmm0
0x140c8e45f  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e464  xor     r9d, r9d; TitleIndex
0x140c8e467  mov     [rsp+3B0h+Class], r12; Class
0x140c8e46c  mov     edx, esi; DesiredAccess
0x140c8e46e  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], r14
0x140c8e473  mov     [rbp+2B0h+ObjectAttributes.Attributes], r15d
0x140c8e477  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e47c  call    ZwCreateKey
0x140c8e481  mov     ebx, eax
0x140c8e483  test    eax, eax
0x140c8e485  js      loc_140C8EAF1
0x140c8e48b  mov     rax, [rbp+2B0h+KeyHandle]
0x140c8e48f  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e494  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], rax
0x140c8e499  lea     rcx, [rbp+2B0h+Handle]; KeyHandle
0x140c8e49d  lea     rax, CmpHardwareProfilesString; "\"$"
0x140c8e4a4  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e4a9  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e4ae  xorps   xmm0, xmm0
0x140c8e4b1  lea     rax, [rsp+3B0h+var_36C]
0x140c8e4b6  mov     [rbp+2B0h+ObjectAttributes.Attributes], r15d
0x140c8e4ba  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e4bf  xor     r9d, r9d; TitleIndex
0x140c8e4c2  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e4c7  mov     edx, esi; DesiredAccess
0x140c8e4c9  mov     [rsp+3B0h+Class], r12; Class
0x140c8e4ce  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e4d3  call    ZwCreateKey
0x140c8e4d8  mov     ebx, eax
0x140c8e4da  test    eax, eax
0x140c8e4dc  js      loc_140C8EAF1
0x140c8e4e2  xorps   xmm0, xmm0
0x140c8e4e5  mov     [rsp+3B0h+Data], r12d
0x140c8e4ea  movups  xmmword ptr [rsp+3B0h+DestinationString.Length], xmm0
0x140c8e4ef  mov     eax, 100h
0x140c8e4f4  lea     rdx, a04d; "%04d"
0x140c8e4fb  mov     [rsp+3B0h+DestinationString.MaximumLength], ax
0x140c8e500  lea     rcx, [rsp+3B0h+DestinationString]; DestinationString
0x140c8e505  lea     rax, [rbp+2B0h+var_250]
0x140c8e509  xor     r8d, r8d
0x140c8e50c  mov     [rsp+3B0h+DestinationString.Buffer], rax
0x140c8e511  call    RtlUnicodeStringPrintf
0x140c8e516  mov     rax, [rbp+2B0h+Handle]
0x140c8e51a  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e51f  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], rax
0x140c8e524  lea     rcx, [rbp+2B0h+var_310]; KeyHandle
0x140c8e528  lea     rax, [rsp+3B0h+DestinationString]
0x140c8e52d  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e532  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e537  xorps   xmm0, xmm0
0x140c8e53a  lea     rax, [rsp+3B0h+var_36C]
0x140c8e53f  mov     [rbp+2B0h+ObjectAttributes.Attributes], r15d
0x140c8e543  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e548  xor     r9d, r9d; TitleIndex
0x140c8e54b  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e550  mov     edx, esi; DesiredAccess
0x140c8e552  mov     [rsp+3B0h+Class], r12; Class
0x140c8e557  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e55c  call    ZwCreateKey
0x140c8e561  mov     rcx, [rbp+2B0h+Handle]; Handle
0x140c8e565  mov     ebx, eax
0x140c8e567  call    ZwClose
0x140c8e56c  mov     [rbp+2B0h+Handle], r12
0x140c8e570  test    ebx, ebx
0x140c8e572  js      loc_140C8EAF1
0x140c8e578  mov     rcx, [rbp+2B0h+var_310]; Handle
0x140c8e57c  call    ZwClose
0x140c8e581  mov     rcx, [rbp+2B0h+KeyHandle]; KeyHandle
0x140c8e585  lea     r15d, [r12+4]
0x140c8e58a  lea     rax, [rsp+3B0h+Data]
0x140c8e58f  mov     [rsp+3B0h+CreateOptions], r15d; DataSize
0x140c8e594  mov     r9d, r15d; Type
0x140c8e597  mov     [rsp+3B0h+Class], rax; Data
0x140c8e59c  xor     r8d, r8d; TitleIndex
0x140c8e59f  mov     [rbp+2B0h+var_310], r12
0x140c8e5a3  lea     rdx, CmpCurrentConfigString; ValueName
0x140c8e5aa  call    ZwSetValueKey
0x140c8e5af  mov     ebx, eax
0x140c8e5b1  test    eax, eax
0x140c8e5b3  js      loc_140C8EAF1
0x140c8e5b9  jmp     short loc_140C8E613
0x140c8e5bb  test    eax, eax
0x140c8e5bd  js      loc_140C8EAF1
0x140c8e5c3  mov     rcx, [rbp+2B0h+KeyHandle]; KeyHandle
0x140c8e5c7  lea     rax, [rbp+2B0h+ResultLength]
0x140c8e5cb  mov     qword ptr [rsp+3B0h+CreateOptions], rax; ResultLength
0x140c8e5d0  lea     r9, [rbp+2B0h+KeyValueInformation]; KeyValueInformation
0x140c8e5d4  mov     r8d, 1; KeyValueInformationClass
0x140c8e5da  mov     dword ptr [rsp+3B0h+Class], 80h; Length
0x140c8e5e2  lea     rdx, CmpCurrentConfigString; ValueName
0x140c8e5e9  call    ZwQueryValueKey
0x140c8e5ee  mov     ebx, eax
0x140c8e5f0  test    eax, eax
0x140c8e5f2  js      loc_140C8EAF1
0x140c8e5f8  mov     r15d, 4
0x140c8e5fe  cmp     [rbp+2B0h+var_2CC], r15d
0x140c8e602  jnz     loc_140C8EAF1
0x140c8e608  mov     eax, [rbp+2B0h+var_2C8]
0x140c8e60b  mov     ecx, [rbp+rax+2B0h+KeyValueInformation]
0x140c8e60f  mov     [rsp+3B0h+Data], ecx
0x140c8e613  lea     rax, CmpHardwareProfilesString; "\"$"
0x140c8e61a  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e61f  xorps   xmm0, xmm0
0x140c8e622  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e627  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e62c  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], r14
0x140c8e631  mov     edx, esi; DesiredAccess
0x140c8e633  mov     [rbp+2B0h+ObjectAttributes.Attributes], 240h
0x140c8e63a  lea     rcx, [rbp+2B0h+var_300]; KeyHandle
0x140c8e63e  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e643  call    ZwOpenKey
0x140c8e648  mov     ebx, eax
0x140c8e64a  cmp     eax, 0C0000034h
0x140c8e64f  jnz     short loc_140C8E687
0x140c8e651  cmp     cs:CmStateSeparationEnabled, r12d
0x140c8e658  jz      loc_140C8EAF1
0x140c8e65e  lea     rax, [rsp+3B0h+var_36C]
0x140c8e663  xor     r9d, r9d; TitleIndex
0x140c8e666  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e66b  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e670  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e675  lea     rcx, [rbp+2B0h+var_300]; KeyHandle
0x140c8e679  mov     edx, esi; DesiredAccess
0x140c8e67b  mov     [rsp+3B0h+Class], r12; Class
0x140c8e680  call    ZwCreateKey
0x140c8e685  mov     ebx, eax
0x140c8e687  test    ebx, ebx
0x140c8e689  js      loc_140C8EAF1
0x140c8e68f  mov     r8d, [rsp+3B0h+Data]
0x140c8e694  lea     rdx, a04d; "%04d"
0x140c8e69b  xorps   xmm0, xmm0
0x140c8e69e  lea     rcx, [rsp+3B0h+DestinationString]; DestinationString
0x140c8e6a3  movups  xmmword ptr [rsp+3B0h+DestinationString.Length], xmm0
0x140c8e6a8  mov     eax, 100h
0x140c8e6ad  mov     [rsp+3B0h+DestinationString.MaximumLength], ax
0x140c8e6b2  lea     rax, [rbp+2B0h+var_250]
0x140c8e6b6  mov     [rsp+3B0h+DestinationString.Buffer], rax
0x140c8e6bb  call    RtlUnicodeStringPrintf
0x140c8e6c0  mov     rax, [rbp+2B0h+var_300]
0x140c8e6c4  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e6c9  mov     [rsp+3B0h+ObjectAttributes.RootDirectory], rax
0x140c8e6ce  lea     rcx, [rbp+2B0h+var_310]; KeyHandle
0x140c8e6d2  lea     rax, [rsp+3B0h+DestinationString]
0x140c8e6d7  mov     [rsp+3B0h+ObjectAttributes.Length], r13d
0x140c8e6dc  xorps   xmm0, xmm0
0x140c8e6df  mov     [rsp+3B0h+ObjectAttributes.ObjectName], rax
0x140c8e6e4  mov     esi, 2001Fh
0x140c8e6e9  mov     [rbp+2B0h+ObjectAttributes.Attributes], 240h
0x140c8e6f0  mov     edx, esi; DesiredAccess
0x140c8e6f2  movdqu  xmmword ptr [rbp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140c8e6f7  call    ZwOpenKey
0x140c8e6fc  mov     ebx, eax
0x140c8e6fe  cmp     eax, 0C0000034h
0x140c8e703  jnz     short loc_140C8E73B
0x140c8e705  cmp     cs:CmStateSeparationEnabled, r12d
0x140c8e70c  jz      loc_140C8EAF1
0x140c8e712  lea     rax, [rsp+3B0h+var_36C]
0x140c8e717  xor     r9d, r9d; TitleIndex
0x140c8e71a  mov     [rsp+3B0h+Disposition], rax; Disposition
0x140c8e71f  lea     r8, [rsp+3B0h+ObjectAttributes]; ObjectAttributes
0x140c8e724  mov     [rsp+3B0h+CreateOptions], r12d; CreateOptions
0x140c8e729  lea     rcx, [rbp+2B0h+var_310]; KeyHandle
0x140c8e72d  mov     edx, esi; DesiredAccess
0x140c8e72f  mov     [rsp+3B0h+Class], r12; ULONG
0x140c8e734  call    ZwCreateKey
0x140c8e739  mov     ebx, eax
0x140c8e73b  test    ebx, ebx
0x140c8e73d  js      loc_140C8EAF1
0x140c8e743  mov     rdi, [rdi+0F0h]
0x140c8e74a  mov     ebx, 3
0x140c8e74f  movzx   esi, r12b
0x140c8e753  movzx   edx, word ptr [rdi+8]
0x140c8e757  cmp     dx, bx
0x140c8e75a  jnz     short loc_140C8E763
0x140c8e75c  lea     edx, [rbx-2]
0x140c8e75f  mov     [rdi+8], dx
0x140c8e763  movzx   ecx, word ptr [rdi+4]
0x140c8e767  sub     ecx, 1
0x140c8e76a  jz      loc_140C8E7F3
0x140c8e770  sub     ecx, 1
0x140c8e773  jz      loc_140C8E805
0x140c8e779  cmp     ecx, 1
0x140c8e77c  jnz     loc_140C8E88B
0x140c8e782  mov     r9d, [rsp+3B0h+Data]
0x140c8e787  lea     rax, [rsp+3B0h+Data]
0x140c8e78c  mov     r8, [rbp+2B0h+var_310]
0x140c8e790  mov     rcx, [rbp+2B0h+KeyHandle]
0x140c8e794  mov     [rsp+3B0h+Disposition], rax
0x140c8e799  lea     rax, [rbp+2B0h+var_310]
0x140c8e79d  mov     qword ptr [rsp+3B0h+CreateOptions], rax
0x140c8e7a2  mov     word ptr [rsp+3B0h+Class], dx
0x140c8e7a7  mov     rdx, [rbp+2B0h+var_300]
0x140c8e7ab  call    CmpCloneHwProfile
0x140c8e7b0  mov     ebx, eax
0x140c8e7b2  test    eax, eax
0x140c8e7b4  jns     short loc_140C8E7BF
0x140c8e7b6  mov     [rbp+2B0h+var_310], r12
0x140c8e7ba  jmp     loc_140C8EAF1
0x140c8e7bf  mov     rcx, [rbp+2B0h+KeyHandle]; KeyHandle
0x140c8e7c3  lea     rax, [rsp+3B0h+Data]
0x140c8e7c8  mov     [rsp+3B0h+CreateOptions], r15d; DataSize
0x140c8e7cd  lea     rdx, CmpCurrentConfigString; ValueName
0x140c8e7d4  mov     r9d, r15d; Type
0x140c8e7d7  mov     [rsp+3B0h+Class], rax; Data
0x140c8e7dc  xor     r8d, r8d; TitleIndex
0x140c8e7df  call    ZwSetValueKey
0x140c8e7e4  mov     ebx, eax
0x140c8e7e6  test    eax, eax
0x140c8e7e8  js      loc_140C8EAF1
0x140c8e7ee  mov     ebx, 3
0x140c8e7f3  mov     r8d, [rsp+3B0h+Data]
0x140c8e7f8  lea     rdx, [rdi+4]
  ... truncated ...
```
