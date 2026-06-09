# PerfDiagShared::GetDeviceDescription(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800ce950`
- end: `0x1800cea4e`
- name: `?GetDeviceDescription@PerfDiagShared@@YAJPEAG_KPEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(PBYTE PropertyBuffer, unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180034c2c`

## callees

- `0x1800421b8`
- `0x1800ce950`
- `0x1800cf080`

## import_xrefs

- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800ce98a`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x1800ce98a`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x1800cea08`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x1800cea08`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800ce9d1`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800ce9d1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800cea20`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800cea20`

## pseudocode

```c
__int64 __fastcall PerfDiagShared::GetDeviceDescription(
        BYTE *PropertyBuffer,
        unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  HDEVINFO DeviceInfoList; // rdi
  unsigned int Error; // ebx
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+40h] [rbp-38h] BYREF

  if ( !a3 || !PropertyBuffer )
    return 2147500035LL;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  if ( DeviceInfoList == (HDEVINFO)-1LL )
    return ATL::AtlHresultFromLastError();
  DeviceInfoData.cbSize = 32;
  memset(&DeviceInfoData.ClassGuid, 0, 28);
  if ( SetupDiOpenDeviceInfoW(DeviceInfoList, a3, 0, 2u, &DeviceInfoData)
    && SetupDiGetDeviceRegistryPropertyW(DeviceInfoList, &DeviceInfoData, 0, 0, PropertyBuffer, 0x200u, 0) )
  {
    Error = 0;
    *((_WORD *)PropertyBuffer + 255) = 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
  }
  SetupDiDestroyDeviceInfoList(DeviceInfoList);
  return Error;
}

```

## disassembly

```asm
0x1800ce950  mov     [rsp+arg_8], rbx
0x1800ce955  mov     [rsp+arg_18], rsi
0x1800ce95a  push    rdi
0x1800ce95b  sub     rsp, 70h
0x1800ce95f  mov     rax, cs:__security_cookie
0x1800ce966  xor     rax, rsp
0x1800ce969  mov     [rsp+78h+var_18], rax
0x1800ce96e  mov     rbx, r8
0x1800ce971  mov     rsi, rcx
0x1800ce974  test    r8, r8
0x1800ce977  jz      loc_1800CEA2A
0x1800ce97d  test    rcx, rcx
0x1800ce980  jz      loc_1800CEA2A
0x1800ce986  xor     edx, edx; hwndParent
0x1800ce988  xor     ecx, ecx; ClassGuid
0x1800ce98a  call    cs:__imp_SetupDiCreateDeviceInfoList
0x1800ce990  mov     rdi, rax
0x1800ce993  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ce997  jnz     short loc_1800CE9A3
0x1800ce999  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800ce99e  jmp     loc_1800CEA2F
0x1800ce9a3  xorps   xmm0, xmm0
0x1800ce9a6  mov     [rsp+78h+var_38.cbSize], 20h ; ' '
0x1800ce9ae  lea     rax, [rsp+78h+var_38]
0x1800ce9b3  mov     r9d, 2; OpenFlags
0x1800ce9b9  movups  xmmword ptr [rsp+78h+var_38.ClassGuid.Data1], xmm0
0x1800ce9be  xor     r8d, r8d; hwndParent
0x1800ce9c1  mov     [rsp+78h+DeviceInfoData], rax; DeviceInfoData
0x1800ce9c6  mov     rdx, rbx; DeviceInstanceId
0x1800ce9c9  mov     rcx, rdi; DeviceInfoSet
0x1800ce9cc  movups  xmmword ptr [rsp+78h+var_38.ClassGuid.Data4+4], xmm0
0x1800ce9d1  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800ce9d7  test    eax, eax
0x1800ce9d9  jnz     short loc_1800CE9E4
0x1800ce9db  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800ce9e0  mov     ebx, eax
0x1800ce9e2  jmp     short loc_1800CEA1D
0x1800ce9e4  mov     [rsp+78h+RequiredSize], 0; RequiredSize
0x1800ce9ed  lea     rdx, [rsp+78h+var_38]; DeviceInfoData
0x1800ce9f2  mov     [rsp+78h+PropertyBufferSize], 200h; PropertyBufferSize
0x1800ce9fa  xor     r9d, r9d; PropertyRegDataType
0x1800ce9fd  xor     r8d, r8d; Property
0x1800cea00  mov     [rsp+78h+DeviceInfoData], rsi; PropertyBuffer
0x1800cea05  mov     rcx, rdi; DeviceInfoSet
0x1800cea08  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x1800cea0e  test    eax, eax
0x1800cea10  jz      short loc_1800CE9DB
0x1800cea12  xor     ebx, ebx
0x1800cea14  xor     eax, eax
0x1800cea16  mov     [rsi+1FEh], ax
0x1800cea1d  mov     rcx, rdi; DeviceInfoSet
0x1800cea20  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800cea26  mov     eax, ebx
0x1800cea28  jmp     short loc_1800CEA2F
0x1800cea2a  mov     eax, 80004003h
0x1800cea2f  mov     rcx, [rsp+78h+var_18]
0x1800cea34  xor     rcx, rsp; StackCookie
0x1800cea37  call    __security_check_cookie
0x1800cea3c  lea     r11, [rsp+78h+var_8]
0x1800cea41  mov     rbx, [r11+18h]
0x1800cea45  mov     rsi, [r11+28h]
0x1800cea49  mov     rsp, r11
0x1800cea4c  pop     rdi
0x1800cea4d  retn
```
