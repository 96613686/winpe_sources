# Intl_ResetLocaleSettings(void)

- ea: `0x1800260e4`
- end: `0x1800261e7`
- name: `?Intl_ResetLocaleSettings@@YAXXZ`
- size: `259`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180015704`

## callees

- `0x180023490`
- `0x1800260e4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800261c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800261c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800261ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800261ac`
- `KERNEL32!NlsUpdateLocale` at `0x180026176`
- `KERNEL32!NlsUpdateLocale` at `0x180026176`
- `USER32!SendNotifyMessageW` at `0x180026192`
- `USER32!SendNotifyMessageW` at `0x180026192`

## string_xrefs

- `0x1800261a5`: `CoreGlobConfig.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Intl_ResetLocaleSettings(void)
{
  __int64 v0; // rdx
  unsigned int v1; // ebx
  unsigned int v2; // r8d
  __int64 v3; // r9
  HMODULE Library; // rax
  void (*ProcAddress)(void); // rax
  HMODULE v6; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 2;
  v2 = UserLocaleIndex;
  v3 = *((_QWORD *)g_localeInfo + UserLocaleIndex);
  if ( *(_DWORD *)(v3 + 16) == 1034 )
  {
    while ( (unsigned int)v0 < g_dwLocaleCount )
    {
      if ( *(_DWORD *)(*((_QWORD *)g_localeInfo + v0) + 16LL) == 3082 )
        goto LABEL_10;
      v0 = (unsigned int)(v0 + 1);
    }
  }
  else if ( *(_DWORD *)(v3 + 16) != 3082 && !*(_DWORD *)(v3 + 20) )
  {
    while ( (unsigned int)v0 < g_dwLocaleCount )
    {
      if ( *(_WORD *)(*((_QWORD *)g_localeInfo + v0) + 16LL) == *(_WORD *)(v3 + 16) )
      {
LABEL_10:
        v1 = 3;
        UserLocaleIndex = v0;
        v2 = v0;
        break;
      }
      v0 = (unsigned int)(v0 + 1);
    }
  }
  if ( v2 == g_savedLocaleIndex )
    v1 |= 4u;
  if ( !(unsigned int)NlsUpdateLocale(*(_QWORD *)(*((_QWORD *)g_localeInfo + v2) + 8LL), v1) )
  {
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
    if ( (v1 & 4) != 0 )
    {
      Library = LoadLibraryExW(L"CoreGlobConfig.dll", 0, 0x800u);
      v6 = Library;
      if ( Library )
      {
        ProcAddress = (void (*)(void))GetProcAddress(Library, "SyncLanguageDataToCloud");
        if ( ProcAddress )
          ProcAddress();
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v6);
    }
  }
}

```

## disassembly

```asm
0x1800260e4  push    rbx
0x1800260e6  sub     rsp, 20h
0x1800260ea  xor     edx, edx
0x1800260ec  lea     ebx, [rdx+2]
0x1800260ef  mov     r8d, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800260f6  mov     r10, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800260fd  mov     r9, [r10+r8*8]
0x180026101  cmp     dword ptr [r9+10h], 40Ah
0x180026109  jnz     short loc_180026124
0x18002610b  cmp     edx, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x180026111  jnb     short loc_18002615D
0x180026113  mov     rcx, [r10+rdx*8]
0x180026117  cmp     dword ptr [rcx+10h], 0C0Ah
0x18002611e  jz      short loc_18002614F
0x180026120  inc     edx
0x180026122  jmp     short loc_18002610B
0x180026124  cmp     dword ptr [r9+10h], 0C0Ah
0x18002612c  jz      short loc_18002615D
0x18002612e  cmp     [r9+14h], edx
0x180026132  jnz     short loc_18002615D
0x180026134  cmp     edx, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x18002613a  jnb     short loc_18002615D
0x18002613c  mov     rcx, [r10+rdx*8]
0x180026140  movzx   eax, word ptr [r9+10h]
0x180026145  cmp     [rcx+10h], ax
0x180026149  jz      short loc_18002614F
0x18002614b  inc     edx
0x18002614d  jmp     short loc_180026134
0x18002614f  mov     ebx, 3
0x180026154  mov     cs:?UserLocaleIndex@@3KA, edx; ulong UserLocaleIndex
0x18002615a  mov     r8d, edx
0x18002615d  cmp     r8d, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x180026164  jnz     short loc_180026169
0x180026166  or      ebx, 4
0x180026169  mov     eax, r8d
0x18002616c  mov     rcx, [r10+rax*8]
0x180026170  mov     edx, ebx
0x180026172  mov     rcx, [rcx+8]
0x180026176  call    cs:__imp_NlsUpdateLocale
0x18002617c  test    eax, eax
0x18002617e  jnz     short loc_1800261E1
0x180026180  lea     r9, lParam; "intl"
0x180026187  xor     r8d, r8d; wParam
0x18002618a  lea     edx, [rax+1Ah]; Msg
0x18002618d  mov     ecx, 0FFFFh; hWnd
0x180026192  call    cs:__imp_SendNotifyMessageW
0x180026198  test    bl, 4
0x18002619b  jz      short loc_1800261E1
0x18002619d  xor     edx, edx; hFile
0x18002619f  mov     r8d, 800h; dwFlags
0x1800261a5  lea     rcx, aCoreglobconfig; "CoreGlobConfig.dll"
0x1800261ac  call    cs:__imp_LoadLibraryExW
0x1800261b2  mov     [rsp+28h+arg_0], rax
0x1800261b7  test    rax, rax
0x1800261ba  jz      short loc_1800261D7
0x1800261bc  lea     rdx, aSynclanguageda; "SyncLanguageDataToCloud"
0x1800261c3  mov     rcx, rax; hModule
0x1800261c6  call    cs:__imp_GetProcAddress
0x1800261cc  test    rax, rax
0x1800261cf  jz      short loc_1800261D7
0x1800261d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261d6  nop
0x1800261d7  lea     rcx, [rsp+28h+arg_0]
0x1800261dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800261e1  add     rsp, 20h
0x1800261e5  pop     rbx
0x1800261e6  retn
```
