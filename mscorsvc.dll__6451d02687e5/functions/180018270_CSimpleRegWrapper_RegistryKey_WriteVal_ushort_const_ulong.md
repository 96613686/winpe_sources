# CSimpleRegWrapper::RegistryKey::WriteVal(ushort const *,ulong)

- ea: `0x180018270`
- end: `0x180018314`
- name: `?WriteVal@RegistryKey@CSimpleRegWrapper@@UEAAXPEBGK@Z`
- size: `164`
- prototype: `void(CSimpleRegWrapper::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180018270`
- `0x180034fd4`
- `0x1800366a8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800182eb`
- `ADVAPI32!RegSetValueExW` at `0x1800182eb`
- `KERNEL32!DebugBreak` at `0x1800182b2`
- `KERNEL32!DebugBreak` at `0x1800182b2`
- `KERNEL32!TerminateProcess` at `0x1800182c6`
- `KERNEL32!TerminateProcess` at `0x1800182c6`
- `KERNEL32!GetCurrentProcess` at `0x1800182b8`
- `KERNEL32!GetCurrentProcess` at `0x1800182b8`

## pseudocode

```c
void __fastcall CSimpleRegWrapper::RegistryKey::WriteVal(HKEY *this, const unsigned __int16 *a2, int a3)
{
  int v3; // eax
  HANDLE CurrentProcess; // rax
  LSTATUS v7; // eax
  unsigned int v8; // ecx
  bool v9; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  v3 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v3 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             (bool)a2,
             &v9) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  v7 = RegSetValueExW(this[2], a2, 0, 4u, (const BYTE *)&Data, 4u);
  if ( v7 )
  {
    v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 <= 0 )
      v8 = v7;
    ThrowHR(v8);
  }
}

```

## disassembly

```asm
0x180018270  mov     [rsp+arg_8], rbx
0x180018275  mov     [rsp+Data], r8d
0x18001827a  push    rdi
0x18001827b  sub     rsp, 30h
0x18001827f  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x180018285  mov     rdi, rcx
0x180018288  or      ecx, 0FFFFFFFFh
0x18001828b  mov     rbx, rdx
0x18001828e  cmp     eax, ecx
0x180018290  jz      short loc_1800182CC
0x180018292  add     eax, ecx
0x180018294  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x18001829a  jnz     short loc_1800182CC
0x18001829c  lea     r8, [rsp+38h+arg_0]; bool *
0x1800182a1  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800182a8  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800182ad  cmp     eax, 1
0x1800182b0  jnz     short loc_1800182B8
0x1800182b2  call    cs:__imp_DebugBreak
0x1800182b8  call    cs:__imp_GetCurrentProcess
0x1800182be  mov     rcx, rax; hProcess
0x1800182c1  mov     edx, 1; uExitCode
0x1800182c6  call    cs:__imp_TerminateProcess
0x1800182cc  mov     rcx, [rdi+10h]; hKey
0x1800182d0  lea     rax, [rsp+38h+Data]
0x1800182d5  mov     r9d, 4; dwType
0x1800182db  xor     r8d, r8d; Reserved
0x1800182de  mov     [rsp+38h+cbData], r9d; cbData
0x1800182e3  mov     rdx, rbx; lpValueName
0x1800182e6  mov     [rsp+38h+lpData], rax; lpData
0x1800182eb  call    cs:__imp_RegSetValueExW
0x1800182f1  test    eax, eax
0x1800182f3  jnz     short loc_180018300
0x1800182f5  mov     rbx, [rsp+38h+arg_8]
0x1800182fa  add     rsp, 30h
0x1800182fe  pop     rdi
0x1800182ff  retn
0x180018300  movzx   ecx, ax
0x180018303  or      ecx, 80070000h
0x180018309  test    eax, eax
0x18001830b  cmovle  ecx, eax; int
0x18001830e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
