# OpenDeviceInterfaceKey

- ea: `0x180063aa8`
- end: `0x180063e63`
- name: `OpenDeviceInterfaceKey`
- size: `955`
- prototype: `__int64 __fastcall(HANDLE *, __int64, const GUID *, const WCHAR *, GUID *Guid)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063884`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180063aa8`
- `0x180063e6c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c16`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063dec`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063dfc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063c16`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063dec`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180063dfc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063ca5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063ca5`
- `ntoskrnl!RtlStringFromGUID` at `0x180063b5b`
- `ntoskrnl!RtlStringFromGUID` at `0x180063bc5`
- `ntoskrnl!RtlStringFromGUID` at `0x180063b5b`
- `ntoskrnl!RtlStringFromGUID` at `0x180063bc5`
- `ntoskrnl!ZwClose` at `0x180063bac`
- `ntoskrnl!ZwClose` at `0x180063db2`
- `ntoskrnl!ZwClose` at `0x180063dc7`
- `ntoskrnl!ZwClose` at `0x180063ddc`
- `ntoskrnl!ZwClose` at `0x180063e0c`
- `ntoskrnl!ZwClose` at `0x180063bac`
- `ntoskrnl!ZwClose` at `0x180063db2`
- `ntoskrnl!ZwClose` at `0x180063dc7`
- `ntoskrnl!ZwClose` at `0x180063ddc`
- `ntoskrnl!ZwClose` at `0x180063e0c`
- `ntoskrnl!ZwOpenKey` at `0x180063c64`
- `ntoskrnl!ZwOpenKey` at `0x180063ce3`
- `ntoskrnl!ZwOpenKey` at `0x180063d48`
- `ntoskrnl!ZwOpenKey` at `0x180063c64`
- `ntoskrnl!ZwOpenKey` at `0x180063ce3`
- `ntoskrnl!ZwOpenKey` at `0x180063d48`

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
0x180063aa8  push    rbp
0x180063aaa  push    rbx
0x180063aab  push    rsi
0x180063aac  push    rdi
0x180063aad  push    r12
0x180063aaf  push    r13
0x180063ab1  push    r14
0x180063ab3  push    r15
0x180063ab5  lea     rbp, [rsp-0Fh]
0x180063aba  sub     rsp, 0B8h
0x180063ac1  xorps   xmm0, xmm0
0x180063ac4  xor     r15d, r15d
0x180063ac7  xorps   xmm1, xmm1
0x180063aca  mov     [rbp+47h+KeyHandle], r15
0x180063ace  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x180063ad2  mov     r14, r9
0x180063ad5  mov     rdi, r8
0x180063ad8  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x180063adc  mov     rbx, rdx
0x180063adf  mov     [rbp+47h+Handle], r15
0x180063ae3  mov     rsi, rcx
0x180063ae6  mov     [rbp+47h+var_C0], r15
0x180063aea  mov     [rbp+47h+var_B0], r15
0x180063aee  xor     eax, eax
0x180063af0  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x180063af4  movups  xmmword ptr [rbp+47h+GuidString.Length], xmm0
0x180063af8  movups  xmmword ptr [rbp+47h+UnicodeString.Length], xmm1
0x180063afc  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180063b00  lea     r12, WPP_RECORDER_INITIALIZED
0x180063b07  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063b0e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063b15  lea     r13d, [r15+1]
0x180063b19  jz      short loc_180063B40
0x180063b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b22  cmp     [rcx+48h], r15w
0x180063b27  jz      short loc_180063B40
0x180063b29  mov     rcx, [rcx+40h]
0x180063b2d  lea     r9d, [r15+5Fh]
0x180063b31  mov     r8d, r13d
0x180063b34  mov     [rsp+0F0h+var_D0], rax
0x180063b39  mov     dl, 5
0x180063b3b  call    WPP_RECORDER_SF_
0x180063b40  mov     rdx, rbx
0x180063b43  lea     rcx, [rbp+47h+Handle]
0x180063b47  call    OpenDeviceInterfacesKey
0x180063b4c  test    eax, eax
0x180063b4e  js      loc_180063E4E
0x180063b54  lea     rdx, [rbp+47h+GuidString]; GuidString
0x180063b58  mov     rcx, rdi; Guid
0x180063b5b  call    cs:__imp_RtlStringFromGUID
0x180063b62  nop     dword ptr [rax+rax+00h]
0x180063b67  mov     ebx, eax
0x180063b69  test    eax, eax
0x180063b6b  jns     short loc_180063BBD
0x180063b6d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063b74  jz      short loc_180063BA8
0x180063b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180063b7d  cmp     [rcx+48h], r15w
0x180063b82  jz      short loc_180063BA8
0x180063b84  mov     rcx, [rcx+40h]
0x180063b88  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063b8f  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180063b93  mov     r9d, 60h ; '`'
0x180063b99  mov     r8d, r13d
0x180063b9c  mov     [rsp+0F0h+var_D0], rdi
0x180063ba1  mov     dl, 5
0x180063ba3  call    WPP_RECORDER_SF_D
0x180063ba8  mov     rcx, [rbp+47h+Handle]; Handle
0x180063bac  call    cs:__imp_ZwClose
0x180063bb3  nop     dword ptr [rax+rax+00h]
0x180063bb8  jmp     loc_180063E4C
0x180063bbd  mov     rcx, [rbp+47h+Guid]; Guid
0x180063bc1  lea     rdx, [rbp+47h+UnicodeString]; GuidString
0x180063bc5  call    cs:__imp_RtlStringFromGUID
0x180063bcc  nop     dword ptr [rax+rax+00h]
0x180063bd1  mov     ebx, eax
0x180063bd3  test    eax, eax
0x180063bd5  jns     short loc_180063C24
0x180063bd7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063bde  jz      short loc_180063C12
0x180063be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180063be7  cmp     [rcx+48h], r15w
0x180063bec  jz      short loc_180063C12
0x180063bee  mov     rcx, [rcx+40h]
0x180063bf2  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063bf9  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180063bfd  mov     r9d, 61h ; 'a'
0x180063c03  mov     r8d, r13d
0x180063c06  mov     [rsp+0F0h+var_D0], rdi
0x180063c0b  mov     dl, 5
0x180063c0d  call    WPP_RECORDER_SF_D
0x180063c12  lea     rcx, [rbp+47h+GuidString]; UnicodeString
0x180063c16  call    cs:__imp_RtlFreeUnicodeString
0x180063c1d  nop     dword ptr [rax+rax+00h]
0x180063c22  jmp     short loc_180063BA8
0x180063c24  mov     rax, [rbp+47h+Handle]
0x180063c28  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063c2c  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063c30  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x180063c34  lea     rax, [rbp+47h+GuidString]
0x180063c38  mov     [rbp+47h+var_C0], r15
0x180063c3c  xorps   xmm0, xmm0
0x180063c3f  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063c43  mov     edi, 30h ; '0'
0x180063c48  mov     [rbp+47h+var_B0], r15
0x180063c4c  mov     edx, 20019h; DesiredAccess
0x180063c51  mov     [rbp+47h+KeyHandle], r15
0x180063c55  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063c58  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x180063c5f  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063c64  call    cs:__imp_ZwOpenKey
0x180063c6b  nop     dword ptr [rax+rax+00h]
0x180063c70  mov     ebx, eax
0x180063c72  test    eax, eax
0x180063c74  jns     short loc_180063C9E
0x180063c76  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063c7d  jz      loc_180063DA2
0x180063c83  mov     rcx, cs:WPP_GLOBAL_Control
0x180063c8a  cmp     [rcx+48h], r15w
0x180063c8f  jz      loc_180063DA2
0x180063c95  lea     r9d, [rdi+32h]
0x180063c99  jmp     loc_180063D77
0x180063c9e  mov     rdx, r14; SourceString
0x180063ca1  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180063ca5  call    cs:__imp_RtlInitUnicodeString
0x180063cac  nop     dword ptr [rax+rax+00h]
0x180063cb1  mov     rax, [rbp+47h+KeyHandle]
0x180063cb5  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063cb9  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063cbd  lea     rcx, [rbp+47h+var_B0]; KeyHandle
0x180063cc1  lea     rax, [rbp+47h+DestinationString]
0x180063cc5  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063cc8  xorps   xmm0, xmm0
0x180063ccb  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063ccf  mov     r14d, 240h
0x180063cd5  mov     edx, 20019h; DesiredAccess
0x180063cda  mov     [rbp+47h+ObjectAttributes.Attributes], r14d
0x180063cde  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063ce3  call    cs:__imp_ZwOpenKey
0x180063cea  nop     dword ptr [rax+rax+00h]
0x180063cef  mov     ebx, eax
0x180063cf1  test    eax, eax
0x180063cf3  jns     short loc_180063D1C
0x180063cf5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063cfc  jz      loc_180063DA2
0x180063d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180063d09  cmp     [rcx+48h], r15w
0x180063d0e  jz      loc_180063DA2
0x180063d14  mov     r9d, 63h ; 'c'
0x180063d1a  jmp     short loc_180063D77
0x180063d1c  mov     rax, [rbp+47h+var_B0]
0x180063d20  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180063d24  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x180063d28  lea     rcx, [rbp+47h+var_C0]; KeyHandle
0x180063d2c  lea     rax, [rbp+47h+UnicodeString]
0x180063d30  mov     [rbp+47h+ObjectAttributes.Length], edi
0x180063d33  xorps   xmm0, xmm0
0x180063d36  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180063d3a  mov     edx, 20019h; DesiredAccess
0x180063d3f  mov     [rbp+47h+ObjectAttributes.Attributes], r14d
0x180063d43  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063d48  call    cs:__imp_ZwOpenKey
0x180063d4f  nop     dword ptr [rax+rax+00h]
0x180063d54  mov     ebx, eax
0x180063d56  test    eax, eax
0x180063d58  jns     short loc_180063D97
0x180063d5a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063d61  jz      short loc_180063DA2
0x180063d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180063d6a  cmp     [rcx+48h], r15w
0x180063d6f  jz      short loc_180063DA2
0x180063d71  mov     r9d, 64h ; 'd'
0x180063d77  mov     rcx, [rcx+40h]
0x180063d7b  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063d82  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180063d86  mov     r8d, r13d
0x180063d89  mov     dl, 5
0x180063d8b  mov     [rsp+0F0h+var_D0], rdi
0x180063d90  call    WPP_RECORDER_SF_D
0x180063d95  jmp     short loc_180063DA9
0x180063d97  mov     rax, [rbp+47h+var_C0]
0x180063d9b  mov     [rsi], rax
0x180063d9e  mov     [rbp+47h+var_C0], r15
0x180063da2  lea     rdi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063da9  mov     rcx, [rbp+47h+var_C0]; Handle
0x180063dad  test    rcx, rcx
0x180063db0  jz      short loc_180063DBE
0x180063db2  call    cs:__imp_ZwClose
0x180063db9  nop     dword ptr [rax+rax+00h]
0x180063dbe  mov     rcx, [rbp+47h+var_B0]; Handle
0x180063dc2  test    rcx, rcx
0x180063dc5  jz      short loc_180063DD3
0x180063dc7  call    cs:__imp_ZwClose
0x180063dce  nop     dword ptr [rax+rax+00h]
0x180063dd3  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x180063dd7  test    rcx, rcx
0x180063dda  jz      short loc_180063DE8
0x180063ddc  call    cs:__imp_ZwClose
0x180063de3  nop     dword ptr [rax+rax+00h]
0x180063de8  lea     rcx, [rbp+47h+GuidString]; UnicodeString
0x180063dec  call    cs:__imp_RtlFreeUnicodeString
0x180063df3  nop     dword ptr [rax+rax+00h]
0x180063df8  lea     rcx, [rbp+47h+UnicodeString]; UnicodeString
0x180063dfc  call    cs:__imp_RtlFreeUnicodeString
0x180063e03  nop     dword ptr [rax+rax+00h]
0x180063e08  mov     rcx, [rbp+47h+Handle]; Handle
0x180063e0c  call    cs:__imp_ZwClose
0x180063e13  nop     dword ptr [rax+rax+00h]
0x180063e18  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180063e1f  jz      short loc_180063E4C
0x180063e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e28  cmp     [rcx+48h], r15w
0x180063e2d  jz      short loc_180063E4C
0x180063e2f  mov     rcx, [rcx+40h]
0x180063e33  mov     r9d, 65h ; 'e'
0x180063e39  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x180063e3d  mov     r8d, r13d
0x180063e40  mov     dl, 5
0x180063e42  mov     [rsp+0F0h+var_D0], rdi
0x180063e47  call    WPP_RECORDER_SF_D
0x180063e4c  mov     eax, ebx
0x180063e4e  add     rsp, 0B8h
0x180063e55  pop     r15
0x180063e57  pop     r14
0x180063e59  pop     r13
0x180063e5b  pop     r12
0x180063e5d  pop     rdi
0x180063e5e  pop     rsi
0x180063e5f  pop     rbx
0x180063e60  pop     rbp
0x180063e61  retn
```
