# Resources::classInit(bool)

- ea: `0x1005515d`
- end: `0x10055282`
- name: `?classInit@Resources@@SGX_N@Z`
- size: `293`
- prototype: `void __stdcall(bool fLoadResDLL)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x10067032`

## callees

- `0x1005515d`
- `0x10055288`
- `0x100552db`
- `0x10064c94`
- `0x1006b470`
- `0x1007acbb`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10055249`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10055249`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x10055185`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x10055185`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10055272`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10055272`

## string_xrefs

- `0x100551c6`: `msxml6r.dll`

## pseudocode

```c
void __usercall Resources::classInit(unsigned __int16 *a1@<edi>, unsigned __int16 a2@<si>)
{
  unsigned __int16 *v2; // eax
  const wchar_t *v3; // esi
  wchar_t *v4; // ecx
  signed int v5; // edx
  unsigned int i; // eax
  HMODULE Library; // eax
  int verDll[4]; // [esp+4h] [ebp-230h] BYREF
  int verRes[4]; // [esp+14h] [ebp-220h] BYREF
  wchar_t szModulePath[262]; // [esp+24h] [ebp-210h] BYREF

  if ( GetModuleFileNameW(g_hInstance, szModulePath, 0x104u) )
  {
    szModulePath[260] = 0;
    if ( !Resources::GetVersion(g_hInstance, (int (*)[4])verDll) )
      goto LABEL_3;
    v2 = wcsrchr(a1, a2);
    v3 = L"msxml6r.dll";
    v4 = v2 + 1;
    v5 = 261 - (v2 + 1 - szModulePath);
    for ( i = 0; i < 0x7FFFFFFF; ++i )
    {
      if ( !*v3 )
        break;
      ++v3;
    }
    if ( (int)i < v5 )
    {
      if ( StringCchCopyW(v4, v5, L"msxml6r.dll") < 0 )
        goto LABEL_3;
      Library = LoadLibraryExW(szModulePath, 0, 2u);
      Resources::s_hInstance = Library;
    }
    else
    {
      Library = Resources::s_hInstance;
    }
    if ( Resources::GetVersion(Library, (int (*)[4])verRes) && verRes[0] == verDll[0] && verRes[1] <= verDll[1] )
      goto LABEL_12;
    FreeLibrary(Resources::s_hInstance);
    Resources::s_hInstance = 0;
LABEL_3:
    Exception::throw_E_FAIL();
  }
LABEL_12:
  if ( !Resources::s_hInstance )
    goto LABEL_3;
}

```

## disassembly

```asm
0x1005515d  mov     edi, edi
0x1005515f  push    ebp
0x10055160  mov     ebp, esp
0x10055162  sub     esp, 230h
0x10055168  mov     eax, ___security_cookie
0x1005516d  xor     eax, ebp
0x1005516f  mov     [ebp+var_4], eax
0x10055172  push    ebx
0x10055173  push    104h; nSize
0x10055178  lea     eax, [ebp+szModulePath]
0x1005517e  push    eax; lpFilename
0x1005517f  push    ?g_hInstance@@3PAUHINSTANCE__@@A; hModule
0x10055185  call    ds:__imp__GetModuleFileNameW@12; GetModuleFileNameW(x,x,x)
0x1005518b  test    eax, eax
0x1005518d  jz      loc_10055229
0x10055193  mov     ecx, ?g_hInstance@@3PAUHINSTANCE__@@A; hmod
0x10055199  lea     edx, [ebp+verDll]; auiVersion
0x1005519f  xor     eax, eax
0x100551a1  mov     [ebp+szModulePath+208h], ax
0x100551a5  call    ?GetVersion@Resources@@SG_NPAUHINSTANCE__@@AAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x100551aa  test    al, al
0x100551ac  jnz     short loc_100551B3
0x100551ae  call    ?throw_E_FAIL@Exception@@SGXXZ; Exception::throw_E_FAIL(void)
0x100551b3  push    esi
0x100551b4  push    edi
0x100551b5  lea     ecx, [ebp+szModulePath]; _String
0x100551bb  call    ?wcsrchr@@YAPAGPAGG@Z; wcsrchr(ushort *,ushort)
0x100551c0  lea     edx, [ebp+szModulePath]
0x100551c6  mov     ebx, offset aMsxml6rDll; "msxml6r.dll"
0x100551cb  mov     esi, ebx
0x100551cd  lea     ecx, [eax+2]; pszDest
0x100551d0  mov     eax, ecx
0x100551d2  sub     eax, edx
0x100551d4  mov     edx, 105h
0x100551d9  sar     eax, 1
0x100551db  sub     edx, eax; cchDest
0x100551dd  xor     edi, edi
0x100551df  mov     eax, edi
0x100551e1  cmp     [esi], di
0x100551e4  jz      short loc_100551F1
0x100551e6  add     esi, 2
0x100551e9  inc     eax
0x100551ea  cmp     eax, 7FFFFFFFh
0x100551ef  jb      short loc_100551E1
0x100551f1  cmp     eax, edx
0x100551f3  jl      short loc_1005525A
0x100551f5  mov     eax, ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; HINSTANCE__ * Resources::s_hInstance
0x100551fa  lea     edx, [ebp+verRes]; auiVersion
0x10055200  mov     ecx, eax; hmod
0x10055202  call    ?GetVersion@Resources@@SG_NPAUHINSTANCE__@@AAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x10055207  test    al, al
0x10055209  jz      short loc_10055243
0x1005520b  mov     eax, [ebp+verRes]
0x10055211  cmp     eax, [ebp+verDll]
0x10055217  jnz     short loc_10055243
0x10055219  mov     eax, [ebp+verRes+4]
0x1005521f  cmp     eax, [ebp+verDll+4]
0x10055225  jg      short loc_10055243
0x10055227  pop     edi
0x10055228  pop     esi
0x10055229  cmp     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, 0; HINSTANCE__ * Resources::s_hInstance
0x10055230  jz      loc_100551AE
0x10055236  mov     ecx, [ebp+var_4]
0x10055239  xor     ecx, ebp; cookie
0x1005523b  pop     ebx
0x1005523c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10055241  leave
0x10055242  retn
0x10055243  push    ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; hLibModule
0x10055249  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1005524f  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, edi; HINSTANCE__ * Resources::s_hInstance
0x10055255  jmp     loc_100551AE
0x1005525a  push    ebx; pszSrc
0x1005525b  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x10055260  test    eax, eax
0x10055262  js      loc_100551AE
0x10055268  push    2; dwFlags
0x1005526a  push    edi; hFile
0x1005526b  lea     eax, [ebp+szModulePath]
0x10055271  push    eax; lpLibFileName
0x10055272  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10055278  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, eax; HINSTANCE__ * Resources::s_hInstance
0x1005527d  jmp     loc_100551FA
```
