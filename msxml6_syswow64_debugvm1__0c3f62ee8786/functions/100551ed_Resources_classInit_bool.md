# Resources::classInit(bool)

- ea: `0x100551ed`
- end: `0x10055312`
- name: `?classInit@Resources@@SGX_N@Z`
- size: `293`
- prototype: `void __stdcall(bool fLoadResDLL)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x100670d2`

## callees

- `0x100551ed`
- `0x10055318`
- `0x1005536b`
- `0x10064d34`
- `0x1006b510`
- `0x1007ac7b`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100552d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100552d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x10055215`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x10055215`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10055302`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10055302`

## string_xrefs

- `0x10055256`: `msxml6r.dll`

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
0x100551ed  mov     edi, edi
0x100551ef  push    ebp
0x100551f0  mov     ebp, esp
0x100551f2  sub     esp, 230h
0x100551f8  mov     eax, ___security_cookie
0x100551fd  xor     eax, ebp
0x100551ff  mov     [ebp+var_4], eax
0x10055202  push    ebx
0x10055203  push    104h; nSize
0x10055208  lea     eax, [ebp+szModulePath]
0x1005520e  push    eax; lpFilename
0x1005520f  push    ?g_hInstance@@3PAUHINSTANCE__@@A; hModule
0x10055215  call    ds:__imp__GetModuleFileNameW@12; GetModuleFileNameW(x,x,x)
0x1005521b  test    eax, eax
0x1005521d  jz      loc_100552B9
0x10055223  mov     ecx, ?g_hInstance@@3PAUHINSTANCE__@@A; hmod
0x10055229  lea     edx, [ebp+verDll]; auiVersion
0x1005522f  xor     eax, eax
0x10055231  mov     [ebp+szModulePath+208h], ax
0x10055235  call    ?GetVersion@Resources@@SG_NPAUHINSTANCE__@@AAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x1005523a  test    al, al
0x1005523c  jnz     short loc_10055243
0x1005523e  call    ?throw_E_FAIL@Exception@@SGXXZ; Exception::throw_E_FAIL(void)
0x10055243  push    esi
0x10055244  push    edi
0x10055245  lea     ecx, [ebp+szModulePath]; _String
0x1005524b  call    ?wcsrchr@@YAPAGPAGG@Z; wcsrchr(ushort *,ushort)
0x10055250  lea     edx, [ebp+szModulePath]
0x10055256  mov     ebx, offset aMsxml6rDll; "msxml6r.dll"
0x1005525b  mov     esi, ebx
0x1005525d  lea     ecx, [eax+2]; pszDest
0x10055260  mov     eax, ecx
0x10055262  sub     eax, edx
0x10055264  mov     edx, 105h
0x10055269  sar     eax, 1
0x1005526b  sub     edx, eax; cchDest
0x1005526d  xor     edi, edi
0x1005526f  mov     eax, edi
0x10055271  cmp     [esi], di
0x10055274  jz      short loc_10055281
0x10055276  add     esi, 2
0x10055279  inc     eax
0x1005527a  cmp     eax, 7FFFFFFFh
0x1005527f  jb      short loc_10055271
0x10055281  cmp     eax, edx
0x10055283  jl      short loc_100552EA
0x10055285  mov     eax, ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; HINSTANCE__ * Resources::s_hInstance
0x1005528a  lea     edx, [ebp+verRes]; auiVersion
0x10055290  mov     ecx, eax; hmod
0x10055292  call    ?GetVersion@Resources@@SG_NPAUHINSTANCE__@@AAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x10055297  test    al, al
0x10055299  jz      short loc_100552D3
0x1005529b  mov     eax, [ebp+verRes]
0x100552a1  cmp     eax, [ebp+verDll]
0x100552a7  jnz     short loc_100552D3
0x100552a9  mov     eax, [ebp+verRes+4]
0x100552af  cmp     eax, [ebp+verDll+4]
0x100552b5  jg      short loc_100552D3
0x100552b7  pop     edi
0x100552b8  pop     esi
0x100552b9  cmp     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, 0; HINSTANCE__ * Resources::s_hInstance
0x100552c0  jz      loc_1005523E
0x100552c6  mov     ecx, [ebp+var_4]
0x100552c9  xor     ecx, ebp; cookie
0x100552cb  pop     ebx
0x100552cc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100552d1  leave
0x100552d2  retn
0x100552d3  push    ?s_hInstance@Resources@@2PAUHINSTANCE__@@A; hLibModule
0x100552d9  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100552df  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, edi; HINSTANCE__ * Resources::s_hInstance
0x100552e5  jmp     loc_1005523E
0x100552ea  push    ebx; pszSrc
0x100552eb  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x100552f0  test    eax, eax
0x100552f2  js      loc_1005523E
0x100552f8  push    2; dwFlags
0x100552fa  push    edi; hFile
0x100552fb  lea     eax, [ebp+szModulePath]
0x10055301  push    eax; lpLibFileName
0x10055302  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10055308  mov     ?s_hInstance@Resources@@2PAUHINSTANCE__@@A, eax; HINSTANCE__ * Resources::s_hInstance
0x1005530d  jmp     loc_1005528A
```
