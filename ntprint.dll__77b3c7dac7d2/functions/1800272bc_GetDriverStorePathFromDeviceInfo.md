# GetDriverStorePathFromDeviceInfo

- ea: `0x1800272bc`
- end: `0x18002740e`
- name: `GetDriverStorePathFromDeviceInfo`
- size: `338`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PWSTR ReturnBuffer)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180009724`
- `0x18000c870`
- `0x1800180f0`
- `0x18001c978`
- `0x1800284d0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x180012b28`
- `0x1800272bc`
- `0x180027414`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273d2`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800273af`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800273af`

## string_xrefs

- `0x1800273b8`: `Retrieved driver store path %ws from device info`
- `0x1800273bf`: `GetDriverStorePathFromDeviceInfo`
- `0x1800273e2`: `GetDriverStorePathFromDeviceInfo`
- `0x1800273db`: `Error retrieving driver store path from device info: %d`

## pseudocode

```c
__int64 __fastcall GetDriverStorePathFromDeviceInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        BOOL *a5,
        PWSTR ReturnBuffer)
{
  __int64 v8; // rbp
  __int64 v9; // rdx
  unsigned int PublishedPathFromDeviceInfo; // ebx
  WORD v11; // ax
  DWORD LastError; // eax
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+30h] [rbp-268h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  v8 = a4;
  memset_0(FileName, 0, 0x208u);
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || !a3
    || !(unsigned int)ValidPlatform((unsigned int)v8)
    || !a5
    || !ReturnBuffer )
  {
    PublishedPathFromDeviceInfo = 0;
    goto LABEL_9;
  }
  PublishedPathFromDeviceInfo = GetPublishedPathFromDeviceInfo(a1, v9, a3, FileName);
  if ( !PublishedPathFromDeviceInfo )
  {
LABEL_9:
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "GetDriverStorePathFromDeviceInfo",
      L"Error retrieving driver store path from device info: %d",
      LastError);
    return PublishedPathFromDeviceInfo;
  }
  HIWORD(AlternatePlatformInfo.FirstValidatedMinorVersion) = 0;
  v11 = *((_WORD *)&PlatformArch + 4 * v8 + 2);
  AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * v8);
  *(_QWORD *)&AlternatePlatformInfo.MajorVersion = 0;
  *(_QWORD *)&AlternatePlatformInfo.Reserved = 0;
  AlternatePlatformInfo.cbSize = 28;
  AlternatePlatformInfo.ProcessorArchitecture = v11;
  *a5 = SetupGetInfDriverStoreLocationW(FileName, &AlternatePlatformInfo, 0, ReturnBuffer, 0x104u, 0);
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "GetDriverStorePathFromDeviceInfo",
    L"Retrieved driver store path %ws from device info",
    ReturnBuffer);
  return PublishedPathFromDeviceInfo;
}

```

## disassembly

```asm
0x1800272bc  push    rbx
0x1800272be  push    rbp
0x1800272bf  push    rsi
0x1800272c0  push    rdi
0x1800272c1  push    r14
0x1800272c3  sub     rsp, 270h
0x1800272ca  mov     rax, cs:__security_cookie
0x1800272d1  xor     rax, rsp
0x1800272d4  mov     [rsp+298h+var_38], rax
0x1800272dc  mov     r14, [rsp+298h+arg_20]
0x1800272e4  mov     rbx, r8
0x1800272e7  mov     rdi, [rsp+298h+ReturnBuffer]
0x1800272ef  mov     rsi, rcx
0x1800272f2  mov     r8d, 208h; Size
0x1800272f8  movsxd  rbp, r9d
0x1800272fb  lea     rcx, [rsp+298h+FileName]; void *
0x180027300  xor     edx, edx; Val
0x180027302  call    memset_0
0x180027307  lea     rax, [rsi-1]
0x18002730b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002730f  ja      loc_1800273D0
0x180027315  test    rbx, rbx
0x180027318  jz      loc_1800273D0
0x18002731e  mov     ecx, ebp
0x180027320  call    ValidPlatform
0x180027325  test    eax, eax
0x180027327  jz      loc_1800273D0
0x18002732d  test    r14, r14
0x180027330  jz      loc_1800273D0
0x180027336  test    rdi, rdi
0x180027339  jz      loc_1800273D0
0x18002733f  lea     r9, [rsp+298h+FileName]
0x180027344  mov     r8, rbx
0x180027347  mov     rcx, rsi
0x18002734a  call    GetPublishedPathFromDeviceInfo
0x18002734f  mov     ebx, eax
0x180027351  test    eax, eax
0x180027353  jz      short loc_1800273D2
0x180027355  xor     ecx, ecx
0x180027357  mov     [rsp+298h+RequiredSize], 0; RequiredSize
0x180027360  lea     rdx, PlatformArch
0x180027367  mov     word ptr [rsp+298h+AlternatePlatformInfo.FirstValidatedMinorVersion+2], cx
0x18002736c  mov     ecx, [rdx+rbp*8]
0x18002736f  mov     r9, rdi; ReturnBuffer
0x180027372  movzx   eax, word ptr [rdx+rbp*8+4]
0x180027377  xor     r8d, r8d; LocaleName
0x18002737a  mov     [rsp+298h+AlternatePlatformInfo.Platform], ecx
0x18002737e  lea     rdx, [rsp+298h+AlternatePlatformInfo]; AlternatePlatformInfo
0x180027383  lea     rcx, [rsp+298h+FileName]; FileName
0x180027388  mov     qword ptr [rsp+298h+AlternatePlatformInfo.MajorVersion], 0
0x180027391  mov     qword ptr [rsp+298h+AlternatePlatformInfo.12h], 0
0x18002739a  mov     [rsp+298h+AlternatePlatformInfo.cbSize], 1Ch
0x1800273a2  mov     [rsp+298h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x1800273a7  mov     [rsp+298h+ReturnBufferSize], 104h; ReturnBufferSize
0x1800273af  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x1800273b5  mov     r8, rdi
0x1800273b8  lea     rdx, aRetrievedDrive; "Retrieved driver store path %ws from de"...
0x1800273bf  lea     rcx, aGetdriverstore; "GetDriverStorePathFromDeviceInfo"
0x1800273c6  mov     [r14], eax
0x1800273c9  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800273ce  jmp     short loc_1800273EE
0x1800273d0  xor     ebx, ebx
0x1800273d2  call    cs:__imp_GetLastError
0x1800273d8  mov     r8d, eax
0x1800273db  lea     rdx, aErrorRetrievin_3; "Error retrieving driver store path from"...
0x1800273e2  lea     rcx, aGetdriverstore; "GetDriverStorePathFromDeviceInfo"
0x1800273e9  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800273ee  mov     eax, ebx
0x1800273f0  mov     rcx, [rsp+298h+var_38]
0x1800273f8  xor     rcx, rsp; StackCookie
0x1800273fb  call    __security_check_cookie
0x180027400  add     rsp, 270h
0x180027407  pop     r14
0x180027409  pop     rdi
0x18002740a  pop     rsi
0x18002740b  pop     rbp
0x18002740c  pop     rbx
0x18002740d  retn
```
