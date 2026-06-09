# FAKEVID_CreateDevice(_DRIVER_OBJECT *,uint,_DEVICE_OBJECT * *)

- ea: `0x140020c38`
- end: `0x140020d5d`
- name: `?FAKEVID_CreateDevice@@YAJPEAU_DRIVER_OBJECT@@IPEAPEAU_DEVICE_OBJECT@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, ULONG DeviceCharacteristics, PDEVICE_OBJECT *DeviceObject)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002e078`

## callees

- `0x14000327c`
- `0x140005c74`
- `0x140006480`
- `0x140020c38`
- `0x140020e7c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140020ca1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020cb8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020ca1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020cb8`

## pseudocode

```c
__int64 __fastcall FAKEVID_CreateDevice(
        PDRIVER_OBJECT DriverObject,
        ULONG DeviceCharacteristics,
        PDEVICE_OBJECT *DeviceObject)
{
  NTSTATUS v5; // ebx
  BOOLEAN v8; // [rsp+28h] [rbp-41h]
  UNICODE_STRING DefaultSDDLString; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  GUID DeviceClassGuid; // [rsp+70h] [rbp+7h] BYREF
  wchar_t pszDest[8]; // [rsp+80h] [rbp+17h] BYREF
  __int128 v13; // [rsp+90h] [rbp+27h]
  int v14; // [rsp+A0h] [rbp+37h]

  v14 = 0;
  DestinationString = 0;
  DefaultSDDLString = 0;
  DeviceClassGuid = 0;
  *(_OWORD *)pszDest = 0;
  v13 = 0;
  RtlStringCchPrintfW(pszDest, 0x12u, L"%s%d", L"\\Device\\FakeVid");
  RtlInitUnicodeString(&DestinationString, pszDest);
  RtlInitUnicodeString(&DefaultSDDLString, L"D:P(A;;GA;;;NS)(A;;GA;;;SY)");
  DeviceClassGuid = (GUID)DYNVC_DEVICE_GUID;
  v5 = WdmlibIoCreateDeviceSecure(
         DriverObject,
         0,
         &DestinationString,
         0x10u,
         DeviceCharacteristics,
         v8,
         &DefaultSDDLString,
         &DeviceClassGuid,
         DeviceObject);
  if ( v5 >= 0 )
  {
    (*DeviceObject)->Flags &= ~0x80u;
    (*DeviceObject)->Flags |= 0x10u;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5b0df44774553e9aef533b28e6800864_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140020c38  push    rbp
0x140020c3a  push    rbx
0x140020c3b  push    rdi
0x140020c3c  lea     rbp, [rsp-47h]
0x140020c41  sub     rsp, 0B0h
0x140020c48  mov     rax, cs:__security_cookie
0x140020c4f  xor     rax, rsp
0x140020c52  mov     [rbp+57h+var_18], rax
0x140020c56  xorps   xmm1, xmm1
0x140020c59  mov     [rsp+0C0h+DeviceCharacteristics], edx; DeviceCharacteristics
0x140020c5d  xor     eax, eax
0x140020c5f  lea     r9, aDeviceFakevid; "\\Device\\FakeVid"
0x140020c66  xorps   xmm0, xmm0
0x140020c69  mov     [rbp+57h+var_20], eax
0x140020c6c  mov     rdi, r8
0x140020c6f  mov     rbx, rcx
0x140020c72  lea     r8, aSD; "%s%d"
0x140020c79  lea     edx, [rax+12h]; cchDest
0x140020c7c  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140020c80  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140020c84  movups  xmmword ptr [rbp+57h+var_70.Length], xmm1
0x140020c88  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140020c8c  movups  xmmword ptr [rbp+57h+pszDest], xmm1
0x140020c90  movups  [rbp+57h+var_30], xmm1
0x140020c94  call    RtlStringCchPrintfW
0x140020c99  lea     rdx, [rbp+57h+pszDest]; SourceString
0x140020c9d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140020ca1  call    cs:__imp_RtlInitUnicodeString
0x140020ca8  nop     dword ptr [rax+rax+00h]
0x140020cad  lea     rdx, aDPAGaNsAGaSy; "D:P(A;;GA;;;NS)(A;;GA;;;SY)"
0x140020cb4  lea     rcx, [rbp+57h+var_70]; DestinationString
0x140020cb8  call    cs:__imp_RtlInitUnicodeString
0x140020cbf  nop     dword ptr [rax+rax+00h]
0x140020cc4  movups  xmm0, cs:DYNVC_DEVICE_GUID
0x140020ccb  lea     rax, [rbp+57h+var_50]
0x140020ccf  mov     [rsp+0C0h+DeviceObject], rdi; DeviceObject
0x140020cd4  mov     [rsp+0C0h+DeviceClassGuid], rax; DeviceClassGuid
0x140020cd9  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x140020cdd  lea     rax, [rbp+57h+var_70]
0x140020ce1  mov     r9d, 10h; DeviceType
0x140020ce7  xor     edx, edx; DeviceExtensionSize
0x140020ce9  mov     [rsp+0C0h+DefaultSDDLString], rax; DefaultSDDLString
0x140020cee  mov     rcx, rbx; DriverObject
0x140020cf1  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x140020cf6  call    WdmlibIoCreateDeviceSecure
0x140020cfb  mov     ebx, eax
0x140020cfd  test    eax, eax
0x140020cff  jns     short loc_140020D34
0x140020d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d08  lea     rax, WPP_GLOBAL_Control
0x140020d0f  cmp     rcx, rax
0x140020d12  jz      short loc_140020D43
0x140020d14  cmp     byte ptr [rcx+29h], 2
0x140020d18  jb      short loc_140020D43
0x140020d1a  mov     rcx, [rcx+18h]
0x140020d1e  lea     r8, WPP_5b0df44774553e9aef533b28e6800864_Traceguids
0x140020d25  mov     edx, 0Ah
0x140020d2a  mov     r9d, ebx
0x140020d2d  call    WPP_SF_d
0x140020d32  jmp     short loc_140020D43
0x140020d34  mov     rax, [rdi]
0x140020d37  btr     dword ptr [rax+30h], 7
0x140020d3c  mov     rax, [rdi]
0x140020d3f  or      dword ptr [rax+30h], 10h
0x140020d43  mov     eax, ebx
0x140020d45  mov     rcx, [rbp+57h+var_18]
0x140020d49  xor     rcx, rsp; StackCookie
0x140020d4c  call    __security_check_cookie
0x140020d51  add     rsp, 0B0h
0x140020d58  pop     rdi
0x140020d59  pop     rbx
0x140020d5a  pop     rbp
0x140020d5b  retn
```
