# WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(HWND__ *,int *,int *,int *)

- ea: `0x180008d9c`
- end: `0x180008e15`
- name: `?DoModal@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@QEAAJPEAUHWND__@@PEAH11@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008e20`
- `0x18000ae20`
- `0x18000aed8`
- `0x18001035e`

## callees

- `0x180008d9c`
- `0x180011010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180008dc5`
- `KERNEL32!LoadLibraryW` at `0x180008dc5`
- `KERNEL32!GetProcAddress` at `0x180008ddd`
- `KERNEL32!GetProcAddress` at `0x180008ddd`
- `KERNEL32!FreeLibrary` at `0x180008dfd`
- `KERNEL32!FreeLibrary` at `0x180008dfd`

## string_xrefs

- `0x180008db9`: `comctl32.dll`
- `0x180008dd3`: `TaskDialogIndirect`

## pseudocode

```c
__int64 __fastcall WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(__int64 a1, __int64 a2)
{
  unsigned int v3; // esi
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax

  if ( !*(_QWORD *)(a1 + 4) )
    *(_QWORD *)(a1 + 4) = a2;
  v3 = -2147418113;
  LibraryW = LoadLibraryW(L"comctl32.dll");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "TaskDialogIndirect");
    if ( ProcAddress )
      v3 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(a1, 0, 0, 0);
    FreeLibrary(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180008d9c  mov     [rsp+arg_0], rbx
0x180008da1  mov     [rsp+arg_8], rsi
0x180008da6  push    rdi
0x180008da7  sub     rsp, 30h
0x180008dab  cmp     qword ptr [rcx+4], 0
0x180008db0  mov     rdi, rcx
0x180008db3  jnz     short loc_180008DB9
0x180008db5  mov     [rcx+4], rdx
0x180008db9  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180008dc0  mov     esi, 8000FFFFh
0x180008dc5  call    cs:__imp_LoadLibraryW
0x180008dcb  mov     rbx, rax
0x180008dce  test    rax, rax
0x180008dd1  jz      short loc_180008E03
0x180008dd3  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180008dda  mov     rcx, rax; hModule
0x180008ddd  call    cs:__imp_GetProcAddress
0x180008de3  test    rax, rax
0x180008de6  jz      short loc_180008DFA
0x180008de8  xor     r9d, r9d
0x180008deb  xor     r8d, r8d
0x180008dee  xor     edx, edx
0x180008df0  mov     rcx, rdi
0x180008df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df8  mov     esi, eax
0x180008dfa  mov     rcx, rbx; hLibModule
0x180008dfd  call    cs:__imp_FreeLibrary
0x180008e03  mov     rbx, [rsp+38h+arg_0]
0x180008e08  mov     eax, esi
0x180008e0a  mov     rsi, [rsp+38h+arg_8]
0x180008e0f  add     rsp, 30h
0x180008e13  pop     rdi
0x180008e14  retn
```
