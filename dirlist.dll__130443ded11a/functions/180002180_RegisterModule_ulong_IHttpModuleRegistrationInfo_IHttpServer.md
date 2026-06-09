# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002180`
- end: `0x18000229a`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x180002180`
- `0x180003918`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002216`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002204`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002204`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000223f`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000223f`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180002261`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180002261`

## string_xrefs

- `0x1800021fb`: `iisres.dll`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  __int64 result; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  LANG_STRING *v9; // rax
  LANG_STRING *v10; // rax

  g_pDirListingModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v5 = operator new(0x10u);
  if ( v5 )
  {
    *v5 = &CIISModuleFactory::`vftable';
    v5[1] = &CIISHttpModule::`vftable';
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
               a2,
               v5,
               128,
               0);
    if ( (int)result < 0 )
      return result;
    DIR_LISTING_HANDLER::sm_hResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
    if ( !DIR_LISTING_HANDLER::sm_hResourceDll )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_12;
    }
    v9 = (LANG_STRING *)operator new(0x58u);
    if ( v9 )
    {
      v10 = LANG_STRING::LANG_STRING(v9);
      DIR_LISTING_HANDLER::sm_pLangString = v10;
      if ( v10 )
      {
        v8 = LANG_STRING::Initialize(v10, DIR_LISTING_HANDLER::sm_hResourceDll, 5u);
        if ( v8 >= 0 )
          return 0;
LABEL_12:
        DIR_LISTING_HANDLER::Terminate();
        return (unsigned int)v8;
      }
    }
    else
    {
      DIR_LISTING_HANDLER::sm_pLangString = 0;
    }
    v8 = -2147024888;
    goto LABEL_12;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002180  mov     [rsp+arg_0], rbx
0x180002185  push    rdi
0x180002186  sub     rsp, 30h
0x18000218a  mov     rax, [rdx]
0x18000218d  mov     rcx, rdx
0x180002190  mov     rbx, r8
0x180002193  mov     rdi, rdx
0x180002196  mov     rax, [rax+8]
0x18000219a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219f  mov     ecx, 10h; Size
0x1800021a4  mov     cs:?g_pDirListingModuleContext@@3PEAXEA, rax; void * g_pDirListingModuleContext
0x1800021ab  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x1800021b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021b7  mov     rdx, rax
0x1800021ba  test    rax, rax
0x1800021bd  jz      loc_18000228A
0x1800021c3  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800021ca  xor     r9d, r9d
0x1800021cd  mov     [rdx], rax
0x1800021d0  mov     r8d, 80h
0x1800021d6  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800021dd  mov     [rdx+8], rax
0x1800021e1  mov     rcx, [rdi]
0x1800021e4  mov     rax, [rcx+10h]
0x1800021e8  mov     rcx, rdi
0x1800021eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021f0  test    eax, eax
0x1800021f2  js      loc_18000228F
0x1800021f8  xor     r8d, r8d; dwFlags
0x1800021fb  lea     rcx, LibFileName; "iisres.dll"
0x180002202  xor     edx, edx; hFile
0x180002204  call    cs:__imp_LoadLibraryExW
0x18000220a  mov     cs:?sm_hResourceDll@DIR_LISTING_HANDLER@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * DIR_LISTING_HANDLER::sm_hResourceDll
0x180002211  test    rax, rax
0x180002214  jnz     short loc_18000222D
0x180002216  call    cs:__imp_GetLastError
0x18000221c  mov     ebx, eax
0x18000221e  test    eax, eax
0x180002220  jle     short loc_180002281
0x180002222  movzx   ebx, ax
0x180002225  or      ebx, 80070000h
0x18000222b  jmp     short loc_180002281
0x18000222d  mov     ecx, 58h ; 'X'; Size
0x180002232  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002237  test    rax, rax
0x18000223a  jz      short loc_180002271
0x18000223c  mov     rcx, rax
0x18000223f  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x180002245  mov     cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA, rax; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x18000224c  test    rax, rax
0x18000224f  jz      short loc_18000227C
0x180002251  mov     rdx, cs:?sm_hResourceDll@DIR_LISTING_HANDLER@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * DIR_LISTING_HANDLER::sm_hResourceDll
0x180002258  mov     r8d, 5
0x18000225e  mov     rcx, rax
0x180002261  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x180002267  mov     ebx, eax
0x180002269  test    eax, eax
0x18000226b  js      short loc_180002281
0x18000226d  xor     ebx, ebx
0x18000226f  jmp     short loc_180002286
0x180002271  mov     cs:?sm_pLangString@DIR_LISTING_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * DIR_LISTING_HANDLER::sm_pLangString
0x18000227c  mov     ebx, 80070008h
0x180002281  call    ?Terminate@DIR_LISTING_HANDLER@@SAXXZ; DIR_LISTING_HANDLER::Terminate(void)
0x180002286  mov     eax, ebx
0x180002288  jmp     short loc_18000228F
0x18000228a  mov     eax, 80070008h
0x18000228f  mov     rbx, [rsp+38h+arg_0]
0x180002294  add     rsp, 30h
0x180002298  pop     rdi
0x180002299  retn
```
