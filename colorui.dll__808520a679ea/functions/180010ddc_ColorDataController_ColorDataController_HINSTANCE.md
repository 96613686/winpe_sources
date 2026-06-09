# ColorDataController::ColorDataController(HINSTANCE__ *)

- ea: `0x180010ddc`
- end: `0x180010e94`
- name: `??0ColorDataController@@QEAA@PEAUHINSTANCE__@@@Z`
- size: `184`
- prototype: `ColorDataController *__fastcall(ColorDataController *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006880`

## callees

- `0x180010ddc`
- `0x1800125ec`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010e80`
- `KERNEL32!GetLastError` at `0x180010e80`
- `KERNEL32!GetProcAddress` at `0x180010e51`
- `KERNEL32!GetProcAddress` at `0x180010e51`
- `KERNEL32!LoadLibraryExW` at `0x180010e38`
- `KERNEL32!LoadLibraryExW` at `0x180010e38`

## string_xrefs

- `0x180010e2b`: `sti.dll`
- `0x180010e47`: `StiCreateInstance`

## pseudocode

```c
ColorDataController *__fastcall ColorDataController::ColorDataController(ColorDataController *this, HINSTANCE a2)
{
  _QWORD *v2; // rdi
  HRESULT v4; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  v2 = (_QWORD *)((char *)this + 48);
  *(_QWORD *)this = g_hInst;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v4 = ColorDataController::RunRestricted(this);
  *((_DWORD *)this + 3) = v4;
  if ( v4 >= 0 )
  {
    Library = LoadLibraryExW(L"sti.dll", 0, 0x800u);
    *((_QWORD *)this + 4) = Library;
    if ( Library
      && (ProcAddress = GetProcAddress(Library, "StiCreateInstance"), (*((_QWORD *)this + 5) = ProcAddress) != 0) )
    {
      if ( ((int (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD))ProcAddress)(*(_QWORD *)this, 16777218, v2, 0) < 0 )
        *v2 = 0;
    }
    else
    {
      GetLastError();
    }
  }
  return this;
}

```

## disassembly

```asm
0x180010ddc  mov     [rsp+arg_0], rbx
0x180010de1  push    rdi
0x180010de2  sub     rsp, 30h
0x180010de6  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180010ded  lea     rdi, [rcx+30h]
0x180010df1  mov     [rcx], rax
0x180010df4  mov     rbx, rcx
0x180010df7  mov     qword ptr [rdi], 0
0x180010dfe  mov     dword ptr [rcx+8], 0
0x180010e05  mov     qword ptr [rcx+10h], 0
0x180010e0d  mov     qword ptr [rcx+20h], 0
0x180010e15  mov     qword ptr [rcx+28h], 0
0x180010e1d  call    ?RunRestricted@ColorDataController@@QEAAJXZ; ColorDataController::RunRestricted(void)
0x180010e22  mov     [rbx+0Ch], eax
0x180010e25  test    eax, eax
0x180010e27  js      short loc_180010E86
0x180010e29  xor     edx, edx; hFile
0x180010e2b  lea     rcx, aStiDll; "sti.dll"
0x180010e32  mov     r8d, 800h; dwFlags
0x180010e38  call    cs:__imp_LoadLibraryExW
0x180010e3e  mov     [rbx+20h], rax
0x180010e42  test    rax, rax
0x180010e45  jz      short loc_180010E80
0x180010e47  lea     rdx, aSticreateinsta; "StiCreateInstance"
0x180010e4e  mov     rcx, rax; hModule
0x180010e51  call    cs:__imp_GetProcAddress
0x180010e57  mov     [rbx+28h], rax
0x180010e5b  test    rax, rax
0x180010e5e  jz      short loc_180010E80
0x180010e60  mov     rcx, [rbx]
0x180010e63  xor     r9d, r9d
0x180010e66  mov     r8, rdi
0x180010e69  mov     edx, 1000002h
0x180010e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e73  test    eax, eax
0x180010e75  jns     short loc_180010E86
0x180010e77  mov     qword ptr [rdi], 0
0x180010e7e  jmp     short loc_180010E86
0x180010e80  call    cs:__imp_GetLastError
0x180010e86  mov     rax, rbx
0x180010e89  mov     rbx, [rsp+38h+arg_0]
0x180010e8e  add     rsp, 30h
0x180010e92  pop     rdi
0x180010e93  retn
```
