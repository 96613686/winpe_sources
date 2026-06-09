# EnableAutoWPPTracing

- ea: `0x1800bc148`
- end: `0x1800bc1d6`
- name: `EnableAutoWPPTracing`
- size: `142`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008a200`
- `0x18008b360`

## callees

- `0x1800bc148`
- `0x1800bc1dc`
- `0x1800bc4e0`
- `0x1800bce34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bc1c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bc1c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc187`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bc187`

## string_xrefs

- `0x1800bc17a`: `wevtapi.dll`
- `0x1800bc198`: `Windows Networking Vpn Plugin Platform/Operational`
- `0x1800bc1af`: `Windows Networking Vpn Plugin Platform/OperationalVerbose`

## pseudocode

```c
__int64 EnableAutoWPPTracing()
{
  unsigned int v0; // ebx
  unsigned int i; // edi
  unsigned int v2; // eax
  HMODULE Library; // rax
  HMODULE v4; // rdi
  unsigned int v5; // eax
  unsigned int v6; // eax

  v0 = 0;
  if ( (unsigned int)IsDefaultTracingEnabled() )
  {
    for ( i = 1; i < 6; ++i )
    {
      v2 = EnableAutoWPPTracingForSubComponent(i);
      if ( v2 )
        return v2;
    }
    Library = LoadLibraryExW(L"wevtapi.dll", 0, 0x800u);
    v4 = Library;
    if ( Library )
    {
      v5 = EnableVpnPluginETWChannel(L"Windows Networking Vpn Plugin Platform/Operational", Library);
      if ( v5 )
      {
        v0 = v5;
      }
      else
      {
        v6 = EnableVpnPluginETWChannel(L"Windows Networking Vpn Plugin Platform/OperationalVerbose", v4);
        if ( v6 )
          v0 = v6;
      }
      FreeLibrary(v4);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800bc148  mov     [rsp+arg_0], rbx
0x1800bc14d  push    rdi
0x1800bc14e  sub     rsp, 20h
0x1800bc152  xor     ebx, ebx
0x1800bc154  call    IsDefaultTracingEnabled
0x1800bc159  test    eax, eax
0x1800bc15b  jz      short loc_1800BC1C9
0x1800bc15d  lea     edi, [rbx+1]
0x1800bc160  cmp     edi, 6
0x1800bc163  jnb     short loc_1800BC178
0x1800bc165  mov     ecx, edi
0x1800bc167  call    EnableAutoWPPTracingForSubComponent
0x1800bc16c  test    eax, eax
0x1800bc16e  jnz     short loc_1800BC174
0x1800bc170  inc     edi
0x1800bc172  jmp     short loc_1800BC160
0x1800bc174  mov     ebx, eax
0x1800bc176  jmp     short loc_1800BC1C9
0x1800bc178  xor     edx, edx; hFile
0x1800bc17a  lea     rcx, aWevtapiDll_0; "wevtapi.dll"
0x1800bc181  mov     r8d, 800h; dwFlags
0x1800bc187  call    cs:__imp_LoadLibraryExW
0x1800bc18d  mov     rdi, rax
0x1800bc190  test    rax, rax
0x1800bc193  jz      short loc_1800BC1C9
0x1800bc195  mov     rdx, rax; hModule
0x1800bc198  lea     rcx, ChannelPath; "Windows Networking Vpn Plugin Platform/"...
0x1800bc19f  call    EnableVpnPluginETWChannel
0x1800bc1a4  test    eax, eax
0x1800bc1a6  jz      short loc_1800BC1AC
0x1800bc1a8  mov     ebx, eax
0x1800bc1aa  jmp     short loc_1800BC1C0
0x1800bc1ac  mov     rdx, rdi; hModule
0x1800bc1af  lea     rcx, aWindowsNetwork; "Windows Networking Vpn Plugin Platform/"...
0x1800bc1b6  call    EnableVpnPluginETWChannel
0x1800bc1bb  test    eax, eax
0x1800bc1bd  cmovnz  ebx, eax
0x1800bc1c0  mov     rcx, rdi; hLibModule
0x1800bc1c3  call    cs:__imp_FreeLibrary
0x1800bc1c9  mov     eax, ebx
0x1800bc1cb  mov     rbx, [rsp+28h+arg_0]
0x1800bc1d0  add     rsp, 20h
0x1800bc1d4  pop     rdi
0x1800bc1d5  retn
```
