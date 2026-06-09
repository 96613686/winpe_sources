# ExcludeIppDllHostPrintTicketServerFromPdcRegen

- ea: `0x18001288c`
- end: `0x180012993`
- name: `ExcludeIppDllHostPrintTicketServerFromPdcRegen`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9a0`
- `0x18000c9f0`

## callees

- `0x18000f970`
- `0x18001288c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001290b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001290b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012939`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012939`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800128f5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800128f5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001295c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001295c`
- `KERNEL32!GetModuleFileNameW` at `0x1800128dd`
- `KERNEL32!GetModuleFileNameW` at `0x1800128dd`
- `KERNEL32!GetCommandLineW` at `0x180012915`
- `KERNEL32!GetCommandLineW` at `0x180012915`
- `IppCommon!IsModernPrinter` at `0x1800128b7`
- `IppCommon!IsModernPrinter` at `0x1800128b7`
- `Print.PrintSupport.Source!ExcludePdcRegenerationForPsaActivationProcess` at `0x18001296c`
- `Print.PrintSupport.Source!ExcludePdcRegenerationForPsaActivationProcess` at `0x18001296c`

## string_xrefs

- `0x180012904`: `dllhost.exe`

## pseudocode

```c
int __fastcall ExcludeIppDllHostPrintTicketServerFromPdcRegen(__int64 a1)
{
  wchar_t *CommandLineW; // rax
  const wchar_t *v2; // rcx
  wchar_t **v3; // rdi
  wchar_t *v4; // rbx
  _BYTE v6[16]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  v6[0] = 0;
  LODWORD(CommandLineW) = IsModernPrinter(a1, 0, v6);
  if ( (int)CommandLineW >= 0 )
  {
    if ( v6[0] )
    {
      LODWORD(CommandLineW) = GetModuleFileNameW(0, Filename, 0x104u);
      if ( (_DWORD)CommandLineW )
      {
        CommandLineW = wcsrchr(Filename, 0x5Cu);
        if ( CommandLineW )
        {
          LODWORD(CommandLineW) = _o__wcsicmp(CommandLineW + 1, L"dllhost.exe");
          if ( !(_DWORD)CommandLineW )
          {
            CommandLineW = GetCommandLineW();
            if ( CommandLineW )
            {
              v2 = CommandLineW;
LABEL_12:
              CommandLineW = wcschr(v2, 0x7Bu);
              v4 = CommandLineW;
              if ( CommandLineW )
              {
                v3 = off_1800252B0;
                while ( (unsigned int)_o__wcsnicmp(v4 + 1, *v3, 36) )
                {
                  if ( ++v3 == &`ATL::CRegParser::HKeyFromString'::`2'::map )
                  {
                    v2 = v4 + 2;
                    goto LABEL_12;
                  }
                }
                LODWORD(CommandLineW) = ExcludePdcRegenerationForPsaActivationProcess();
              }
            }
          }
        }
      }
    }
  }
  return (int)CommandLineW;
}

```

## disassembly

```asm
0x18001288c  mov     [rsp+arg_8], rbx
0x180012891  push    rdi
0x180012892  sub     rsp, 250h
0x180012899  mov     rax, cs:__security_cookie
0x1800128a0  xor     rax, rsp
0x1800128a3  mov     [rsp+258h+var_18], rax
0x1800128ab  lea     r8, [rsp+258h+var_238]
0x1800128b0  mov     [rsp+258h+var_238], 0
0x1800128b5  xor     edx, edx
0x1800128b7  call    cs:__imp_IsModernPrinter
0x1800128bd  test    eax, eax
0x1800128bf  js      loc_180012972
0x1800128c5  cmp     [rsp+258h+var_238], 0
0x1800128ca  jz      loc_180012972
0x1800128d0  mov     r8d, 104h; nSize
0x1800128d6  lea     rdx, [rsp+258h+Filename]; lpFilename
0x1800128db  xor     ecx, ecx; hModule
0x1800128dd  call    cs:__imp_GetModuleFileNameW
0x1800128e3  test    eax, eax
0x1800128e5  jz      loc_180012972
0x1800128eb  mov     edx, 5Ch ; '\'; Ch
0x1800128f0  lea     rcx, [rsp+258h+Filename]; Str
0x1800128f5  call    cs:__imp_wcsrchr
0x1800128fb  test    rax, rax
0x1800128fe  jz      short loc_180012972
0x180012900  lea     rcx, [rax+2]
0x180012904  lea     rdx, aDllhostExe; "dllhost.exe"
0x18001290b  call    cs:__imp__o__wcsicmp
0x180012911  test    eax, eax
0x180012913  jnz     short loc_180012972
0x180012915  call    cs:__imp_GetCommandLineW
0x18001291b  test    rax, rax
0x18001291e  jz      short loc_180012972
0x180012920  mov     rcx, rax
0x180012923  jmp     short loc_180012957
0x180012925  lea     rdi, off_1800252B0; "B86F86AF-AA5D-47C2-AB44-17AB64F907B4"
0x18001292c  mov     rdx, [rdi]
0x18001292f  lea     rcx, [rbx+2]
0x180012933  mov     r8d, 24h ; '$'
0x180012939  call    cs:__imp__o__wcsnicmp
0x18001293f  test    eax, eax
0x180012941  jz      short loc_18001296C
0x180012943  add     rdi, 8
0x180012947  lea     rax, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001294e  cmp     rdi, rax
0x180012951  jnz     short loc_18001292C
0x180012953  lea     rcx, [rbx+4]; Str
0x180012957  mov     edx, 7Bh ; '{'; Ch
0x18001295c  call    cs:__imp_wcschr
0x180012962  mov     rbx, rax
0x180012965  test    rax, rax
0x180012968  jnz     short loc_180012925
0x18001296a  jmp     short loc_180012972
0x18001296c  call    cs:__imp_ExcludePdcRegenerationForPsaActivationProcess
0x180012972  mov     rcx, [rsp+258h+var_18]
0x18001297a  xor     rcx, rsp; StackCookie
0x18001297d  call    __security_check_cookie
0x180012982  mov     rbx, [rsp+258h+arg_8]
0x18001298a  add     rsp, 250h
0x180012991  pop     rdi
0x180012992  retn
```
