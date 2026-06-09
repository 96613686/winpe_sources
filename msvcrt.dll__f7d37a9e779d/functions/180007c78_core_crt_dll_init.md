# _core_crt_dll_init

- ea: `0x180007c78`
- end: `0x180007d6a`
- name: `_core_crt_dll_init`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a24`
- `0x18001d350`
- `0x18001d688`

## callees

- `0x180007c78`
- `0x18001ce00`
- `0x18001ce74`
- `0x180033a90`
- `0x18003e1dc`
- `0x180079760`
- `0x18007d030`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180007cce`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180007cce`

## pseudocode

```c
__int64 core_crt_dll_init()
{
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  if ( !core_crt_dll_init_completed )
  {
    memset_thunk_772440563353939046(&VersionInformation, 0, 0x114u);
    _app_type = get_image_app_type((unsigned int)_app_type);
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( !GetVersionExW(&VersionInformation) )
      return 0;
    osplatform = VersionInformation.dwPlatformId;
    winmajor = VersionInformation.dwMajorVersion;
    winminor = VersionInformation.dwMinorVersion;
    osver = VersionInformation.dwBuildNumber & 0x7FFF;
    if ( VersionInformation.dwPlatformId != 2 )
      osver = VersionInformation.dwBuildNumber & 0x7FFF | 0x8000;
    winver = VersionInformation.dwMinorVersion + (VersionInformation.dwMajorVersion << 8);
    if ( !(unsigned int)heap_init(1) )
      return 0;
    if ( !(unsigned int)mtinit() )
    {
      heap_term();
      return 0;
    }
    core_crt_dll_init_completed = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180007c78  sub     rsp, 158h
0x180007c7f  mov     rax, cs:__security_cookie
0x180007c86  xor     rax, rsp
0x180007c89  mov     [rsp+158h+var_18], rax
0x180007c91  cmp     cs:_core_crt_dll_init_completed, 0
0x180007c98  jnz     loc_180007D4D
0x180007c9e  xor     edx, edx; Val
0x180007ca0  lea     rcx, [rsp+158h+VersionInformation]; void *
0x180007ca5  mov     r8d, 114h; Size
0x180007cab  call    memset$thunk$772440563353939046
0x180007cb0  mov     ecx, cs:__app_type
0x180007cb6  call    _get_image_app_type
0x180007cbb  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x180007cc0  mov     cs:__app_type, eax
0x180007cc6  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x180007cce  call    cs:__imp_GetVersionExW
0x180007cd4  test    eax, eax
0x180007cd6  jz      short loc_180007D3F
0x180007cd8  mov     eax, [rsp+158h+VersionInformation.dwPlatformId]
0x180007cdc  mov     ecx, [rsp+158h+VersionInformation.dwBuildNumber]
0x180007ce0  mov     edx, [rsp+158h+VersionInformation.dwMajorVersion]
0x180007ce4  and     ecx, 7FFFh
0x180007cea  mov     r8d, [rsp+158h+VersionInformation.dwMinorVersion]
0x180007cef  mov     cs:_osplatform, eax
0x180007cf5  mov     cs:_winmajor, edx
0x180007cfb  mov     cs:_winminor, r8d
0x180007d02  mov     cs:_osver, ecx
0x180007d08  cmp     eax, 2
0x180007d0b  jz      short loc_180007D17
0x180007d0d  bts     ecx, 0Fh
0x180007d11  mov     cs:_osver, ecx
0x180007d17  shl     edx, 8
0x180007d1a  mov     ecx, 1
0x180007d1f  add     edx, r8d
0x180007d22  mov     cs:_winver, edx
0x180007d28  call    _heap_init
0x180007d2d  test    eax, eax
0x180007d2f  jz      short loc_180007D3F
0x180007d31  call    _mtinit
0x180007d36  test    eax, eax
0x180007d38  jnz     short loc_180007D43
0x180007d3a  call    _heap_term
0x180007d3f  xor     eax, eax
0x180007d41  jmp     short loc_180007D52
0x180007d43  mov     cs:_core_crt_dll_init_completed, 1
0x180007d4d  mov     eax, 1
0x180007d52  mov     rcx, [rsp+158h+var_18]
0x180007d5a  xor     rcx, rsp; StackCookie
0x180007d5d  call    __security_check_cookie
0x180007d62  add     rsp, 158h
0x180007d69  retn
```
