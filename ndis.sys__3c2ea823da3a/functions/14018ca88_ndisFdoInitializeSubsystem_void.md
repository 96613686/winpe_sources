# ndisFdoInitializeSubsystem(void)

- ea: `0x14018ca88`
- end: `0x14018cbdd`
- name: `?ndisFdoInitializeSubsystem@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14018b240`

## callees

- `0x14006c030`
- `0x140143090`
- `0x14018ca88`
- `0x14018cefc`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x14018cadb`
- `ntoskrnl!IoCreateDevice` at `0x14018cadb`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14018cb19`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14018cb19`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018caa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cb03`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018caa2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018cb03`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14018cbc1`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14018cbc1`

## pseudocode

```c
int ndisFdoInitializeSubsystem(void)
{
  int result; // eax
  char *v1; // rdi
  struct _ACL *v2; // rcx
  __int64 v3; // rdx
  struct _ACL *v4; // r9
  __int64 v5; // rdx
  struct _ACL *v6; // r9
  __int64 v7; // rdx
  struct _ACL *v8; // r9
  NTSTATUS v9; // eax
  int v10; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+50h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Ndis");
  result = IoCreateDevice((PDRIVER_OBJECT)ndisDriverObject, 0, &DestinationString, 0x12u, 0x100u, 0, &ndisDeviceObject);
  if ( result >= 0 )
  {
    SymbolicLinkName = 0;
    RtlInitUnicodeString(&SymbolicLinkName, L"\\Global??\\NDIS");
    result = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
    if ( result >= 0 )
    {
      v1 = (char *)ndisDriverObject + 112;
      ndisDeviceObject->Flags |= 0x10u;
      memset64(v1, (unsigned __int64)&ndisDriverDispatch, 0x1Cu);
      result = ndisCreateSecurityDescriptor(ndisDeviceObject, &ndisSecurityDescriptor, 191);
      if ( result >= 0 )
      {
        result = ndisCreateSecurityDescriptorEx(v2);
        if ( result >= 0 )
        {
          result = CreateDeviceDriverSecurityDescriptor(ndisDriverObject, v3, 0, v4);
          if ( result >= 0 )
          {
            result = CreateDeviceDriverSecurityDescriptor(*((void **)ndisDriverObject + 1), v5, 0, v6);
            if ( result >= 0 )
            {
              result = CreateDeviceDriverSecurityDescriptor(ndisDeviceObject, v7, 1u, v8);
              if ( result >= 0 )
              {
                v9 = IoWMIRegistrationControl(ndisDeviceObject, 1u);
                v10 = 0;
                if ( v9 < 0 )
                  return v9;
                return v10;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14018ca88  push    rdi
0x14018ca8a  sub     rsp, 60h
0x14018ca8e  xorps   xmm0, xmm0
0x14018ca91  lea     rdx, aDeviceNdis_0; "\\Device\\Ndis"
0x14018ca98  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14018ca9d  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14018caa2  call    cs:__imp_RtlInitUnicodeString
0x14018caa9  nop     dword ptr [rax+rax+00h]
0x14018caae  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; DriverObject
0x14018cab5  lea     rax, ?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * ndisDeviceObject
0x14018cabc  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x14018cac1  lea     r8, [rsp+68h+DestinationString]; DeviceName
0x14018cac6  mov     [rsp+68h+Exclusive], 0; Exclusive
0x14018cacb  mov     r9d, 12h; DeviceType
0x14018cad1  xor     edx, edx; DeviceExtensionSize
0x14018cad3  mov     [rsp+68h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14018cadb  call    cs:__imp_IoCreateDevice
0x14018cae2  nop     dword ptr [rax+rax+00h]
0x14018cae7  test    eax, eax
0x14018cae9  js      loc_14018CBD6
0x14018caef  xorps   xmm0, xmm0
0x14018caf2  lea     rdx, aGlobalNdis; "\\Global??\\NDIS"
0x14018caf9  lea     rcx, [rsp+68h+SymbolicLinkName]; DestinationString
0x14018cafe  movups  xmmword ptr [rsp+68h+SymbolicLinkName.Length], xmm0
0x14018cb03  call    cs:__imp_RtlInitUnicodeString
0x14018cb0a  nop     dword ptr [rax+rax+00h]
0x14018cb0f  lea     rdx, [rsp+68h+DestinationString]; DeviceName
0x14018cb14  lea     rcx, [rsp+68h+SymbolicLinkName]; SymbolicLinkName
0x14018cb19  call    cs:__imp_IoCreateSymbolicLink
0x14018cb20  nop     dword ptr [rax+rax+00h]
0x14018cb25  test    eax, eax
0x14018cb27  js      loc_14018CBD6
0x14018cb2d  mov     rax, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * ndisDeviceObject
0x14018cb34  lea     rdx, ?ndisSecurityDescriptor@@3PEAXEA; void **
0x14018cb3b  mov     rdi, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x14018cb42  mov     ecx, 1Ch
0x14018cb47  add     rdi, 70h ; 'p'
0x14018cb4b  mov     r8d, 0BFh; unsigned int
0x14018cb51  or      dword ptr [rax+30h], 10h
0x14018cb55  lea     rax, ndisDriverDispatch
0x14018cb5c  rep stosq
0x14018cb5f  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; struct _DEVICE_OBJECT *
0x14018cb66  call    ?ndisCreateSecurityDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAPEAXK@Z; ndisCreateSecurityDescriptor(_DEVICE_OBJECT *,void * *,ulong)
0x14018cb6b  test    eax, eax
0x14018cb6d  js      short loc_14018CBD6
0x14018cb6f  call    ?ndisCreateSecurityDescriptorEx@@YAJPEAXK@Z; ndisCreateSecurityDescriptorEx(void *,ulong)
0x14018cb74  test    eax, eax
0x14018cb76  js      short loc_14018CBD6
0x14018cb78  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; void *
0x14018cb7f  xor     r8d, r8d; unsigned __int8
0x14018cb82  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x14018cb87  test    eax, eax
0x14018cb89  js      short loc_14018CBD6
0x14018cb8b  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x14018cb92  xor     r8d, r8d; unsigned __int8
0x14018cb95  mov     rcx, [rcx+8]; void *
0x14018cb99  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x14018cb9e  test    eax, eax
0x14018cba0  js      short loc_14018CBD6
0x14018cba2  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; void *
0x14018cba9  mov     r8b, 1; unsigned __int8
0x14018cbac  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x14018cbb1  test    eax, eax
0x14018cbb3  js      short loc_14018CBD6
0x14018cbb5  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; DeviceObject
0x14018cbbc  mov     edx, 1; Action
0x14018cbc1  call    cs:__imp_IoWMIRegistrationControl
0x14018cbc8  nop     dword ptr [rax+rax+00h]
0x14018cbcd  xor     ecx, ecx
0x14018cbcf  test    eax, eax
0x14018cbd1  cmovs   ecx, eax
0x14018cbd4  mov     eax, ecx
0x14018cbd6  add     rsp, 60h
0x14018cbda  pop     rdi
0x14018cbdb  retn
```
