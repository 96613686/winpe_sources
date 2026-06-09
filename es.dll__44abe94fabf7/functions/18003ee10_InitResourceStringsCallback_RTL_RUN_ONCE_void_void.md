# InitResourceStringsCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18003ee10`
- end: `0x18003eeaf`
- name: `?InitResourceStringsCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `159`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003ee10`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003ee7c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003ee7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ee2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ee2a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ee9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ee9c`

## string_xrefs

- `0x18003ee1d`: `comres.dll`

## pseudocode

```c
__int64 __fastcall InitResourceStringsCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  unsigned int v3; // esi
  HMODULE Library; // rbp
  unsigned __int64 i; // rbx
  WCHAR *lpBuffer; // rax

  v3 = 0;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  if ( Library )
  {
    v3 = 1;
    for ( i = 0; i < 3; ++i )
    {
      lpBuffer = (WCHAR *)(&off_180063990)[2 * i];
      if ( !*(_QWORD *)lpBuffer )
      {
        FormatMessageW(0xB00u, Library, (DWORD)(&off_180063990)[2 * i + 1], 0, lpBuffer, 0, 0);
        v3 &= -(*(&off_180063990)[2 * i] != 0);
      }
    }
    FreeLibrary(Library);
  }
  return v3;
}

```

## disassembly

```asm
0x18003ee10  push    rbx
0x18003ee12  push    rbp
0x18003ee13  push    rsi
0x18003ee14  push    rdi
0x18003ee15  push    r15
0x18003ee17  sub     rsp, 40h
0x18003ee1b  xor     esi, esi
0x18003ee1d  lea     rcx, LibFileName; "comres.dll"
0x18003ee24  xor     edx, edx; hFile
0x18003ee26  lea     r8d, [rsi+2]; dwFlags
0x18003ee2a  call    cs:__imp_LoadLibraryExW
0x18003ee30  mov     rbp, rax
0x18003ee33  test    rax, rax
0x18003ee36  jz      short loc_18003EEA2
0x18003ee38  mov     esi, 1
0x18003ee3d  lea     r15, off_180063990
0x18003ee44  xor     ebx, ebx
0x18003ee46  mov     rdi, rbx
0x18003ee49  add     rdi, rdi
0x18003ee4c  mov     rax, [r15+rdi*8]
0x18003ee50  cmp     qword ptr [rax], 0
0x18003ee54  jnz     short loc_18003EE90
0x18003ee56  mov     r8d, [r15+rdi*8+8]; dwMessageId
0x18003ee5b  xor     r9d, r9d; dwLanguageId
0x18003ee5e  mov     [rsp+68h+Arguments], 0; Arguments
0x18003ee67  mov     rdx, rbp; lpSource
0x18003ee6a  mov     [rsp+68h+nSize], 0; nSize
0x18003ee72  mov     ecx, 0B00h; dwFlags
0x18003ee77  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18003ee7c  call    cs:__imp_FormatMessageW
0x18003ee82  mov     rax, [r15+rdi*8]
0x18003ee86  mov     rcx, [rax]
0x18003ee89  neg     rcx
0x18003ee8c  sbb     eax, eax
0x18003ee8e  and     esi, eax
0x18003ee90  inc     rbx
0x18003ee93  cmp     rbx, 3
0x18003ee97  jb      short loc_18003EE46
0x18003ee99  mov     rcx, rbp; hLibModule
0x18003ee9c  call    cs:__imp_FreeLibrary
0x18003eea2  mov     eax, esi
0x18003eea4  add     rsp, 40h
0x18003eea8  pop     r15
0x18003eeaa  pop     rdi
0x18003eeab  pop     rsi
0x18003eeac  pop     rbp
0x18003eead  pop     rbx
0x18003eeae  retn
```
