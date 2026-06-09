# CLauncherUtils::IsRunningOnPortableOperatingSystem(void)

- ea: `0x18000c60c`
- end: `0x18000c6b6`
- name: `?IsRunningOnPortableOperatingSystem@CLauncherUtils@@SA_NXZ`
- size: `170`
- prototype: `BOOL(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008e20`
- `0x180009100`
- `0x1800091c0`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x18000c60c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000c631`
- `ntdll!RtlNtStatusToDosError` at `0x18000c631`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18000c61c`
- `ntdll!RtlCheckPortableOperatingSystem` at `0x18000c61c`

## string_xrefs

- `0x18000c667`: `drivers\wdm\usbpw\launcher\dll\clauncherutils.cpp`

## pseudocode

```c
BOOL CLauncherUtils::IsRunningOnPortableOperatingSystem(void)
{
  NTSTATUS v0; // eax
  signed int v1; // ebx
  char v3; // [rsp+40h] [rbp+8h] BYREF
  char pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v3 = 0;
  v0 = RtlCheckPortableOperatingSystem(&v3);
  if ( v0 == -1073741275 )
  {
    v0 = 0;
    v3 = 0;
  }
  v1 = RtlNtStatusToDosError(v0);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_dc7b223a12573dae09b82d0e41284e3f_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\clauncherutils.cpp",
        60,
        v1);
    if ( v1 > 0 )
      v1 = (unsigned __int16)v1 | 0x80070000;
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, v1);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  return v3 != 0;
}

```

## disassembly

```asm
0x18000c60c  push    rbx
0x18000c60e  sub     rsp, 30h
0x18000c612  lea     rcx, [rsp+38h+arg_0]
0x18000c617  mov     [rsp+38h+arg_0], 0
0x18000c61c  call    cs:__imp_RtlCheckPortableOperatingSystem
0x18000c622  cmp     eax, 0C0000225h
0x18000c627  jnz     short loc_18000C62F
0x18000c629  xor     eax, eax
0x18000c62b  mov     [rsp+38h+arg_0], al
0x18000c62f  mov     ecx, eax; Status
0x18000c631  call    cs:__imp_RtlNtStatusToDosError
0x18000c637  mov     ebx, eax
0x18000c639  test    eax, eax
0x18000c63b  jnz     short loc_18000C64A
0x18000c63d  cmp     [rsp+38h+arg_0], al
0x18000c641  setnz   al
0x18000c644  add     rsp, 30h
0x18000c648  pop     rbx
0x18000c649  retn
0x18000c64a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c651  lea     rax, WPP_GLOBAL_Control
0x18000c658  cmp     rcx, rax
0x18000c65b  jz      short loc_18000C68B
0x18000c65d  test    byte ptr [rcx+1Ch], 1
0x18000c661  jz      short loc_18000C68B
0x18000c663  mov     rcx, [rcx+10h]
0x18000c667  lea     r9, aDriversWdmUsbp_3; "drivers\\wdm\\usbpw\\launcher\\dll\\cla"...
0x18000c66e  mov     edx, 0Ah
0x18000c673  mov     [rsp+38h+var_10], ebx
0x18000c677  lea     r8, WPP_dc7b223a12573dae09b82d0e41284e3f_Traceguids
0x18000c67e  mov     [rsp+38h+var_18], 3Ch ; '<'
0x18000c686  call    WPP_SF_sdD
0x18000c68b  test    ebx, ebx
0x18000c68d  jle     short loc_18000C698
0x18000c68f  movzx   ebx, bx
0x18000c692  or      ebx, 80070000h
0x18000c698  mov     edx, ebx; int
0x18000c69a  lea     rcx, [rsp+38h+pExceptionObject]; this
0x18000c69f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000c6a4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000c6ab  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000c6b0  call    _CxxThrowException_0
```
