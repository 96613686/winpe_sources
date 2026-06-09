# RegisterDeviceAssociation

- ea: `0x180063884`
- end: `0x180063aa2`
- name: `RegisterDeviceAssociation`
- size: `542`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065620`

## callees

- `0x180011684`
- `0x180034ba0`
- `0x180063884`
- `0x180063aa8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800638dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063949`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800638dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180063949`
- `ntoskrnl!ZwClose` at `0x1800639e1`
- `ntoskrnl!ZwClose` at `0x1800639f1`
- `ntoskrnl!ZwClose` at `0x180063a00`
- `ntoskrnl!ZwClose` at `0x1800639e1`
- `ntoskrnl!ZwClose` at `0x1800639f1`
- `ntoskrnl!ZwClose` at `0x180063a00`
- `ntoskrnl!ZwOpenKey` at `0x180063988`
- `ntoskrnl!ZwOpenKey` at `0x180063988`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1800638fe`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1800638fe`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x180063a57`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x180063a57`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800639ba`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800639ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063a74`
- `ntoskrnl!ExFreePoolWithTag` at `0x180063a74`

## pseudocode

```c
__int64 __fastcall RegisterDeviceAssociation(PDEVICE_OBJECT *a1, __int64 a2, __int64 a3)
{
  const WCHAR *v4; // rdx
  int v7; // ebx
  HANDLE v8; // rsi
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  void *v12; // rcx
  void *DeviceInterfaceRegKey[2]; // [rsp+30h] [rbp-39h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  UNICODE_STRING v16; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  void *KeyHandle; // [rsp+D0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+D8h] [rbp+6Fh] BYREF

  v4 = *(const WCHAR **)(a2 + 96);
  Handle = 0;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v16 = 0;
  *(_OWORD *)DeviceInterfaceRegKey = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  v7 = IoRegisterDeviceInterface(a1[12], (const GUID *)(a3 + 16), &DestinationString, (PUNICODE_STRING)(a3 + 32));
  if ( v7 >= 0 )
  {
    v7 = OpenDeviceInterfaceKey(&Handle, a1 + 42, a2 + 64, a2 + 136, a3 + 16);
    if ( v7 >= 0 )
    {
      RtlInitUnicodeString(&v16, L"Parameters");
      v8 = Handle;
      ObjectAttributes.ObjectName = &v16;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      v7 = v9;
      if ( v9 == -1073741772 )
      {
        v7 = 0;
      }
      else if ( v9 >= 0 )
      {
        DeviceInterfaceRegKey[1] = 0;
        DeviceInterfaceRegKey[0] = a1;
        v7 = IoOpenDeviceInterfaceRegistryKey((PUNICODE_STRING)(a3 + 32), 0x2001Fu, &DeviceInterfaceRegKey[1]);
        if ( v7 >= 0 )
        {
          v7 = CopyDeviceInterfaceParameters(KeyHandle, 0, (__int64)DeviceInterfaceRegKey);
          ZwClose(DeviceInterfaceRegKey[1]);
        }
        ZwClose(KeyHandle);
      }
      ZwClose(v8);
      if ( v7 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_S(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            v11,
            70,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            *(_QWORD *)(a3 + 40));
        v7 = IoSetDeviceInterfaceState((PUNICODE_STRING)(a3 + 32), 1u);
        if ( v7 < 0 )
        {
          v12 = *(void **)(a3 + 40);
          if ( v12 )
          {
            ExFreePoolWithTag(v12, 0);
            *(_QWORD *)(a3 + 40) = 0;
          }
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180063884  mov     [rsp-8+arg_10], rbx
0x180063889  push    rbp
0x18006388a  push    rsi
0x18006388b  push    rdi
0x18006388c  push    r12
0x18006388e  push    r13
0x180063890  push    r14
0x180063892  push    r15
0x180063894  lea     rbp, [rsp-27h]
0x180063899  sub     rsp, 90h
0x1800638a0  xorps   xmm0, xmm0
0x1800638a3  mov     rsi, rdx
0x1800638a6  mov     rdx, [rdx+60h]; SourceString
0x1800638aa  mov     r14, rcx
0x1800638ad  xor     r13d, r13d
0x1800638b0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800638b4  xorps   xmm1, xmm1
0x1800638b7  mov     [rbp+57h+Handle], r13
0x1800638bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800638bf  xor     eax, eax
0x1800638c1  mov     [rbp+57h+KeyHandle], r13
0x1800638c5  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800638c9  mov     rdi, r8
0x1800638cc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800638d0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800638d4  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1800638d8  movups  xmmword ptr [rbp+57h+DeviceInterfaceRegKey], xmm1
0x1800638dc  call    cs:__imp_RtlInitUnicodeString
0x1800638e3  nop     dword ptr [rax+rax+00h]
0x1800638e8  mov     rcx, [r14+60h]; PhysicalDeviceObject
0x1800638ec  lea     r15, [rdi+20h]
0x1800638f0  lea     r12, [rdi+10h]
0x1800638f4  mov     r9, r15; SymbolicLinkName
0x1800638f7  mov     rdx, r12; InterfaceClassGuid
0x1800638fa  lea     r8, [rbp+57h+DestinationString]; ReferenceString
0x1800638fe  call    cs:__imp_IoRegisterDeviceInterface
0x180063905  nop     dword ptr [rax+rax+00h]
0x18006390a  mov     ebx, eax
0x18006390c  test    eax, eax
0x18006390e  js      loc_180063A84
0x180063914  lea     r9, [rsi+88h]
0x18006391b  mov     [rsp+0C0h+var_A0], r12
0x180063920  lea     r8, [rsi+40h]
0x180063924  lea     rdx, [r14+150h]
0x18006392b  lea     rcx, [rbp+57h+Handle]
0x18006392f  call    OpenDeviceInterfaceKey
0x180063934  mov     ebx, eax
0x180063936  test    eax, eax
0x180063938  js      loc_180063A84
0x18006393e  lea     rdx, aParameters_0; "Parameters"
0x180063945  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180063949  call    cs:__imp_RtlInitUnicodeString
0x180063950  nop     dword ptr [rax+rax+00h]
0x180063955  mov     rsi, [rbp+57h+Handle]
0x180063959  lea     rax, [rbp+57h+var_70]
0x18006395d  xorps   xmm0, xmm0
0x180063960  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180063964  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180063968  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006396f  mov     edx, 20019h; DesiredAccess
0x180063974  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180063978  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18006397c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180063983  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180063988  call    cs:__imp_ZwOpenKey
0x18006398f  nop     dword ptr [rax+rax+00h]
0x180063994  mov     ebx, eax
0x180063996  cmp     eax, 0C0000034h
0x18006399b  jnz     short loc_1800639A2
0x18006399d  mov     ebx, r13d
0x1800639a0  jmp     short loc_1800639FD
0x1800639a2  test    eax, eax
0x1800639a4  js      short loc_1800639FD
0x1800639a6  lea     r8, [rbp+57h+DeviceInterfaceRegKey+8]; DeviceInterfaceRegKey
0x1800639aa  mov     [rbp+57h+DeviceInterfaceRegKey+8], r13
0x1800639ae  mov     edx, 2001Fh; DesiredAccess
0x1800639b3  mov     [rbp+57h+DeviceInterfaceRegKey], r14
0x1800639b7  mov     rcx, r15; SymbolicLinkName
0x1800639ba  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x1800639c1  nop     dword ptr [rax+rax+00h]
0x1800639c6  mov     ebx, eax
0x1800639c8  test    eax, eax
0x1800639ca  js      short loc_1800639ED
0x1800639cc  mov     rcx, [rbp+57h+KeyHandle]
0x1800639d0  lea     r8, [rbp+57h+DeviceInterfaceRegKey]
0x1800639d4  xor     edx, edx
0x1800639d6  call    CopyDeviceInterfaceParameters
0x1800639db  mov     rcx, [rbp+57h+DeviceInterfaceRegKey+8]; Handle
0x1800639df  mov     ebx, eax
0x1800639e1  call    cs:__imp_ZwClose
0x1800639e8  nop     dword ptr [rax+rax+00h]
0x1800639ed  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800639f1  call    cs:__imp_ZwClose
0x1800639f8  nop     dword ptr [rax+rax+00h]
0x1800639fd  mov     rcx, rsi; Handle
0x180063a00  call    cs:__imp_ZwClose
0x180063a07  nop     dword ptr [rax+rax+00h]
0x180063a0c  test    ebx, ebx
0x180063a0e  js      short loc_180063A84
0x180063a10  lea     rax, WPP_RECORDER_INITIALIZED
0x180063a17  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180063a1e  jz      short loc_180063A52
0x180063a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180063a27  cmp     [rcx+48h], r13w
0x180063a2c  jz      short loc_180063A52
0x180063a2e  mov     rax, [rdi+28h]
0x180063a32  mov     r9d, 46h ; 'F'
0x180063a38  mov     rcx, [rcx+40h]
0x180063a3c  mov     [rsp+0C0h+var_98], rax
0x180063a41  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180063a48  mov     [rsp+0C0h+var_A0], rax
0x180063a4d  call    WPP_RECORDER_SF_S
0x180063a52  mov     dl, 1; Enable
0x180063a54  mov     rcx, r15; SymbolicLinkName
0x180063a57  call    cs:__imp_IoSetDeviceInterfaceState
0x180063a5e  nop     dword ptr [rax+rax+00h]
0x180063a63  mov     ebx, eax
0x180063a65  test    eax, eax
0x180063a67  jns     short loc_180063A84
0x180063a69  mov     rcx, [rdi+28h]; P
0x180063a6d  test    rcx, rcx
0x180063a70  jz      short loc_180063A84
0x180063a72  xor     edx, edx; Tag
0x180063a74  call    cs:__imp_ExFreePoolWithTag
0x180063a7b  nop     dword ptr [rax+rax+00h]
0x180063a80  mov     [rdi+28h], r13
0x180063a84  mov     eax, ebx
0x180063a86  mov     rbx, [rsp+0C0h+arg_10]
0x180063a8e  add     rsp, 90h
0x180063a95  pop     r15
0x180063a97  pop     r14
0x180063a99  pop     r13
0x180063a9b  pop     r12
0x180063a9d  pop     rdi
0x180063a9e  pop     rsi
0x180063a9f  pop     rbp
0x180063aa0  retn
```
