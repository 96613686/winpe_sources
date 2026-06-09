# NtWin32LiveSystemProvider::~NtWin32LiveSystemProvider(void)

- ea: `0x180023234`
- end: `0x1800232d3`
- name: `??1NtWin32LiveSystemProvider@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(NtWin32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800204c4`
- `0x1800232f0`

## callees

- `0x1800110a8`
- `0x180023234`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180023267`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180023267`

## pseudocode

```c
void __fastcall NtWin32LiveSystemProvider::~NtWin32LiveSystemProvider(NtWin32LiveSystemProvider *this)
{
  HMODULE v2; // rcx

  *(_QWORD *)this = &NtWin32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'};
  *((_QWORD *)this + 1) = &NtWin32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'};
  v2 = (HMODULE)*((_QWORD *)this + 124);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 124) = 0;
  }
  if ( *((_QWORD *)this + 136) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
    *((_QWORD *)this + 136) = 0;
  }
  if ( *((_QWORD *)this + 131) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
    *((_QWORD *)this + 131) = 0;
  }
  Win32LiveSystemProvider::~Win32LiveSystemProvider(this);
}

```

## disassembly

```asm
0x180023234  push    rbx
0x180023236  sub     rsp, 30h
0x18002323a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180023243  mov     rbx, rcx
0x180023246  lea     rax, ??_7NtWin32LiveSystemProvider@@6BMiniDumpSystemProvider@@@; const NtWin32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'}
0x18002324d  mov     [rcx], rax
0x180023250  lea     rax, ??_7NtWin32LiveSystemProvider@@6BMiniDumpVmHookedProvider@@@; const NtWin32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'}
0x180023257  mov     [rcx+8], rax
0x18002325b  mov     rcx, [rcx+3E0h]; hLibModule
0x180023262  test    rcx, rcx
0x180023265  jz      short loc_180023278
0x180023267  call    cs:__imp_FreeLibrary
0x18002326d  mov     qword ptr [rbx+3E0h], 0
0x180023278  mov     rdx, [rbx+440h]
0x18002327f  test    rdx, rdx
0x180023282  jz      short loc_18002329F
0x180023284  mov     rcx, [rbx+30h]
0x180023288  mov     rax, [rcx]
0x18002328b  mov     rax, [rax+18h]
0x18002328f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023294  mov     qword ptr [rbx+440h], 0
0x18002329f  mov     rdx, [rbx+418h]
0x1800232a6  test    rdx, rdx
0x1800232a9  jz      short loc_1800232C6
0x1800232ab  mov     rcx, [rbx+30h]
0x1800232af  mov     rax, [rcx]
0x1800232b2  mov     rax, [rax+18h]
0x1800232b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232bb  mov     qword ptr [rbx+418h], 0
0x1800232c6  mov     rcx, rbx; this
0x1800232c9  add     rsp, 30h
0x1800232cd  pop     rbx
0x1800232ce  jmp     ??1Win32LiveSystemProvider@@UEAA@XZ; Win32LiveSystemProvider::~Win32LiveSystemProvider(void)
```
