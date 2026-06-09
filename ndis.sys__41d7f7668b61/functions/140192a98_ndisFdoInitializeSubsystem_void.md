# ndisFdoInitializeSubsystem(void)

- ea: `0x140192a98`
- end: `0x140192bed`
- name: `?ndisFdoInitializeSubsystem@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140191240`

## callees

- `0x1400719b0`
- `0x14014a030`
- `0x140192a98`
- `0x140192f0c`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140192aeb`
- `ntoskrnl!IoCreateDevice` at `0x140192aeb`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140192b29`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140192b29`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192ab2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192b13`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192ab2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192b13`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140192bd1`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140192bd1`

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
      result = ndisCreateSecurityDescriptor(ndisDeviceObject, &ndisSecurityDescriptor, 0xBFu);
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
0x140192a98  push    rdi
0x140192a9a  sub     rsp, 60h
0x140192a9e  xorps   xmm0, xmm0
0x140192aa1  lea     rdx, aDeviceNdis_0; "\\Device\\Ndis"
0x140192aa8  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140192aad  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140192ab2  call    cs:__imp_RtlInitUnicodeString
0x140192ab9  nop     dword ptr [rax+rax+00h]
0x140192abe  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; DriverObject
0x140192ac5  lea     rax, ?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * ndisDeviceObject
0x140192acc  mov     [rsp+68h+DeviceObject], rax; DeviceObject
0x140192ad1  lea     r8, [rsp+68h+DestinationString]; DeviceName
0x140192ad6  mov     [rsp+68h+Exclusive], 0; Exclusive
0x140192adb  mov     r9d, 12h; DeviceType
0x140192ae1  xor     edx, edx; DeviceExtensionSize
0x140192ae3  mov     [rsp+68h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140192aeb  call    cs:__imp_IoCreateDevice
0x140192af2  nop     dword ptr [rax+rax+00h]
0x140192af7  test    eax, eax
0x140192af9  js      loc_140192BE6
0x140192aff  xorps   xmm0, xmm0
0x140192b02  lea     rdx, aGlobalNdis; "\\Global??\\NDIS"
0x140192b09  lea     rcx, [rsp+68h+SymbolicLinkName]; DestinationString
0x140192b0e  movups  xmmword ptr [rsp+68h+SymbolicLinkName.Length], xmm0
0x140192b13  call    cs:__imp_RtlInitUnicodeString
0x140192b1a  nop     dword ptr [rax+rax+00h]
0x140192b1f  lea     rdx, [rsp+68h+DestinationString]; DeviceName
0x140192b24  lea     rcx, [rsp+68h+SymbolicLinkName]; SymbolicLinkName
0x140192b29  call    cs:__imp_IoCreateSymbolicLink
0x140192b30  nop     dword ptr [rax+rax+00h]
0x140192b35  test    eax, eax
0x140192b37  js      loc_140192BE6
0x140192b3d  mov     rax, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * ndisDeviceObject
0x140192b44  lea     rdx, ?ndisSecurityDescriptor@@3PEAXEA; void **
0x140192b4b  mov     rdi, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x140192b52  mov     ecx, 1Ch
0x140192b57  add     rdi, 70h ; 'p'
0x140192b5b  mov     r8d, 0BFh; unsigned int
0x140192b61  or      dword ptr [rax+30h], 10h
0x140192b65  lea     rax, ndisDriverDispatch
0x140192b6c  rep stosq
0x140192b6f  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; struct _DEVICE_OBJECT *
0x140192b76  call    ?ndisCreateSecurityDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAPEAXK@Z; ndisCreateSecurityDescriptor(_DEVICE_OBJECT *,void * *,ulong)
0x140192b7b  test    eax, eax
0x140192b7d  js      short loc_140192BE6
0x140192b7f  call    ?ndisCreateSecurityDescriptorEx@@YAJPEAXK@Z; ndisCreateSecurityDescriptorEx(void *,ulong)
0x140192b84  test    eax, eax
0x140192b86  js      short loc_140192BE6
0x140192b88  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; void *
0x140192b8f  xor     r8d, r8d; unsigned __int8
0x140192b92  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x140192b97  test    eax, eax
0x140192b99  js      short loc_140192BE6
0x140192b9b  mov     rcx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x140192ba2  xor     r8d, r8d; unsigned __int8
0x140192ba5  mov     rcx, [rcx+8]; void *
0x140192ba9  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x140192bae  test    eax, eax
0x140192bb0  js      short loc_140192BE6
0x140192bb2  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; void *
0x140192bb9  mov     r8b, 1; unsigned __int8
0x140192bbc  call    ?CreateDeviceDriverSecurityDescriptor@@YAJPEAXEEPEAU_ACL@@@Z; CreateDeviceDriverSecurityDescriptor(void *,uchar,uchar,_ACL *)
0x140192bc1  test    eax, eax
0x140192bc3  js      short loc_140192BE6
0x140192bc5  mov     rcx, cs:?ndisDeviceObject@@3PEAU_DEVICE_OBJECT@@EA; DeviceObject
0x140192bcc  mov     edx, 1; Action
0x140192bd1  call    cs:__imp_IoWMIRegistrationControl
0x140192bd8  nop     dword ptr [rax+rax+00h]
0x140192bdd  xor     ecx, ecx
0x140192bdf  test    eax, eax
0x140192be1  cmovs   ecx, eax
0x140192be4  mov     eax, ecx
0x140192be6  add     rsp, 60h
0x140192bea  pop     rdi
0x140192beb  retn
```
