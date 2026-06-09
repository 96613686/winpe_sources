# Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)

- ea: `0x1007aa1a`
- end: `0x1007ab54`
- name: `?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z`
- size: `314`
- prototype: `unsigned int __userpurge@<eax>(const wchar_t *pszModule@<ecx>, unsigned int errorid@<edx>, wchar_t *buffer, unsigned int fCheckBeforeLoad, bool pszModule@<cl>)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1003f671`

## callees

- `0x100552db`
- `0x1007aa1a`
- `0x1007ab5a`
- `0x10170c20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1007ab36`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1007ab36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1007aac6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1007aac6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1007aadf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1007aadf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1007ab14`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1007ab14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1007aa5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1007aa5d`

## pseudocode

```c
DWORD __userpurge Resources::SafeFormatMessage@<eax>(
        DWORD a1@<edx>,
        const wchar_t *a2@<ecx>,
        wchar_t *buffer,
        unsigned int a4,
        unsigned __int16 *fCheckBeforeLoad,
        unsigned int a6,
        bool a7)
{
  UINT SystemDirectoryW; // eax
  unsigned __int16 **v10; // ecx
  HINSTANCE__ *Library; // eax
  unsigned int *v13; // [esp+0h] [ebp-244h]
  unsigned int v14; // [esp+4h] [ebp-240h]
  DWORD rc; // [esp+10h] [ebp-234h]
  wchar_t *pszDestEnd; // [esp+14h] [ebp-230h] BYREF
  unsigned int cchRemaining; // [esp+18h] [ebp-22Ch] BYREF
  HINSTANCE__ *h; // [esp+1Ch] [ebp-228h]
  wchar_t szModuleFullPath[262]; // [esp+20h] [ebp-224h] BYREF
  CPPEH_RECORD ms_exc; // [esp+22Ch] [ebp-18h]

  rc = 0;
  h = 0;
  pszDestEnd = 0;
  cchRemaining = 0;
  szModuleFullPath[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(szModuleFullPath, 0x104u);
  if ( !SystemDirectoryW
    || SystemDirectoryW >= 0x104
    || (int)StringCchCatExW(L"\\", &pszDestEnd, (const unsigned __int16 *)&cchRemaining, v10, v13, v14) < 0
    || StringCchCopyW(pszDestEnd, cchRemaining, a2) < 0 )
  {
    return rc;
  }
  if ( (_BYTE)fCheckBeforeLoad )
  {
    if ( !GetModuleHandleW(szModuleFullPath) )
      goto LABEL_10;
    Library = LoadLibraryExW(szModuleFullPath, 0, 0);
  }
  else
  {
    Library = LoadLibraryExW(szModuleFullPath, 0, 2u);
  }
  h = Library;
LABEL_10:
  if ( h )
  {
    ms_exc.registration.TryLevel = 0;
    rc = FormatMessageW(0x800u, h, a1, 0x400u, buffer, 0x1000u, 0);
    ms_exc.registration.TryLevel = -2;
    FreeLibrary(h);
  }
  return rc;
}

```

## disassembly

```asm
0x1007aa1a  push    224h
0x1007aa1f  push    offset stru_101744B8
0x1007aa24  call    __SEH_prolog4_GS
0x1007aa29  mov     edi, errorid
0x1007aa2b  mov     esi, pszModule
0x1007aa2d  mov     ebx, [ebp+buffer]
0x1007aa30  xor     eax, eax
0x1007aa32  mov     [ebp+rc], eax
0x1007aa38  mov     [ebp+h], eax
0x1007aa3e  mov     [ebp+pszDestEnd], eax
0x1007aa44  mov     [ebp+cchRemaining], eax
0x1007aa4a  mov     [ebp+szModuleFullPath], ax
0x1007aa51  push    104h; uSize
0x1007aa56  lea     eax, [ebp+szModuleFullPath]
0x1007aa5c  push    eax; lpBuffer
0x1007aa5d  call    ds:__imp__GetSystemDirectoryW@8; GetSystemDirectoryW(x,x)
0x1007aa63  test    eax, eax
0x1007aa65  jz      exit
0x1007aa6b  mov     errorid, 104h; cchDest
0x1007aa70  cmp     eax, errorid
0x1007aa72  jnb     exit
0x1007aa78  push    pszModule
0x1007aa79  lea     eax, [ebp+cchRemaining]
0x1007aa7f  push    eax; pcchRemaining
0x1007aa80  lea     eax, [ebp+pszDestEnd]
0x1007aa86  push    eax; ppszDestEnd
0x1007aa87  push    offset asc_1001E7CC; "\\"
0x1007aa8c  lea     pszModule, [ebp+szModuleFullPath]; pszDest
0x1007aa92  call    ?StringCchCatExW@@YGJPAGIPBGPAPAGPAIK@Z; StringCchCatExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)
0x1007aa97  test    eax, eax
0x1007aa99  js      exit
0x1007aa9f  push    esi; pszSrc
0x1007aaa0  mov     errorid, [ebp+cchRemaining]; cchDest
0x1007aaa6  mov     pszModule, [ebp+pszDestEnd]; pszDest
0x1007aaac  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x1007aab1  test    eax, eax
0x1007aab3  js      exit
0x1007aab9  lea     eax, [ebp+szModuleFullPath]
0x1007aabf  cmp     [ebp+fCheckBeforeLoad], 0
0x1007aac3  jz      short loc_1007AADA
0x1007aac5  push    eax; lpModuleName
0x1007aac6  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1007aacc  test    eax, eax
0x1007aace  jz      short loc_1007AAEB
0x1007aad0  push    0
0x1007aad2  lea     eax, [ebp+szModuleFullPath]
0x1007aad8  jmp     short loc_1007AADC
0x1007aada  push    2; dwFlags
0x1007aadc  push    0; hFile
0x1007aade  push    eax; lpLibFileName
0x1007aadf  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1007aae5  mov     [ebp+h], eax
0x1007aaeb  cmp     [ebp+h], 0
0x1007aaf2  jz      short exit
0x1007aaf4  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1007aafb  push    0; Arguments
0x1007aafd  push    1000h; nSize
0x1007ab02  push    ebx; lpBuffer
0x1007ab03  push    400h; dwLanguageId
0x1007ab08  push    edi; dwMessageId
0x1007ab09  push    [ebp+h]; lpSource
0x1007ab0f  push    800h; dwFlags
0x1007ab14  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1007ab1a  mov     [ebp+rc], eax
0x1007ab20  jmp     short loc_1007AB29
0x1007ab22  xor     eax, eax
0x1007ab24  inc     eax
0x1007ab25  retn
0x1007ab26  mov     esp, [ebp+ms_exc.old_esp]
0x1007ab29  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007ab30  push    [ebp+h]; hLibModule
0x1007ab36  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1007ab3c  mov     eax, [ebp+rc]
0x1007ab42  mov     pszModule, [ebp+ms_exc.registration.Next]
0x1007ab45  mov     large fs:0, pszModule
0x1007ab4c  pop     pszModule
0x1007ab4d  pop     edi
0x1007ab4e  pop     esi
0x1007ab4f  pop     ebx
0x1007ab50  leave
0x1007ab51  retn    0Ch
```
