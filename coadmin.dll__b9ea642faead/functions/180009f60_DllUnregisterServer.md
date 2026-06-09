# DllUnregisterServer

- ea: `0x180009f60`
- end: `0x18000a0a2`
- name: `DllUnregisterServer`
- size: `322`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009f60`
- `0x18000f940`
- `0x18000f998`
- `0x18000fb1e`
- `0x18000fb50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009fa9`
- `KERNEL32!GetLastError` at `0x180009fa9`
- `KERNEL32!DeleteCriticalSection` at `0x18000a06b`
- `KERNEL32!DeleteCriticalSection` at `0x18000a06b`
- `KERNEL32!GetVersionExA` at `0x180009fdb`
- `KERNEL32!GetVersionExA` at `0x180009fdb`
- `IisRTL!IISInitializeCriticalSection` at `0x180009f9f`
- `IisRTL!IISInitializeCriticalSection` at `0x180009f9f`

## string_xrefs

- `0x18000a01f`: `MS IIS DCOM Server`
- `0x18000a030`: `MS IIS DCOM Server`
- `0x18000a03e`: `MS IIS DCOM Client`
- `0x18000a04f`: `MS IIS DCOM Client`
- `0x18000a07b`: `RemoveComponent`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  signed int LastError; // eax
  const unsigned __int16 *v1; // rcx
  HRESULT v2; // ebx
  _OSVERSIONINFOA VersionInformation; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( dword_180016F40 )
  {
LABEL_11:
    v2 = 0;
    if ( fCryptoSettingsDoOverrride )
      dword_180016F3C = fCryptoSettingsOverrideFlag;
    goto LABEL_13;
  }
  if ( (unsigned int)IISInitializeCriticalSection(&IcpGlobals) )
  {
    dword_180016F38 = 0;
    VersionInformation.dwOSVersionInfoSize = 148;
    if ( !GetVersionExA(&VersionInformation) || (dword_180016F3C = 1, VersionInformation.dwPlatformId != 2) )
      dword_180016F3C = 0;
    dword_180016F40 = 1;
    goto LABEL_11;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_13:
    IISCryptoDeleteContainerByName("MS IIS DCOM Server");
    IISCryptoDeleteContainerByName("MS IIS DCOM Server");
    IISCryptoDeleteContainerByName("MS IIS DCOM Client");
    IISCryptoDeleteContainerByName("MS IIS DCOM Client");
    if ( dword_180016F40 )
    {
      DeleteCriticalSection(&IcpGlobals);
      dword_180016F40 = 0;
    }
  }
  CallRegisterComponent(v1, "RemoveComponent");
  return v2;
}

```

## disassembly

```asm
0x180009f60  push    rbx
0x180009f62  sub     rsp, 0D0h
0x180009f69  mov     rax, cs:__security_cookie
0x180009f70  xor     rax, rsp
0x180009f73  mov     [rsp+0D8h+var_18], rax
0x180009f7b  mov     ebx, 94h
0x180009f80  lea     rcx, [rsp+0D8h+VersionInformation]; void *
0x180009f85  mov     r8d, ebx; Size
0x180009f88  xor     edx, edx; Val
0x180009f8a  call    memset_0
0x180009f8f  cmp     cs:dword_180016F40, 0
0x180009f96  jnz     short loc_18000A007
0x180009f98  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; _IC_GLOBALS IcpGlobals
0x180009f9f  call    cs:__imp_IISInitializeCriticalSection
0x180009fa5  test    eax, eax
0x180009fa7  jnz     short loc_180009FC8
0x180009fa9  call    cs:__imp_GetLastError
0x180009faf  mov     ebx, eax
0x180009fb1  test    eax, eax
0x180009fb3  jle     short loc_180009FBE
0x180009fb5  movzx   ebx, ax
0x180009fb8  or      ebx, 80070000h
0x180009fbe  test    ebx, ebx
0x180009fc0  js      loc_18000A07B
0x180009fc6  jmp     short loc_18000A01D
0x180009fc8  lea     rcx, [rsp+0D8h+VersionInformation]; lpVersionInformation
0x180009fcd  mov     cs:dword_180016F38, 0
0x180009fd7  mov     [rsp+0D8h+VersionInformation.dwOSVersionInfoSize], ebx
0x180009fdb  call    cs:__imp_GetVersionExA
0x180009fe1  mov     ecx, 1
0x180009fe6  test    eax, eax
0x180009fe8  jz      short loc_180009FF7
0x180009fea  cmp     [rsp+0D8h+VersionInformation.dwPlatformId], 2
0x180009fef  mov     cs:dword_180016F3C, ecx
0x180009ff5  jz      short loc_18000A001
0x180009ff7  mov     cs:dword_180016F3C, 0
0x18000a001  mov     cs:dword_180016F40, ecx
0x18000a007  xor     ebx, ebx
0x18000a009  cmp     cs:?fCryptoSettingsDoOverrride@@3HA, ebx; int fCryptoSettingsDoOverrride
0x18000a00f  jz      short loc_18000A01D
0x18000a011  mov     eax, cs:?fCryptoSettingsOverrideFlag@@3HA; int fCryptoSettingsOverrideFlag
0x18000a017  mov     cs:dword_180016F3C, eax
0x18000a01d  xor     edx, edx
0x18000a01f  lea     rcx, szContainer; "MS IIS DCOM Server"
0x18000a026  call    IISCryptoDeleteContainerByName
0x18000a02b  mov     edx, 20h ; ' '
0x18000a030  lea     rcx, szContainer; "MS IIS DCOM Server"
0x18000a037  call    IISCryptoDeleteContainerByName
0x18000a03c  xor     edx, edx
0x18000a03e  lea     rcx, aMsIisDcomClien; "MS IIS DCOM Client"
0x18000a045  call    IISCryptoDeleteContainerByName
0x18000a04a  mov     edx, 20h ; ' '
0x18000a04f  lea     rcx, aMsIisDcomClien; "MS IIS DCOM Client"
0x18000a056  call    IISCryptoDeleteContainerByName
0x18000a05b  cmp     cs:dword_180016F40, 0
0x18000a062  jz      short loc_18000A07B
0x18000a064  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18000a06b  call    cs:__imp_DeleteCriticalSection
0x18000a071  mov     cs:dword_180016F40, 0
0x18000a07b  lea     rdx, aRemovecomponen; "RemoveComponent"
0x18000a082  call    ?CallRegisterComponent@@YAJPEBGPEAD@Z; CallRegisterComponent(ushort const *,char *)
0x18000a087  mov     eax, ebx
0x18000a089  mov     rcx, [rsp+0D8h+var_18]
0x18000a091  xor     rcx, rsp; StackCookie
0x18000a094  call    __security_check_cookie
0x18000a099  add     rsp, 0D0h
0x18000a0a0  pop     rbx
0x18000a0a1  retn
```
