# Uninstall(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180011f90`
- end: `0x180012120`
- name: `?Uninstall@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `400`
- prototype: `void __fastcall(HWND hwnd, HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180002620`
- `0x180008c94`
- `0x180011f90`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x1800120f6`
- `SHELL32!ShellExecuteW` at `0x1800120f6`
- `SHLWAPI!PathAppendW` at `0x180012064`
- `SHLWAPI!PathAppendW` at `0x1800120cc`
- `SHLWAPI!PathAppendW` at `0x180012064`
- `SHLWAPI!PathAppendW` at `0x1800120cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001208f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001208f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001209d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001209d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011ff7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012013`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011ff7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180012013`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012046`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800120af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180012046`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800120af`
- `KERNEL32!lstrlenW` at `0x180011fcd`
- `KERNEL32!lstrlenW` at `0x180011fcd`
- `USER32!MessageBoxW` at `0x18001202e`
- `USER32!MessageBoxW` at `0x18001202e`

## string_xrefs

- `0x180012059`: `setupapi.dll`
- `0x180012073`: `%s,InstallHinfSection DefaultUninstall 132 %s`
- `0x1800120be`: `rundll32.exe`

## pseudocode

```c
void __fastcall Uninstall(HWND hwnd, HINSTANCE a2, const unsigned __int16 *a3)
{
  HANDLE CurrentThread; // rax
  WCHAR Caption[104]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR File[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR Buffer[360]; // [rsp+520h] [rbp+420h] BYREF

  if ( a3 )
  {
    if ( lstrlenW(a3) < 260 )
    {
      LoadStringW(g_hinst, 0xEu, Buffer, 360);
      LoadStringW(g_hinst, 0xFu, Caption, 100);
      if ( MessageBoxW(hwnd, Buffer, Caption, 0x14u) == 6 && GetSystemDirectoryW(pszPath, 0x104u) - 1 <= 0x102 )
      {
        PathAppendW(pszPath, L"setupapi.dll");
        if ( StringCchPrintfW(Buffer, 0x168u, L"%s,InstallHinfSection DefaultUninstall 132 %s", pszPath, a3) >= 0 )
        {
          CurrentThread = GetCurrentThread();
          SetThreadPriority(CurrentThread, 1);
          if ( GetSystemDirectoryW(File, 0x104u) - 1 <= 0x102 )
          {
            PathAppendW(File, L"rundll32.exe");
            ShellExecuteW(hwnd, 0, File, Buffer, 0, 2);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180011f90  test    r8, r8
0x180011f93  jz      locret_18001211F
0x180011f99  mov     [rsp-8+arg_8], rbx
0x180011f9e  mov     [rsp-8+arg_18], rdi
0x180011fa3  push    rbp
0x180011fa4  lea     rbp, [rsp-700h]
0x180011fac  sub     rsp, 800h
0x180011fb3  mov     rax, cs:__security_cookie
0x180011fba  xor     rax, rsp
0x180011fbd  mov     [rbp+700h+var_10], rax
0x180011fc4  mov     rbx, r8
0x180011fc7  mov     rdi, rcx
0x180011fca  mov     rcx, rbx; lpString
0x180011fcd  call    cs:__imp_lstrlenW
0x180011fd3  cmp     eax, 104h
0x180011fd8  jge     loc_1800120FC
0x180011fde  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180011fe5  lea     r8, [rbp+700h+Buffer]; lpBuffer
0x180011fec  mov     r9d, 168h; cchBufferMax
0x180011ff2  mov     edx, 0Eh; uID
0x180011ff7  call    cs:__imp_LoadStringW
0x180011ffd  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180012004  lea     r8, [rsp+800h+Caption]; lpBuffer
0x180012009  mov     r9d, 64h ; 'd'; cchBufferMax
0x18001200f  lea     edx, [r9-55h]; uID
0x180012013  call    cs:__imp_LoadStringW
0x180012019  mov     r9d, 14h; uType
0x18001201f  lea     r8, [rsp+800h+Caption]; lpCaption
0x180012024  lea     rdx, [rbp+700h+Buffer]; lpText
0x18001202b  mov     rcx, rdi; hWnd
0x18001202e  call    cs:__imp_MessageBoxW
0x180012034  cmp     eax, 6
0x180012037  jnz     loc_1800120FC
0x18001203d  mov     edx, 104h; uSize
0x180012042  lea     rcx, [rbp+700h+pszPath]; lpBuffer
0x180012046  call    cs:__imp_GetSystemDirectoryW
0x18001204c  dec     eax
0x18001204e  cmp     eax, 102h
0x180012053  ja      loc_1800120FC
0x180012059  lea     rdx, pszMore; "setupapi.dll"
0x180012060  lea     rcx, [rbp+700h+pszPath]; pszPath
0x180012064  call    cs:__imp_PathAppendW
0x18001206a  lea     r9, [rbp+700h+pszPath]
0x18001206e  mov     [rsp+800h+lpDirectory], rbx
0x180012073  lea     r8, aSInstallhinfse; "%s,InstallHinfSection DefaultUninstall "...
0x18001207a  mov     edx, 168h; unsigned __int64
0x18001207f  lea     rcx, [rbp+700h+Buffer]; unsigned __int16 *
0x180012086  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001208b  test    eax, eax
0x18001208d  js      short loc_1800120FC
0x18001208f  call    cs:__imp_GetCurrentThread
0x180012095  mov     rcx, rax; hThread
0x180012098  mov     edx, 1; nPriority
0x18001209d  call    cs:__imp_SetThreadPriority
0x1800120a3  mov     edx, 104h; uSize
0x1800120a8  lea     rcx, [rbp+700h+File]; lpBuffer
0x1800120af  call    cs:__imp_GetSystemDirectoryW
0x1800120b5  dec     eax
0x1800120b7  cmp     eax, 102h
0x1800120bc  ja      short loc_1800120FC
0x1800120be  lea     rdx, aRundll32Exe; "rundll32.exe"
0x1800120c5  lea     rcx, [rbp+700h+File]; pszPath
0x1800120cc  call    cs:__imp_PathAppendW
0x1800120d2  lea     r9, [rbp+700h+Buffer]; lpParameters
0x1800120d9  mov     [rsp+800h+nShowCmd], 2; nShowCmd
0x1800120e1  lea     r8, [rbp+700h+File]; lpFile
0x1800120e8  mov     [rsp+800h+lpDirectory], 0; lpDirectory
0x1800120f1  xor     edx, edx; lpOperation
0x1800120f3  mov     rcx, rdi; hwnd
0x1800120f6  call    cs:__imp_ShellExecuteW
0x1800120fc  mov     rcx, [rbp+700h+var_10]
0x180012103  xor     rcx, rsp; StackCookie
0x180012106  call    __security_check_cookie
0x18001210b  lea     r11, [rsp+800h+var_s0]
0x180012113  mov     rbx, [r11+18h]
0x180012117  mov     rdi, [r11+28h]
0x18001211b  mov     rsp, r11
0x18001211e  pop     rbp
0x18001211f  retn
```
