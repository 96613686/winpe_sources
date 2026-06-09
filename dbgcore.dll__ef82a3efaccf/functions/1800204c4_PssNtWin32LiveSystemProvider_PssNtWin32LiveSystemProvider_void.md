# PssNtWin32LiveSystemProvider::~PssNtWin32LiveSystemProvider(void)

- ea: `0x1800204c4`
- end: `0x1800205b0`
- name: `??1PssNtWin32LiveSystemProvider@@UEAA@XZ`
- size: `236`
- prototype: `void __fastcall(PssNtWin32LiveSystemProvider *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800205d0`

## callees

- `0x1800204c4`
- `0x180023234`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002057e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180020590`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002057e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180020590`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002059d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002059d`

## pseudocode

```c
void __fastcall PssNtWin32LiveSystemProvider::~PssNtWin32LiveSystemProvider(PssNtWin32LiveSystemProvider *this)
{
  __int64 v2; // rcx
  void (__fastcall *v3)(__int64); // rax
  void (__fastcall *v4)(__int64); // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  HMODULE v9; // rcx

  *(_QWORD *)this = &PssNtWin32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'};
  *((_QWORD *)this + 1) = &PssNtWin32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'};
  v2 = *((_QWORD *)this + 151);
  if ( v2 )
  {
    v3 = (void (__fastcall *)(__int64))*((_QWORD *)this + 139);
    if ( v3 )
      v3(v2);
  }
  if ( *((_QWORD *)this + 141) )
  {
    v4 = (void (__fastcall *)(__int64))*((_QWORD *)this + 145);
    if ( v4 )
    {
      v5 = *((_QWORD *)this + 157);
      if ( v5 )
        v4(v5);
      v6 = *((_QWORD *)this + 156);
      if ( v6 )
        (*((void (__fastcall **)(__int64))this + 145))(v6);
      v7 = *((_QWORD *)this + 155);
      if ( v7 )
        (*((void (__fastcall **)(__int64))this + 145))(v7);
      v8 = *((_QWORD *)this + 154);
      if ( v8 )
        (*((void (__fastcall **)(__int64))this + 145))(v8);
    }
    FreeLibrary(*((HMODULE *)this + 141));
  }
  v9 = (HMODULE)*((_QWORD *)this + 149);
  if ( v9 )
    FreeLibrary(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  NtWin32LiveSystemProvider::~NtWin32LiveSystemProvider(this);
}

```

## disassembly

```asm
0x1800204c4  push    rbx
0x1800204c6  sub     rsp, 30h
0x1800204ca  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800204d3  mov     rbx, rcx
0x1800204d6  lea     rax, ??_7PssNtWin32LiveSystemProvider@@6BMiniDumpSystemProvider@@@; const PssNtWin32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'}
0x1800204dd  mov     [rcx], rax
0x1800204e0  lea     rax, ??_7PssNtWin32LiveSystemProvider@@6BMiniDumpVmHookedProvider@@@; const PssNtWin32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'}
0x1800204e7  mov     [rcx+8], rax
0x1800204eb  mov     rcx, [rcx+4B8h]
0x1800204f2  test    rcx, rcx
0x1800204f5  jz      short loc_180020508
0x1800204f7  mov     rax, [rbx+458h]
0x1800204fe  test    rax, rax
0x180020501  jz      short loc_180020508
0x180020503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020508  cmp     qword ptr [rbx+468h], 0
0x180020510  jz      short loc_180020584
0x180020512  mov     rax, [rbx+488h]
0x180020519  test    rax, rax
0x18002051c  jz      short loc_180020577
0x18002051e  mov     rcx, [rbx+4E8h]
0x180020525  test    rcx, rcx
0x180020528  jz      short loc_18002052F
0x18002052a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002052f  mov     rcx, [rbx+4E0h]
0x180020536  test    rcx, rcx
0x180020539  jz      short loc_180020547
0x18002053b  mov     rax, [rbx+488h]
0x180020542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020547  mov     rcx, [rbx+4D8h]
0x18002054e  test    rcx, rcx
0x180020551  jz      short loc_18002055F
0x180020553  mov     rax, [rbx+488h]
0x18002055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002055f  mov     rcx, [rbx+4D0h]
0x180020566  test    rcx, rcx
0x180020569  jz      short loc_180020577
0x18002056b  mov     rax, [rbx+488h]
0x180020572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020577  mov     rcx, [rbx+468h]; hLibModule
0x18002057e  call    cs:__imp_FreeLibrary
0x180020584  mov     rcx, [rbx+4A8h]; hLibModule
0x18002058b  test    rcx, rcx
0x18002058e  jz      short loc_180020596
0x180020590  call    cs:__imp_FreeLibrary
0x180020596  lea     rcx, [rbx+510h]; lpCriticalSection
0x18002059d  call    cs:__imp_DeleteCriticalSection
0x1800205a3  mov     rcx, rbx; this
0x1800205a6  add     rsp, 30h
0x1800205aa  pop     rbx
0x1800205ab  jmp     ??1NtWin32LiveSystemProvider@@UEAA@XZ; NtWin32LiveSystemProvider::~NtWin32LiveSystemProvider(void)
```
