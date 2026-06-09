# GameConfigStore::GameConfigStore(void)

- ea: `0x180050ab0`
- end: `0x180050b42`
- name: `??0GameConfigStore@@QEAA@XZ`
- size: `146`
- prototype: `GameConfigStore *__fastcall(GameConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18008bfbc`

## callees

- `0x180010d40`
- `0x180050ab0`
- `0x180050b48`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050b10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050b10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050aef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050aef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180050ad8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180050ad8`

## string_xrefs

- `0x180050ad1`: `csrsrv.dll`
- `0x180050b06`: `CreateGameConfigStoreClient`
- `0x180050ae8`: `ext-ms-win-core-resourcepolicy-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GameConfigStore *__fastcall GameConfigStore::GameConfigStore(GameConfigStore *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v4; // eax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( !GetModuleHandleA("csrsrv.dll") )
  {
    Library = LoadLibraryExW(L"ext-ms-win-core-resourcepolicy-l1-1-0.dll", 0, 0);
    UniqueHMODULE::attach(this, Library);
  }
  if ( !*(_QWORD *)this )
    DXGIThrowFailure(-2147418113);
  ProcAddress = GetProcAddress(*(HMODULE *)this, "CreateGameConfigStoreClient");
  v4 = ((__int64 (__fastcall *)(char *))ProcAddress)((char *)this + 8);
  DXGIThrowFailure(v4);
  return this;
}

```

## disassembly

```asm
0x180050ab0  mov     [rsp+arg_8], rbx
0x180050ab5  mov     [rsp+arg_0], rcx
0x180050aba  push    rdi
0x180050abb  sub     rsp, 20h
0x180050abf  mov     rbx, rcx
0x180050ac2  mov     qword ptr [rcx], 0
0x180050ac9  mov     qword ptr [rcx+8], 0
0x180050ad1  lea     rcx, aCsrsrvDll; "csrsrv.dll"
0x180050ad8  call    cs:__imp_GetModuleHandleA
0x180050ade  test    rax, rax
0x180050ae1  jnz     short loc_180050B00
0x180050ae3  xor     r8d, r8d; dwFlags
0x180050ae6  xor     edx, edx; hFile
0x180050ae8  lea     rcx, aExtMsWinCoreRe; "ext-ms-win-core-resourcepolicy-l1-1-0.d"...
0x180050aef  call    cs:__imp_LoadLibraryExW
0x180050af5  mov     rdx, rax; HINSTANCE
0x180050af8  mov     rcx, rbx; this
0x180050afb  call    ?attach@UniqueHMODULE@@QEAAXPEAUHINSTANCE__@@@Z; UniqueHMODULE::attach(HINSTANCE__ *)
0x180050b00  cmp     qword ptr [rbx], 0
0x180050b04  jz      short loc_180050B35
0x180050b06  lea     rdx, aCreategameconf; "CreateGameConfigStoreClient"
0x180050b0d  mov     rcx, [rbx]; hModule
0x180050b10  call    cs:__imp_GetProcAddress
0x180050b16  lea     rcx, [rbx+8]
0x180050b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b1f  mov     ecx, eax; int
0x180050b21  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180050b26  nop
0x180050b27  mov     rax, rbx
0x180050b2a  mov     rbx, [rsp+28h+arg_8]
0x180050b2f  add     rsp, 20h
0x180050b33  pop     rdi
0x180050b34  retn
0x180050b35  mov     ecx, 8000FFFFh; int
0x180050b3a  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180050b3f  jmp     short loc_180050B06
```
