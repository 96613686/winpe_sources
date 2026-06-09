# OpenDeviceInterfaceKey

- ea: `0x180063908`
- end: `0x180063cc3`
- name: `OpenDeviceInterfaceKey`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800636e4`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180063908`
- `0x180063ccc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180063a76`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c4c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c5c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063a76`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c4c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063b05`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063b05`
- `ntoskrnl!RtlStringFromGUID` at `0x1800639bb`
- `ntoskrnl!RtlStringFromGUID` at `0x180063a25`
- `ntoskrnl!RtlStringFromGUID` at `0x1800639bb`
- `ntoskrnl!RtlStringFromGUID` at `0x180063a25`
- `ntoskrnl!ZwClose` at `0x180063a0c`
- `ntoskrnl!ZwClose` at `0x180063c12`
- `ntoskrnl!ZwClose` at `0x180063c27`
- `ntoskrnl!ZwClose` at `0x180063c3c`
- `ntoskrnl!ZwClose` at `0x180063c6c`
- `ntoskrnl!ZwClose` at `0x180063a0c`
- `ntoskrnl!ZwClose` at `0x180063c12`
- `ntoskrnl!ZwClose` at `0x180063c27`
- `ntoskrnl!ZwClose` at `0x180063c3c`
- `ntoskrnl!ZwClose` at `0x180063c6c`
- `ntoskrnl!ZwOpenKey` at `0x180063ac4`
- `ntoskrnl!ZwOpenKey` at `0x180063b43`
- `ntoskrnl!ZwOpenKey` at `0x180063ba8`
- `ntoskrnl!ZwOpenKey` at `0x180063ac4`
- `ntoskrnl!ZwOpenKey` at `0x180063b43`
- `ntoskrnl!ZwOpenKey` at `0x180063ba8`

## pseudocode

```c
__int64 __fastcall OpenDeviceInterfaceKey(HANDLE *a1, __int64 a2, const GUID *a3, const WCHAR *a4, GUID *Guid)
{
  __int64 v7; // rbx
  __int64 result; // rax
  NTSTATUS v10; // eax
  int v11; // edx
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  int v14; // edx
  NTSTATUS v15; // eax
  int v16; // edx
  PDEVICE_OBJECT v17; // rcx
  int v18; // r9d
  int v19; // edx
  __int64 v20; // [rsp+28h] [rbp-81h]
  HANDLE v21; // [rsp+30h] [rbp-79h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-71h] BYREF
  HANDLE v23; // [rsp+40h] [rbp-69h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  UNICODE_STRING GuidString; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-19h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-9h] BYREF

  KeyHandle = 0;
  v7 = a2;
  Handle = 0;
  v21 = 0;
  v23 = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      95,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  result = OpenDeviceInterfacesKey(&Handle, v7, a3);
  if ( (int)result >= 0 )
  {
    v10 = RtlStringFromGUID(a3, &GuidString);
    v12 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v11) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v11,
            1,
            96,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v10,
            v21);
        }
      }
LABEL_9:
      ZwClose(Handle);
      return v12;
    }
    v13 = RtlStringFromGUID(Guid, &UnicodeString);
    v12 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v14) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          1,
          97,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          v13,
          v21);
      }
      RtlFreeUnicodeString(&GuidString);
      goto LABEL_9;
    }
    ObjectAttributes.RootDirectory = Handle;
    v21 = 0;
    ObjectAttributes.ObjectName = &GuidString;
    v23 = 0;
    KeyHandle = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v12 = v15;
    if ( v15 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, a4);
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = ZwOpenKey(&v23, 0x20019u, &ObjectAttributes);
      v12 = v15;
      if ( v15 >= 0 )
      {
        ObjectAttributes.RootDirectory = v23;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &UnicodeString;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v15 = ZwOpenKey(&v21, 0x20019u, &ObjectAttributes);
        v12 = v15;
        if ( v15 >= 0 )
        {
          *a1 = v21;
          v21 = 0;
          goto LABEL_29;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_29;
        v17 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_29;
        v18 = 100;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_29;
        v17 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_29;
        v18 = 99;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_29;
      v17 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_29;
      v18 = 98;
    }
    LOBYTE(v16) = 5;
    WPP_RECORDER_SF_D(v17->DeviceExtension, v16, 1, v18, (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids, v15);
LABEL_29:
    if ( v21 )
      ZwClose(v21);
    if ( v23 )
      ZwClose(v23);
    if ( KeyHandle )
      ZwClose(KeyHandle);
    RtlFreeUnicodeString(&GuidString);
    RtlFreeUnicodeString(&UnicodeString);
    ZwClose(Handle);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v20) = v12;
      LOBYTE(v19) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        1,
        101,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v20);
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180063908  push    rbp
0x18006390a  push    rbx
0x18006390b  push    rsi
0x18006390c  push    rdi
0x18006390d  push    r12
0x18006390f  push    r13
0x180063911  push    r14
0x180063913  push    r15
0x180063915  lea     rbp, [rsp-0Fh]
0x18006391a  sub     rsp, 0B8h
0x180063921  xorps   xmm0, xmm0
0x180063924  xor     r15d, r15d
0x180063927  xorps   xmm1, xmm1
0x18006392a  mov     [rbp+47h+KeyHandle], r15
0x18006392e  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x180063932  mov     r14, r9
0x180063935  mov     rdi, r8
0x180063938  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x18006393c  mov     rbx, rdx
0x18006393f  mov     [rbp+47h+Handle], r15
0x180063943  mov     rsi, rcx
0x180063946  mov     [rbp+47h+var_C0], r15
0x18006394a  mov     [rbp+47h+var_B0], r15
0x18006394e  xor     eax, eax
0x180063950  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x180063954  movups  xmmword ptr [rbp+47h+GuidString.Length], xmm0
0x180063958  movups  xmmword ptr [rbp+47h+UnicodeString.Length], xmm1
0x18006395c  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180063960  lea     r12, WPP_RECORDER_INITIALIZED
0x180063967  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18006396e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063975  lea     r13d, [r15+1]
0x180063979  jz      short loc_1800639A0
0x18006397b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063982  cmp     [rcx+48h], r15w
0x180063987  jz      short loc_1800639A0
0x180063989  mov     rcx, [rcx+40h]
0x18006398d  lea     r9d, [r15+5Fh]
0x180063991  mov     r8d, r13d
0x180063994  mov     [rsp+0F0h+var_D0], rax
0x180063999  mov     dl, 5
0x18006399b  call    WPP_RECORDER_SF_
0x1800639a0  mov     rdx, rbx
0x1800639a3  lea     rcx, [rbp+47h+Handle]
0x1800639a7  call    OpenDeviceInterfacesKey
0x1800639ac  test    eax, eax
0x1800639ae  js      loc_180063CAE
0x1800639b4  lea     rdx, [rbp+47h+GuidString]; GuidString
0x1800639b8  mov     rcx, rdi; Guid
0x1800639bb  call    cs:__imp_RtlStringFromGUID
0x1800639c2  nop     dword ptr [rax+rax+00h]
0x1800639c7  mov     ebx, eax
0x1800639c9  test    eax, eax
0x1800639cb  jns     short loc_180063A1D
0x1800639cd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800639d4  jz      short loc_180063A08
0x1800639d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800639dd  cmp     [rcx+48h], r15w
0x1800639e2  jz      short loc_180063A08
0x1800639e4  mov     rcx, [rcx+40h]
0x1800639e8  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800639ef  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1800639f3  mov     r9d, 60h ; '`'
0x1800639f9  mov     r8d, r13d
0x1800639fc  mov     [rsp+0F0h+var_D0], rdi
0x180063a01  mov     dl, 5
0x180063a03  call    WPP_RECORDER_SF_D
0x180063a08  mov     rcx, [rbp+47h+Handle]; Handle
0x180063a0c  call    cs:__imp_ZwClose
0x180063a13  nop     dword ptr [rax+rax+00h]
0x180063a18  jmp     loc_180063CAC
0x180063a1d  mov     rcx, [rbp+47h+Guid]; Guid
0x180063a21  lea     rdx, [rbp+47h+UnicodeString]; GuidString
0x180063a25  call    cs:__imp_RtlStringFromGUID
0x180063a2c  nop     dword ptr [rax+rax+00h]
0x180063a31  mov     ebx, eax
0x180063a33  test    eax, eax
0x180063a35  jns     short loc_180063A84
0x180063a37  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063a3e  jz      short loc_180063A72
0x180063a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a47  cmp     [rcx+48h], r15w
0x180063a4c  jz      short loc_180063A72
0x180063a4e  mov     rcx, [rcx+40h]
0x180063a52  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063a59  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180063a5d  mov     r9d, 61h ; 'a'
0x180063a63  mov     r8d, r13d
0x180063a66  mov     [rsp+0F0h+var_D0], rdi
0x180063a6b  mov     dl, 5
0x180063a6d  call    WPP_RECORDER_SF_D
0x180063a72  lea     rcx, [rbp+47h+GuidString]; UnicodeString
0x180063a76  call    cs:__imp_RtlFreeUnicodeString
0x180063a7d  nop     dword ptr [rax+rax+00h]
0x180063a82  jmp     short loc_180063A08
0x180063a84  mov     rax, [rbp+47h+Handle]
0x180063a88  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063a8c  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063a90  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x180063a94  lea     rax, [rbp+47h+GuidString]
0x180063a98  mov     [rbp+47h+var_C0], r15
0x180063a9c  xorps   xmm0, xmm0
0x180063a9f  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063aa3  mov     edi, 30h ; '0'
0x180063aa8  mov     [rbp+47h+var_B0], r15
0x180063aac  mov     edx, 20019h; DesiredAccess
0x180063ab1  mov     [rbp+47h+KeyHandle], r15
0x180063ab5  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063ab8  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x180063abf  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063ac4  call    cs:__imp_ZwOpenKey
0x180063acb  nop     dword ptr [rax+rax+00h]
0x180063ad0  mov     ebx, eax
0x180063ad2  test    eax, eax
0x180063ad4  jns     short loc_180063AFE
0x180063ad6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063add  jz      loc_180063C02
0x180063ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063aea  cmp     [rcx+48h], r15w
0x180063aef  jz      loc_180063C02
0x180063af5  lea     r9d, [rdi+32h]
0x180063af9  jmp     loc_180063BD7
0x180063afe  mov     rdx, r14; SourceString
0x180063b01  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180063b05  call    cs:__imp_RtlInitUnicodeString
0x180063b0c  nop     dword ptr [rax+rax+00h]
0x180063b11  mov     rax, [rbp+47h+KeyHandle]
0x180063b15  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063b19  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063b1d  lea     rcx, [rbp+47h+var_B0]; KeyHandle
0x180063b21  lea     rax, [rbp+47h+DestinationString]
0x180063b25  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063b28  xorps   xmm0, xmm0
0x180063b2b  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063b2f  mov     r14d, 240h
0x180063b35  mov     edx, 20019h; DesiredAccess
0x180063b3a  mov     [rbp+47h+ObjectAttributes.Attributes], r14d
0x180063b3e  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063b43  call    cs:__imp_ZwOpenKey
0x180063b4a  nop     dword ptr [rax+rax+00h]
0x180063b4f  mov     ebx, eax
0x180063b51  test    eax, eax
0x180063b53  jns     short loc_180063B7C
0x180063b55  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063b5c  jz      loc_180063C02
0x180063b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b69  cmp     [rcx+48h], r15w
0x180063b6e  jz      loc_180063C02
0x180063b74  mov     r9d, 63h ; 'c'
0x180063b7a  jmp     short loc_180063BD7
0x180063b7c  mov     rax, [rbp+47h+var_B0]
0x180063b80  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063b84  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063b88  lea     rcx, [rbp+47h+var_C0]; KeyHandle
0x180063b8c  lea     rax, [rbp+47h+UnicodeString]
0x180063b90  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063b93  xorps   xmm0, xmm0
0x180063b96  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063b9a  mov     edx, 20019h; DesiredAccess
0x180063b9f  mov     [rbp+47h+ObjectAttributes.Attributes], r14d
0x180063ba3  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063ba8  call    cs:__imp_ZwOpenKey
0x180063baf  nop     dword ptr [rax+rax+00h]
0x180063bb4  mov     ebx, eax
0x180063bb6  test    eax, eax
0x180063bb8  jns     short loc_180063BF7
0x180063bba  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063bc1  jz      short loc_180063C02
0x180063bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063bca  cmp     [rcx+48h], r15w
0x180063bcf  jz      short loc_180063C02
0x180063bd1  mov     r9d, 64h ; 'd'
0x180063bd7  mov     rcx, [rcx+40h]
0x180063bdb  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063be2  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180063be6  mov     r8d, r13d
0x180063be9  mov     dl, 5
0x180063beb  mov     [rsp+0F0h+var_D0], rdi
0x180063bf0  call    WPP_RECORDER_SF_D
0x180063bf5  jmp     short loc_180063C09
0x180063bf7  mov     rax, [rbp+47h+var_C0]
0x180063bfb  mov     [rsi], rax
0x180063bfe  mov     [rbp+47h+var_C0], r15
0x180063c02  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063c09  mov     rcx, [rbp+47h+var_C0]; Handle
0x180063c0d  test    rcx, rcx
0x180063c10  jz      short loc_180063C1E
0x180063c12  call    cs:__imp_ZwClose
0x180063c19  nop     dword ptr [rax+rax+00h]
0x180063c1e  mov     rcx, [rbp+47h+var_B0]; Handle
0x180063c22  test    rcx, rcx
0x180063c25  jz      short loc_180063C33
0x180063c27  call    cs:__imp_ZwClose
0x180063c2e  nop     dword ptr [rax+rax+00h]
0x180063c33  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x180063c37  test    rcx, rcx
0x180063c3a  jz      short loc_180063C48
0x180063c3c  call    cs:__imp_ZwClose
0x180063c43  nop     dword ptr [rax+rax+00h]
0x180063c48  lea     rcx, [rbp+47h+GuidString]; UnicodeString
0x180063c4c  call    cs:__imp_RtlFreeUnicodeString
0x180063c53  nop     dword ptr [rax+rax+00h]
0x180063c58  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x180063c5c  call    cs:__imp_RtlFreeUnicodeString
0x180063c63  nop     dword ptr [rax+rax+00h]
0x180063c68  mov     rcx, [rbp+47h+Handle]; Handle
0x180063c6c  call    cs:__imp_ZwClose
0x180063c73  nop     dword ptr [rax+rax+00h]
0x180063c78  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063c7f  jz      short loc_180063CAC
0x180063c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c88  cmp     [rcx+48h], r15w
0x180063c8d  jz      short loc_180063CAC
0x180063c8f  mov     rcx, [rcx+40h]
0x180063c93  mov     r9d, 65h ; 'e'
0x180063c99  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180063c9d  mov     r8d, r13d
0x180063ca0  mov     dl, 5
0x180063ca2  mov     [rsp+0F0h+var_D0], rdi
0x180063ca7  call    WPP_RECORDER_SF_D
0x180063cac  mov     eax, ebx
0x180063cae  add     rsp, 0B8h
0x180063cb5  pop     r15
0x180063cb7  pop     r14
0x180063cb9  pop     r13
0x180063cbb  pop     r12
0x180063cbd  pop     rdi
0x180063cbe  pop     rsi
0x180063cbf  pop     rbx
0x180063cc0  pop     rbp
0x180063cc1  retn
```
