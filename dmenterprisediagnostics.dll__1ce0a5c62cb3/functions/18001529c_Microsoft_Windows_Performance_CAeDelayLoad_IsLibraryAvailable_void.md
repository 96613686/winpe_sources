# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x18001529c`
- end: `0x180015348`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017364`
- `0x1800176b0`

## callees

- `0x18001529c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800152c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800152c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800152ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001531b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800152ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001531b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800152dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015308`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800152dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015308`

## string_xrefs

- `0x1800152b6`: `aepic.dll`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  char v2; // di
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  v2 = 1;
  if ( !*(_BYTE *)this )
  {
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
      v5 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
      *((_QWORD *)this + 3) = v5;
      if ( !v5 )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
    }
  }
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18001529c  mov     [rsp+arg_0], rbx
0x1800152a1  push    rdi
0x1800152a2  sub     rsp, 20h
0x1800152a6  cmp     byte ptr [rcx], 0
0x1800152a9  mov     rbx, rcx
0x1800152ac  mov     dil, 1
0x1800152af  jnz     short loc_180015329
0x1800152b1  mov     [rcx], dil
0x1800152b4  xor     edx, edx; hFile
0x1800152b6  lea     rcx, aAepicDll; "aepic.dll"
0x1800152bd  mov     r8d, 800h; dwFlags
0x1800152c3  call    cs:__imp_LoadLibraryExW
0x1800152c9  mov     [rbx+8], rax
0x1800152cd  test    rax, rax
0x1800152d0  jz      short loc_180015329
0x1800152d2  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x1800152d9  mov     rcx, rax; hModule
0x1800152dc  call    cs:__imp_GetProcAddress
0x1800152e2  mov     [rbx+10h], rax
0x1800152e6  test    rax, rax
0x1800152e9  jnz     short loc_1800152FD
0x1800152eb  mov     rcx, [rbx+8]; hLibModule
0x1800152ef  call    cs:__imp_FreeLibrary
0x1800152f5  mov     qword ptr [rbx+8], 0
0x1800152fd  mov     rcx, [rbx+8]; hModule
0x180015301  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180015308  call    cs:__imp_GetProcAddress
0x18001530e  mov     [rbx+18h], rax
0x180015312  test    rax, rax
0x180015315  jnz     short loc_180015329
0x180015317  mov     rcx, [rbx+8]; hLibModule
0x18001531b  call    cs:__imp_FreeLibrary
0x180015321  mov     qword ptr [rbx+8], 0
0x180015329  cmp     qword ptr [rbx+10h], 0
0x18001532e  jz      short loc_180015337
0x180015330  cmp     qword ptr [rbx+18h], 0
0x180015335  jnz     short loc_18001533A
0x180015337  xor     dil, dil
0x18001533a  mov     rbx, [rsp+28h+arg_0]
0x18001533f  mov     al, dil
0x180015342  add     rsp, 20h
0x180015346  pop     rdi
0x180015347  retn
```
