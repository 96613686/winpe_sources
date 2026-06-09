# GdipThaiBreakingFunctionInitializer

- ea: `0x18014f720`
- end: `0x18014f96d`
- name: `GdipThaiBreakingFunctionInitializer`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x18014f720`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18014f7fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18014f7fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014f793`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014f865`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014f793`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014f865`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18014f937`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18014f937`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18014f7bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18014f7bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014f88f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014f8ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014f88f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014f8ac`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18014f752`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18014f752`

## string_xrefs

- `0x18014f78c`: `usp10.dll`
- `0x18014f820`: `usp10.dll`
- `0x18014f7b8`: `mso.dll`

## pseudocode

```c
__int64 __fastcall GdipThaiBreakingFunctionInitializer(
        const unsigned __int16 *a1,
        unsigned int a2,
        const struct tag_SCRIPT_ANALYSIS *a3,
        struct tag_SCRIPT_LOGATTR *a4)
{
  HMODULE Library; // rdi
  HMODULE ModuleHandleW; // rsi
  WCHAR *v11; // rax
  const WCHAR *v12; // rbx
  DWORD ModuleFileNameW; // edx
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // rsi
  FARPROC ProcAddress; // rax
  __int16 v19; // [rsp+4Ch] [rbp-5Ch]

  if ( FindResourceW(DllInstance, L"SIAMMAIN", L"SIAMDB") )
  {
    GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunctionInGdiplus;
    return GdipThaiBreakingFunctionInGdiplus(a1, a2, a3, a4);
  }
  GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))SimpleBreak;
  Library = LoadLibraryExW(L"usp10.dll", 0, 0);
  if ( Library )
    goto LABEL_16;
  if ( Globals::OsVer.dwMajorVersion != 6 )
  {
    ModuleHandleW = GetModuleHandleW(L"mso.dll");
    if ( ModuleHandleW )
    {
      v11 = (WCHAR *)GpMallocEx(512, 0);
      v12 = v11;
      if ( v11 )
      {
        ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, v11, 0x100u);
        if ( ModuleFileNameW )
        {
          do
          {
            v14 = ModuleFileNameW - 1;
            if ( v12[v14] == 92 )
              break;
            --ModuleFileNameW;
          }
          while ( (_DWORD)v14 );
          v15 = 0;
          do
            v16 = ++v15;
          while ( Src[v16] );
          v17 = v15 + ModuleFileNameW;
          if ( (unsigned int)v17 < ModuleFileNameW )
          {
            GpFree(v12);
            return 2147942934LL;
          }
          if ( (unsigned int)v17 < 0x100 )
          {
            memcpy_0((void *)&v12[ModuleFileNameW], L"usp10.dll", v16 * 2);
            v12[v17] = 0;
            Library = LoadLibraryExW(v12, 0, 0);
          }
        }
      }
      GpFree(v12);
      if ( Library )
      {
LABEL_16:
        GdipScriptBreak = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GetProcAddress(Library, "ScriptBreak");
        ProcAddress = GetProcAddress(Library, "ScriptItemize");
        if ( ProcAddress
          && GdipScriptBreak
          && ((int (__fastcall *)(int *, __int64, __int64))ProcAddress)(&dword_18018C36C, 1, 2) >= 0 )
        {
          Globals::UniscribeDllModule = Library;
          ScriptThaiUsp = v19 & 0x3FF;
          GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunctionInUniscribe;
          return GdipThaiBreakingFunctionInUniscribe(a1, a2, a3, a4);
        }
        FreeLibrary(Library);
      }
    }
  }
  return ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunction)(
           a1,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x18014f720  push    rbx
0x18014f722  push    rbp
0x18014f723  push    rsi
0x18014f724  push    rdi
0x18014f725  push    r12
0x18014f727  push    r13
0x18014f729  push    r14
0x18014f72b  push    r15
0x18014f72d  sub     rsp, 68h
0x18014f731  mov     r14, r8
0x18014f734  mov     r15d, edx
0x18014f737  mov     r12, rcx
0x18014f73a  lea     r8, Type; "SIAMDB"
0x18014f741  mov     rcx, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18014f748  lea     rdx, aSiammain; "SIAMMAIN"
0x18014f74f  mov     rbp, r9
0x18014f752  call    cs:__imp_FindResourceW
0x18014f759  nop     dword ptr [rax+rax+00h]
0x18014f75e  xor     r13d, r13d
0x18014f761  test    rax, rax
0x18014f764  jz      short loc_18014F779
0x18014f766  lea     rax, ?GdipThaiBreakingFunctionInGdiplus@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInGdiplus(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f76d  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f774  jmp     loc_18014F943
0x18014f779  lea     rax, ?SimpleBreak@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; SimpleBreak(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f780  xor     r8d, r8d; dwFlags
0x18014f783  xor     edx, edx; hFile
0x18014f785  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f78c  lea     rcx, Src; "usp10.dll"
0x18014f793  call    cs:__imp_LoadLibraryExW
0x18014f79a  nop     dword ptr [rax+rax+00h]
0x18014f79f  mov     rdi, rax
0x18014f7a2  test    rax, rax
0x18014f7a5  jnz     loc_18014F885
0x18014f7ab  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 6; _OSVERSIONINFOA Globals::OsVer ...
0x18014f7b2  jz      loc_18014F943
0x18014f7b8  lea     rcx, aMsoDll; "mso.dll"
0x18014f7bf  call    cs:__imp_GetModuleHandleW
0x18014f7c6  nop     dword ptr [rax+rax+00h]
0x18014f7cb  mov     rsi, rax
0x18014f7ce  test    rax, rax
0x18014f7d1  jz      loc_18014F943
0x18014f7d7  xor     edx, edx
0x18014f7d9  mov     ecx, 200h
0x18014f7de  call    GpMallocEx
0x18014f7e3  mov     rbx, rax
0x18014f7e6  test    rax, rax
0x18014f7e9  jz      loc_18014F874
0x18014f7ef  mov     r8d, 100h; nSize
0x18014f7f5  mov     rdx, rax; lpFilename
0x18014f7f8  mov     rcx, rsi; hModule
0x18014f7fb  call    cs:__imp_GetModuleFileNameW
0x18014f802  nop     dword ptr [rax+rax+00h]
0x18014f807  mov     edx, eax
0x18014f809  test    eax, eax
0x18014f80b  jz      short loc_18014F874
0x18014f80d  lea     eax, [rdx-1]
0x18014f810  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18014f815  jz      short loc_18014F81D
0x18014f817  mov     edx, eax
0x18014f819  test    eax, eax
0x18014f81b  jnz     short loc_18014F80D
0x18014f81d  mov     ecx, r13d
0x18014f820  lea     r9, Src; "usp10.dll"
0x18014f827  inc     ecx
0x18014f829  movsxd  rax, ecx
0x18014f82c  lea     r8, [rax+rax]; Size
0x18014f830  cmp     [r8+r9], r13w
0x18014f835  jnz     short loc_18014F827
0x18014f837  lea     esi, [rcx+rdx]
0x18014f83a  cmp     esi, edx
0x18014f83c  jb      loc_18014F925
0x18014f842  cmp     esi, 100h
0x18014f848  jnb     short loc_18014F874
0x18014f84a  mov     eax, edx
0x18014f84c  mov     rdx, r9; Src
0x18014f84f  lea     rcx, [rbx+rax*2]; void *
0x18014f853  call    memcpy_0
0x18014f858  xor     r8d, r8d; dwFlags
0x18014f85b  mov     [rbx+rsi*2], r13w
0x18014f860  xor     edx, edx; hFile
0x18014f862  mov     rcx, rbx; lpLibFileName
0x18014f865  call    cs:__imp_LoadLibraryExW
0x18014f86c  nop     dword ptr [rax+rax+00h]
0x18014f871  mov     rdi, rax
0x18014f874  mov     rcx, rbx
0x18014f877  call    GpFree
0x18014f87c  test    rdi, rdi
0x18014f87f  jz      loc_18014F943
0x18014f885  lea     rdx, aScriptbreak; "ScriptBreak"
0x18014f88c  mov     rcx, rdi; hModule
0x18014f88f  call    cs:__imp_GetProcAddress
0x18014f896  nop     dword ptr [rax+rax+00h]
0x18014f89b  lea     rdx, aScriptitemize; "ScriptItemize"
0x18014f8a2  mov     rcx, rdi; hModule
0x18014f8a5  mov     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f8ac  call    cs:__imp_GetProcAddress
0x18014f8b3  nop     dword ptr [rax+rax+00h]
0x18014f8b8  test    rax, rax
0x18014f8bb  jz      short loc_18014F934
0x18014f8bd  cmp     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, r13; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f8c4  jz      short loc_18014F934
0x18014f8c6  xor     r9d, r9d
0x18014f8c9  mov     [rsp+0A8h+var_68], r13d
0x18014f8ce  lea     rcx, [rsp+0A8h+var_68]
0x18014f8d3  mov     [rsp+0A8h+var_78], rcx
0x18014f8d8  lea     rcx, [rsp+0A8h+var_60]
0x18014f8dd  mov     [rsp+0A8h+var_80], rcx
0x18014f8e2  lea     rcx, dword_18018C36C
0x18014f8e9  lea     edx, [r9+1]
0x18014f8ed  mov     [rsp+0A8h+var_88], r13
0x18014f8f2  lea     r8d, [r9+2]
0x18014f8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f8fb  test    eax, eax
0x18014f8fd  js      short loc_18014F934
0x18014f8ff  mov     eax, dword ptr [rsp+0A8h+var_5C]
0x18014f903  and     eax, 3FFh
0x18014f908  mov     cs:?UniscribeDllModule@Globals@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * Globals::UniscribeDllModule
0x18014f90f  mov     cs:?ScriptThaiUsp@@3HA, eax; int ScriptThaiUsp
0x18014f915  lea     rax, ?GdipThaiBreakingFunctionInUniscribe@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInUniscribe(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f91c  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f923  jmp     short loc_18014F943
0x18014f925  mov     rcx, rbx
0x18014f928  call    GpFree
0x18014f92d  mov     eax, 80070216h
0x18014f932  jmp     short loc_18014F95B
0x18014f934  mov     rcx, rdi; hLibModule
0x18014f937  call    cs:__imp_FreeLibrary
0x18014f93e  nop     dword ptr [rax+rax+00h]
0x18014f943  mov     rax, cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014f94a  mov     r9, rbp
0x18014f94d  mov     r8, r14
0x18014f950  mov     edx, r15d
0x18014f953  mov     rcx, r12
0x18014f956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f95b  add     rsp, 68h
0x18014f95f  pop     r15
0x18014f961  pop     r14
0x18014f963  pop     r13
0x18014f965  pop     r12
0x18014f967  pop     rdi
0x18014f968  pop     rsi
0x18014f969  pop     rbp
0x18014f96a  pop     rbx
0x18014f96b  retn
```
