# LoadInjector

- ea: `0x180006850`
- end: `0x18000694f`
- name: `LoadInjector`
- size: `255`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006958`

## callees

- `0x18000175c`
- `0x180006850`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800068fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006938`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006938`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800068c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800068a6`

## pseudocode

```c
void __fastcall LoadInjector(LPCWSTR lpLibFileName)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-18h]
  int v7; // [rsp+34h] [rbp-14h]

  if ( !nitsinj_handle )
  {
    if ( NITS_PRESENCE_STUB == 1
      || (v6 = 0, v5 = 0, v7 = -3, !((unsigned int (__fastcall *)(__int128 *, _QWORD))NITS_STUB[0])(&v5, 0)) )
    {
      if ( lpLibFileName )
      {
        Library = LoadLibraryExW(lpLibFileName, 0, 0);
        nitsinj_handle = Library;
        if ( !Library )
          return;
        ProcAddress = GetProcAddress(Library, "NitsStartInjector");
        if ( ProcAddress )
        {
          NitsStartInjectorFunc = (__int64)ProcAddress;
          v4 = GetProcAddress(nitsinj_handle, "NitsStopInjector");
          if ( v4 )
          {
            NitsStopInjectorFunc = (__int64)v4;
            if ( !(unsigned int)((__int64 (*)(void))NitsStartInjectorFunc)() )
            {
              atexit((void (__cdecl *)())unloadInjector);
              return;
            }
          }
        }
        FreeLibrary(nitsinj_handle);
      }
    }
    else
    {
      SetLastError(0xEu);
    }
    nitsinj_handle = 0;
  }
}

```

## disassembly

```asm
0x180006850  push    rbx
0x180006852  sub     rsp, 40h
0x180006856  cmp     cs:nitsinj_handle, 0
0x18000685e  mov     rbx, rcx
0x180006861  jnz     loc_180006949
0x180006867  cmp     cs:NITS_PRESENCE_STUB, 1
0x18000686f  jz      short loc_1800068B1
0x180006871  mov     rax, cs:NITS_STUB
0x180006878  lea     rcx, [rsp+48h+var_28]
0x18000687d  xorps   xmm0, xmm0
0x180006880  mov     [rsp+48h+var_18], 0
0x180006888  xor     edx, edx
0x18000688a  movdqa  [rsp+48h+var_28], xmm0
0x180006890  mov     [rsp+48h+var_14], 0FFFFFFFDh
0x180006898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000689d  test    eax, eax
0x18000689f  jz      short loc_1800068B1
0x1800068a1  mov     ecx, 0Eh; dwErrCode
0x1800068a6  call    cs:__imp_SetLastError
0x1800068ac  jmp     loc_18000693E
0x1800068b1  test    rbx, rbx
0x1800068b4  jz      loc_18000693E
0x1800068ba  xor     r8d, r8d; dwFlags
0x1800068bd  xor     edx, edx; hFile
0x1800068bf  mov     rcx, rbx; lpLibFileName
0x1800068c2  call    cs:__imp_LoadLibraryExW
0x1800068c8  mov     cs:nitsinj_handle, rax
0x1800068cf  test    rax, rax
0x1800068d2  jz      short loc_180006949
0x1800068d4  lea     rdx, ProcName; "NitsStartInjector"
0x1800068db  mov     rcx, rax; hModule
0x1800068de  call    cs:__imp_GetProcAddress
0x1800068e4  test    rax, rax
0x1800068e7  jz      short loc_180006931
0x1800068e9  mov     rcx, cs:nitsinj_handle; hModule
0x1800068f0  lea     rdx, aNitsstopinject; "NitsStopInjector"
0x1800068f7  mov     cs:NitsStartInjectorFunc, rax
0x1800068fe  call    cs:__imp_GetProcAddress
0x180006904  test    rax, rax
0x180006907  jz      short loc_180006931
0x180006909  mov     cs:NitsStopInjectorFunc, rax
0x180006910  mov     rax, cs:NitsStartInjectorFunc
0x180006917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000691c  test    eax, eax
0x18000691e  jnz     short loc_180006931
0x180006920  lea     rcx, unloadInjector
0x180006927  add     rsp, 40h
0x18000692b  pop     rbx
0x18000692c  jmp     atexit
0x180006931  mov     rcx, cs:nitsinj_handle; hLibModule
0x180006938  call    cs:__imp_FreeLibrary
0x18000693e  mov     cs:nitsinj_handle, 0
0x180006949  add     rsp, 40h
0x18000694d  pop     rbx
0x18000694e  retn
```
