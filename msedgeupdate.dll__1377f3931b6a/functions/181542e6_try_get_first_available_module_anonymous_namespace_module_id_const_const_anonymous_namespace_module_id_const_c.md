# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x181542e6`
- end: `0x181543ad`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z`
- size: `199`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x181543ad`

## callees

- `0x18150de8`
- `0x181542e6`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18154330`
- `KERNEL32!GetLastError` at `0x18154330`
- `KERNEL32!FreeLibrary` at `0x1815438c`
- `KERNEL32!FreeLibrary` at `0x1815438c`
- `KERNEL32!LoadLibraryExW` at `0x18154324`
- `KERNEL32!LoadLibraryExW` at `0x18154366`
- `KERNEL32!LoadLibraryExW` at `0x18154324`
- `KERNEL32!LoadLibraryExW` at `0x18154366`

## pseudocode

```c
HMODULE __cdecl try_get_first_available_module(_DWORD *a1, _DWORD *a2)
{
  HMODULE Library; // esi
  const WCHAR *v4; // ebx
  volatile __int32 *v6; // [esp+Ch] [ebp-4h]

  while ( 1 )
  {
    if ( a1 == a2 )
      return 0;
    Library = (HMODULE)dword_181ED598[*a1];
    v6 = &dword_181ED598[*a1];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_16:
    ++a1;
  }
  v4 = (&String1)[*a1];
  Library = LoadLibraryExW(v4, 0, 0x800u);
  if ( !Library )
  {
    Library = GetLastError() != 87 || !wcsncmp(v4, L"api-ms-", 7u) || !wcsncmp(v4, L"ext-ms-", 7u)
            ? 0
            : LoadLibraryExW(v4, 0, 0);
    if ( !Library )
    {
      _InterlockedExchange(v6, -1);
      goto LABEL_16;
    }
  }
  if ( _InterlockedExchange(v6, (__int32)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x181542e6  mov     edi, edi
0x181542e8  push    ebp
0x181542e9  mov     ebp, esp
0x181542eb  push    ecx
0x181542ec  push    ebx
0x181542ed  push    esi
0x181542ee  push    edi
0x181542ef  mov     edi, [ebp+arg_0]
0x181542f2  jmp     loc_18154399
0x181542f7  mov     ebx, [edi]
0x181542f9  lea     eax, dword_181ED598[ebx*4]
0x18154300  mov     esi, [eax]
0x18154302  mov     [ebp+var_4], eax
0x18154305  nop
0x18154306  test    esi, esi
0x18154308  jz      short loc_18154315
0x1815430a  cmp     esi, 0FFFFFFFFh
0x1815430d  jz      loc_18154396
0x18154313  jmp     short loc_18154392
0x18154315  mov     ebx, ds:String1[ebx*4]
0x1815431c  push    800h; dwFlags
0x18154321  push    0; hFile
0x18154323  push    ebx; lpLibFileName
0x18154324  call    ds:LoadLibraryExW
0x1815432a  mov     esi, eax
0x1815432c  test    esi, esi
0x1815432e  jnz     short loc_18154380
0x18154330  call    ds:GetLastError
0x18154336  cmp     eax, 57h ; 'W'
0x18154339  jnz     short loc_18154370
0x1815433b  push    7; MaxCount
0x1815433d  push    offset aApiMs
0x18154342  push    ebx; String1
0x18154343  call    _wcsncmp
0x18154348  add     esp, 0Ch
0x1815434b  test    eax, eax
0x1815434d  jz      short loc_18154370
0x1815434f  push    7; MaxCount
0x18154351  push    offset aExtMs
0x18154356  push    ebx; String1
0x18154357  call    _wcsncmp
0x1815435c  add     esp, 0Ch
0x1815435f  test    eax, eax
0x18154361  jz      short loc_18154370
0x18154363  push    esi; dwFlags
0x18154364  push    esi; hFile
0x18154365  push    ebx; lpLibFileName
0x18154366  call    ds:LoadLibraryExW
0x1815436c  mov     esi, eax
0x1815436e  jmp     short loc_18154372
0x18154370  xor     esi, esi
0x18154372  test    esi, esi
0x18154374  jnz     short loc_18154380
0x18154376  mov     ecx, [ebp+var_4]
0x18154379  or      eax, 0FFFFFFFFh
0x1815437c  xchg    eax, [ecx]
0x1815437e  jmp     short loc_18154396
0x18154380  mov     ecx, [ebp+var_4]
0x18154383  mov     eax, esi
0x18154385  xchg    eax, [ecx]
0x18154387  test    eax, eax
0x18154389  jz      short loc_18154392
0x1815438b  push    esi; hLibModule
0x1815438c  call    ds:FreeLibrary
0x18154392  test    esi, esi
0x18154394  jnz     short loc_181543A9
0x18154396  add     edi, 4
0x18154399  cmp     edi, [ebp+arg_4]
0x1815439c  jnz     loc_181542F7
0x181543a2  xor     eax, eax
0x181543a4  pop     edi
0x181543a5  pop     esi
0x181543a6  pop     ebx
0x181543a7  leave
0x181543a8  retn
0x181543a9  mov     eax, esi
0x181543ab  jmp     short loc_181543A4
```
