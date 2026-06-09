# CmSetAcpiHwProfile

- ea: `0x1407fc114`
- end: `0x1407fc97a`
- name: `CmSetAcpiHwProfile`
- size: `2150`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14077c894`
- `0x140c8e2e8`

## callees

- `0x140403380`
- `0x14048eb48`
- `0x1405490f0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x1406eb0e0`
- `0x1406f6f80`
- `0x1407282c4`
- `0x1407f864c`
- `0x1407fc114`
- `0x1407fc980`
- `0x1407fcee0`
- `0x1407fd12c`
- `0x1407fd968`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1407fc3e5`: `CurrentConfig`
- `0x1407fc69c`: `CurrentConfig`
- `0x1407fc907`: `\Registry\Machine\%wZ\CurrentControlSet\Hardware Profiles\%04d`

## pseudocode

```c
__int64 __fastcall CmSetAcpiHwProfile(unsigned __int16 *a1, __int64 a2, __int64 a3, HANDLE *a4, _BYTE *a5)
{
  void *Pool2; // rdi
  NTSTATUS AcpiProfileInformation; // ebx
  void *v8; // r12
  int v9; // ebx
  unsigned int v10; // esi
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r14d
  unsigned int v14; // edx
  HANDLE v15; // rcx
  NTSTATUS v16; // eax
  _DWORD *v17; // rcx
  unsigned int v18; // edx
  __int64 v19; // rax
  __int64 v20; // rax
  _DWORD *v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rax
  int Length; // [rsp+20h] [rbp-E0h]
  unsigned int Data; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v32; // [rsp+68h] [rbp-98h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v34; // [rsp+74h] [rbp-8Ch]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+A8h] [rbp-58h] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE v38; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v39; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v40; // [rsp+C8h] [rbp-38h] BYREF
  void *v41; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE *v42; // [rsp+D8h] [rbp-28h]
  __int128 v43; // [rsp+E0h] [rbp-20h] BYREF
  int KeyValueInformation; // [rsp+F0h] [rbp-10h] BYREF
  int v45; // [rsp+F4h] [rbp-Ch]
  unsigned int v46; // [rsp+F8h] [rbp-8h]
  size_t Size; // [rsp+FCh] [rbp-4h]
  wchar_t Dst[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v42 = a4;
  v41 = 0;
  KeyHandle = 0;
  Pool2 = 0;
  v32 = 0;
  Handle = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  *a5 = 0;
  v40 = 0;
  v38 = 0;
  v43 = 0;
  ResultLength = 0;
  DestinationString = 0;
  v28 = 0;
  v34 = 0;
  Data = 0;
  Disposition = 0;
  v39 = 0;
  P = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  AcpiProfileInformation = CmpOpenDevicesControlSet(a1, &v41, &v43);
  if ( AcpiProfileInformation >= 0 )
  {
    v8 = v41;
    ObjectAttributes.RootDirectory = v41;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"$&";
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.Length = 48;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AcpiProfileInformation = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( AcpiProfileInformation < 0 )
    {
      KeyHandle = 0;
      goto LABEL_37;
    }
    AcpiProfileInformation = CmpGetAcpiProfileInformation(
                               (int)KeyHandle,
                               (int)&P,
                               (int)&v39,
                               (int)Dst,
                               &KeyValueInformation);
    if ( AcpiProfileInformation >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)L"24";
      ObjectAttributes.RootDirectory = v8;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      AcpiProfileInformation = ZwOpenKey(&v32, 0x20019u, &ObjectAttributes);
      if ( AcpiProfileInformation < 0 )
      {
        v32 = 0;
        goto LABEL_37;
      }
      RtlInitUnicodeString(&DestinationString, L"CurrentDockInfo");
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      AcpiProfileInformation = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      if ( AcpiProfileInformation < 0 )
      {
        Handle = 0;
        goto LABEL_37;
      }
      RtlInitUnicodeString(&DestinationString, L"DockingState");
      if ( ZwQueryValueKey(
             Handle,
             &DestinationString,
             KeyValueFullInformation,
             &KeyValueInformation,
             0x100u,
             &ResultLength) < 0
        || v45 != 4 )
      {
        goto LABEL_36;
      }
      v9 = *(int *)((char *)&KeyValueInformation + v46);
      RtlInitUnicodeString(&DestinationString, L"AcpiSerialNumber");
      if ( ZwQueryValueKey(
             Handle,
             &DestinationString,
             KeyValueFullInformation,
             &KeyValueInformation,
             0x100u,
             &ResultLength) >= 0
        && v45 == 3 )
      {
        Pool2 = (void *)ExAllocatePool2(256, (unsigned int)Size, 538987843);
        if ( !Pool2 )
        {
          AcpiProfileInformation = -1073741670;
          goto LABEL_37;
        }
        memmove(Pool2, (char *)&KeyValueInformation + v46, (unsigned int)Size);
      }
      RtlInitUnicodeString(&DestinationString, L"CurrentConfig");
      if ( ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValueFullInformation,
             &KeyValueInformation,
             0x100u,
             &ResultLength) < 0
        || v45 != 4 )
      {
LABEL_36:
        AcpiProfileInformation = -1073741492;
        goto LABEL_37;
      }
      v10 = *(int *)((char *)&KeyValueInformation + v46);
      AcpiProfileInformation = CmpFilterAcpiDockingState((_DWORD)a1, v9, (_DWORD)Pool2, v10, (__int64)P, (__int64)v39);
      if ( AcpiProfileInformation < 0 )
        goto LABEL_37;
      v11 = guard_dispatch_icall_no_overrides(P);
      AcpiProfileInformation = v11;
      if ( v34 != -1 )
      {
        if ( v11 < 0 )
          goto LABEL_37;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)L"\"$";
        ObjectAttributes.RootDirectory = v8;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        AcpiProfileInformation = ZwOpenKey(&v38, 0x20019u, &ObjectAttributes);
        if ( AcpiProfileInformation < 0 )
        {
          v38 = 0;
          goto LABEL_37;
        }
        v12 = 32LL * v34;
        v13 = *(_DWORD *)((char *)P + v12 + 32);
        v14 = *(_DWORD *)((char *)P + v12 + 28);
        Data = v14;
        if ( (v13 & 8) != 0 )
        {
          AcpiProfileInformation = CmpMoveBiosAliasTable(KeyHandle, Handle, v10, v14, Dst);
          if ( AcpiProfileInformation < 0 )
            goto LABEL_37;
          v14 = Data;
        }
        if ( (v13 & 4) != 0 || v14 != v10 )
        {
          v15 = Handle;
          *a5 = 1;
          ZwClose(v15);
          Handle = 0;
          if ( (v13 & 4) != 0 )
          {
            LOWORD(Length) = *a1;
            v16 = CmpCloneHwProfile(KeyHandle, v38, v32, Data, Length, &v32, &Data);
          }
          else
          {
            ZwClose(v32);
            swprintf_s(Dst, 0x80u, L"%04d", Data);
            RtlInitUnicodeString(&DestinationString, Dst);
            ObjectAttributes.RootDirectory = v38;
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v16 = ZwOpenKey(&v32, 0x20019u, &ObjectAttributes);
          }
          AcpiProfileInformation = v16;
          if ( v16 < 0 )
          {
            v32 = 0;
            goto LABEL_37;
          }
          RtlInitUnicodeString(&DestinationString, L"CurrentDockInfo");
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          AcpiProfileInformation = ZwCreateKey(&Handle, 0x2001Fu, &ObjectAttributes, 0, 0, 1u, &Disposition);
          if ( AcpiProfileInformation < 0 )
          {
            Handle = 0;
            goto LABEL_37;
          }
          RtlInitUnicodeString(&DestinationString, L"CurrentConfig");
          if ( ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u) < 0 )
            goto LABEL_36;
        }
        v28 = *a1;
        RtlInitUnicodeString(&DestinationString, L"DockingState");
        ZwSetValueKey(Handle, &DestinationString, 0, 4u, &v28, 4u);
        RtlInitUnicodeString(&DestinationString, L"AcpiSerialNumber");
        AcpiProfileInformation = ZwSetValueKey(Handle, &DestinationString, 0, 3u, a1 + 2, a1[1]);
        if ( (v13 & 2) == 0 )
          AcpiProfileInformation = CmpAddAcpiAliasEntry(KeyHandle, a1, Data, Dst);
        if ( Data != v10 )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)L"24";
          ObjectAttributes.RootDirectory = v8;
          ObjectAttributes.Attributes = 832;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          ZwCreateKey(&v40, 0x20u, &ObjectAttributes, 0, 0, 8u, &Disposition);
          *(_QWORD *)&DestinationString.Length = 0x1000000;
          DestinationString.Buffer = Dst;
          RtlUnicodeStringPrintf(
            &DestinationString,
            L"\\Registry\\Machine\\%wZ\\CurrentControlSet\\Hardware Profiles\\%04d",
            &v43,
            Data);
          AcpiProfileInformation = ZwSetValueKey(
                                     v40,
                                     &CmSymbolicLinkValueName,
                                     0,
                                     6u,
                                     DestinationString.Buffer,
                                     DestinationString.Length);
        }
      }
      if ( AcpiProfileInformation >= 0 )
      {
        *v42 = v32;
        goto LABEL_39;
      }
    }
  }
LABEL_37:
  if ( v32 )
    ZwClose(v32);
LABEL_39:
  if ( v40 )
    ZwClose(v40);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v38 )
    ZwClose(v38);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  v17 = P;
  if ( P )
  {
    v18 = 0;
    v28 = 0;
    if ( *((_DWORD *)P + 1) )
    {
      v19 = 0;
      do
      {
        v20 = 8 * v19;
        if ( *(_QWORD *)&v17[v20 + 4] )
        {
          ExFreePoolWithTag(*(PVOID *)&v17[v20 + 4], 0);
          v18 = v28;
          v17 = P;
        }
        v28 = ++v18;
        v19 = v18;
      }
      while ( v18 < v17[1] );
    }
    ExFreePoolWithTag(v17, 0);
  }
  v21 = v39;
  if ( v39 )
  {
    v22 = 0;
    v28 = 0;
    if ( *((_DWORD *)v39 + 1) )
    {
      v23 = 0;
      do
      {
        v24 = 3 * (v23 + 1);
        if ( *(_QWORD *)&v21[2 * v24] )
        {
          ExFreePoolWithTag(*(PVOID *)&v21[2 * v24], 0);
          v22 = v28;
          v21 = v39;
        }
        v28 = ++v22;
        v23 = v22;
      }
      while ( v22 < v21[1] );
    }
    ExFreePoolWithTag(v21, 0);
  }
  return (unsigned int)AcpiProfileInformation;
}

```

## disassembly

```asm
0x1407fc114  mov     [rsp-8+arg_10], rbx
0x1407fc119  push    rbp
0x1407fc11a  push    rsi
0x1407fc11b  push    rdi
0x1407fc11c  push    r12
0x1407fc11e  push    r13
0x1407fc120  push    r14
0x1407fc122  push    r15
0x1407fc124  lea     rbp, [rsp-200h]
0x1407fc12c  sub     rsp, 300h
0x1407fc133  mov     rax, cs:__security_cookie
0x1407fc13a  xor     rax, rsp
0x1407fc13d  mov     [rbp+230h+var_40], rax
0x1407fc144  mov     r13, [rbp+230h+arg_20]
0x1407fc14b  lea     r8, [rbp+230h+var_250]
0x1407fc14f  xorps   xmm0, xmm0
0x1407fc152  mov     [rbp+230h+var_258], r9
0x1407fc156  mov     r14, rdx
0x1407fc159  mov     [rbp+230h+var_260], 0
0x1407fc161  xorps   xmm1, xmm1
0x1407fc164  mov     [rsp+330h+KeyHandle], 0
0x1407fc16d  xor     edi, edi
0x1407fc16f  mov     [rsp+330h+var_2C8], 0
0x1407fc178  xor     eax, eax
0x1407fc17a  mov     [rsp+330h+Handle], 0
0x1407fc183  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x1407fc187  lea     rdx, [rbp+230h+var_260]
0x1407fc18b  mov     [r13+0], al
0x1407fc18f  mov     r15, rcx
0x1407fc192  mov     [rbp+230h+var_268], 0
0x1407fc19a  mov     [rbp+230h+var_278], 0
0x1407fc1a2  movups  [rbp+230h+var_250], xmm0
0x1407fc1a6  mov     [rsp+330h+var_2C0], 0
0x1407fc1ae  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm1
0x1407fc1b3  mov     [rsp+330h+var_2EC], 0
0x1407fc1bb  mov     [rsp+330h+var_2BC], 0
0x1407fc1c3  mov     [rsp+330h+Data], 0
0x1407fc1cb  mov     [rbp+230h+var_280], 0
0x1407fc1d2  mov     [rbp+230h+var_270], rdi
0x1407fc1d6  mov     [rbp+230h+P], rdi
0x1407fc1da  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x1407fc1df  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x1407fc1e3  call    CmpOpenDevicesControlSet
0x1407fc1e8  mov     ebx, eax
0x1407fc1ea  test    eax, eax
0x1407fc1ec  js      loc_1407FC6E2
0x1407fc1f2  mov     r12, [rbp+230h+var_260]
0x1407fc1f6  lea     rax, CmpControlIdConfigDbString; "$&"
0x1407fc1fd  xorps   xmm0, xmm0
0x1407fc200  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407fc204  mov     esi, 240h
0x1407fc209  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc20d  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc212  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407fc215  mov     edx, 20019h; DesiredAccess
0x1407fc21a  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc222  lea     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x1407fc227  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407fc22c  call    ZwOpenKey
0x1407fc231  mov     ebx, eax
0x1407fc233  test    eax, eax
0x1407fc235  jns     short loc_1407FC241
0x1407fc237  mov     [rsp+330h+KeyHandle], rdi
0x1407fc23c  jmp     loc_1407FC6E2
0x1407fc241  mov     rcx, [rsp+330h+KeyHandle]; int
0x1407fc246  lea     rax, [rbp+230h+KeyValueInformation]
0x1407fc24a  mov     dword ptr [rsp+330h+ResultLength], 100h
0x1407fc252  lea     r9, [rbp+230h+Dst]; int
0x1407fc259  lea     r8, [rbp+230h+var_270]; int
0x1407fc25d  mov     qword ptr [rsp+330h+Length], rax; KeyValueInformation
0x1407fc262  lea     rdx, [rbp+230h+P]; int
0x1407fc266  call    CmpGetAcpiProfileInformation
0x1407fc26b  mov     ebx, eax
0x1407fc26d  test    eax, eax
0x1407fc26f  js      loc_1407FC6E2
0x1407fc275  lea     rax, CmpHardwareProfilesCurrentString; "24"
0x1407fc27c  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc284  xorps   xmm0, xmm0
0x1407fc287  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc28b  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc290  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407fc294  mov     edx, 20019h; DesiredAccess
0x1407fc299  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407fc29c  lea     rcx, [rsp+330h+var_2C8]; KeyHandle
0x1407fc2a1  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407fc2a6  call    ZwOpenKey
0x1407fc2ab  mov     ebx, eax
0x1407fc2ad  test    eax, eax
0x1407fc2af  jns     short loc_1407FC2BB
0x1407fc2b1  mov     [rsp+330h+var_2C8], rdi
0x1407fc2b6  jmp     loc_1407FC6E2
0x1407fc2bb  lea     rdx, aCurrentdockinf; "CurrentDockInfo"
0x1407fc2c2  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc2c7  call    RtlInitUnicodeString
0x1407fc2cc  mov     rax, [rsp+330h+KeyHandle]
0x1407fc2d1  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc2d6  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407fc2da  lea     rcx, [rsp+330h+Handle]; KeyHandle
0x1407fc2df  lea     rax, [rsp+330h+DestinationString]
0x1407fc2e4  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc2ec  xorps   xmm0, xmm0
0x1407fc2ef  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc2f3  mov     edx, 20019h; DesiredAccess
0x1407fc2f8  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407fc2fb  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407fc300  call    ZwOpenKey
0x1407fc305  mov     ebx, eax
0x1407fc307  test    eax, eax
0x1407fc309  jns     short loc_1407FC315
0x1407fc30b  mov     [rsp+330h+Handle], rdi
0x1407fc310  jmp     loc_1407FC6E2
0x1407fc315  lea     rdx, aDockingstate; "DockingState"
0x1407fc31c  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc321  call    RtlInitUnicodeString
0x1407fc326  mov     rcx, [rsp+330h+Handle]; KeyHandle
0x1407fc32b  lea     rax, [rsp+330h+var_2C0]
0x1407fc330  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407fc335  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407fc339  mov     esi, 100h
0x1407fc33e  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407fc343  mov     r8d, 1; KeyValueInformationClass
0x1407fc349  mov     [rsp+330h+Length], esi; Length
0x1407fc34d  call    ZwQueryValueKey
0x1407fc352  test    eax, eax
0x1407fc354  js      loc_1407FC6DD
0x1407fc35a  cmp     [rbp+230h+var_23C], 4
0x1407fc35e  jnz     loc_1407FC6DD
0x1407fc364  mov     eax, [rbp+230h+var_238]
0x1407fc367  lea     rdx, aAcpiserialnumb; "AcpiSerialNumber"
0x1407fc36e  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc373  mov     ebx, [rbp+rax+230h+KeyValueInformation]
0x1407fc377  call    RtlInitUnicodeString
0x1407fc37c  mov     rcx, [rsp+330h+Handle]; KeyHandle
0x1407fc381  lea     rax, [rsp+330h+var_2C0]
0x1407fc386  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407fc38b  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407fc38f  mov     r8d, 1; KeyValueInformationClass
0x1407fc395  mov     [rsp+330h+Length], esi; Length
0x1407fc399  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407fc39e  call    ZwQueryValueKey
0x1407fc3a3  test    eax, eax
0x1407fc3a5  js      short loc_1407FC3E5
0x1407fc3a7  cmp     [rbp+230h+var_23C], 3
0x1407fc3ab  jnz     short loc_1407FC3E5
0x1407fc3ad  mov     edx, dword ptr [rbp+230h+Size]
0x1407fc3b0  mov     r8d, 20204D43h
0x1407fc3b6  mov     ecx, esi
0x1407fc3b8  call    ExAllocatePool2
0x1407fc3bd  mov     rdi, rax
0x1407fc3c0  test    rax, rax
0x1407fc3c3  jnz     short loc_1407FC3CF
0x1407fc3c5  mov     ebx, 0C000009Ah
0x1407fc3ca  jmp     loc_1407FC6E2
0x1407fc3cf  mov     eax, [rbp+230h+var_238]
0x1407fc3d2  lea     rdx, [rbp+230h+KeyValueInformation]
0x1407fc3d6  mov     r8d, dword ptr [rbp+230h+Size]; Size
0x1407fc3da  add     rdx, rax; Src
0x1407fc3dd  mov     rcx, rdi; void *
0x1407fc3e0  call    memmove
0x1407fc3e5  lea     rdx, aCurrentconfig_0; "CurrentConfig"
0x1407fc3ec  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc3f1  call    RtlInitUnicodeString
0x1407fc3f6  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x1407fc3fb  lea     rax, [rsp+330h+var_2C0]
0x1407fc400  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407fc405  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407fc409  mov     r8d, 1; KeyValueInformationClass
0x1407fc40f  mov     [rsp+330h+Length], esi; Length
0x1407fc413  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407fc418  call    ZwQueryValueKey
0x1407fc41d  test    eax, eax
0x1407fc41f  js      loc_1407FC6DD
0x1407fc425  cmp     [rbp+230h+var_23C], 4
0x1407fc429  jnz     loc_1407FC6DD
0x1407fc42f  mov     eax, [rbp+230h+var_238]
0x1407fc432  mov     r8, rdi
0x1407fc435  mov     edx, ebx
0x1407fc437  mov     rcx, r15
0x1407fc43a  mov     esi, [rbp+rax+230h+KeyValueInformation]
0x1407fc43e  mov     r9d, esi
0x1407fc441  mov     rax, [rbp+230h+var_270]
0x1407fc445  mov     [rsp+330h+ResultLength], rax
0x1407fc44a  mov     rax, [rbp+230h+P]
0x1407fc44e  mov     qword ptr [rsp+330h+Length], rax
0x1407fc453  call    CmpFilterAcpiDockingState
0x1407fc458  mov     ebx, eax
0x1407fc45a  test    eax, eax
0x1407fc45c  js      loc_1407FC6E2
0x1407fc462  mov     rcx, [rbp+230h+P]
0x1407fc466  lea     rdx, [rsp+330h+var_2BC]
0x1407fc46b  xor     r8d, r8d
0x1407fc46e  mov     rax, r14
0x1407fc471  call    _guard_dispatch_icall_no_overrides
0x1407fc476  cmp     [rsp+330h+var_2BC], 0FFFFFFFFh
0x1407fc47b  mov     ebx, eax
0x1407fc47d  jz      loc_1407FC961
0x1407fc483  test    eax, eax
0x1407fc485  js      loc_1407FC6E2
0x1407fc48b  lea     rax, CmpHardwareProfilesString; "\"$"
0x1407fc492  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc49a  xorps   xmm0, xmm0
0x1407fc49d  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc4a1  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc4a6  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407fc4aa  mov     edx, 20019h; DesiredAccess
0x1407fc4af  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407fc4b6  lea     rcx, [rbp+230h+var_278]; KeyHandle
0x1407fc4ba  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407fc4bf  call    ZwOpenKey
0x1407fc4c4  mov     ebx, eax
0x1407fc4c6  test    eax, eax
0x1407fc4c8  jns     short loc_1407FC4D7
0x1407fc4ca  mov     [rbp+230h+var_278], 0
0x1407fc4d2  jmp     loc_1407FC6E2
0x1407fc4d7  mov     rax, [rbp+230h+P]
0x1407fc4db  mov     ecx, [rsp+330h+var_2BC]
0x1407fc4df  shl     rcx, 5
0x1407fc4e3  mov     r14d, [rcx+rax+20h]
0x1407fc4e8  mov     edx, [rcx+rax+1Ch]
0x1407fc4ec  mov     [rsp+330h+Data], edx
0x1407fc4f0  test    r14b, 8
0x1407fc4f4  jz      short loc_1407FC52E
0x1407fc4f6  mov     rcx, [rsp+330h+KeyHandle]
0x1407fc4fb  lea     rax, [rbp+230h+KeyValueInformation]
0x1407fc4ff  mov     [rsp+330h+Disposition], rax
0x1407fc504  mov     r9d, edx
0x1407fc507  mov     rdx, [rsp+330h+Handle]
0x1407fc50c  lea     rax, [rbp+230h+Dst]
0x1407fc513  mov     r8d, esi
0x1407fc516  mov     qword ptr [rsp+330h+Length], rax
0x1407fc51b  call    CmpMoveBiosAliasTable
0x1407fc520  mov     ebx, eax
0x1407fc522  test    eax, eax
0x1407fc524  js      loc_1407FC6E2
0x1407fc52a  mov     edx, [rsp+330h+Data]
0x1407fc52e  mov     ebx, r14d
0x1407fc531  and     ebx, 4
0x1407fc534  jnz     short loc_1407FC53E
0x1407fc536  cmp     edx, esi
0x1407fc538  jz      loc_1407FC7FD
0x1407fc53e  mov     rcx, [rsp+330h+Handle]; Handle
0x1407fc543  mov     byte ptr [r13+0], 1
0x1407fc548  call    ZwClose
0x1407fc54d  mov     [rsp+330h+Handle], 0
0x1407fc556  test    ebx, ebx
0x1407fc558  jz      short loc_1407FC5A7
0x1407fc55a  mov     r9d, [rsp+330h+Data]
0x1407fc55f  lea     rax, [rsp+330h+Data]
0x1407fc564  mov     r8, [rsp+330h+var_2C8]
0x1407fc569  mov     rdx, [rbp+230h+var_278]
0x1407fc56d  mov     rcx, [rsp+330h+KeyHandle]
0x1407fc572  mov     [rsp+330h+Disposition], rax
0x1407fc577  lea     rax, [rsp+330h+var_2C8]
0x1407fc57c  mov     [rsp+330h+ResultLength], rax
0x1407fc581  movzx   eax, word ptr [r15]
0x1407fc585  mov     word ptr [rsp+330h+Length], ax
0x1407fc58a  call    CmpCloneHwProfile
0x1407fc58f  mov     ebx, eax
0x1407fc591  test    eax, eax
0x1407fc593  jns     loc_1407FC620
0x1407fc599  mov     [rsp+330h+var_2C8], 0
0x1407fc5a2  jmp     loc_1407FC6E2
0x1407fc5a7  mov     rcx, [rsp+330h+var_2C8]; Handle
0x1407fc5ac  call    ZwClose
0x1407fc5b1  mov     r9d, [rsp+330h+Data]
0x1407fc5b6  lea     r8, a04d_0; "%04d"
0x1407fc5bd  mov     edx, 80h; SizeInWords
0x1407fc5c2  lea     rcx, [rbp+230h+Dst]; Dst
0x1407fc5c9  call    swprintf_s
0x1407fc5ce  lea     rdx, [rbp+230h+Dst]; SourceString
0x1407fc5d5  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc5da  call    RtlInitUnicodeString
0x1407fc5df  mov     rax, [rbp+230h+var_278]
0x1407fc5e3  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc5e8  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407fc5ec  lea     rcx, [rsp+330h+var_2C8]; KeyHandle
0x1407fc5f1  lea     rax, [rsp+330h+DestinationString]
0x1407fc5f6  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc5fe  xorps   xmm0, xmm0
0x1407fc601  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc605  mov     edx, 20019h; DesiredAccess
0x1407fc60a  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407fc611  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407fc616  call    ZwOpenKey
0x1407fc61b  jmp     loc_1407FC58F
0x1407fc620  lea     rdx, aCurrentdockinf; "CurrentDockInfo"
0x1407fc627  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407fc62c  call    RtlInitUnicodeString
0x1407fc631  mov     rax, [rsp+330h+KeyHandle]
0x1407fc636  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407fc63b  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407fc63f  lea     rcx, [rsp+330h+Handle]; KeyHandle
0x1407fc644  lea     rax, [rsp+330h+DestinationString]
0x1407fc649  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407fc651  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407fc655  xorps   xmm0, xmm0
0x1407fc658  lea     rax, [rbp+230h+var_280]
0x1407fc65c  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407fc663  mov     [rsp+330h+Disposition], rax; Disposition
0x1407fc668  xor     r9d, r9d; TitleIndex
  ... truncated ...
```
