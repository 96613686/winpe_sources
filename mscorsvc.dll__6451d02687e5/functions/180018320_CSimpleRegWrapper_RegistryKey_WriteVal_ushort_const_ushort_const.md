# CSimpleRegWrapper::RegistryKey::WriteVal(ushort const *,ushort const *)

- ea: `0x180018320`
- end: `0x1800183e5`
- name: `?WriteVal@RegistryKey@CSimpleRegWrapper@@UEAAXPEBG0@Z`
- size: `197`
- prototype: `void(CSimpleRegWrapper::RegistryKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180018320`
- `0x180034fd4`
- `0x1800366a8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800183b2`
- `ADVAPI32!RegSetValueExW` at `0x1800183b2`
- `KERNEL32!DebugBreak` at `0x180018369`
- `KERNEL32!DebugBreak` at `0x180018369`
- `KERNEL32!TerminateProcess` at `0x18001837d`
- `KERNEL32!TerminateProcess` at `0x18001837d`
- `KERNEL32!GetCurrentProcess` at `0x18001836f`
- `KERNEL32!GetCurrentProcess` at `0x18001836f`

## pseudocode

```c
void __fastcall CSimpleRegWrapper::RegistryKey::WriteVal(HKEY *this, const unsigned __int16 *a2, const BYTE *a3)
{
  int v3; // eax
  HANDLE CurrentProcess; // rax
  __int64 v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ecx
  bool v11; // [rsp+40h] [rbp+8h] BYREF

  v3 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v3 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             (bool)a2,
             &v11) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&a3[2 * v8] );
  v9 = RegSetValueExW(this[2], a2, 0, 1u, a3, 2 * v8 + 2);
  if ( v9 )
  {
    v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v10 = v9;
    ThrowHR(v10);
  }
}

```

## disassembly

```asm
0x180018320  mov     r11, rsp
0x180018323  mov     [r11+10h], rbx
0x180018327  mov     [r11+18h], rbp
0x18001832b  mov     [r11+20h], rsi
0x18001832f  push    rdi
0x180018330  sub     rsp, 30h
0x180018334  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x18001833a  mov     rsi, rcx
0x18001833d  or      ecx, 0FFFFFFFFh
0x180018340  mov     rbx, r8
0x180018343  mov     rdi, rdx
0x180018346  cmp     eax, ecx
0x180018348  jz      short loc_180018383
0x18001834a  add     eax, ecx
0x18001834c  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x180018352  jnz     short loc_180018383
0x180018354  lea     r8, [r11+8]; bool *
0x180018358  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001835f  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180018364  cmp     eax, 1
0x180018367  jnz     short loc_18001836F
0x180018369  call    cs:__imp_DebugBreak
0x18001836f  call    cs:__imp_GetCurrentProcess
0x180018375  mov     rcx, rax; hProcess
0x180018378  mov     edx, 1; uExitCode
0x18001837d  call    cs:__imp_TerminateProcess
0x180018383  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018387  xor     ebp, ebp
0x180018389  inc     rax
0x18001838c  cmp     [rbx+rax*2], bp
0x180018390  jnz     short loc_180018389
0x180018392  mov     rcx, [rsi+10h]; hKey
0x180018396  lea     eax, ds:2[rax*2]
0x18001839d  mov     [rsp+38h+cbData], eax; cbData
0x1800183a1  mov     r9d, 1; dwType
0x1800183a7  xor     r8d, r8d; Reserved
0x1800183aa  mov     [rsp+38h+lpData], rbx; lpData
0x1800183af  mov     rdx, rdi; lpValueName
0x1800183b2  call    cs:__imp_RegSetValueExW
0x1800183b8  test    eax, eax
0x1800183ba  jnz     short loc_1800183D1
0x1800183bc  mov     rbx, [rsp+38h+arg_8]
0x1800183c1  mov     rbp, [rsp+38h+arg_10]
0x1800183c6  mov     rsi, [rsp+38h+arg_18]
0x1800183cb  add     rsp, 30h
0x1800183cf  pop     rdi
0x1800183d0  retn
0x1800183d1  movzx   ecx, ax
0x1800183d4  or      ecx, 80070000h
0x1800183da  test    eax, eax
0x1800183dc  cmovle  ecx, eax; int
0x1800183df  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
