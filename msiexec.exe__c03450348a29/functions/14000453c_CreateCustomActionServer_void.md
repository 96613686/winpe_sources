# CreateCustomActionServer(void)

- ea: `0x14000453c`
- end: `0x1400045e9`
- name: `?CreateCustomActionServer@@YAPEAUIUnknown@@XZ`
- size: `173`
- prototype: `struct IUnknown *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x14000453c`
- `0x14000a010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140004565`
- `KERNEL32!LoadLibraryW` at `0x140004565`
- `KERNEL32!GetProcAddress` at `0x140004581`
- `KERNEL32!GetProcAddress` at `0x140004581`

## string_xrefs

- `0x14000455e`: `Msi.dll`
- `0x140004577`: `DllGetClassObject`

## pseudocode

```c
struct IUnknown *CreateCustomActionServer(void)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  struct IUnknown *result; // rax
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF
  struct IUnknown *v4; // [rsp+48h] [rbp+10h] BYREF

  LibraryW = g_hKernel;
  v4 = 0;
  v3 = 0;
  if ( !g_hKernel )
  {
    LibraryW = LoadLibraryW(L"Msi.dll");
    g_hKernel = LibraryW;
    if ( !LibraryW )
      return 0;
  }
  ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
  if ( !ProcAddress )
    return 0;
  if ( ((unsigned int (__fastcall *)(void *, GUID *, __int64 *))ProcAddress)(&unk_14000CC18, &IID_IUnknown, &v3) )
    return 0;
  (*(void (__fastcall **)(__int64, _QWORD, void *, struct IUnknown **))(*(_QWORD *)v3 + 24LL))(
    v3,
    0,
    &unk_14000CC18,
    &v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  result = v4;
  if ( !v4 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000453c  sub     rsp, 38h
0x140004540  mov     rax, cs:?g_hKernel@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hKernel
0x140004547  mov     [rsp+38h+arg_8], 0
0x140004550  mov     [rsp+38h+arg_0], 0
0x140004559  test    rax, rax
0x14000455c  jnz     short loc_140004577
0x14000455e  lea     rcx, ModuleName; "Msi.dll"
0x140004565  call    cs:__imp_LoadLibraryW
0x14000456b  mov     cs:?g_hKernel@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hKernel
0x140004572  test    rax, rax
0x140004575  jz      short loc_1400045E2
0x140004577  lea     rdx, ProcName; "DllGetClassObject"
0x14000457e  mov     rcx, rax; hModule
0x140004581  call    cs:__imp_GetProcAddress
0x140004587  test    rax, rax
0x14000458a  jz      short loc_1400045E2
0x14000458c  lea     r8, [rsp+38h+arg_0]
0x140004591  lea     rdx, IID_IUnknown
0x140004598  lea     rcx, unk_14000CC18
0x14000459f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045a4  test    eax, eax
0x1400045a6  jnz     short loc_1400045E2
0x1400045a8  mov     rcx, [rsp+38h+arg_0]
0x1400045ad  lea     r9, [rsp+38h+arg_8]
0x1400045b2  lea     r8, unk_14000CC18
0x1400045b9  xor     edx, edx
0x1400045bb  mov     rax, [rcx]
0x1400045be  mov     rax, [rax+18h]
0x1400045c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045c7  mov     rcx, [rsp+38h+arg_0]
0x1400045cc  mov     rax, [rcx]
0x1400045cf  mov     rax, [rax+10h]
0x1400045d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045d8  mov     rax, [rsp+38h+arg_8]
0x1400045dd  test    rax, rax
0x1400045e0  jnz     short loc_1400045E4
0x1400045e2  xor     eax, eax
0x1400045e4  add     rsp, 38h
0x1400045e8  retn
```
