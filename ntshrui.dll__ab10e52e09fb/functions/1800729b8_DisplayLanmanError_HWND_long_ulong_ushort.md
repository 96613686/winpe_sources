# DisplayLanmanError(HWND__ *,long,ulong,ushort *)

- ea: `0x1800729b8`
- end: `0x180072adc`
- name: `?DisplayLanmanError@@YAXPEAUHWND__@@JKPEAG@Z`
- size: `292`
- prototype: `void __fastcall(HWND, int, DWORD dwMessageId, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800728f8`

## callees

- `0x1800254e0`
- `0x1800729b8`
- `0x180073280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072aac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180072a5d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180072a5d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800729fc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800729fc`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180072a26`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180072a8f`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180072a26`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180072a8f`

## string_xrefs

- `0x1800729f5`: `netmsg.dll`

## pseudocode

```c
void __fastcall DisplayLanmanError(HWND a1, int a2, DWORD dwMessageId, unsigned __int16 *a4)
{
  HMODULE LibraryW; // rdi
  __int64 nSize; // [rsp+28h] [rbp-440h]
  WCHAR Buffer[504]; // [rsp+40h] [rbp-428h] BYREF

  if ( dwMessageId - 2100 > 0xED7 )
  {
    MyErrorDialog(a1, -2147483385);
  }
  else
  {
    LibraryW = LoadLibraryW(L"netmsg.dll");
    if ( LibraryW )
    {
      if ( FormatMessageW(0xA00u, LibraryW, dwMessageId, 0x400u, Buffer, 0x1F4u, 0) )
      {
        MyErrorDialog(a1, a2, a4, Buffer);
      }
      else
      {
        LODWORD(nSize) = GetLastError();
        ShellMessageBoxW(g_hInstance, a1, (LPCWSTR)0x65, (LPCWSTR)0xC80, 0x10u, nSize);
      }
      FreeLibrary(LibraryW);
    }
    else
    {
      ShellMessageBoxW(g_hInstance, a1, (LPCWSTR)0x66, (LPCWSTR)0xC80, 0x10u);
    }
  }
}

```

## disassembly

```asm
0x1800729b8  push    rbx
0x1800729ba  push    rbp
0x1800729bb  push    rsi
0x1800729bc  push    rdi
0x1800729bd  push    r14
0x1800729bf  sub     rsp, 440h
0x1800729c6  mov     rax, cs:__security_cookie
0x1800729cd  xor     rax, rsp
0x1800729d0  mov     [rsp+468h+var_38], rax
0x1800729d8  lea     eax, [r8-834h]
0x1800729df  mov     r14, r9
0x1800729e2  mov     esi, r8d
0x1800729e5  mov     ebp, edx
0x1800729e7  mov     rbx, rcx
0x1800729ea  cmp     eax, 0ED7h
0x1800729ef  ja      loc_180072AB4
0x1800729f5  lea     rcx, aNetmsgDll; "netmsg.dll"
0x1800729fc  call    cs:__imp_LoadLibraryW
0x180072a02  mov     rdi, rax
0x180072a05  test    rax, rax
0x180072a08  jnz     short loc_180072A31
0x180072a0a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hAppInst
0x180072a11  lea     r8d, [rax+66h]; lpcText
0x180072a15  mov     r9d, 0C80h; lpcTitle
0x180072a1b  mov     [rsp+468h+fuStyle], 10h; fuStyle
0x180072a23  mov     rdx, rbx; hWnd
0x180072a26  call    cs:__imp_ShellMessageBoxW
0x180072a2c  jmp     loc_180072ABE
0x180072a31  mov     [rsp+468h+Arguments], 0; Arguments
0x180072a3a  lea     rax, [rsp+468h+Buffer]
0x180072a3f  mov     dword ptr [rsp+468h+nSize], 1F4h; nSize
0x180072a47  mov     r9d, 400h; dwLanguageId
0x180072a4d  mov     r8d, esi; dwMessageId
0x180072a50  mov     qword ptr [rsp+468h+fuStyle], rax; lpBuffer
0x180072a55  mov     rdx, rdi; lpSource
0x180072a58  mov     ecx, 0A00h; dwFlags
0x180072a5d  call    cs:__imp_FormatMessageW
0x180072a63  test    eax, eax
0x180072a65  jnz     short loc_180072A97
0x180072a67  call    cs:__imp_GetLastError
0x180072a6d  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hAppInst
0x180072a74  mov     r9d, 0C80h; lpcTitle
0x180072a7a  mov     dword ptr [rsp+468h+nSize], eax
0x180072a7e  mov     r8d, 65h ; 'e'; lpcText
0x180072a84  mov     rdx, rbx; hWnd
0x180072a87  mov     [rsp+468h+fuStyle], 10h; fuStyle
0x180072a8f  call    cs:__imp_ShellMessageBoxW
0x180072a95  jmp     short loc_180072AA9
0x180072a97  lea     r9, [rsp+468h+Buffer]
0x180072a9c  mov     r8, r14
0x180072a9f  mov     edx, ebp; int
0x180072aa1  mov     rcx, rbx; HWND
0x180072aa4  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180072aa9  mov     rcx, rdi; hLibModule
0x180072aac  call    cs:__imp_FreeLibrary
0x180072ab2  jmp     short loc_180072ABE
0x180072ab4  mov     edx, 80000107h; int
0x180072ab9  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180072abe  mov     rcx, [rsp+468h+var_38]
0x180072ac6  xor     rcx, rsp; StackCookie
0x180072ac9  call    __security_check_cookie
0x180072ace  add     rsp, 440h
0x180072ad5  pop     r14
0x180072ad7  pop     rdi
0x180072ad8  pop     rsi
0x180072ad9  pop     rbp
0x180072ada  pop     rbx
0x180072adb  retn
```
