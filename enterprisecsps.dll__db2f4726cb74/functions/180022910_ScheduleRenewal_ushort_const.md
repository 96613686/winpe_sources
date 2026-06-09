# ScheduleRenewal(ushort const *)

- ea: `0x180022910`
- end: `0x180022b6a`
- name: `?ScheduleRenewal@@YAJPEBG@Z`
- size: `602`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800222c0`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000da10`
- `0x18000db08`
- `0x18002201c`
- `0x180022910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229ff`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180022af5`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180022af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022a2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022b3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022a2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002299e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002299e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800229ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800229ef`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800229cc`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800229cc`

## string_xrefs

- `0x1800229e8`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ScheduleRenewal(const unsigned __int16 *a1)
{
  const WCHAR *v3; // rax
  LSTATUS v4; // eax
  bool v5; // sf
  signed int LastError; // eax
  signed int v7; // ebx
  HKEY v8; // rcx
  HKEY v9; // rcx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Dst[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(CommandLine, 0, 0x208u);
  hKey = 0;
  if ( !a1 )
    return 2147942487LL;
  v3 = (const WCHAR *)DMGetKnownRegPath(1);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x2001Fu, &hKey);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( !v5 )
    OmaDmRegistrySetDWORD(hKey, a1, L"RenewNow", 1u);
  if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
    goto LABEL_8;
  v7 = StringCchCopyW(CommandLine, 0x104u, L"/C /r /d \"");
  if ( v7 < 0
    || (v7 = StringCchCatW(CommandLine, 0x104u, a1), v7 < 0)
    || (v7 = StringCchCatW(CommandLine, 0x104u, L"\""), v7 < 0) )
  {
LABEL_10:
    v8 = hKey;
    hKey = 0;
    if ( v8 )
      RegCloseKey(v8);
    return (unsigned int)v7;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  if ( !CreateProcessW(Dst, CommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
  {
LABEL_8:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_10;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  v9 = hKey;
  hKey = 0;
  if ( v9 )
    RegCloseKey(v9);
  return 0;
}

```

## disassembly

```asm
0x180022910  push    rbp
0x180022912  push    rbx
0x180022913  push    rdi
0x180022914  push    r14
0x180022916  lea     rbp, [rsp-418h]
0x18002291e  sub     rsp, 518h
0x180022925  mov     rax, cs:__security_cookie
0x18002292c  xor     rax, rsp
0x18002292f  mov     [rbp+430h+var_30], rax
0x180022936  mov     rdi, rcx
0x180022939  mov     ebx, 208h
0x18002293e  mov     r8d, ebx; Size
0x180022941  xor     edx, edx; Val
0x180022943  lea     rcx, [rbp+430h+Dst]; void *
0x18002294a  call    memset_0
0x18002294f  mov     r8d, ebx; Size
0x180022952  xor     edx, edx; Val
0x180022954  lea     rcx, [rbp+430h+CommandLine]; void *
0x180022958  call    memset_0
0x18002295d  mov     [rsp+530h+hKey], 0
0x180022966  test    rdi, rdi
0x180022969  jnz     short loc_180022975
0x18002296b  mov     eax, 80070057h
0x180022970  jmp     loc_180022B4D
0x180022975  mov     ebx, 1
0x18002297a  mov     ecx, ebx
0x18002297c  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180022981  lea     rcx, [rsp+530h+hKey]
0x180022986  mov     [rsp+530h+phkResult], rcx; phkResult
0x18002298b  mov     r9d, 2001Fh; samDesired
0x180022991  xor     r8d, r8d; ulOptions
0x180022994  mov     rdx, rax; lpSubKey
0x180022997  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002299e  call    cs:__imp_RegOpenKeyExW
0x1800229a5  nop     dword ptr [rax+rax+00h]
0x1800229aa  test    eax, eax
0x1800229ac  jle     short loc_1800229B8
0x1800229ae  movzx   eax, ax
0x1800229b1  or      eax, 80070000h
0x1800229b6  test    eax, eax
0x1800229b8  js      short loc_1800229D8
0x1800229ba  mov     r9d, ebx
0x1800229bd  lea     r8, aRenewnow; "RenewNow"
0x1800229c4  mov     rdx, rdi
0x1800229c7  mov     rcx, [rsp+530h+hKey]
0x1800229cc  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800229d3  nop     dword ptr [rax+rax+00h]
0x1800229d8  mov     r14d, 104h
0x1800229de  mov     r8d, r14d; nSize
0x1800229e1  lea     rdx, [rbp+430h+Dst]; lpDst
0x1800229e8  lea     rcx, Src; "%windir%\\system32\\deviceenroller.exe"
0x1800229ef  call    cs:__imp_ExpandEnvironmentStringsW
0x1800229f6  nop     dword ptr [rax+rax+00h]
0x1800229fb  test    eax, eax
0x1800229fd  jnz     short loc_180022A40
0x1800229ff  call    cs:__imp_GetLastError
0x180022a06  nop     dword ptr [rax+rax+00h]
0x180022a0b  test    eax, eax
0x180022a0d  mov     ebx, eax
0x180022a0f  jle     short loc_180022A1A
0x180022a11  movzx   ebx, ax
0x180022a14  or      ebx, 80070000h
0x180022a1a  mov     rcx, [rsp+530h+hKey]; hKey
0x180022a1f  mov     [rsp+530h+hKey], 0
0x180022a28  test    rcx, rcx
0x180022a2b  jz      short loc_180022A39
0x180022a2d  call    cs:__imp_RegCloseKey
0x180022a34  nop     dword ptr [rax+rax+00h]
0x180022a39  mov     eax, ebx
0x180022a3b  jmp     loc_180022B4D
0x180022a40  lea     r8, aCRD; "/C /r /d \""
0x180022a47  mov     rdx, r14; unsigned __int64
0x180022a4a  lea     rcx, [rbp+430h+CommandLine]; unsigned __int16 *
0x180022a4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022a53  mov     ebx, eax
0x180022a55  test    eax, eax
0x180022a57  js      short loc_180022A1A
0x180022a59  mov     r8, rdi; unsigned __int16 *
0x180022a5c  mov     rdx, r14; unsigned __int64
0x180022a5f  lea     rcx, [rbp+430h+CommandLine]; unsigned __int16 *
0x180022a63  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022a68  mov     ebx, eax
0x180022a6a  test    eax, eax
0x180022a6c  js      short loc_180022A1A
0x180022a6e  lea     r8, asc_18011E928; "\""
0x180022a75  mov     rdx, r14; unsigned __int64
0x180022a78  lea     rcx, [rbp+430h+CommandLine]; unsigned __int16 *
0x180022a7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022a81  mov     ebx, eax
0x180022a83  test    eax, eax
0x180022a85  js      short loc_180022A1A
0x180022a87  xorps   xmm0, xmm0
0x180022a8a  xor     eax, eax
0x180022a8c  movups  xmmword ptr [rsp+530h+ProcessInformation.hProcess], xmm0
0x180022a91  mov     qword ptr [rsp+530h+ProcessInformation.dwProcessId], rax
0x180022a96  xor     edx, edx; Val
0x180022a98  lea     r8d, [rax+64h]; Size
0x180022a9c  lea     rcx, [rsp+530h+StartupInfo+4]; void *
0x180022aa1  call    memset_0
0x180022aa6  mov     [rsp+530h+StartupInfo.cb], 68h ; 'h'
0x180022aae  lea     rax, [rsp+530h+ProcessInformation]
0x180022ab3  mov     [rsp+530h+lpProcessInformation], rax; lpProcessInformation
0x180022ab8  lea     rax, [rsp+530h+StartupInfo]
0x180022abd  mov     [rsp+530h+lpStartupInfo], rax; lpStartupInfo
0x180022ac2  mov     [rsp+530h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180022acb  mov     [rsp+530h+lpEnvironment], 0; lpEnvironment
0x180022ad4  mov     [rsp+530h+dwCreationFlags], 8000000h; dwCreationFlags
0x180022adc  mov     dword ptr [rsp+530h+phkResult], 0; bInheritHandles
0x180022ae4  xor     r9d, r9d; lpThreadAttributes
0x180022ae7  xor     r8d, r8d; lpProcessAttributes
0x180022aea  lea     rdx, [rbp+430h+CommandLine]; lpCommandLine
0x180022aee  lea     rcx, [rbp+430h+Dst]; lpApplicationName
0x180022af5  call    cs:__imp_CreateProcessW
0x180022afc  nop     dword ptr [rax+rax+00h]
0x180022b01  test    eax, eax
0x180022b03  jz      loc_1800229FF
0x180022b09  mov     rcx, [rsp+530h+ProcessInformation.hProcess]; hObject
0x180022b0e  call    cs:__imp_CloseHandle
0x180022b15  nop     dword ptr [rax+rax+00h]
0x180022b1a  mov     rcx, [rsp+530h+ProcessInformation.hThread]; hObject
0x180022b1f  call    cs:__imp_CloseHandle
0x180022b26  nop     dword ptr [rax+rax+00h]
0x180022b2b  nop
0x180022b2c  mov     rcx, [rsp+530h+hKey]; hKey
0x180022b31  mov     [rsp+530h+hKey], 0
0x180022b3a  test    rcx, rcx
0x180022b3d  jz      short loc_180022B4B
0x180022b3f  call    cs:__imp_RegCloseKey
0x180022b46  nop     dword ptr [rax+rax+00h]
0x180022b4b  xor     eax, eax
0x180022b4d  mov     rcx, [rbp+430h+var_30]
0x180022b54  xor     rcx, rsp; StackCookie
0x180022b57  call    __security_check_cookie
0x180022b5c  add     rsp, 518h
0x180022b63  pop     r14
0x180022b65  pop     rdi
0x180022b66  pop     rbx
0x180022b67  pop     rbp
0x180022b68  retn
```
