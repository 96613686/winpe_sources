# Microsoft::Windows::Performance::CAeDelayLoad::LoadAeModule(void)

- ea: `0x180015c44`
- end: `0x180015cee`
- name: `?LoadAeModule@CAeDelayLoad@Performance@Windows@Microsoft@@AEAAPEAUHINSTANCE__@@XZ`
- size: `170`
- prototype: `HINSTANCE __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015bc0`

## callees

- `0x180015c44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015c5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180015c5f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015c97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015ccf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015c97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015ccf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015cb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015c7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015cb6`

## string_xrefs

- `0x180015c50`: `aepic.dll`

## pseudocode

```c
HINSTANCE __fastcall Microsoft::Windows::Performance::CAeDelayLoad::LoadAeModule(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax

  *(_BYTE *)this = 1;
  Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
  *((_QWORD *)this + 1) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PicRetrieveFileInfo");
    *((_QWORD *)this + 2) = ProcAddress;
    if ( !ProcAddress )
    {
      FreeLibrary(*((HMODULE *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    v4 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
    *((_QWORD *)this + 3) = v4;
    if ( !v4 )
    {
      FreeLibrary(*((HMODULE *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
  }
  return (HINSTANCE)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x180015c44  push    rbx
0x180015c46  sub     rsp, 20h
0x180015c4a  mov     rbx, rcx
0x180015c4d  mov     byte ptr [rcx], 1
0x180015c50  lea     rcx, aAepicDll; "aepic.dll"
0x180015c57  xor     edx, edx; hFile
0x180015c59  mov     r8d, 800h; dwFlags
0x180015c5f  call    cs:__imp_LoadLibraryExW
0x180015c66  nop     dword ptr [rax+rax+00h]
0x180015c6b  mov     [rbx+8], rax
0x180015c6f  test    rax, rax
0x180015c72  jz      short loc_180015CE3
0x180015c74  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x180015c7b  mov     rcx, rax; hModule
0x180015c7e  call    cs:__imp_GetProcAddress
0x180015c85  nop     dword ptr [rax+rax+00h]
0x180015c8a  mov     [rbx+10h], rax
0x180015c8e  test    rax, rax
0x180015c91  jnz     short loc_180015CAB
0x180015c93  mov     rcx, [rbx+8]; hLibModule
0x180015c97  call    cs:__imp_FreeLibrary
0x180015c9e  nop     dword ptr [rax+rax+00h]
0x180015ca3  mov     qword ptr [rbx+8], 0
0x180015cab  mov     rcx, [rbx+8]; hModule
0x180015caf  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180015cb6  call    cs:__imp_GetProcAddress
0x180015cbd  nop     dword ptr [rax+rax+00h]
0x180015cc2  mov     [rbx+18h], rax
0x180015cc6  test    rax, rax
0x180015cc9  jnz     short loc_180015CE3
0x180015ccb  mov     rcx, [rbx+8]; hLibModule
0x180015ccf  call    cs:__imp_FreeLibrary
0x180015cd6  nop     dword ptr [rax+rax+00h]
0x180015cdb  mov     qword ptr [rbx+8], 0
0x180015ce3  mov     rax, [rbx+8]
0x180015ce7  add     rsp, 20h
0x180015ceb  pop     rbx
0x180015cec  retn
```
