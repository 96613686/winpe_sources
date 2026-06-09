# CDragProxy::Register(void)

- ea: `0x180087420`
- end: `0x1800874d0`
- name: `?Register@CDragProxy@@QEAAHXZ`
- size: `176`
- prototype: `__int64 __fastcall(CDragProxy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18008760c`

## callees

- `0x180087420`
- `0x180090020`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180087446`
- `KERNEL32!LoadLibraryW` at `0x180087446`
- `KERNEL32!GetProcAddress` at `0x18008745f`
- `KERNEL32!GetProcAddress` at `0x18008747f`
- `KERNEL32!GetProcAddress` at `0x1800874a6`
- `KERNEL32!GetProcAddress` at `0x18008745f`
- `KERNEL32!GetProcAddress` at `0x18008747f`
- `KERNEL32!GetProcAddress` at `0x1800874a6`
- `KERNEL32!GetModuleHandleW` at `0x180087434`
- `KERNEL32!GetModuleHandleW` at `0x180087434`
- `KERNEL32!FreeLibrary` at `0x1800874b5`
- `KERNEL32!FreeLibrary` at `0x1800874b5`

## string_xrefs

- `0x18008742d`: `OLE32.DLL`
- `0x18008743f`: `OLE32.DLL`

## pseudocode

```c
__int64 __fastcall CDragProxy::Register(CDragProxy *this)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 v4; // rbx
  FARPROC v5; // rax
  void (*v7)(void); // rax

  ModuleHandleW = GetModuleHandleW(L"OLE32.DLL");
  if ( ModuleHandleW )
    ModuleHandleW = LoadLibraryW(L"OLE32.DLL");
  *((_QWORD *)this + 10) = ModuleHandleW;
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CoInitialize");
    if ( ((int (__fastcall *)(_QWORD))ProcAddress)(0) >= 0 )
    {
      v4 = *((_QWORD *)this + 2);
      v5 = GetProcAddress(*((HMODULE *)this + 10), "RegisterDragDrop");
      if ( ((int (__fastcall *)(__int64, CDragProxy *))v5)(v4, this) >= 0 )
        return 1;
      v7 = (void (*)(void))GetProcAddress(*((HMODULE *)this + 10), "CoUninitialize");
      v7();
    }
    FreeLibrary(*((HMODULE *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180087420  mov     [rsp+arg_0], rbx
0x180087425  push    rdi
0x180087426  sub     rsp, 20h
0x18008742a  mov     rdi, rcx
0x18008742d  lea     rcx, aOle32Dll; "OLE32.DLL"
0x180087434  call    cs:__imp_GetModuleHandleW
0x18008743a  test    rax, rax
0x18008743d  jz      short loc_18008744C
0x18008743f  lea     rcx, aOle32Dll; "OLE32.DLL"
0x180087446  call    cs:__imp_LoadLibraryW
0x18008744c  mov     [rdi+50h], rax
0x180087450  test    rax, rax
0x180087453  jz      short loc_1800874C3
0x180087455  lea     rdx, aCoinitialize; "CoInitialize"
0x18008745c  mov     rcx, rax; hModule
0x18008745f  call    cs:__imp_GetProcAddress
0x180087465  xor     ecx, ecx
0x180087467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008746c  test    eax, eax
0x18008746e  js      short loc_1800874B1
0x180087470  mov     rcx, [rdi+50h]; hModule
0x180087474  lea     rdx, aRegisterdragdr; "RegisterDragDrop"
0x18008747b  mov     rbx, [rdi+10h]
0x18008747f  call    cs:__imp_GetProcAddress
0x180087485  mov     rdx, rdi
0x180087488  mov     rcx, rbx
0x18008748b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087490  test    eax, eax
0x180087492  js      short loc_18008749B
0x180087494  mov     eax, 1
0x180087499  jmp     short loc_1800874C5
0x18008749b  mov     rcx, [rdi+50h]; hModule
0x18008749f  lea     rdx, aCouninitialize; "CoUninitialize"
0x1800874a6  call    cs:__imp_GetProcAddress
0x1800874ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800874b1  mov     rcx, [rdi+50h]; hLibModule
0x1800874b5  call    cs:__imp_FreeLibrary
0x1800874bb  mov     qword ptr [rdi+50h], 0
0x1800874c3  xor     eax, eax
0x1800874c5  mov     rbx, [rsp+28h+arg_0]
0x1800874ca  add     rsp, 20h
0x1800874ce  pop     rdi
0x1800874cf  retn
```
