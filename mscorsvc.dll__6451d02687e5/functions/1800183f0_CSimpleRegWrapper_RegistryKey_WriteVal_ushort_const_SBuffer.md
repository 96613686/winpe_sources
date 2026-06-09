# CSimpleRegWrapper::RegistryKey::WriteVal(ushort const *,SBuffer *)

- ea: `0x1800183f0`
- end: `0x18001849c`
- name: `?WriteVal@RegistryKey@CSimpleRegWrapper@@UEAAXPEBGPEAVSBuffer@@@Z`
- size: `172`
- prototype: `void(CSimpleRegWrapper::RegistryKey *__hidden this, const unsigned __int16 *, struct SBuffer *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800183f0`
- `0x180034fd4`
- `0x1800366a8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001846e`
- `ADVAPI32!RegSetValueExW` at `0x18001846e`
- `KERNEL32!DebugBreak` at `0x180018435`
- `KERNEL32!DebugBreak` at `0x180018435`
- `KERNEL32!TerminateProcess` at `0x180018449`
- `KERNEL32!TerminateProcess` at `0x180018449`
- `KERNEL32!GetCurrentProcess` at `0x18001843b`
- `KERNEL32!GetCurrentProcess` at `0x18001843b`

## pseudocode

```c
void __fastcall CSimpleRegWrapper::RegistryKey::WriteVal(HKEY *this, const unsigned __int16 *a2, const BYTE **a3)
{
  int v3; // eax
  HANDLE CurrentProcess; // rax
  LSTATUS v8; // eax
  unsigned int v9; // ecx
  bool v10; // [rsp+40h] [rbp+8h] BYREF

  v3 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v3 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             (bool)a2,
             &v10) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  v8 = RegSetValueExW(this[2], a2, 0, 3u, a3[2], *(_DWORD *)a3);
  if ( v8 )
  {
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    ThrowHR(v9);
  }
}

```

## disassembly

```asm
0x1800183f0  mov     [rsp+arg_8], rbx
0x1800183f5  mov     [rsp+arg_10], rsi
0x1800183fa  push    rdi
0x1800183fb  sub     rsp, 30h
0x1800183ff  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x180018405  mov     rsi, rcx
0x180018408  or      ecx, 0FFFFFFFFh
0x18001840b  mov     rbx, r8
0x18001840e  mov     rdi, rdx
0x180018411  cmp     eax, ecx
0x180018413  jz      short loc_18001844F
0x180018415  add     eax, ecx
0x180018417  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x18001841d  jnz     short loc_18001844F
0x18001841f  lea     r8, [rsp+38h+arg_0]; bool *
0x180018424  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001842b  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180018430  cmp     eax, 1
0x180018433  jnz     short loc_18001843B
0x180018435  call    cs:__imp_DebugBreak
0x18001843b  call    cs:__imp_GetCurrentProcess
0x180018441  mov     rcx, rax; hProcess
0x180018444  mov     edx, 1; uExitCode
0x180018449  call    cs:__imp_TerminateProcess
0x18001844f  mov     eax, [rbx]
0x180018451  mov     r9d, 3; dwType
0x180018457  mov     rcx, [rsi+10h]; hKey
0x18001845b  xor     r8d, r8d; Reserved
0x18001845e  mov     [rsp+38h+cbData], eax; cbData
0x180018462  mov     rdx, rdi; lpValueName
0x180018465  mov     rax, [rbx+10h]
0x180018469  mov     [rsp+38h+lpData], rax; lpData
0x18001846e  call    cs:__imp_RegSetValueExW
0x180018474  test    eax, eax
0x180018476  jnz     short loc_180018488
0x180018478  mov     rbx, [rsp+38h+arg_8]
0x18001847d  mov     rsi, [rsp+38h+arg_10]
0x180018482  add     rsp, 30h
0x180018486  pop     rdi
0x180018487  retn
0x180018488  movzx   ecx, ax
0x18001848b  or      ecx, 80070000h
0x180018491  test    eax, eax
0x180018493  cmovle  ecx, eax; int
0x180018496  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
