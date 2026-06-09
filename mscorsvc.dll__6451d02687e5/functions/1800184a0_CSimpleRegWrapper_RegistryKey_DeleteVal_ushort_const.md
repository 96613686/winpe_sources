# CSimpleRegWrapper::RegistryKey::DeleteVal(ushort const *)

- ea: `0x1800184a0`
- end: `0x180018533`
- name: `?DeleteVal@RegistryKey@CSimpleRegWrapper@@UEAAXPEBG@Z`
- size: `147`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800184a0`
- `0x180034fd4`
- `0x1800366a8`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1800184fe`
- `ADVAPI32!RegDeleteValueW` at `0x1800184fe`
- `KERNEL32!DebugBreak` at `0x1800184dd`
- `KERNEL32!DebugBreak` at `0x1800184dd`
- `KERNEL32!TerminateProcess` at `0x1800184f1`
- `KERNEL32!TerminateProcess` at `0x1800184f1`
- `KERNEL32!GetCurrentProcess` at `0x1800184e3`
- `KERNEL32!GetCurrentProcess` at `0x1800184e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSimpleRegWrapper::RegistryKey::DeleteVal(HKEY *this, const unsigned __int16 *a2)
{
  int v2; // eax
  HANDLE CurrentProcess; // rax
  LSTATUS v6; // eax
  unsigned int v7; // ecx
  bool v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v2 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             (bool)a2,
             &v8) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  v6 = RegDeleteValueW(this[2], a2);
  if ( v6 && v6 != 2 && v6 != 161 )
  {
    v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v7 = v6;
    ThrowHR(v7);
  }
}

```

## disassembly

```asm
0x1800184a0  mov     [rsp+arg_8], rbx
0x1800184a5  push    rdi
0x1800184a6  sub     rsp, 20h
0x1800184aa  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x1800184b0  mov     rdi, rcx
0x1800184b3  or      ecx, 0FFFFFFFFh
0x1800184b6  mov     rbx, rdx
0x1800184b9  cmp     eax, ecx
0x1800184bb  jz      short loc_1800184F7
0x1800184bd  add     eax, ecx
0x1800184bf  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x1800184c5  jnz     short loc_1800184F7
0x1800184c7  lea     r8, [rsp+28h+arg_0]; bool *
0x1800184cc  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800184d3  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800184d8  cmp     eax, 1
0x1800184db  jnz     short loc_1800184E3
0x1800184dd  call    cs:__imp_DebugBreak
0x1800184e3  call    cs:__imp_GetCurrentProcess
0x1800184e9  mov     rcx, rax; hProcess
0x1800184ec  mov     edx, 1; uExitCode
0x1800184f1  call    cs:__imp_TerminateProcess
0x1800184f7  mov     rcx, [rdi+10h]; hKey
0x1800184fb  mov     rdx, rbx; lpValueName
0x1800184fe  call    cs:__imp_RegDeleteValueW
0x180018504  test    eax, eax
0x180018506  jz      short loc_180018514
0x180018508  cmp     eax, 2
0x18001850b  jz      short loc_180018514
0x18001850d  cmp     eax, 0A1h
0x180018512  jnz     short loc_18001851F
0x180018514  mov     rbx, [rsp+28h+arg_8]
0x180018519  add     rsp, 20h
0x18001851d  pop     rdi
0x18001851e  retn
0x18001851f  movzx   ecx, ax
0x180018522  or      ecx, 80070000h
0x180018528  test    eax, eax
0x18001852a  cmovle  ecx, eax; int
0x18001852d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
