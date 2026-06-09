# RegisterDeviceAssociation

- ea: `0x1800636e4`
- end: `0x180063902`
- name: `RegisterDeviceAssociation`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180065480`

## callees

- `0x180010de4`
- `0x180034a90`
- `0x1800636e4`
- `0x180063908`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006373c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800637a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006373c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800637a9`
- `ntoskrnl!ZwClose` at `0x180063841`
- `ntoskrnl!ZwClose` at `0x180063851`
- `ntoskrnl!ZwClose` at `0x180063860`
- `ntoskrnl!ZwClose` at `0x180063841`
- `ntoskrnl!ZwClose` at `0x180063851`
- `ntoskrnl!ZwClose` at `0x180063860`
- `ntoskrnl!ZwOpenKey` at `0x1800637e8`
- `ntoskrnl!ZwOpenKey` at `0x1800637e8`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x18006375e`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x18006375e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800638b7`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800638b7`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006381a`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006381a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800638d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800638d4`

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
    v7 = OpenDeviceInterfaceKey(
           &Handle,
           (__int64)(a1 + 42),
           (const GUID *)(a2 + 64),
           (const WCHAR *)(a2 + 136),
           (GUID *)(a3 + 16));
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
0x1800636e4  mov     [rsp-8+arg_10], rbx
0x1800636e9  push    rbp
0x1800636ea  push    rsi
0x1800636eb  push    rdi
0x1800636ec  push    r12
0x1800636ee  push    r13
0x1800636f0  push    r14
0x1800636f2  push    r15
0x1800636f4  lea     rbp, [rsp-27h]
0x1800636f9  sub     rsp, 90h
0x180063700  xorps   xmm0, xmm0
0x180063703  mov     rsi, rdx
0x180063706  mov     rdx, [rdx+60h]; SourceString
0x18006370a  mov     r14, rcx
0x18006370d  xor     r13d, r13d
0x180063710  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180063714  xorps   xmm1, xmm1
0x180063717  mov     [rbp+57h+Handle], r13
0x18006371b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006371f  xor     eax, eax
0x180063721  mov     [rbp+57h+KeyHandle], r13
0x180063725  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180063729  mov     rdi, r8
0x18006372c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180063730  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180063734  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x180063738  movups  xmmword ptr [rbp+57h+DeviceInterfaceRegKey], xmm1
0x18006373c  call    cs:__imp_RtlInitUnicodeString
0x180063743  nop     dword ptr [rax+rax+00h]
0x180063748  mov     rcx, [r14+60h]; PhysicalDeviceObject
0x18006374c  lea     r15, [rdi+20h]
0x180063750  lea     r12, [rdi+10h]
0x180063754  mov     r9, r15; SymbolicLinkName
0x180063757  mov     rdx, r12; InterfaceClassGuid
0x18006375a  lea     r8, [rbp+57h+DestinationString]; ReferenceString
0x18006375e  call    cs:__imp_IoRegisterDeviceInterface
0x180063765  nop     dword ptr [rax+rax+00h]
0x18006376a  mov     ebx, eax
0x18006376c  test    eax, eax
0x18006376e  js      loc_1800638E4
0x180063774  lea     r9, [rsi+88h]
0x18006377b  mov     [rsp+0C0h+var_A0], r12
0x180063780  lea     r8, [rsi+40h]
0x180063784  lea     rdx, [r14+150h]
0x18006378b  lea     rcx, [rbp+57h+Handle]
0x18006378f  call    OpenDeviceInterfaceKey
0x180063794  mov     ebx, eax
0x180063796  test    eax, eax
0x180063798  js      loc_1800638E4
0x18006379e  lea     rdx, aParameters_0; "Parameters"
0x1800637a5  lea     rcx, [rbp+57h+var_70]; DestinationString
0x1800637a9  call    cs:__imp_RtlInitUnicodeString
0x1800637b0  nop     dword ptr [rax+rax+00h]
0x1800637b5  mov     rsi, [rbp+57h+Handle]
0x1800637b9  lea     rax, [rbp+57h+var_70]
0x1800637bd  xorps   xmm0, xmm0
0x1800637c0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800637c4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800637c8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800637cf  mov     edx, 20019h; DesiredAccess
0x1800637d4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800637d8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800637dc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800637e3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800637e8  call    cs:__imp_ZwOpenKey
0x1800637ef  nop     dword ptr [rax+rax+00h]
0x1800637f4  mov     ebx, eax
0x1800637f6  cmp     eax, 0C0000034h
0x1800637fb  jnz     short loc_180063802
0x1800637fd  mov     ebx, r13d
0x180063800  jmp     short loc_18006385D
0x180063802  test    eax, eax
0x180063804  js      short loc_18006385D
0x180063806  lea     r8, [rbp+57h+DeviceInterfaceRegKey+8]; DeviceInterfaceRegKey
0x18006380a  mov     [rbp+57h+DeviceInterfaceRegKey+8], r13
0x18006380e  mov     edx, 2001Fh; DesiredAccess
0x180063813  mov     [rbp+57h+DeviceInterfaceRegKey], r14
0x180063817  mov     rcx, r15; SymbolicLinkName
0x18006381a  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x180063821  nop     dword ptr [rax+rax+00h]
0x180063826  mov     ebx, eax
0x180063828  test    eax, eax
0x18006382a  js      short loc_18006384D
0x18006382c  mov     rcx, [rbp+57h+KeyHandle]
0x180063830  lea     r8, [rbp+57h+DeviceInterfaceRegKey]
0x180063834  xor     edx, edx
0x180063836  call    CopyDeviceInterfaceParameters
0x18006383b  mov     rcx, [rbp+57h+DeviceInterfaceRegKey+8]; Handle
0x18006383f  mov     ebx, eax
0x180063841  call    cs:__imp_ZwClose
0x180063848  nop     dword ptr [rax+rax+00h]
0x18006384d  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180063851  call    cs:__imp_ZwClose
0x180063858  nop     dword ptr [rax+rax+00h]
0x18006385d  mov     rcx, rsi; Handle
0x180063860  call    cs:__imp_ZwClose
0x180063867  nop     dword ptr [rax+rax+00h]
0x18006386c  test    ebx, ebx
0x18006386e  js      short loc_1800638E4
0x180063870  lea     rax, WPP_RECORDER_INITIALIZED
0x180063877  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18006387e  jz      short loc_1800638B2
0x180063880  mov     rcx, cs:WPP_GLOBAL_Control
0x180063887  cmp     [rcx+48h], r13w
0x18006388c  jz      short loc_1800638B2
0x18006388e  mov     rax, [rdi+28h]
0x180063892  mov     r9d, 46h ; 'F'
0x180063898  mov     rcx, [rcx+40h]
0x18006389c  mov     [rsp+0C0h+var_98], rax
0x1800638a1  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800638a8  mov     [rsp+0C0h+var_A0], rax
0x1800638ad  call    WPP_RECORDER_SF_S
0x1800638b2  mov     dl, 1; Enable
0x1800638b4  mov     rcx, r15; SymbolicLinkName
0x1800638b7  call    cs:__imp_IoSetDeviceInterfaceState
0x1800638be  nop     dword ptr [rax+rax+00h]
0x1800638c3  mov     ebx, eax
0x1800638c5  test    eax, eax
0x1800638c7  jns     short loc_1800638E4
0x1800638c9  mov     rcx, [rdi+28h]; P
0x1800638cd  test    rcx, rcx
0x1800638d0  jz      short loc_1800638E4
0x1800638d2  xor     edx, edx; Tag
0x1800638d4  call    cs:__imp_ExFreePoolWithTag
0x1800638db  nop     dword ptr [rax+rax+00h]
0x1800638e0  mov     [rdi+28h], r13
0x1800638e4  mov     eax, ebx
0x1800638e6  mov     rbx, [rsp+0C0h+arg_10]
0x1800638ee  add     rsp, 90h
0x1800638f5  pop     r15
0x1800638f7  pop     r14
0x1800638f9  pop     r13
0x1800638fb  pop     r12
0x1800638fd  pop     rdi
0x1800638fe  pop     rsi
0x1800638ff  pop     rbp
0x180063900  retn
```
