# LoadModuleWithFailureDiagnosis

- ea: `0x1800532fc`
- end: `0x18005349f`
- name: `LoadModuleWithFailureDiagnosis`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180047b90`
- `0x1800532fc`

## callees

- `0x1800532fc`
- `0x1800534a8`
- `0x1800664c8`
- `0x180083bc2`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180053319`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180053319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053410`
- `imagehlp!ImageRvaToVa` at `0x1800533c2`
- `imagehlp!ImageRvaToVa` at `0x1800533c2`
- `imagehlp!UnMapAndLoad` at `0x1800533e4`
- `imagehlp!UnMapAndLoad` at `0x1800533e4`
- `imagehlp!ImageNtHeader` at `0x1800533ae`
- `imagehlp!ImageNtHeader` at `0x1800533ae`
- `imagehlp!MapAndLoad` at `0x18005335d`
- `imagehlp!MapAndLoad` at `0x18005335d`
- `imagehlp!ImageDirectoryEntryToData` at `0x180053388`
- `imagehlp!ImageDirectoryEntryToData` at `0x180053388`

## pseudocode

```c
HMODULE __fastcall LoadModuleWithFailureDiagnosis(const CHAR *a1)
{
  HMODULE result; // rax
  signed int LastError; // eax
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  ULONG v6; // ebx
  struct _IMAGE_NT_HEADERS64 *v7; // rax
  PVOID v8; // rax
  signed int v9; // eax
  _LOADED_IMAGE LoadedImage; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  ULONG Size; // [rsp+A8h] [rbp+10h] BYREF

  result = LoadLibraryExA(a1, 0, 0x800u);
  if ( !result )
  {
    LastError = GetLastError();
    if ( LastError == 126 )
    {
      memset_0(&LoadedImage, 0, sizeof(LoadedImage));
      if ( MapAndLoad(a1, 0, &LoadedImage, 1, 1) )
      {
        Size = 0;
        v4 = ImageDirectoryEntryToData(LoadedImage.MappedAddress, 0, 1u, &Size);
        v5 = v4;
        if ( v4 && Size && v4[3] )
        {
          do
          {
            v6 = v5[3];
            v7 = ImageNtHeader(LoadedImage.MappedAddress);
            v8 = ImageRvaToVa(v7, LoadedImage.MappedAddress, v6, 0);
            if ( v8 )
              LoadModuleWithFailureDiagnosis(v8);
            v5 += 5;
          }
          while ( v5[3] );
        }
        UnMapAndLoad(&LoadedImage);
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
          "%hs",
          a1);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
        (const char *)(unsigned int)v9,
        (int)"%hs",
        a1);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
      (const char *)(unsigned int)LastError,
      (int)"%hs",
      a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800532fc  mov     [rsp+arg_0], rbx
0x180053301  mov     [rsp+arg_10], rsi
0x180053306  push    rdi
0x180053307  sub     rsp, 90h
0x18005330e  xor     edx, edx; hFile
0x180053310  mov     r8d, 800h; dwFlags
0x180053316  mov     rsi, rcx
0x180053319  call    cs:__imp_LoadLibraryExA
0x18005331f  test    rax, rax
0x180053322  jnz     loc_18005348A
0x180053328  call    cs:__imp_GetLastError
0x18005332e  cmp     eax, 7Eh ; '~'
0x180053331  jnz     loc_180053450
0x180053337  xor     edx, edx; Val
0x180053339  lea     r8d, [rax-26h]; Size
0x18005333d  lea     rcx, [rsp+98h+LoadedImage]; void *
0x180053342  call    memset_0
0x180053347  mov     ebx, 1
0x18005334c  lea     r8, [rsp+98h+LoadedImage]; LoadedImage
0x180053351  mov     r9d, ebx; DotDll
0x180053354  mov     [rsp+98h+ReadOnly], ebx; ReadOnly
0x180053358  xor     edx, edx; DllPath
0x18005335a  mov     rcx, rsi; ImageName
0x18005335d  call    cs:__imp_MapAndLoad
0x180053363  test    eax, eax
0x180053365  jz      loc_180053410
0x18005336b  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180053370  lea     r9, [rsp+98h+Size]; Size
0x180053378  mov     r8d, ebx; DirectoryEntry
0x18005337b  mov     [rsp+98h+Size], 0
0x180053386  xor     edx, edx; MappedAsImage
0x180053388  call    cs:__imp_ImageDirectoryEntryToData
0x18005338e  mov     rdi, rax
0x180053391  test    rax, rax
0x180053394  jz      short loc_1800533DF
0x180053396  cmp     [rsp+98h+Size], 0
0x18005339e  jz      short loc_1800533DF
0x1800533a0  cmp     dword ptr [rax+0Ch], 0
0x1800533a4  jz      short loc_1800533DF
0x1800533a6  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x1800533ab  mov     ebx, [rdi+0Ch]
0x1800533ae  call    cs:__imp_ImageNtHeader
0x1800533b4  mov     rdx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x1800533b9  xor     r9d, r9d; LastRvaSection
0x1800533bc  mov     rcx, rax; NtHeaders
0x1800533bf  mov     r8d, ebx; Rva
0x1800533c2  call    cs:__imp_ImageRvaToVa
0x1800533c8  test    rax, rax
0x1800533cb  jz      short loc_1800533D5
0x1800533cd  mov     rcx, rax
0x1800533d0  call    LoadModuleWithFailureDiagnosis
0x1800533d5  add     rdi, 14h
0x1800533d9  cmp     dword ptr [rdi+0Ch], 0
0x1800533dd  jnz     short loc_1800533A6
0x1800533df  lea     rcx, [rsp+98h+LoadedImage]; LoadedImage
0x1800533e4  call    cs:__imp_UnMapAndLoad
0x1800533ea  mov     rcx, [rsp+98h]; this
0x1800533f2  lea     r9, aHs; "%hs"
0x1800533f9  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180053400  mov     qword ptr [rsp+98h+ReadOnly], rsi; char *
0x180053405  mov     edx, 2Fh ; '/'; void *
0x18005340a  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x180053410  call    cs:__imp_GetLastError
0x180053416  test    eax, eax
0x180053418  jle     short loc_180053422
0x18005341a  movzx   eax, ax
0x18005341d  or      eax, 80070000h
0x180053422  mov     rcx, [rsp+98h]; this
0x18005342a  lea     rdx, aHs; "%hs"
0x180053431  mov     [rsp+98h+var_70], rsi; char *
0x180053436  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18005343d  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x180053442  mov     r9d, eax; char *
0x180053445  mov     edx, 33h ; '3'; void *
0x18005344a  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053450  test    eax, eax
0x180053452  jle     short loc_18005345C
0x180053454  movzx   eax, ax
0x180053457  or      eax, 80070000h
0x18005345c  mov     rcx, [rsp+98h]; this
0x180053464  lea     rdx, aHs; "%hs"
0x18005346b  mov     [rsp+98h+var_70], rsi; char *
0x180053470  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180053477  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x18005347c  mov     r9d, eax; char *
0x18005347f  mov     edx, 38h ; '8'; void *
0x180053484  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005348a  lea     r11, [rsp+98h+var_8]
0x180053492  mov     rbx, [r11+10h]
0x180053496  mov     rsi, [r11+20h]
0x18005349a  mov     rsp, r11
0x18005349d  pop     rdi
0x18005349e  retn
```
