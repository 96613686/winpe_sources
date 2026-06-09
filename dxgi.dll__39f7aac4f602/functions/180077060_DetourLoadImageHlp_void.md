# DetourLoadImageHlp(void)

- ea: `0x180077060`
- end: `0x1800772b5`
- name: `?DetourLoadImageHlp@@YAPEAU_DETOUR_SYM_INFO@@XZ`
- size: `597`
- prototype: `struct _DETOUR_SYM_INFO *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180077540`

## callees

- `0x180077060`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800770ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077105`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007713b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077156`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007718c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800770ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077105`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077120`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007713b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077156`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007718c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800770c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800770c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077272`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180077272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800770af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800770af`

## string_xrefs

- `0x1800770b8`: `dbghelp.dll`

## pseudocode

```c
struct _DETOUR_SYM_INFO *DetourLoadImageHlp(void)
{
  struct _DETOUR_SYM_INFO *result; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v3; // eax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180108E20 )
    return 0;
  result = (struct _DETOUR_SYM_INFO *)qword_180108E18;
  if ( !qword_180108E18 )
  {
    xmmword_180108DD0 = 0;
    qword_180108E10 = 0;
    xmmword_180108DE0 = 0;
    xmmword_180108DF0 = 0;
    xmmword_180108E00 = 0;
    *(_QWORD *)&xmmword_180108DD0 = GetCurrentProcess();
    Library = LoadLibraryExW(L"dbghelp.dll", 0, 0);
    *((_QWORD *)&xmmword_180108DD0 + 1) = Library;
    if ( Library )
    {
      *(_QWORD *)&xmmword_180108DE0 = GetProcAddress(Library, "ImagehlpApiVersionEx");
      *((_QWORD *)&xmmword_180108DE0 + 1) = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymInitialize");
      *(_QWORD *)&xmmword_180108DF0 = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymSetOptions");
      *((_QWORD *)&xmmword_180108DF0 + 1) = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymGetOptions");
      *(_QWORD *)&xmmword_180108E00 = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymLoadModule64");
      *((_QWORD *)&xmmword_180108E00 + 1) = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymGetModuleInfo64");
      ProcAddress = GetProcAddress(*((HMODULE *)&xmmword_180108DD0 + 1), "SymFromName");
      v4 = 12;
      qword_180108E10 = (__int64)ProcAddress;
      if ( (_QWORD)xmmword_180108DE0 )
      {
        if ( *((_QWORD *)&xmmword_180108DE0 + 1) )
        {
          if ( (_QWORD)xmmword_180108E00 )
          {
            if ( *((_QWORD *)&xmmword_180108E00 + 1) )
            {
              if ( ProcAddress )
              {
                ((void (__fastcall *)(__int64 *))xmmword_180108DE0)(&v4);
                if ( (unsigned __int16)v4 >= 0xCu )
                {
                  if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))&xmmword_180108DE0 + 1))(
                         xmmword_180108DD0,
                         0,
                         0) )
                  {
                    if ( *((_QWORD *)&xmmword_180108DF0 + 1) )
                    {
                      if ( (_QWORD)xmmword_180108DF0 )
                      {
                        v3 = (*((__int64 (**)(void))&xmmword_180108DF0 + 1))();
                        ((void (__fastcall *)(_QWORD))xmmword_180108DF0)(v3 & 0xFFFFD8F8 | 0x2704);
                      }
                    }
                    result = (struct _DETOUR_SYM_INFO *)&xmmword_180108DD0;
                    qword_180108E18 = (__int64)&xmmword_180108DD0;
                    return result;
                  }
                }
              }
            }
          }
        }
      }
      Library = (HMODULE)*((_QWORD *)&xmmword_180108DD0 + 1);
    }
    dword_180108E20 = 1;
    if ( Library )
      FreeLibrary(Library);
    result = 0;
    xmmword_180108DE0 = 0u;
    xmmword_180108DF0 = 0u;
    xmmword_180108E00 = 0u;
    qword_180108E10 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180077060  sub     rsp, 28h
0x180077064  cmp     cs:dword_180108E20, 0
0x18007706b  jz      short loc_180077074
0x18007706d  xor     eax, eax
0x18007706f  add     rsp, 28h
0x180077073  retn
0x180077074  mov     rax, cs:qword_180108E18
0x18007707b  test    rax, rax
0x18007707e  jnz     loc_1800772B0
0x180077084  xorps   xmm0, xmm0
0x180077087  mov     [rsp+28h+var_8], rbx
0x18007708c  movups  cs:xmmword_180108DD0, xmm0
0x180077093  mov     cs:qword_180108E10, rax
0x18007709a  movups  cs:xmmword_180108DE0, xmm0
0x1800770a1  movups  cs:xmmword_180108DF0, xmm0
0x1800770a8  movups  cs:xmmword_180108E00, xmm0
0x1800770af  call    cs:__imp_GetCurrentProcess
0x1800770b5  xor     r8d, r8d; dwFlags
0x1800770b8  lea     rcx, aDbghelpDll; "dbghelp.dll"
0x1800770bf  xor     edx, edx; hFile
0x1800770c1  mov     qword ptr cs:xmmword_180108DD0, rax
0x1800770c8  call    cs:__imp_LoadLibraryExW
0x1800770ce  xor     ebx, ebx
0x1800770d0  mov     qword ptr cs:xmmword_180108DD0+8, rax
0x1800770d7  test    rax, rax
0x1800770da  jz      loc_180077260
0x1800770e0  lea     rdx, aImagehlpapiver; "ImagehlpApiVersionEx"
0x1800770e7  mov     rcx, rax; hModule
0x1800770ea  call    cs:__imp_GetProcAddress
0x1800770f0  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x1800770f7  lea     rdx, aSyminitialize; "SymInitialize"
0x1800770fe  mov     qword ptr cs:xmmword_180108DE0, rax
0x180077105  call    cs:__imp_GetProcAddress
0x18007710b  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x180077112  lea     rdx, aSymsetoptions; "SymSetOptions"
0x180077119  mov     qword ptr cs:xmmword_180108DE0+8, rax
0x180077120  call    cs:__imp_GetProcAddress
0x180077126  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x18007712d  lea     rdx, aSymgetoptions; "SymGetOptions"
0x180077134  mov     qword ptr cs:xmmword_180108DF0, rax
0x18007713b  call    cs:__imp_GetProcAddress
0x180077141  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x180077148  lea     rdx, aSymloadmodule6; "SymLoadModule64"
0x18007714f  mov     qword ptr cs:xmmword_180108DF0+8, rax
0x180077156  call    cs:__imp_GetProcAddress
0x18007715c  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x180077163  lea     rdx, aSymgetmodulein; "SymGetModuleInfo64"
0x18007716a  mov     qword ptr cs:xmmword_180108E00, rax
0x180077171  call    cs:__imp_GetProcAddress
0x180077177  mov     rcx, qword ptr cs:xmmword_180108DD0+8; hModule
0x18007717e  lea     rdx, aSymfromname; "SymFromName"
0x180077185  mov     qword ptr cs:xmmword_180108E00+8, rax
0x18007718c  call    cs:__imp_GetProcAddress
0x180077192  mov     rdx, qword ptr cs:xmmword_180108DE0
0x180077199  mov     ecx, 0Ch
0x18007719e  mov     [rsp+28h+arg_0], rbx
0x1800771a3  mov     cs:qword_180108E10, rax
0x1800771aa  mov     word ptr [rsp+28h+arg_0], cx
0x1800771af  test    rdx, rdx
0x1800771b2  jz      loc_180077259
0x1800771b8  cmp     qword ptr cs:xmmword_180108DE0+8, rbx
0x1800771bf  jz      loc_180077259
0x1800771c5  cmp     qword ptr cs:xmmword_180108E00, rbx
0x1800771cc  jz      loc_180077259
0x1800771d2  cmp     qword ptr cs:xmmword_180108E00+8, rbx
0x1800771d9  jz      short loc_180077259
0x1800771db  test    rax, rax
0x1800771de  jz      short loc_180077259
0x1800771e0  lea     rcx, [rsp+28h+arg_0]
0x1800771e5  mov     rax, rdx
0x1800771e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771ed  cmp     word ptr [rsp+28h+arg_0], 0Ch
0x1800771f3  jb      short loc_180077259
0x1800771f5  mov     rcx, qword ptr cs:xmmword_180108DD0
0x1800771fc  xor     r8d, r8d
0x1800771ff  mov     rax, qword ptr cs:xmmword_180108DE0+8
0x180077206  xor     edx, edx
0x180077208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007720d  test    eax, eax
0x18007720f  jz      short loc_180077259
0x180077211  mov     rax, qword ptr cs:xmmword_180108DF0+8
0x180077218  test    rax, rax
0x18007721b  jz      short loc_180077241
0x18007721d  cmp     qword ptr cs:xmmword_180108DF0, rbx
0x180077224  jz      short loc_180077241
0x180077226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007722b  and     eax, 0FFFFFFFCh
0x18007722e  or      eax, 2704h
0x180077233  mov     ecx, eax
0x180077235  mov     rax, qword ptr cs:xmmword_180108DF0
0x18007723c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077241  mov     rbx, [rsp+28h+var_8]
0x180077246  lea     rax, xmmword_180108DD0
0x18007724d  mov     cs:qword_180108E18, rax
0x180077254  add     rsp, 28h
0x180077258  retn
0x180077259  mov     rax, qword ptr cs:xmmword_180108DD0+8
0x180077260  mov     cs:dword_180108E20, 1
0x18007726a  test    rax, rax
0x18007726d  jz      short loc_180077278
0x18007726f  mov     rcx, rax; hLibModule
0x180077272  call    cs:__imp_FreeLibrary
0x180077278  mov     qword ptr cs:xmmword_180108DE0, rbx
0x18007727f  xor     eax, eax
0x180077281  mov     qword ptr cs:xmmword_180108DE0+8, rbx
0x180077288  mov     qword ptr cs:xmmword_180108DF0, rbx
0x18007728f  mov     qword ptr cs:xmmword_180108DF0+8, rbx
0x180077296  mov     qword ptr cs:xmmword_180108E00, rbx
0x18007729d  mov     qword ptr cs:xmmword_180108E00+8, rbx
0x1800772a4  mov     cs:qword_180108E10, rbx
0x1800772ab  mov     rbx, [rsp+28h+var_8]
0x1800772b0  add     rsp, 28h
0x1800772b4  retn
```
