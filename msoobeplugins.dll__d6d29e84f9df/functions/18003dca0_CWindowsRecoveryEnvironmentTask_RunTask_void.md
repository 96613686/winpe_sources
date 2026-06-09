# CWindowsRecoveryEnvironmentTask::RunTask(void)

- ea: `0x18003dca0`
- end: `0x18003dd8b`
- name: `?RunTask@CWindowsRecoveryEnvironmentTask@@UEAAJXZ`
- size: `235`
- prototype: `__int64 __fastcall(CWindowsRecoveryEnvironmentTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ac48`
- `0x180026b68`
- `0x18003dca0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003dcdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003dcdc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003dd43`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003dd43`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003dcc4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003dcc4`

## string_xrefs

- `0x18003dcbd`: `ReAgent.dll`
- `0x18003dcaf`: `Installing Windows Recovery Environment`
- `0x18003dcf4`: `Successfully installed Windows Recovery Environment`
- `0x18003dcd2`: `WinReOobeInstall`
- `0x18003dd68`: `ReAgent.dll not present.  Windows Recovery Environment will not be installed.  Note: This is expected on Server Core SKUs.`
- `0x18003dd0c`: `WinReOobeInstall call failed [hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWindowsRecoveryEnvironmentTask::RunTask(CWindowsRecoveryEnvironmentTask *this)
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rdi
  unsigned int (*ProcAddress)(void); // rax
  unsigned int v4; // ebx
  __int64 Error; // rsi
  __int64 v6; // rcx
  unsigned int v7; // eax

  UnattendLogW(0, L"Installing Windows Recovery Environment");
  LibraryW = LoadLibraryW(L"ReAgent.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = (unsigned int (*)(void))GetProcAddress(LibraryW, "WinReOobeInstall");
    if ( ProcAddress )
    {
      v4 = 0;
      if ( ProcAddress() )
      {
        LODWORD(Error) = 0;
        UnattendLogW(0, L"Successfully installed Windows Recovery Environment");
      }
      else
      {
        Error = (unsigned int)ResultFromKnownLastError();
        UnattendLogW(2, L"WinReOobeInstall call failed [hr=0x%08X]", Error);
      }
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v6, WinREInstall_Info, (unsigned int)Error);
    }
    else
    {
      v4 = ResultFromKnownLastError();
    }
    FreeLibrary(v2);
  }
  else
  {
    v4 = ResultFromKnownLastError();
    v7 = (unsigned __int16)v4;
    if ( (v4 & 0x1FFF0000) != 0x70000 )
      v7 = v4;
    if ( v7 == 126 )
    {
      UnattendLogW(
        2,
        L"ReAgent.dll not present.  Windows Recovery Environment will not be installed.  Note: This is expected on Server Core SKUs.");
      return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003dca0  mov     [rsp+arg_0], rbx
0x18003dca5  mov     [rsp+arg_8], rsi
0x18003dcaa  push    rdi
0x18003dcab  sub     rsp, 20h
0x18003dcaf  lea     rdx, aInstallingWind; "Installing Windows Recovery Environment"
0x18003dcb6  xor     ecx, ecx
0x18003dcb8  call    UnattendLogW
0x18003dcbd  lea     rcx, aReagentDll; "ReAgent.dll"
0x18003dcc4  call    cs:__imp_LoadLibraryW
0x18003dcca  mov     rdi, rax
0x18003dccd  test    rax, rax
0x18003dcd0  jz      short loc_18003DD4B
0x18003dcd2  lea     rdx, aWinreoobeinsta_0; "WinReOobeInstall"
0x18003dcd9  mov     rcx, rax; hModule
0x18003dcdc  call    cs:__imp_GetProcAddress
0x18003dce2  test    rax, rax
0x18003dce5  jz      short loc_18003DD39
0x18003dce7  xor     ebx, ebx
0x18003dce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcee  test    eax, eax
0x18003dcf0  jz      short loc_18003DD04
0x18003dcf2  xor     esi, esi
0x18003dcf4  lea     rdx, aSuccessfullyIn; "Successfully installed Windows Recovery"...
0x18003dcfb  xor     ecx, ecx
0x18003dcfd  call    UnattendLogW
0x18003dd02  jmp     short loc_18003DD1F
0x18003dd04  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003dd09  mov     r8d, eax
0x18003dd0c  lea     rdx, aWinreoobeinsta; "WinReOobeInstall call failed [hr=0x%08X"...
0x18003dd13  mov     ecx, 2
0x18003dd18  mov     esi, eax
0x18003dd1a  call    UnattendLogW
0x18003dd1f  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x18003dd26  jz      short loc_18003DD40
0x18003dd28  mov     r8d, esi
0x18003dd2b  lea     rdx, WinREInstall_Info
0x18003dd32  call    McTemplateU0q_EventWriteTransfer
0x18003dd37  jmp     short loc_18003DD40
0x18003dd39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003dd3e  mov     ebx, eax
0x18003dd40  mov     rcx, rdi; hLibModule
0x18003dd43  call    cs:__imp_FreeLibrary
0x18003dd49  jmp     short loc_18003DD79
0x18003dd4b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003dd50  mov     ebx, eax
0x18003dd52  and     eax, 1FFF0000h
0x18003dd57  cmp     eax, 70000h
0x18003dd5c  movzx   eax, bx
0x18003dd5f  jz      short loc_18003DD63
0x18003dd61  mov     eax, ebx
0x18003dd63  cmp     eax, 7Eh ; '~'
0x18003dd66  jnz     short loc_18003DD79
0x18003dd68  lea     rdx, aReagentDllNotP; "ReAgent.dll not present.  Windows Recov"...
0x18003dd6f  lea     ecx, [rax-7Ch]
0x18003dd72  call    UnattendLogW
0x18003dd77  xor     ebx, ebx
0x18003dd79  mov     rsi, [rsp+28h+arg_8]
0x18003dd7e  mov     eax, ebx
0x18003dd80  mov     rbx, [rsp+28h+arg_0]
0x18003dd85  add     rsp, 20h
0x18003dd89  pop     rdi
0x18003dd8a  retn
```
