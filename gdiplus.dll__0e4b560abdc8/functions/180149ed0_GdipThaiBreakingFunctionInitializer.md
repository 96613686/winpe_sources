# GdipThaiBreakingFunctionInitializer

- ea: `0x180149ed0`
- end: `0x18014a139`
- name: `GdipThaiBreakingFunctionInitializer`
- size: `617`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18001f950`
- `0x1800e5044`
- `0x180149ed0`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180149fb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180149fb6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18014a0f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18014a0f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014a04e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014a06b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014a04e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18014a06b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180149f4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014a024`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180149f4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18014a024`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180149f7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180149f7a`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180149f0d`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180149f0d`

## string_xrefs

- `0x180149f47`: `usp10.dll`
- `0x180149fd9`: `usp10.dll`
- `0x18014a002`: `usp10.dll`
- `0x180149f73`: `mso.dll`

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
  DWORD ModuleFileNameW; // eax
  __int64 v14; // rdx
  int v15; // ecx
  const WCHAR *v16; // rdx
  __int64 v17; // rsi
  FARPROC ProcAddress; // rax
  __int16 v19; // [rsp+4Ch] [rbp-3Ch]

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
          v16 = L"usp10.dll";
          do
          {
            ++v15;
            ++v16;
          }
          while ( *v16 );
          v17 = v15 + ModuleFileNameW;
          if ( (unsigned int)v17 < ModuleFileNameW )
          {
            GpFree(v12);
            return 2147942934LL;
          }
          if ( (unsigned int)v17 < 0x100 )
          {
            memcpy_0((void *)&v12[ModuleFileNameW], L"usp10.dll", 2LL * v15);
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
          && ((int (__fastcall *)(int *, __int64, __int64))ProcAddress)(&dword_18018E82C, 1, 2) >= 0 )
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
0x180149ed0  mov     [rsp+arg_0], rbx
0x180149ed5  mov     [rsp+arg_8], rbp
0x180149eda  mov     [rsp+arg_10], rsi
0x180149edf  push    rdi
0x180149ee0  push    r12
0x180149ee2  push    r13
0x180149ee4  push    r14
0x180149ee6  push    r15
0x180149ee8  sub     rsp, 60h
0x180149eec  mov     r14, r8
0x180149eef  mov     r15d, edx
0x180149ef2  mov     r12, rcx
0x180149ef5  lea     r8, Type; "SIAMDB"
0x180149efc  mov     rcx, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180149f03  lea     rdx, Name; "SIAMMAIN"
0x180149f0a  mov     rbp, r9
0x180149f0d  call    cs:__imp_FindResourceW
0x180149f14  nop     dword ptr [rax+rax+00h]
0x180149f19  xor     r13d, r13d
0x180149f1c  test    rax, rax
0x180149f1f  jz      short loc_180149F34
0x180149f21  lea     rax, ?GdipThaiBreakingFunctionInGdiplus@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInGdiplus(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180149f28  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180149f2f  jmp     loc_18014A102
0x180149f34  lea     rax, ?SimpleBreak@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; SimpleBreak(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180149f3b  xor     r8d, r8d; dwFlags
0x180149f3e  xor     edx, edx; hFile
0x180149f40  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180149f47  lea     rcx, Src; "usp10.dll"
0x180149f4e  call    cs:__imp_LoadLibraryExW
0x180149f55  nop     dword ptr [rax+rax+00h]
0x180149f5a  mov     rdi, rax
0x180149f5d  test    rax, rax
0x180149f60  jnz     loc_18014A044
0x180149f66  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 6; _OSVERSIONINFOA Globals::OsVer ...
0x180149f6d  jz      loc_18014A102
0x180149f73  lea     rcx, aMsoDll; "mso.dll"
0x180149f7a  call    cs:__imp_GetModuleHandleW
0x180149f81  nop     dword ptr [rax+rax+00h]
0x180149f86  mov     rsi, rax
0x180149f89  test    rax, rax
0x180149f8c  jz      loc_18014A102
0x180149f92  xor     edx, edx
0x180149f94  mov     ecx, 200h
0x180149f99  call    GpMallocEx
0x180149f9e  mov     rbx, rax
0x180149fa1  test    rax, rax
0x180149fa4  jz      loc_18014A033
0x180149faa  mov     r8d, 100h; nSize
0x180149fb0  mov     rdx, rax; lpFilename
0x180149fb3  mov     rcx, rsi; hModule
0x180149fb6  call    cs:__imp_GetModuleFileNameW
0x180149fbd  nop     dword ptr [rax+rax+00h]
0x180149fc2  test    eax, eax
0x180149fc4  jz      short loc_18014A033
0x180149fc6  lea     edx, [rax-1]
0x180149fc9  cmp     word ptr [rbx+rdx*2], 5Ch ; '\'
0x180149fce  jz      short loc_180149FD6
0x180149fd0  mov     eax, edx
0x180149fd2  test    edx, edx
0x180149fd4  jnz     short loc_180149FC6
0x180149fd6  mov     ecx, r13d
0x180149fd9  lea     rdx, Src; "usp10.dll"
0x180149fe0  inc     ecx
0x180149fe2  lea     rdx, [rdx+2]
0x180149fe6  cmp     [rdx], r13w
0x180149fea  jnz     short loc_180149FE0
0x180149fec  lea     esi, [rcx+rax]
0x180149fef  cmp     esi, eax
0x180149ff1  jb      loc_18014A0E4
0x180149ff7  cmp     esi, 100h
0x180149ffd  jnb     short loc_18014A033
0x180149fff  movsxd  r8, ecx
0x18014a002  lea     rdx, Src; "usp10.dll"
0x18014a009  mov     eax, eax
0x18014a00b  add     r8, r8; Size
0x18014a00e  lea     rcx, [rbx+rax*2]; void *
0x18014a012  call    memcpy_0
0x18014a017  xor     r8d, r8d; dwFlags
0x18014a01a  mov     [rbx+rsi*2], r13w
0x18014a01f  xor     edx, edx; hFile
0x18014a021  mov     rcx, rbx; lpLibFileName
0x18014a024  call    cs:__imp_LoadLibraryExW
0x18014a02b  nop     dword ptr [rax+rax+00h]
0x18014a030  mov     rdi, rax
0x18014a033  mov     rcx, rbx
0x18014a036  call    GpFree
0x18014a03b  test    rdi, rdi
0x18014a03e  jz      loc_18014A102
0x18014a044  lea     rdx, aScriptbreak; "ScriptBreak"
0x18014a04b  mov     rcx, rdi; hModule
0x18014a04e  call    cs:__imp_GetProcAddress
0x18014a055  nop     dword ptr [rax+rax+00h]
0x18014a05a  lea     rdx, aScriptitemize; "ScriptItemize"
0x18014a061  mov     rcx, rdi; hModule
0x18014a064  mov     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014a06b  call    cs:__imp_GetProcAddress
0x18014a072  nop     dword ptr [rax+rax+00h]
0x18014a077  test    rax, rax
0x18014a07a  jz      short loc_18014A0F3
0x18014a07c  cmp     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, r13; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014a083  jz      short loc_18014A0F3
0x18014a085  xor     r9d, r9d
0x18014a088  mov     [rsp+88h+var_48], r13d
0x18014a08d  lea     rcx, [rsp+88h+var_48]
0x18014a092  mov     [rsp+88h+var_58], rcx
0x18014a097  lea     rcx, [rsp+88h+var_40]
0x18014a09c  mov     [rsp+88h+var_60], rcx
0x18014a0a1  lea     rcx, dword_18018E82C
0x18014a0a8  lea     edx, [r9+1]
0x18014a0ac  mov     [rsp+88h+var_68], r13
0x18014a0b1  lea     r8d, [r9+2]
0x18014a0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014a0ba  test    eax, eax
0x18014a0bc  js      short loc_18014A0F3
0x18014a0be  mov     eax, dword ptr [rsp+88h+var_3C]
0x18014a0c2  and     eax, 3FFh
0x18014a0c7  mov     cs:?UniscribeDllModule@Globals@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * Globals::UniscribeDllModule
0x18014a0ce  mov     cs:?ScriptThaiUsp@@3HA, eax; int ScriptThaiUsp
0x18014a0d4  lea     rax, ?GdipThaiBreakingFunctionInUniscribe@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInUniscribe(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014a0db  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014a0e2  jmp     short loc_18014A102
0x18014a0e4  mov     rcx, rbx
0x18014a0e7  call    GpFree
0x18014a0ec  mov     eax, 80070216h
0x18014a0f1  jmp     short loc_18014A11A
0x18014a0f3  mov     rcx, rdi; hLibModule
0x18014a0f6  call    cs:__imp_FreeLibrary
0x18014a0fd  nop     dword ptr [rax+rax+00h]
0x18014a102  mov     rax, cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x18014a109  mov     r9, rbp
0x18014a10c  mov     r8, r14
0x18014a10f  mov     edx, r15d
0x18014a112  mov     rcx, r12
0x18014a115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014a11a  lea     r11, [rsp+88h+var_28]
0x18014a11f  mov     rbx, [r11+30h]
0x18014a123  mov     rbp, [r11+38h]
0x18014a127  mov     rsi, [r11+40h]
0x18014a12b  mov     rsp, r11
0x18014a12e  pop     r15
0x18014a130  pop     r14
0x18014a132  pop     r13
0x18014a134  pop     r12
0x18014a136  pop     rdi
0x18014a137  retn
```
