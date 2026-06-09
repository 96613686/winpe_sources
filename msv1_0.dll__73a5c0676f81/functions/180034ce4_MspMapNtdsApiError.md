# MspMapNtdsApiError

- ea: `0x180034ce4`
- end: `0x180034d7c`
- name: `MspMapNtdsApiError`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032c8c`
- `0x180033148`

## callees

- `0x180034ce4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034d3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034d27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034d27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034d56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180034d56`

## string_xrefs

- `0x180034d1e`: `rpcrt4.dll`

## pseudocode

```c
__int64 __fastcall MspMapNtdsApiError(int a1, unsigned int a2)
{
  int v3; // ebx
  unsigned int i; // eax
  HMODULE Library; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax

  v3 = a1;
  if ( a1 >= 0 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( LODWORD(qword_180072530[i]) == a1 )
        return HIDWORD(qword_180072530[i]);
    }
    Library = LoadLibraryExW(L"rpcrt4.dll", 0, 0);
    v7 = Library;
    if ( !Library )
      return a2;
    ProcAddress = GetProcAddress(Library, "I_RpcMapWin32Status");
    if ( ProcAddress )
      v3 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)((unsigned int)v3);
    FreeLibrary(v7);
    if ( v3 >= 0 )
      return a2;
  }
  if ( v3 == -1073741823 )
    return a2;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180034ce4  mov     [rsp+arg_0], rbx
0x180034ce9  mov     [rsp+arg_8], rsi
0x180034cee  push    rdi
0x180034cef  sub     rsp, 20h
0x180034cf3  mov     esi, edx
0x180034cf5  mov     ebx, ecx
0x180034cf7  test    ecx, ecx
0x180034cf9  js      short loc_180034D60
0x180034cfb  xor     eax, eax
0x180034cfd  lea     rdx, qword_180072530
0x180034d04  cmp     eax, 4
0x180034d07  jnb     short loc_180034D1B
0x180034d09  movsxd  rcx, eax
0x180034d0c  cmp     [rdx+rcx*8], ebx
0x180034d0f  jz      short loc_180034D15
0x180034d11  inc     eax
0x180034d13  jmp     short loc_180034D04
0x180034d15  mov     eax, [rdx+rcx*8+4]
0x180034d19  jmp     short loc_180034D6C
0x180034d1b  xor     r8d, r8d; dwFlags
0x180034d1e  lea     rcx, aRpcrt4Dll_0; "rpcrt4.dll"
0x180034d25  xor     edx, edx; hFile
0x180034d27  call    cs:__imp_LoadLibraryExW
0x180034d2d  mov     rdi, rax
0x180034d30  test    rax, rax
0x180034d33  jz      short loc_180034D68
0x180034d35  lea     rdx, aIRpcmapwin32st_0; "I_RpcMapWin32Status"
0x180034d3c  mov     rcx, rax; hModule
0x180034d3f  call    cs:__imp_GetProcAddress
0x180034d45  test    rax, rax
0x180034d48  jz      short loc_180034D53
0x180034d4a  mov     ecx, ebx
0x180034d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d51  mov     ebx, eax
0x180034d53  mov     rcx, rdi; hLibModule
0x180034d56  call    cs:__imp_FreeLibrary
0x180034d5c  test    ebx, ebx
0x180034d5e  jns     short loc_180034D68
0x180034d60  cmp     ebx, 0C0000001h
0x180034d66  jnz     short loc_180034D6A
0x180034d68  mov     ebx, esi
0x180034d6a  mov     eax, ebx
0x180034d6c  mov     rbx, [rsp+28h+arg_0]
0x180034d71  mov     rsi, [rsp+28h+arg_8]
0x180034d76  add     rsp, 20h
0x180034d7a  pop     rdi
0x180034d7b  retn
```
