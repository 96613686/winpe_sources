# CSimpleRegWrapper::RegistryKey::DeleteKey(ushort const *,bool)

- ea: `0x180017d20`
- end: `0x180017e3c`
- name: `?DeleteKey@RegistryKey@CSimpleRegWrapper@@UEAA_NPEBG_N@Z`
- size: `284`
- prototype: `char __fastcall(HKEY *this, const unsigned __int16 *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180017d20`
- `0x180034fd4`
- `0x1800366a8`
- `0x18003f280`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180017dfc`
- `ADVAPI32!RegDeleteKeyW` at `0x180017dfc`
- `KERNEL32!DebugBreak` at `0x180017d65`
- `KERNEL32!DebugBreak` at `0x180017d65`
- `KERNEL32!TerminateProcess` at `0x180017d79`
- `KERNEL32!TerminateProcess` at `0x180017d79`
- `KERNEL32!GetCurrentProcess` at `0x180017d6b`
- `KERNEL32!GetCurrentProcess` at `0x180017d6b`
- `KERNEL32!GetModuleHandleW` at `0x180017d8f`
- `KERNEL32!GetModuleHandleW` at `0x180017d8f`
- `KERNEL32!GetProcAddress` at `0x180017da4`
- `KERNEL32!GetProcAddress` at `0x180017da4`

## string_xrefs

- `0x180017d88`: `advapi32.dll`
- `0x180017d9a`: `RegDeleteKeyExW`

## pseudocode

```c
char __fastcall CSimpleRegWrapper::RegistryKey::DeleteKey(HKEY *this, const unsigned __int16 *a2, char a3)
{
  int v3; // eax
  HANDLE CurrentProcess; // rax
  HMODULE ModuleHandleW; // rax
  HKEY v9; // rcx
  LSTATUS v10; // eax
  unsigned int v12; // ecx
  bool v13; // [rsp+50h] [rbp+18h] BYREF

  v3 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v3 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             (bool)a2,
             &v13) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  if ( !`CSimpleRegWrapper::RegistryKey::DeleteKey'::`2'::initialized )
  {
    ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
    if ( ModuleHandleW )
      `CSimpleRegWrapper::RegistryKey::DeleteKey'::`2'::pfnRegDeleteKeyExW = (__int64)GetProcAddress(
                                                                                        ModuleHandleW,
                                                                                        "RegDeleteKeyExW");
    `CSimpleRegWrapper::RegistryKey::DeleteKey'::`2'::initialized = 1;
  }
  if ( a3 )
    (*((void (__fastcall **)(HKEY *, const unsigned __int16 *))*this + 23))(this, a2);
  v9 = this[2];
  if ( `CSimpleRegWrapper::RegistryKey::DeleteKey'::`2'::pfnRegDeleteKeyExW )
    v10 = ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD))`CSimpleRegWrapper::RegistryKey::DeleteKey'::`2'::pfnRegDeleteKeyExW)(
            v9,
            a2,
            (_DWORD)this[1] & 0x300,
            0);
  else
    v10 = RegDeleteKeyW(v9, a2);
  if ( v10 == 2 || v10 == 161 )
    return 0;
  if ( v10 )
  {
    v12 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v12 = v10;
    ThrowHR(v12);
  }
  return 1;
}

```

## disassembly

```asm
0x180017d20  mov     [rsp+arg_0], rbx
0x180017d25  mov     [rsp+arg_8], rsi
0x180017d2a  push    rdi
0x180017d2b  sub     rsp, 30h
0x180017d2f  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x180017d35  mov     rbx, rcx
0x180017d38  or      ecx, 0FFFFFFFFh
0x180017d3b  mov     sil, r8b
0x180017d3e  mov     rdi, rdx
0x180017d41  cmp     eax, ecx
0x180017d43  jz      short loc_180017D7F
0x180017d45  add     eax, ecx
0x180017d47  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x180017d4d  jnz     short loc_180017D7F
0x180017d4f  lea     r8, [rsp+38h+arg_10]; bool *
0x180017d54  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180017d5b  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180017d60  cmp     eax, 1
0x180017d63  jnz     short loc_180017D6B
0x180017d65  call    cs:__imp_DebugBreak
0x180017d6b  call    cs:__imp_GetCurrentProcess
0x180017d71  mov     rcx, rax; hProcess
0x180017d74  mov     edx, 1; uExitCode
0x180017d79  call    cs:__imp_TerminateProcess
0x180017d7f  cmp     cs:?initialized@?1??DeleteKey@RegistryKey@CSimpleRegWrapper@@UEAA_NPEBG_N@Z@4_NA, 0; bool `CSimpleRegWrapper::RegistryKey::DeleteKey(ushort const *,bool)'::`2'::initialized
0x180017d86  jnz     short loc_180017DB8
0x180017d88  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180017d8f  call    cs:__imp_GetModuleHandleW
0x180017d95  test    rax, rax
0x180017d98  jz      short loc_180017DB1
0x180017d9a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180017da1  mov     rcx, rax; hModule
0x180017da4  call    cs:__imp_GetProcAddress
0x180017daa  mov     cs:?pfnRegDeleteKeyExW@?1??DeleteKey@RegistryKey@CSimpleRegWrapper@@UEAA_NPEBG_N@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`CSimpleRegWrapper::RegistryKey::DeleteKey(ushort const *,bool)'::`2'::pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x180017db1  mov     cs:?initialized@?1??DeleteKey@RegistryKey@CSimpleRegWrapper@@UEAA_NPEBG_N@Z@4_NA, 1; bool `CSimpleRegWrapper::RegistryKey::DeleteKey(ushort const *,bool)'::`2'::initialized
0x180017db8  test    sil, sil
0x180017dbb  jz      short loc_180017DD3
0x180017dbd  mov     rax, [rbx]
0x180017dc0  mov     rdx, rdi
0x180017dc3  mov     rcx, rbx
0x180017dc6  mov     rax, [rax+0B8h]
0x180017dcd  call    cs:__guard_dispatch_icall_fptr
0x180017dd3  mov     rax, cs:?pfnRegDeleteKeyExW@?1??DeleteKey@RegistryKey@CSimpleRegWrapper@@UEAA_NPEBG_N@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`CSimpleRegWrapper::RegistryKey::DeleteKey(ushort const *,bool)'::`2'::pfnRegDeleteKeyExW)(HKEY__ *,ushort const *,ulong,ulong)
0x180017dda  mov     rdx, rdi; lpSubKey
0x180017ddd  mov     rcx, [rbx+10h]; hKey
0x180017de1  test    rax, rax
0x180017de4  jz      short loc_180017DFC
0x180017de6  mov     r8d, [rbx+8]
0x180017dea  xor     r9d, r9d
0x180017ded  and     r8d, 300h
0x180017df4  call    cs:__guard_dispatch_icall_fptr
0x180017dfa  jmp     short loc_180017E02
0x180017dfc  call    cs:__imp_RegDeleteKeyW
0x180017e02  cmp     eax, 2
0x180017e05  jz      short loc_180017E16
0x180017e07  cmp     eax, 0A1h
0x180017e0c  jz      short loc_180017E16
0x180017e0e  test    eax, eax
0x180017e10  jnz     short loc_180017E28
0x180017e12  mov     al, 1
0x180017e14  jmp     short loc_180017E18
0x180017e16  xor     al, al
0x180017e18  mov     rbx, [rsp+38h+arg_0]
0x180017e1d  mov     rsi, [rsp+38h+arg_8]
0x180017e22  add     rsp, 30h
0x180017e26  pop     rdi
0x180017e27  retn
0x180017e28  movzx   ecx, ax
0x180017e2b  or      ecx, 80070000h
0x180017e31  test    eax, eax
0x180017e33  cmovle  ecx, eax; int
0x180017e36  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
