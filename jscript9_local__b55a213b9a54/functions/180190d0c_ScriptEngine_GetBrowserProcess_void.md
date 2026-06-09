# ScriptEngine::GetBrowserProcess(void)

- ea: `0x180190d0c`
- end: `0x18019115a`
- name: `?GetBrowserProcess@ScriptEngine@@QEAA?AW4_BROWSER_PROCESS@@XZ`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18019ff4c`

## callees

- `0x180190d0c`
- `0x1803481f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180190d78`
- `msvcrt!_wcsicmp` at `0x180190d9c`
- `msvcrt!_wcsicmp` at `0x180190dc0`
- `msvcrt!_wcsicmp` at `0x180190de4`
- `msvcrt!_wcsicmp` at `0x180190e08`
- `msvcrt!_wcsicmp` at `0x180190e2c`
- `msvcrt!_wcsicmp` at `0x180190e50`
- `msvcrt!_wcsicmp` at `0x180190e6e`
- `msvcrt!_wcsicmp` at `0x180190e8c`
- `msvcrt!_wcsicmp` at `0x180190eaa`
- `msvcrt!_wcsicmp` at `0x180190ec8`
- `msvcrt!_wcsicmp` at `0x180190eec`
- `msvcrt!_wcsicmp` at `0x180190f10`
- `msvcrt!_wcsicmp` at `0x180190f34`
- `msvcrt!_wcsicmp` at `0x180190f58`
- `msvcrt!_wcsicmp` at `0x180190f7c`
- `msvcrt!_wcsicmp` at `0x180190fc5`
- `msvcrt!_wcsicmp` at `0x180190fe9`
- `msvcrt!_wcsicmp` at `0x180191007`
- `msvcrt!_wcsicmp` at `0x180191025`
- `msvcrt!_wcsicmp` at `0x180191067`
- `msvcrt!_wcsicmp` at `0x18019108b`
- `msvcrt!_wcsicmp` at `0x1801910af`
- `msvcrt!_wcsicmp` at `0x1801910d0`
- `msvcrt!_wcsicmp` at `0x1801910f1`
- `msvcrt!_wcsicmp` at `0x180191112`
- `msvcrt!_wcsicmp` at `0x180190d78`
- `msvcrt!_wcsicmp` at `0x180190d9c`
- `msvcrt!_wcsicmp` at `0x180190dc0`
- `msvcrt!_wcsicmp` at `0x180190de4`
- `msvcrt!_wcsicmp` at `0x180190e08`
- `msvcrt!_wcsicmp` at `0x180190e2c`
- `msvcrt!_wcsicmp` at `0x180190e50`
- `msvcrt!_wcsicmp` at `0x180190e6e`
- `msvcrt!_wcsicmp` at `0x180190e8c`
- `msvcrt!_wcsicmp` at `0x180190eaa`
- `msvcrt!_wcsicmp` at `0x180190ec8`
- `msvcrt!_wcsicmp` at `0x180190eec`
- `msvcrt!_wcsicmp` at `0x180190f10`
- `msvcrt!_wcsicmp` at `0x180190f34`
- `msvcrt!_wcsicmp` at `0x180190f58`
- `msvcrt!_wcsicmp` at `0x180190f7c`
- `msvcrt!_wcsicmp` at `0x180190fc5`
- `msvcrt!_wcsicmp` at `0x180190fe9`
- `msvcrt!_wcsicmp` at `0x180191007`
- `msvcrt!_wcsicmp` at `0x180191025`
- `msvcrt!_wcsicmp` at `0x180191067`
- `msvcrt!_wcsicmp` at `0x18019108b`
- `msvcrt!_wcsicmp` at `0x1801910af`
- `msvcrt!_wcsicmp` at `0x1801910d0`
- `msvcrt!_wcsicmp` at `0x1801910f1`
- `msvcrt!_wcsicmp` at `0x180191112`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180190d5f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180190d5f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180190fa0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180190fa0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180191043`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180191043`
- `KERNEL32!GetModuleFileNameW` at `0x180190d46`
- `KERNEL32!GetModuleFileNameW` at `0x180190d46`

## string_xrefs

- `0x180190f06`: `USERACCOUNTBROKER.EXE`
- `0x180191081`: `browser_broker.exe`
- `0x180191108`: `rundll32.exe`

## pseudocode

```c
__int64 ScriptEngine::GetBrowserProcess()
{
  __int64 result; // rax
  const wchar_t *FileNameW; // rbx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  result = (unsigned int)dword_180443918;
  if ( !dword_180443918 )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      FileNameW = PathFindFileNameW(Filename);
      if ( !_wcsicmp(FileNameW, L"IEXPLORE.EXE") )
      {
        result = 1;
LABEL_55:
        dword_180443918 = result;
        return result;
      }
      if ( !_wcsicmp(FileNameW, L"MSFEEDSSYNC.EXE") )
      {
        result = 2;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"SYSPREP.EXE") )
      {
        result = 3;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"EXPLORER.EXE") )
      {
        result = 4;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"LOADER42.EXE") )
      {
        result = 6;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"WWAHOST.EXE") )
      {
        result = 7;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"IEUTLAUNCH.EXE")
        || !_wcsicmp(FileNameW, L"TE.EXE")
        || !_wcsicmp(FileNameW, L"Te.ProcessHost.exe")
        || !_wcsicmp(FileNameW, L"FAKEVIRTUALSURFACETESTAPP.EXE") )
      {
        result = 5;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"MSOOBE.EXE") )
      {
        result = 8;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"NETPLWIZ.EXE") )
      {
        result = 9;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"USERACCOUNTBROKER.EXE") )
      {
        result = 10;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"MSHTMPAD.EXE") )
      {
        result = 11;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"FirstLogonAnim.exe") )
      {
        result = 12;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"RESTOREOPTIN.EXE") )
      {
        result = 13;
        goto LABEL_55;
      }
      if ( StrStrIW(FileNameW, L"DCIScanner") )
      {
        result = 17;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"microsoftedge.exe") )
      {
        result = 15;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"microsoftedgecp.exe")
        || !_wcsicmp(FileNameW, L"microsoftedgebchost.exe")
        || !_wcsicmp(FileNameW, L"microsoftedgedevtools.exe") )
      {
        result = 16;
        goto LABEL_55;
      }
      if ( !StrCmpICW(FileNameW, L"microsoftedgesh.exe") )
      {
        result = 23;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"pickerhost.exe") )
      {
        result = 20;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"browser_broker.exe") )
      {
        result = 19;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"jshost.exe") )
      {
        result = 21;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"authhost.exe") )
      {
        result = 22;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"mshta.exe") )
      {
        result = 24;
        goto LABEL_55;
      }
      if ( !_wcsicmp(FileNameW, L"rundll32.exe") )
      {
        result = 25;
        goto LABEL_55;
      }
    }
    result = 0xFFFFFFFFLL;
    goto LABEL_55;
  }
  return result;
}

```

## disassembly

```asm
0x180190d0c  mov     [rsp+arg_0], rcx
0x180190d11  push    rbx
0x180190d12  sub     rsp, 240h
0x180190d19  mov     rax, cs:__security_cookie
0x180190d20  xor     rax, rsp
0x180190d23  mov     [rsp+248h+var_18], rax
0x180190d2b  mov     eax, cs:dword_180443918
0x180190d31  test    eax, eax
0x180190d33  jnz     loc_180191140
0x180190d39  mov     r8d, 104h; nSize
0x180190d3f  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180190d44  xor     ecx, ecx; hModule
0x180190d46  call    cs:__imp_GetModuleFileNameW
0x180190d4d  nop     dword ptr [rax+rax+00h]
0x180190d52  test    eax, eax
0x180190d54  jz      loc_180191137
0x180190d5a  lea     rcx, [rsp+248h+Filename]; pszPath
0x180190d5f  call    cs:__imp_PathFindFileNameW
0x180190d66  nop     dword ptr [rax+rax+00h]
0x180190d6b  mov     rcx, rax; String1
0x180190d6e  lea     rdx, aIexploreExe; "IEXPLORE.EXE"
0x180190d75  mov     rbx, rax
0x180190d78  call    cs:__imp__wcsicmp
0x180190d7f  nop     dword ptr [rax+rax+00h]
0x180190d84  test    eax, eax
0x180190d86  jnz     short loc_180190D92
0x180190d88  mov     eax, 1
0x180190d8d  jmp     loc_18019113A
0x180190d92  lea     rdx, aMsfeedssyncExe; "MSFEEDSSYNC.EXE"
0x180190d99  mov     rcx, rbx; String1
0x180190d9c  call    cs:__imp__wcsicmp
0x180190da3  nop     dword ptr [rax+rax+00h]
0x180190da8  test    eax, eax
0x180190daa  jnz     short loc_180190DB6
0x180190dac  mov     eax, 2
0x180190db1  jmp     loc_18019113A
0x180190db6  lea     rdx, aSysprepExe; "SYSPREP.EXE"
0x180190dbd  mov     rcx, rbx; String1
0x180190dc0  call    cs:__imp__wcsicmp
0x180190dc7  nop     dword ptr [rax+rax+00h]
0x180190dcc  test    eax, eax
0x180190dce  jnz     short loc_180190DDA
0x180190dd0  mov     eax, 3
0x180190dd5  jmp     loc_18019113A
0x180190dda  lea     rdx, aExplorerExe; "EXPLORER.EXE"
0x180190de1  mov     rcx, rbx; String1
0x180190de4  call    cs:__imp__wcsicmp
0x180190deb  nop     dword ptr [rax+rax+00h]
0x180190df0  test    eax, eax
0x180190df2  jnz     short loc_180190DFE
0x180190df4  mov     eax, 4
0x180190df9  jmp     loc_18019113A
0x180190dfe  lea     rdx, aLoader42Exe; "LOADER42.EXE"
0x180190e05  mov     rcx, rbx; String1
0x180190e08  call    cs:__imp__wcsicmp
0x180190e0f  nop     dword ptr [rax+rax+00h]
0x180190e14  test    eax, eax
0x180190e16  jnz     short loc_180190E22
0x180190e18  mov     eax, 6
0x180190e1d  jmp     loc_18019113A
0x180190e22  lea     rdx, aWwahostExe_0; "WWAHOST.EXE"
0x180190e29  mov     rcx, rbx; String1
0x180190e2c  call    cs:__imp__wcsicmp
0x180190e33  nop     dword ptr [rax+rax+00h]
0x180190e38  test    eax, eax
0x180190e3a  jnz     short loc_180190E46
0x180190e3c  mov     eax, 7
0x180190e41  jmp     loc_18019113A
0x180190e46  lea     rdx, aIeutlaunchExe; "IEUTLAUNCH.EXE"
0x180190e4d  mov     rcx, rbx; String1
0x180190e50  call    cs:__imp__wcsicmp
0x180190e57  nop     dword ptr [rax+rax+00h]
0x180190e5c  test    eax, eax
0x180190e5e  jz      loc_180191130
0x180190e64  lea     rdx, aTeExe; "TE.EXE"
0x180190e6b  mov     rcx, rbx; String1
0x180190e6e  call    cs:__imp__wcsicmp
0x180190e75  nop     dword ptr [rax+rax+00h]
0x180190e7a  test    eax, eax
0x180190e7c  jz      loc_180191130
0x180190e82  lea     rdx, aTeProcesshostE; "Te.ProcessHost.exe"
0x180190e89  mov     rcx, rbx; String1
0x180190e8c  call    cs:__imp__wcsicmp
0x180190e93  nop     dword ptr [rax+rax+00h]
0x180190e98  test    eax, eax
0x180190e9a  jz      loc_180191130
0x180190ea0  lea     rdx, aFakevirtualsur; "FAKEVIRTUALSURFACETESTAPP.EXE"
0x180190ea7  mov     rcx, rbx; String1
0x180190eaa  call    cs:__imp__wcsicmp
0x180190eb1  nop     dword ptr [rax+rax+00h]
0x180190eb6  test    eax, eax
0x180190eb8  jz      loc_180191130
0x180190ebe  lea     rdx, aMsoobeExe; "MSOOBE.EXE"
0x180190ec5  mov     rcx, rbx; String1
0x180190ec8  call    cs:__imp__wcsicmp
0x180190ecf  nop     dword ptr [rax+rax+00h]
0x180190ed4  test    eax, eax
0x180190ed6  jnz     short loc_180190EE2
0x180190ed8  mov     eax, 8
0x180190edd  jmp     loc_18019113A
0x180190ee2  lea     rdx, aNetplwizExe; "NETPLWIZ.EXE"
0x180190ee9  mov     rcx, rbx; String1
0x180190eec  call    cs:__imp__wcsicmp
0x180190ef3  nop     dword ptr [rax+rax+00h]
0x180190ef8  test    eax, eax
0x180190efa  jnz     short loc_180190F06
0x180190efc  mov     eax, 9
0x180190f01  jmp     loc_18019113A
0x180190f06  lea     rdx, aUseraccountbro; "USERACCOUNTBROKER.EXE"
0x180190f0d  mov     rcx, rbx; String1
0x180190f10  call    cs:__imp__wcsicmp
0x180190f17  nop     dword ptr [rax+rax+00h]
0x180190f1c  test    eax, eax
0x180190f1e  jnz     short loc_180190F2A
0x180190f20  mov     eax, 0Ah
0x180190f25  jmp     loc_18019113A
0x180190f2a  lea     rdx, aMshtmpadExe; "MSHTMPAD.EXE"
0x180190f31  mov     rcx, rbx; String1
0x180190f34  call    cs:__imp__wcsicmp
0x180190f3b  nop     dword ptr [rax+rax+00h]
0x180190f40  test    eax, eax
0x180190f42  jnz     short loc_180190F4E
0x180190f44  mov     eax, 0Bh
0x180190f49  jmp     loc_18019113A
0x180190f4e  lea     rdx, aFirstlogonanim; "FirstLogonAnim.exe"
0x180190f55  mov     rcx, rbx; String1
0x180190f58  call    cs:__imp__wcsicmp
0x180190f5f  nop     dword ptr [rax+rax+00h]
0x180190f64  test    eax, eax
0x180190f66  jnz     short loc_180190F72
0x180190f68  mov     eax, 0Ch
0x180190f6d  jmp     loc_18019113A
0x180190f72  lea     rdx, aRestoreoptinEx; "RESTOREOPTIN.EXE"
0x180190f79  mov     rcx, rbx; String1
0x180190f7c  call    cs:__imp__wcsicmp
0x180190f83  nop     dword ptr [rax+rax+00h]
0x180190f88  test    eax, eax
0x180190f8a  jnz     short loc_180190F96
0x180190f8c  mov     eax, 0Dh
0x180190f91  jmp     loc_18019113A
0x180190f96  lea     rdx, pszSrch; "DCIScanner"
0x180190f9d  mov     rcx, rbx; pszFirst
0x180190fa0  call    cs:__imp_StrStrIW
0x180190fa7  nop     dword ptr [rax+rax+00h]
0x180190fac  test    rax, rax
0x180190faf  jz      short loc_180190FBB
0x180190fb1  mov     eax, 11h
0x180190fb6  jmp     loc_18019113A
0x180190fbb  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x180190fc2  mov     rcx, rbx; String1
0x180190fc5  call    cs:__imp__wcsicmp
0x180190fcc  nop     dword ptr [rax+rax+00h]
0x180190fd1  test    eax, eax
0x180190fd3  jnz     short loc_180190FDF
0x180190fd5  mov     eax, 0Fh
0x180190fda  jmp     loc_18019113A
0x180190fdf  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x180190fe6  mov     rcx, rbx; String1
0x180190fe9  call    cs:__imp__wcsicmp
0x180190ff0  nop     dword ptr [rax+rax+00h]
0x180190ff5  test    eax, eax
0x180190ff7  jz      loc_180191129
0x180190ffd  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x180191004  mov     rcx, rbx; String1
0x180191007  call    cs:__imp__wcsicmp
0x18019100e  nop     dword ptr [rax+rax+00h]
0x180191013  test    eax, eax
0x180191015  jz      loc_180191129
0x18019101b  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x180191022  mov     rcx, rbx; String1
0x180191025  call    cs:__imp__wcsicmp
0x18019102c  nop     dword ptr [rax+rax+00h]
0x180191031  test    eax, eax
0x180191033  jz      loc_180191129
0x180191039  lea     rdx, pszStr2; "microsoftedgesh.exe"
0x180191040  mov     rcx, rbx; pszStr1
0x180191043  call    cs:__imp_StrCmpICW
0x18019104a  nop     dword ptr [rax+rax+00h]
0x18019104f  test    eax, eax
0x180191051  jnz     short loc_18019105D
0x180191053  mov     eax, 17h
0x180191058  jmp     loc_18019113A
0x18019105d  lea     rdx, aPickerhostExe; "pickerhost.exe"
0x180191064  mov     rcx, rbx; String1
0x180191067  call    cs:__imp__wcsicmp
0x18019106e  nop     dword ptr [rax+rax+00h]
0x180191073  test    eax, eax
0x180191075  jnz     short loc_180191081
0x180191077  mov     eax, 14h
0x18019107c  jmp     loc_18019113A
0x180191081  lea     rdx, aBrowserBrokerE; "browser_broker.exe"
0x180191088  mov     rcx, rbx; String1
0x18019108b  call    cs:__imp__wcsicmp
0x180191092  nop     dword ptr [rax+rax+00h]
0x180191097  test    eax, eax
0x180191099  jnz     short loc_1801910A5
0x18019109b  mov     eax, 13h
0x1801910a0  jmp     loc_18019113A
0x1801910a5  lea     rdx, aJshostExe_0; "jshost.exe"
0x1801910ac  mov     rcx, rbx; String1
0x1801910af  call    cs:__imp__wcsicmp
0x1801910b6  nop     dword ptr [rax+rax+00h]
0x1801910bb  test    eax, eax
0x1801910bd  jnz     short loc_1801910C6
0x1801910bf  mov     eax, 15h
0x1801910c4  jmp     short loc_18019113A
0x1801910c6  lea     rdx, aAuthhostExe; "authhost.exe"
0x1801910cd  mov     rcx, rbx; String1
0x1801910d0  call    cs:__imp__wcsicmp
0x1801910d7  nop     dword ptr [rax+rax+00h]
0x1801910dc  test    eax, eax
0x1801910de  jnz     short loc_1801910E7
0x1801910e0  mov     eax, 16h
0x1801910e5  jmp     short loc_18019113A
0x1801910e7  lea     rdx, aMshtaExe; "mshta.exe"
0x1801910ee  mov     rcx, rbx; String1
0x1801910f1  call    cs:__imp__wcsicmp
0x1801910f8  nop     dword ptr [rax+rax+00h]
0x1801910fd  test    eax, eax
0x1801910ff  jnz     short loc_180191108
0x180191101  mov     eax, 18h
0x180191106  jmp     short loc_18019113A
0x180191108  lea     rdx, aRundll32Exe; "rundll32.exe"
0x18019110f  mov     rcx, rbx; String1
0x180191112  call    cs:__imp__wcsicmp
0x180191119  nop     dword ptr [rax+rax+00h]
0x18019111e  test    eax, eax
0x180191120  jnz     short loc_180191137
0x180191122  mov     eax, 19h
0x180191127  jmp     short loc_18019113A
0x180191129  mov     eax, 10h
0x18019112e  jmp     short loc_18019113A
0x180191130  mov     eax, 5
0x180191135  jmp     short loc_18019113A
0x180191137  or      eax, 0FFFFFFFFh
0x18019113a  mov     cs:dword_180443918, eax
0x180191140  mov     rcx, [rsp+248h+var_18]
0x180191148  xor     rcx, rsp; StackCookie
0x18019114b  call    __security_check_cookie
0x180191150  add     rsp, 240h
0x180191157  pop     rbx
0x180191158  retn
```
