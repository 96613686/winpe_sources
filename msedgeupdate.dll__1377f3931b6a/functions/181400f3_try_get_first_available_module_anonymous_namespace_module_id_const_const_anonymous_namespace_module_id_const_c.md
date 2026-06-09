# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x181400f3`
- end: `0x1814018e`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z`
- size: `155`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1814018e`

## callees

- `0x181400f3`
- `0x18150de8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18140134`
- `KERNEL32!GetLastError` at `0x18140134`
- `KERNEL32!FreeLibrary` at `0x18140184`
- `KERNEL32!FreeLibrary` at `0x18140184`
- `KERNEL32!LoadLibraryExW` at `0x18140128`
- `KERNEL32!LoadLibraryExW` at `0x1814015b`
- `KERNEL32!LoadLibraryExW` at `0x18140128`
- `KERNEL32!LoadLibraryExW` at `0x1814015b`

## pseudocode

```c
HMODULE __cdecl try_get_first_available_module(_DWORD *a1, _DWORD *a2)
{
  int *v3; // ebx
  HMODULE Library; // esi
  const WCHAR *lpLibFileName; // [esp+Ch] [ebp-4h]

  while ( 1 )
  {
    if ( a1 == a2 )
      return 0;
    v3 = &dword_181ED090[*a1];
    Library = (HMODULE)*v3;
    if ( !*v3 )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_10:
    ++a1;
  }
  lpLibFileName = (&::lpLibFileName)[*a1];
  Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(lpLibFileName, L"api-ms-", 7u)
     || (Library = LoadLibraryExW(lpLibFileName, 0, 0)) == 0) )
  {
    _InterlockedExchange(v3, -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange(v3, (__int32)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x181400f3  push    ebp
0x181400f4  mov     ebp, esp
0x181400f6  push    ecx
0x181400f7  push    ebx
0x181400f8  push    esi
0x181400f9  push    edi
0x181400fa  mov     edi, [ebp+arg_0]
0x181400fd  jmp     short loc_1814016F
0x181400ff  mov     eax, [edi]
0x18140101  lea     ebx, dword_181ED090[eax*4]
0x18140108  mov     esi, [ebx]
0x1814010a  nop
0x1814010b  test    esi, esi
0x1814010d  jz      short loc_18140116
0x1814010f  cmp     esi, 0FFFFFFFFh
0x18140112  jnz     short loc_1814018A
0x18140114  jmp     short loc_1814016C
0x18140116  mov     eax, ds:lpLibFileName[eax*4]
0x1814011d  push    800h; dwFlags
0x18140122  push    0; hFile
0x18140124  push    eax; lpLibFileName
0x18140125  mov     [ebp+lpLibFileName], eax
0x18140128  call    ds:LoadLibraryExW
0x1814012e  mov     esi, eax
0x18140130  test    esi, esi
0x18140132  jnz     short loc_1814017B
0x18140134  call    ds:GetLastError
0x1814013a  cmp     eax, 57h ; 'W'
0x1814013d  jnz     short loc_18140167
0x1814013f  mov     esi, [ebp+lpLibFileName]
0x18140142  push    7; MaxCount
0x18140144  push    offset aApiMs
0x18140149  push    esi; String1
0x1814014a  call    _wcsncmp
0x1814014f  add     esp, 0Ch
0x18140152  test    eax, eax
0x18140154  jz      short loc_18140167
0x18140156  push    0; dwFlags
0x18140158  push    0; hFile
0x1814015a  push    esi; lpLibFileName
0x1814015b  call    ds:LoadLibraryExW
0x18140161  mov     esi, eax
0x18140163  test    esi, esi
0x18140165  jnz     short loc_1814017B
0x18140167  or      eax, 0FFFFFFFFh
0x1814016a  xchg    eax, [ebx]
0x1814016c  add     edi, 4
0x1814016f  cmp     edi, [ebp+arg_4]
0x18140172  jnz     short loc_181400FF
0x18140174  xor     eax, eax
0x18140176  pop     edi
0x18140177  pop     esi
0x18140178  pop     ebx
0x18140179  leave
0x1814017a  retn
0x1814017b  mov     eax, esi
0x1814017d  xchg    eax, [ebx]
0x1814017f  test    eax, eax
0x18140181  jz      short loc_1814018A
0x18140183  push    esi; hLibModule
0x18140184  call    ds:FreeLibrary
0x1814018a  mov     eax, esi
0x1814018c  jmp     short loc_18140176
```
