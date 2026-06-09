# Resources::SafeFormatMessage(ushort const *,ulong,ushort *,ulong,bool)

- ea: `0x1007a9da`
- end: `0x1007ab14`
- name: `?SafeFormatMessage@Resources@@KGKPBGKPAGK_N@Z`
- size: `314`
- prototype: `unsigned int __userpurge@<eax>(const wchar_t *pszModule@<ecx>, unsigned int errorid@<edx>, wchar_t *buffer, unsigned int fCheckBeforeLoad, bool pszModule@<cl>)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1003f701`

## callees

- `0x1005536b`
- `0x1007a9da`
- `0x1007ab1a`
- `0x10170b30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1007aaf6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1007aaf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1007aa86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1007aa86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1007aa9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1007aa9f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1007aad4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1007aad4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1007aa1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1007aa1d`

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
0x1007a9da  push    224h
0x1007a9df  push    offset stru_101743C8
0x1007a9e4  call    __SEH_prolog4_GS
0x1007a9e9  mov     edi, errorid
0x1007a9eb  mov     esi, pszModule
0x1007a9ed  mov     ebx, [ebp+buffer]
0x1007a9f0  xor     eax, eax
0x1007a9f2  mov     [ebp+rc], eax
0x1007a9f8  mov     [ebp+h], eax
0x1007a9fe  mov     [ebp+pszDestEnd], eax
0x1007aa04  mov     [ebp+cchRemaining], eax
0x1007aa0a  mov     [ebp+szModuleFullPath], ax
0x1007aa11  push    104h; uSize
0x1007aa16  lea     eax, [ebp+szModuleFullPath]
0x1007aa1c  push    eax; lpBuffer
0x1007aa1d  call    ds:__imp__GetSystemDirectoryW@8; GetSystemDirectoryW(x,x)
0x1007aa23  test    eax, eax
0x1007aa25  jz      exit
0x1007aa2b  mov     errorid, 104h; cchDest
0x1007aa30  cmp     eax, errorid
0x1007aa32  jnb     exit
0x1007aa38  push    pszModule
0x1007aa39  lea     eax, [ebp+cchRemaining]
0x1007aa3f  push    eax; pcchRemaining
0x1007aa40  lea     eax, [ebp+pszDestEnd]
0x1007aa46  push    eax; ppszDestEnd
0x1007aa47  push    offset asc_1001E7CC; "\\"
0x1007aa4c  lea     pszModule, [ebp+szModuleFullPath]; pszDest
0x1007aa52  call    ?StringCchCatExW@@YGJPAGIPBGPAPAGPAIK@Z; StringCchCatExW(ushort *,uint,ushort const *,ushort * *,uint *,ulong)
0x1007aa57  test    eax, eax
0x1007aa59  js      exit
0x1007aa5f  push    esi; pszSrc
0x1007aa60  mov     errorid, [ebp+cchRemaining]; cchDest
0x1007aa66  mov     pszModule, [ebp+pszDestEnd]; pszDest
0x1007aa6c  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x1007aa71  test    eax, eax
0x1007aa73  js      exit
0x1007aa79  lea     eax, [ebp+szModuleFullPath]
0x1007aa7f  cmp     [ebp+fCheckBeforeLoad], 0
0x1007aa83  jz      short loc_1007AA9A
0x1007aa85  push    eax; lpModuleName
0x1007aa86  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1007aa8c  test    eax, eax
0x1007aa8e  jz      short loc_1007AAAB
0x1007aa90  push    0
0x1007aa92  lea     eax, [ebp+szModuleFullPath]
0x1007aa98  jmp     short loc_1007AA9C
0x1007aa9a  push    2; dwFlags
0x1007aa9c  push    0; hFile
0x1007aa9e  push    eax; lpLibFileName
0x1007aa9f  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1007aaa5  mov     [ebp+h], eax
0x1007aaab  cmp     [ebp+h], 0
0x1007aab2  jz      short exit
0x1007aab4  mov     [ebp+ms_exc.registration.TryLevel], 0
0x1007aabb  push    0; Arguments
0x1007aabd  push    1000h; nSize
0x1007aac2  push    ebx; lpBuffer
0x1007aac3  push    400h; dwLanguageId
0x1007aac8  push    edi; dwMessageId
0x1007aac9  push    [ebp+h]; lpSource
0x1007aacf  push    800h; dwFlags
0x1007aad4  call    ds:__imp__FormatMessageW@28; FormatMessageW(x,x,x,x,x,x,x)
0x1007aada  mov     [ebp+rc], eax
0x1007aae0  jmp     short loc_1007AAE9
0x1007aae2  xor     eax, eax
0x1007aae4  inc     eax
0x1007aae5  retn
0x1007aae6  mov     esp, [ebp+ms_exc.old_esp]
0x1007aae9  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x1007aaf0  push    [ebp+h]; hLibModule
0x1007aaf6  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1007aafc  mov     eax, [ebp+rc]
0x1007ab02  mov     pszModule, [ebp+ms_exc.registration.Next]
0x1007ab05  mov     large fs:0, pszModule
0x1007ab0c  pop     pszModule
0x1007ab0d  pop     edi
0x1007ab0e  pop     esi
0x1007ab0f  pop     ebx
0x1007ab10  leave
0x1007ab11  retn    0Ch
```
