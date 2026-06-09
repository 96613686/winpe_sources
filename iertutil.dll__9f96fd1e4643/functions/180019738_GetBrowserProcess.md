# GetBrowserProcess

- ea: `0x180019738`
- end: `0x180019b39`
- name: `GetBrowserProcess`
- size: `1025`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800173a0`
- `0x180017620`
- `0x180019b40`
- `0x1800245b0`
- `0x1800246e8`
- `0x1800248f8`
- `0x1800464ac`

## callees

- `0x180019738`
- `0x180048ce0`
- `0x180083c10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800197a9`
- `msvcrt!_wcsicmp` at `0x1800197c1`
- `msvcrt!_wcsicmp` at `0x1800197d9`
- `msvcrt!_wcsicmp` at `0x1800197f1`
- `msvcrt!_wcsicmp` at `0x180019809`
- `msvcrt!_wcsicmp` at `0x180019821`
- `msvcrt!_wcsicmp` at `0x180019839`
- `msvcrt!_wcsicmp` at `0x180019851`
- `msvcrt!_wcsicmp` at `0x180019869`
- `msvcrt!_wcsicmp` at `0x180019881`
- `msvcrt!_wcsicmp` at `0x180019899`
- `msvcrt!_wcsicmp` at `0x1800198b1`
- `msvcrt!_wcsicmp` at `0x1800198c9`
- `msvcrt!_wcsicmp` at `0x1800198e1`
- `msvcrt!_wcsicmp` at `0x1800198f9`
- `msvcrt!_wcsicmp` at `0x180019911`
- `msvcrt!_wcsicmp` at `0x18001994f`
- `msvcrt!_wcsicmp` at `0x180019967`
- `msvcrt!_wcsicmp` at `0x18001997f`
- `msvcrt!_wcsicmp` at `0x180019997`
- `msvcrt!_wcsicmp` at `0x1800199ee`
- `msvcrt!_wcsicmp` at `0x180019a02`
- `msvcrt!_wcsicmp` at `0x180019a1a`
- `msvcrt!_wcsicmp` at `0x180019a32`
- `msvcrt!_wcsicmp` at `0x180019a85`
- `msvcrt!_wcsicmp` at `0x180019af9`
- `msvcrt!_wcsicmp` at `0x1800197a9`
- `msvcrt!_wcsicmp` at `0x1800197c1`
- `msvcrt!_wcsicmp` at `0x1800197d9`
- `msvcrt!_wcsicmp` at `0x1800197f1`
- `msvcrt!_wcsicmp` at `0x180019809`
- `msvcrt!_wcsicmp` at `0x180019821`
- `msvcrt!_wcsicmp` at `0x180019839`
- `msvcrt!_wcsicmp` at `0x180019851`
- `msvcrt!_wcsicmp` at `0x180019869`
- `msvcrt!_wcsicmp` at `0x180019881`
- `msvcrt!_wcsicmp` at `0x180019899`
- `msvcrt!_wcsicmp` at `0x1800198b1`
- `msvcrt!_wcsicmp` at `0x1800198c9`
- `msvcrt!_wcsicmp` at `0x1800198e1`
- `msvcrt!_wcsicmp` at `0x1800198f9`
- `msvcrt!_wcsicmp` at `0x180019911`
- `msvcrt!_wcsicmp` at `0x18001994f`
- `msvcrt!_wcsicmp` at `0x180019967`
- `msvcrt!_wcsicmp` at `0x18001997f`
- `msvcrt!_wcsicmp` at `0x180019997`
- `msvcrt!_wcsicmp` at `0x1800199ee`
- `msvcrt!_wcsicmp` at `0x180019a02`
- `msvcrt!_wcsicmp` at `0x180019a1a`
- `msvcrt!_wcsicmp` at `0x180019a32`
- `msvcrt!_wcsicmp` at `0x180019a85`
- `msvcrt!_wcsicmp` at `0x180019af9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019783`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180019783`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800199d1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800199d1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180019796`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180019796`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800199af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800199af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180019936`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180019936`

## string_xrefs

- `0x1800198bf`: `USERACCOUNTBROKER.EXE`
- `0x1800199f8`: `browser_broker.exe`

## pseudocode

```c
__int64 GetBrowserProcess()
{
  __int64 result; // rax
  const wchar_t *FileNameW; // rbx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  result = (unsigned int)dword_180299FDC;
  if ( !dword_180299FDC )
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      goto LABEL_33;
    FileNameW = PathFindFileNameW(Filename);
    if ( !_wcsicmp(FileNameW, L"IEXPLORE.EXE") )
    {
      result = 1;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"MSFEEDSSYNC.EXE") )
    {
      result = 2;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"SYSPREP.EXE") )
    {
      result = 3;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"EXPLORER.EXE") )
    {
      result = 4;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"LOADER42.EXE") )
    {
      result = 6;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"WWAHOST.EXE") )
    {
      result = 7;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"IEUTLAUNCH.EXE")
      || !_wcsicmp(FileNameW, L"TE.EXE")
      || !_wcsicmp(FileNameW, L"Te.ProcessHost.exe")
      || !_wcsicmp(FileNameW, L"FAKEVIRTUALSURFACETESTAPP.EXE") )
    {
      result = 5;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"MSOOBE.EXE") )
    {
      result = 8;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"NETPLWIZ.EXE") )
    {
      result = 9;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"USERACCOUNTBROKER.EXE") )
    {
      result = 10;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"MSHTMPAD.EXE") )
    {
      result = 11;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"FirstLogonAnim.exe") )
    {
      result = 12;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"RESTOREOPTIN.EXE") )
    {
      result = 13;
      goto LABEL_32;
    }
    if ( IsOs_PhoneNT() && !_wcsicmp(FileNameW, L"EMAIL.EXE") )
    {
      result = 14;
      goto LABEL_32;
    }
    if ( StrStrIW(FileNameW, L"DCIScanner") )
    {
      result = 17;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"microsoftedge.exe") )
    {
      result = 15;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"microsoftedgecp.exe")
      || !_wcsicmp(FileNameW, L"microsoftedgebchost.exe")
      || !_wcsicmp(FileNameW, L"microsoftedgedevtools.exe") )
    {
      result = 16;
      goto LABEL_32;
    }
    if ( !StrCmpICW(FileNameW, L"microsoftedgesh.exe") )
    {
      result = 23;
      goto LABEL_32;
    }
    InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
    if ( byte_180298C9D && !_wcsicmp(FileNameW, L"browser.exe") )
    {
      result = 18;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"pickerhost.exe") )
    {
      result = 20;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"browser_broker.exe") )
    {
      result = 19;
      goto LABEL_32;
    }
    if ( !_wcsicmp(FileNameW, L"jshost.exe") )
    {
      result = 21;
      goto LABEL_32;
    }
    if ( _wcsicmp(FileNameW, L"authhost.exe") )
LABEL_33:
      result = 0xFFFFFFFFLL;
    else
      result = 22;
LABEL_32:
    dword_180299FDC = result;
  }
  return result;
}

```

## disassembly

```asm
0x180019738  push    rbx
0x18001973a  sub     rsp, 240h
0x180019741  mov     rax, cs:__security_cookie
0x180019748  xor     rax, rsp
0x18001974b  mov     [rsp+248h+var_18], rax
0x180019753  mov     eax, cs:dword_180299FDC
0x180019759  test    eax, eax
0x18001975b  jz      short loc_180019776
0x18001975d  mov     rcx, [rsp+248h+var_18]
0x180019765  xor     rcx, rsp; StackCookie
0x180019768  call    __security_check_cookie
0x18001976d  add     rsp, 240h
0x180019774  pop     rbx
0x180019775  retn
0x180019776  mov     r8d, 104h; nSize
0x18001977c  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180019781  xor     ecx, ecx; hModule
0x180019783  call    cs:__imp_GetModuleFileNameW
0x180019789  test    eax, eax
0x18001978b  jz      loc_180019A4C
0x180019791  lea     rcx, [rsp+248h+Filename]; pszPath
0x180019796  call    cs:__imp_PathFindFileNameW
0x18001979c  mov     rcx, rax; String1
0x18001979f  lea     rdx, aIexploreExe_0; "IEXPLORE.EXE"
0x1800197a6  mov     rbx, rax
0x1800197a9  call    cs:__imp__wcsicmp
0x1800197af  test    eax, eax
0x1800197b1  jz      loc_180019AA8
0x1800197b7  lea     rdx, aMsfeedssyncExe; "MSFEEDSSYNC.EXE"
0x1800197be  mov     rcx, rbx; String1
0x1800197c1  call    cs:__imp__wcsicmp
0x1800197c7  test    eax, eax
0x1800197c9  jz      loc_180019AAF
0x1800197cf  lea     rdx, aSysprepExe; "SYSPREP.EXE"
0x1800197d6  mov     rcx, rbx; String1
0x1800197d9  call    cs:__imp__wcsicmp
0x1800197df  test    eax, eax
0x1800197e1  jz      loc_180019AB6
0x1800197e7  lea     rdx, aExplorerExe_0; "EXPLORER.EXE"
0x1800197ee  mov     rcx, rbx; String1
0x1800197f1  call    cs:__imp__wcsicmp
0x1800197f7  test    eax, eax
0x1800197f9  jz      loc_180019A9A
0x1800197ff  lea     rdx, aLoader42Exe_0; "LOADER42.EXE"
0x180019806  mov     rcx, rbx; String1
0x180019809  call    cs:__imp__wcsicmp
0x18001980f  test    eax, eax
0x180019811  jz      loc_180019ABD
0x180019817  lea     rdx, aWwahostExe_0; "WWAHOST.EXE"
0x18001981e  mov     rcx, rbx; String1
0x180019821  call    cs:__imp__wcsicmp
0x180019827  test    eax, eax
0x180019829  jz      loc_180019AA1
0x18001982f  lea     rdx, aIeutlaunchExe_0; "IEUTLAUNCH.EXE"
0x180019836  mov     rcx, rbx; String1
0x180019839  call    cs:__imp__wcsicmp
0x18001983f  test    eax, eax
0x180019841  jz      loc_180019B2F
0x180019847  lea     rdx, aTeExe; "TE.EXE"
0x18001984e  mov     rcx, rbx; String1
0x180019851  call    cs:__imp__wcsicmp
0x180019857  test    eax, eax
0x180019859  jz      loc_180019B2F
0x18001985f  lea     rdx, aTeProcesshostE; "Te.ProcessHost.exe"
0x180019866  mov     rcx, rbx; String1
0x180019869  call    cs:__imp__wcsicmp
0x18001986f  test    eax, eax
0x180019871  jz      loc_180019B2F
0x180019877  lea     rdx, aFakevirtualsur; "FAKEVIRTUALSURFACETESTAPP.EXE"
0x18001987e  mov     rcx, rbx; String1
0x180019881  call    cs:__imp__wcsicmp
0x180019887  test    eax, eax
0x180019889  jz      loc_180019B2F
0x18001988f  lea     rdx, aMsoobeExe; "MSOOBE.EXE"
0x180019896  mov     rcx, rbx; String1
0x180019899  call    cs:__imp__wcsicmp
0x18001989f  test    eax, eax
0x1800198a1  jz      loc_180019AC7
0x1800198a7  lea     rdx, aNetplwizExe; "NETPLWIZ.EXE"
0x1800198ae  mov     rcx, rbx; String1
0x1800198b1  call    cs:__imp__wcsicmp
0x1800198b7  test    eax, eax
0x1800198b9  jz      loc_180019AD1
0x1800198bf  lea     rdx, aUseraccountbro; "USERACCOUNTBROKER.EXE"
0x1800198c6  mov     rcx, rbx; String1
0x1800198c9  call    cs:__imp__wcsicmp
0x1800198cf  test    eax, eax
0x1800198d1  jz      loc_180019ADB
0x1800198d7  lea     rdx, aMshtmpadExe_0; "MSHTMPAD.EXE"
0x1800198de  mov     rcx, rbx; String1
0x1800198e1  call    cs:__imp__wcsicmp
0x1800198e7  test    eax, eax
0x1800198e9  jz      loc_180019A74
0x1800198ef  lea     rdx, aFirstlogonanim; "FirstLogonAnim.exe"
0x1800198f6  mov     rcx, rbx; String1
0x1800198f9  call    cs:__imp__wcsicmp
0x1800198ff  test    eax, eax
0x180019901  jz      loc_180019AE5
0x180019907  lea     rdx, aRestoreoptinEx; "RESTOREOPTIN.EXE"
0x18001990e  mov     rcx, rbx; String1
0x180019911  call    cs:__imp__wcsicmp
0x180019917  test    eax, eax
0x180019919  jz      loc_180019A58
0x18001991f  call    ?IsOs_PhoneNT@@YA_NXZ; IsOs_PhoneNT(void)
0x180019924  test    al, al
0x180019926  jnz     loc_180019AEF
0x18001992c  lea     rdx, pszSrch; "DCIScanner"
0x180019933  mov     rcx, rbx; pszFirst
0x180019936  call    cs:__imp_StrStrIW
0x18001993c  test    rax, rax
0x18001993f  jnz     loc_180019A51
0x180019945  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x18001994c  mov     rcx, rbx; String1
0x18001994f  call    cs:__imp__wcsicmp
0x180019955  test    eax, eax
0x180019957  jz      loc_180019B11
0x18001995d  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x180019964  mov     rcx, rbx; String1
0x180019967  call    cs:__imp__wcsicmp
0x18001996d  test    eax, eax
0x18001996f  jz      loc_180019A6D
0x180019975  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x18001997c  mov     rcx, rbx; String1
0x18001997f  call    cs:__imp__wcsicmp
0x180019985  test    eax, eax
0x180019987  jz      loc_180019A6D
0x18001998d  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x180019994  mov     rcx, rbx; String1
0x180019997  call    cs:__imp__wcsicmp
0x18001999d  test    eax, eax
0x18001999f  jz      loc_180019A6D
0x1800199a5  lea     rdx, aMicrosoftedges; "microsoftedgesh.exe"
0x1800199ac  mov     rcx, rbx; pszStr1
0x1800199af  call    cs:__imp_StrCmpICW
0x1800199b5  test    eax, eax
0x1800199b7  jz      loc_180019A5F
0x1800199bd  xor     r9d, r9d; Context
0x1800199c0  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800199c7  xor     r8d, r8d; Parameter
0x1800199ca  lea     rcx, stru_180299FB8; InitOnce
0x1800199d1  call    cs:__imp_InitOnceExecuteOnce
0x1800199d7  cmp     cs:byte_180298C9D, 0
0x1800199de  jnz     loc_180019A7B
0x1800199e4  lea     rdx, aPickerhostExe; "pickerhost.exe"
0x1800199eb  mov     rcx, rbx; String1
0x1800199ee  call    cs:__imp__wcsicmp
0x1800199f4  test    eax, eax
0x1800199f6  jz      short loc_180019A66
0x1800199f8  lea     rdx, aBrowserBrokerE; "browser_broker.exe"
0x1800199ff  mov     rcx, rbx; String1
0x180019a02  call    cs:__imp__wcsicmp
0x180019a08  test    eax, eax
0x180019a0a  jz      loc_180019B1B
0x180019a10  lea     rdx, aJshostExe; "jshost.exe"
0x180019a17  mov     rcx, rbx; String1
0x180019a1a  call    cs:__imp__wcsicmp
0x180019a20  test    eax, eax
0x180019a22  jz      loc_180019B25
0x180019a28  lea     rdx, aAuthhostExe; "authhost.exe"
0x180019a2f  mov     rcx, rbx; String1
0x180019a32  call    cs:__imp__wcsicmp
0x180019a38  test    eax, eax
0x180019a3a  jnz     short loc_180019A4C
0x180019a3c  mov     eax, 16h
0x180019a41  mov     cs:dword_180299FDC, eax
0x180019a47  jmp     loc_18001975D
0x180019a4c  or      eax, 0FFFFFFFFh
0x180019a4f  jmp     short loc_180019A41
0x180019a51  mov     eax, 11h
0x180019a56  jmp     short loc_180019A41
0x180019a58  mov     eax, 0Dh
0x180019a5d  jmp     short loc_180019A41
0x180019a5f  mov     eax, 17h
0x180019a64  jmp     short loc_180019A41
0x180019a66  mov     eax, 14h
0x180019a6b  jmp     short loc_180019A41
0x180019a6d  mov     eax, 10h
0x180019a72  jmp     short loc_180019A41
0x180019a74  mov     eax, 0Bh
0x180019a79  jmp     short loc_180019A41
0x180019a7b  lea     rdx, aBrowserExe; "browser.exe"
0x180019a82  mov     rcx, rbx; String1
0x180019a85  call    cs:__imp__wcsicmp
0x180019a8b  test    eax, eax
0x180019a8d  jnz     loc_1800199E4
0x180019a93  mov     eax, 12h
0x180019a98  jmp     short loc_180019A41
0x180019a9a  mov     eax, 4
0x180019a9f  jmp     short loc_180019A41
0x180019aa1  mov     eax, 7
0x180019aa6  jmp     short loc_180019A41
0x180019aa8  mov     eax, 1
0x180019aad  jmp     short loc_180019A41
0x180019aaf  mov     eax, 2
0x180019ab4  jmp     short loc_180019A41
0x180019ab6  mov     eax, 3
0x180019abb  jmp     short loc_180019A41
0x180019abd  mov     eax, 6
0x180019ac2  jmp     loc_180019A41
0x180019ac7  mov     eax, 8
0x180019acc  jmp     loc_180019A41
0x180019ad1  mov     eax, 9
0x180019ad6  jmp     loc_180019A41
0x180019adb  mov     eax, 0Ah
0x180019ae0  jmp     loc_180019A41
0x180019ae5  mov     eax, 0Ch
0x180019aea  jmp     loc_180019A41
0x180019aef  lea     rdx, aEmailExe; "EMAIL.EXE"
0x180019af6  mov     rcx, rbx; String1
0x180019af9  call    cs:__imp__wcsicmp
0x180019aff  test    eax, eax
0x180019b01  jnz     loc_18001992C
0x180019b07  mov     eax, 0Eh
0x180019b0c  jmp     loc_180019A41
0x180019b11  mov     eax, 0Fh
0x180019b16  jmp     loc_180019A41
0x180019b1b  mov     eax, 13h
0x180019b20  jmp     loc_180019A41
0x180019b25  mov     eax, 15h
0x180019b2a  jmp     loc_180019A41
0x180019b2f  mov     eax, 5
0x180019b34  jmp     loc_180019A41
```
