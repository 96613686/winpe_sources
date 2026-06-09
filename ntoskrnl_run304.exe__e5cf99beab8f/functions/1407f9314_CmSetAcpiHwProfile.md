# CmSetAcpiHwProfile

- ea: `0x1407f9314`
- end: `0x1407f9b7a`
- name: `CmSetAcpiHwProfile`
- size: `2150`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140778424`
- `0x140c8b488`

## callees

- `0x1403f2d50`
- `0x14047f8a8`
- `0x140541a30`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dab70`
- `0x1406dac30`
- `0x1406db490`
- `0x1406e8590`
- `0x1406f4480`
- `0x140724264`
- `0x1407f580c`
- `0x1407f9314`
- `0x1407f9b80`
- `0x1407fa0e0`
- `0x1407fa32c`
- `0x1407fab68`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x1407f9b07`: `\Registry\Machine\%wZ\CurrentControlSet\Hardware Profiles\%04d`
- `0x1407f95e5`: `CurrentConfig`
- `0x1407f989c`: `CurrentConfig`

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
  unsigned int v34; // [rsp+74h] [rbp-8Ch] BYREF
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
      v11 = guard_dispatch_icall_no_overrides(P, &v34, 0);
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
                                     (PUNICODE_STRING)&PspActiveProcessLock.SchedulingGroup,
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
0x1407f9314  mov     [rsp-8+arg_10], rbx
0x1407f9319  push    rbp
0x1407f931a  push    rsi
0x1407f931b  push    rdi
0x1407f931c  push    r12
0x1407f931e  push    r13
0x1407f9320  push    r14
0x1407f9322  push    r15
0x1407f9324  lea     rbp, [rsp-200h]
0x1407f932c  sub     rsp, 300h
0x1407f9333  mov     rax, cs:__security_cookie
0x1407f933a  xor     rax, rsp
0x1407f933d  mov     [rbp+230h+var_40], rax
0x1407f9344  mov     r13, [rbp+230h+arg_20]
0x1407f934b  lea     r8, [rbp+230h+var_250]
0x1407f934f  xorps   xmm0, xmm0
0x1407f9352  mov     [rbp+230h+var_258], r9
0x1407f9356  mov     r14, rdx
0x1407f9359  mov     [rbp+230h+var_260], 0
0x1407f9361  xorps   xmm1, xmm1
0x1407f9364  mov     [rsp+330h+KeyHandle], 0
0x1407f936d  xor     edi, edi
0x1407f936f  mov     [rsp+330h+var_2C8], 0
0x1407f9378  xor     eax, eax
0x1407f937a  mov     [rsp+330h+Handle], 0
0x1407f9383  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x1407f9387  lea     rdx, [rbp+230h+var_260]
0x1407f938b  mov     [r13+0], al
0x1407f938f  mov     r15, rcx
0x1407f9392  mov     [rbp+230h+var_268], 0
0x1407f939a  mov     [rbp+230h+var_278], 0
0x1407f93a2  movups  [rbp+230h+var_250], xmm0
0x1407f93a6  mov     [rsp+330h+var_2C0], 0
0x1407f93ae  movups  xmmword ptr [rsp+330h+DestinationString.Length], xmm1
0x1407f93b3  mov     [rsp+330h+var_2EC], 0
0x1407f93bb  mov     [rsp+330h+var_2BC], 0
0x1407f93c3  mov     [rsp+330h+Data], 0
0x1407f93cb  mov     [rbp+230h+var_280], 0
0x1407f93d2  mov     [rbp+230h+var_270], rdi
0x1407f93d6  mov     [rbp+230h+P], rdi
0x1407f93da  movups  xmmword ptr [rsp+330h+ObjectAttributes.Length], xmm0
0x1407f93df  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x1407f93e3  call    CmpOpenDevicesControlSet
0x1407f93e8  mov     ebx, eax
0x1407f93ea  test    eax, eax
0x1407f93ec  js      loc_1407F98E2
0x1407f93f2  mov     r12, [rbp+230h+var_260]
0x1407f93f6  lea     rax, CmpControlIdConfigDbString; "$&"
0x1407f93fd  xorps   xmm0, xmm0
0x1407f9400  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407f9404  mov     esi, 240h
0x1407f9409  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f940d  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f9412  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407f9415  mov     edx, 20019h; DesiredAccess
0x1407f941a  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f9422  lea     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x1407f9427  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f942c  call    ZwOpenKey
0x1407f9431  mov     ebx, eax
0x1407f9433  test    eax, eax
0x1407f9435  jns     short loc_1407F9441
0x1407f9437  mov     [rsp+330h+KeyHandle], rdi
0x1407f943c  jmp     loc_1407F98E2
0x1407f9441  mov     rcx, [rsp+330h+KeyHandle]; int
0x1407f9446  lea     rax, [rbp+230h+KeyValueInformation]
0x1407f944a  mov     dword ptr [rsp+330h+ResultLength], 100h
0x1407f9452  lea     r9, [rbp+230h+Dst]; int
0x1407f9459  lea     r8, [rbp+230h+var_270]; int
0x1407f945d  mov     qword ptr [rsp+330h+Length], rax; KeyValueInformation
0x1407f9462  lea     rdx, [rbp+230h+P]; int
0x1407f9466  call    CmpGetAcpiProfileInformation
0x1407f946b  mov     ebx, eax
0x1407f946d  test    eax, eax
0x1407f946f  js      loc_1407F98E2
0x1407f9475  lea     rax, CmpHardwareProfilesCurrentString; "24"
0x1407f947c  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f9484  xorps   xmm0, xmm0
0x1407f9487  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f948b  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f9490  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407f9494  mov     edx, 20019h; DesiredAccess
0x1407f9499  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407f949c  lea     rcx, [rsp+330h+var_2C8]; KeyHandle
0x1407f94a1  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f94a6  call    ZwOpenKey
0x1407f94ab  mov     ebx, eax
0x1407f94ad  test    eax, eax
0x1407f94af  jns     short loc_1407F94BB
0x1407f94b1  mov     [rsp+330h+var_2C8], rdi
0x1407f94b6  jmp     loc_1407F98E2
0x1407f94bb  lea     rdx, aCurrentdockinf; "CurrentDockInfo"
0x1407f94c2  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f94c7  call    RtlInitUnicodeString
0x1407f94cc  mov     rax, [rsp+330h+KeyHandle]
0x1407f94d1  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f94d6  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407f94da  lea     rcx, [rsp+330h+Handle]; KeyHandle
0x1407f94df  lea     rax, [rsp+330h+DestinationString]
0x1407f94e4  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f94ec  xorps   xmm0, xmm0
0x1407f94ef  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f94f3  mov     edx, 20019h; DesiredAccess
0x1407f94f8  mov     [rbp+230h+ObjectAttributes.Attributes], esi
0x1407f94fb  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f9500  call    ZwOpenKey
0x1407f9505  mov     ebx, eax
0x1407f9507  test    eax, eax
0x1407f9509  jns     short loc_1407F9515
0x1407f950b  mov     [rsp+330h+Handle], rdi
0x1407f9510  jmp     loc_1407F98E2
0x1407f9515  lea     rdx, aDockingstate; "DockingState"
0x1407f951c  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f9521  call    RtlInitUnicodeString
0x1407f9526  mov     rcx, [rsp+330h+Handle]; KeyHandle
0x1407f952b  lea     rax, [rsp+330h+var_2C0]
0x1407f9530  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407f9535  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407f9539  mov     esi, 100h
0x1407f953e  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407f9543  mov     r8d, 1; KeyValueInformationClass
0x1407f9549  mov     [rsp+330h+Length], esi; Length
0x1407f954d  call    ZwQueryValueKey
0x1407f9552  test    eax, eax
0x1407f9554  js      loc_1407F98DD
0x1407f955a  cmp     [rbp+230h+var_23C], 4
0x1407f955e  jnz     loc_1407F98DD
0x1407f9564  mov     eax, [rbp+230h+var_238]
0x1407f9567  lea     rdx, aAcpiserialnumb; "AcpiSerialNumber"
0x1407f956e  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f9573  mov     ebx, [rbp+rax+230h+KeyValueInformation]
0x1407f9577  call    RtlInitUnicodeString
0x1407f957c  mov     rcx, [rsp+330h+Handle]; KeyHandle
0x1407f9581  lea     rax, [rsp+330h+var_2C0]
0x1407f9586  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407f958b  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407f958f  mov     r8d, 1; KeyValueInformationClass
0x1407f9595  mov     [rsp+330h+Length], esi; Length
0x1407f9599  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407f959e  call    ZwQueryValueKey
0x1407f95a3  test    eax, eax
0x1407f95a5  js      short loc_1407F95E5
0x1407f95a7  cmp     [rbp+230h+var_23C], 3
0x1407f95ab  jnz     short loc_1407F95E5
0x1407f95ad  mov     edx, dword ptr [rbp+230h+Size]
0x1407f95b0  mov     r8d, 20204D43h
0x1407f95b6  mov     ecx, esi
0x1407f95b8  call    ExAllocatePool2
0x1407f95bd  mov     rdi, rax
0x1407f95c0  test    rax, rax
0x1407f95c3  jnz     short loc_1407F95CF
0x1407f95c5  mov     ebx, 0C000009Ah
0x1407f95ca  jmp     loc_1407F98E2
0x1407f95cf  mov     eax, [rbp+230h+var_238]
0x1407f95d2  lea     rdx, [rbp+230h+KeyValueInformation]
0x1407f95d6  mov     r8d, dword ptr [rbp+230h+Size]; Size
0x1407f95da  add     rdx, rax; Src
0x1407f95dd  mov     rcx, rdi; void *
0x1407f95e0  call    memmove
0x1407f95e5  lea     rdx, aCurrentconfig_0; "CurrentConfig"
0x1407f95ec  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f95f1  call    RtlInitUnicodeString
0x1407f95f6  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x1407f95fb  lea     rax, [rsp+330h+var_2C0]
0x1407f9600  mov     [rsp+330h+ResultLength], rax; ResultLength
0x1407f9605  lea     r9, [rbp+230h+KeyValueInformation]; KeyValueInformation
0x1407f9609  mov     r8d, 1; KeyValueInformationClass
0x1407f960f  mov     [rsp+330h+Length], esi; Length
0x1407f9613  lea     rdx, [rsp+330h+DestinationString]; ValueName
0x1407f9618  call    ZwQueryValueKey
0x1407f961d  test    eax, eax
0x1407f961f  js      loc_1407F98DD
0x1407f9625  cmp     [rbp+230h+var_23C], 4
0x1407f9629  jnz     loc_1407F98DD
0x1407f962f  mov     eax, [rbp+230h+var_238]
0x1407f9632  mov     r8, rdi
0x1407f9635  mov     edx, ebx
0x1407f9637  mov     rcx, r15
0x1407f963a  mov     esi, [rbp+rax+230h+KeyValueInformation]
0x1407f963e  mov     r9d, esi
0x1407f9641  mov     rax, [rbp+230h+var_270]
0x1407f9645  mov     [rsp+330h+ResultLength], rax
0x1407f964a  mov     rax, [rbp+230h+P]
0x1407f964e  mov     qword ptr [rsp+330h+Length], rax
0x1407f9653  call    CmpFilterAcpiDockingState
0x1407f9658  mov     ebx, eax
0x1407f965a  test    eax, eax
0x1407f965c  js      loc_1407F98E2
0x1407f9662  mov     rcx, [rbp+230h+P]
0x1407f9666  lea     rdx, [rsp+330h+var_2BC]
0x1407f966b  xor     r8d, r8d
0x1407f966e  mov     rax, r14
0x1407f9671  call    _guard_dispatch_icall_no_overrides
0x1407f9676  cmp     [rsp+330h+var_2BC], 0FFFFFFFFh
0x1407f967b  mov     ebx, eax
0x1407f967d  jz      loc_1407F9B61
0x1407f9683  test    eax, eax
0x1407f9685  js      loc_1407F98E2
0x1407f968b  lea     rax, CmpHardwareProfilesString; "\"$"
0x1407f9692  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f969a  xorps   xmm0, xmm0
0x1407f969d  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f96a1  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f96a6  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x1407f96aa  mov     edx, 20019h; DesiredAccess
0x1407f96af  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407f96b6  lea     rcx, [rbp+230h+var_278]; KeyHandle
0x1407f96ba  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f96bf  call    ZwOpenKey
0x1407f96c4  mov     ebx, eax
0x1407f96c6  test    eax, eax
0x1407f96c8  jns     short loc_1407F96D7
0x1407f96ca  mov     [rbp+230h+var_278], 0
0x1407f96d2  jmp     loc_1407F98E2
0x1407f96d7  mov     rax, [rbp+230h+P]
0x1407f96db  mov     ecx, [rsp+330h+var_2BC]
0x1407f96df  shl     rcx, 5
0x1407f96e3  mov     r14d, [rcx+rax+20h]
0x1407f96e8  mov     edx, [rcx+rax+1Ch]
0x1407f96ec  mov     [rsp+330h+Data], edx
0x1407f96f0  test    r14b, 8
0x1407f96f4  jz      short loc_1407F972E
0x1407f96f6  mov     rcx, [rsp+330h+KeyHandle]
0x1407f96fb  lea     rax, [rbp+230h+KeyValueInformation]
0x1407f96ff  mov     [rsp+330h+Disposition], rax
0x1407f9704  mov     r9d, edx
0x1407f9707  mov     rdx, [rsp+330h+Handle]
0x1407f970c  lea     rax, [rbp+230h+Dst]
0x1407f9713  mov     r8d, esi
0x1407f9716  mov     qword ptr [rsp+330h+Length], rax
0x1407f971b  call    CmpMoveBiosAliasTable
0x1407f9720  mov     ebx, eax
0x1407f9722  test    eax, eax
0x1407f9724  js      loc_1407F98E2
0x1407f972a  mov     edx, [rsp+330h+Data]
0x1407f972e  mov     ebx, r14d
0x1407f9731  and     ebx, 4
0x1407f9734  jnz     short loc_1407F973E
0x1407f9736  cmp     edx, esi
0x1407f9738  jz      loc_1407F99FD
0x1407f973e  mov     rcx, [rsp+330h+Handle]; Handle
0x1407f9743  mov     byte ptr [r13+0], 1
0x1407f9748  call    ZwClose
0x1407f974d  mov     [rsp+330h+Handle], 0
0x1407f9756  test    ebx, ebx
0x1407f9758  jz      short loc_1407F97A7
0x1407f975a  mov     r9d, [rsp+330h+Data]
0x1407f975f  lea     rax, [rsp+330h+Data]
0x1407f9764  mov     r8, [rsp+330h+var_2C8]
0x1407f9769  mov     rdx, [rbp+230h+var_278]
0x1407f976d  mov     rcx, [rsp+330h+KeyHandle]
0x1407f9772  mov     [rsp+330h+Disposition], rax
0x1407f9777  lea     rax, [rsp+330h+var_2C8]
0x1407f977c  mov     [rsp+330h+ResultLength], rax
0x1407f9781  movzx   eax, word ptr [r15]
0x1407f9785  mov     word ptr [rsp+330h+Length], ax
0x1407f978a  call    CmpCloneHwProfile
0x1407f978f  mov     ebx, eax
0x1407f9791  test    eax, eax
0x1407f9793  jns     loc_1407F9820
0x1407f9799  mov     [rsp+330h+var_2C8], 0
0x1407f97a2  jmp     loc_1407F98E2
0x1407f97a7  mov     rcx, [rsp+330h+var_2C8]; Handle
0x1407f97ac  call    ZwClose
0x1407f97b1  mov     r9d, [rsp+330h+Data]
0x1407f97b6  lea     r8, a04d_0; "%04d"
0x1407f97bd  mov     edx, 80h; SizeInWords
0x1407f97c2  lea     rcx, [rbp+230h+Dst]; Dst
0x1407f97c9  call    swprintf_s
0x1407f97ce  lea     rdx, [rbp+230h+Dst]; SourceString
0x1407f97d5  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f97da  call    RtlInitUnicodeString
0x1407f97df  mov     rax, [rbp+230h+var_278]
0x1407f97e3  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f97e8  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407f97ec  lea     rcx, [rsp+330h+var_2C8]; KeyHandle
0x1407f97f1  lea     rax, [rsp+330h+DestinationString]
0x1407f97f6  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f97fe  xorps   xmm0, xmm0
0x1407f9801  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f9805  mov     edx, 20019h; DesiredAccess
0x1407f980a  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407f9811  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407f9816  call    ZwOpenKey
0x1407f981b  jmp     loc_1407F978F
0x1407f9820  lea     rdx, aCurrentdockinf; "CurrentDockInfo"
0x1407f9827  lea     rcx, [rsp+330h+DestinationString]; DestinationString
0x1407f982c  call    RtlInitUnicodeString
0x1407f9831  mov     rax, [rsp+330h+KeyHandle]
0x1407f9836  lea     r8, [rsp+330h+ObjectAttributes]; ObjectAttributes
0x1407f983b  mov     [rbp+230h+ObjectAttributes.RootDirectory], rax
0x1407f983f  lea     rcx, [rsp+330h+Handle]; KeyHandle
0x1407f9844  lea     rax, [rsp+330h+DestinationString]
0x1407f9849  mov     [rsp+330h+ObjectAttributes.Length], 30h ; '0'
0x1407f9851  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x1407f9855  xorps   xmm0, xmm0
0x1407f9858  lea     rax, [rbp+230h+var_280]
0x1407f985c  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x1407f9863  mov     [rsp+330h+Disposition], rax; Disposition
0x1407f9868  xor     r9d, r9d; TitleIndex
  ... truncated ...
```
