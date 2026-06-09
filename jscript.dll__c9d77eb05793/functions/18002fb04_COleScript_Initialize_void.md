# COleScript::Initialize(void)

- ea: `0x18002fb04`
- end: `0x18002fbdf`
- name: `?Initialize@COleScript@@QEAAHXZ`
- size: `219`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18002f270`
- `0x180067400`
- `0x1800674b0`
- `0x180077820`

## callees

- `0x18002fb04`
- `0x180096010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002fb2a`
- `KERNEL32!LoadLibraryExW` at `0x18002fb2a`
- `KERNEL32!GetProcAddress` at `0x18002fb46`
- `KERNEL32!GetProcAddress` at `0x18002fb5d`
- `KERNEL32!GetProcAddress` at `0x18002fb46`
- `KERNEL32!GetProcAddress` at `0x18002fb5d`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbb1`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbb1`

## string_xrefs

- `0x18002fb4f`: `AmsiScanString`
- `0x18002fb23`: `amsi.dll`
- `0x18002fb3c`: `AmsiInitialize`

## pseudocode

```c
__int64 __fastcall COleScript::Initialize(COleScript *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v4; // rax

  Library = LoadLibraryExW(L"amsi.dll", 0, 0x800u);
  *((_QWORD *)this + 125) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AmsiInitialize");
    v4 = GetProcAddress(*((HMODULE *)this + 125), "AmsiScanString");
    *((_QWORD *)this + 122) = v4;
    if ( ProcAddress )
    {
      if ( v4 && ((int (__fastcall *)(_QWORD, char *))ProcAddress)(*((_QWORD *)this + 23), (char *)this + 968) < 0 )
        *((_QWORD *)this + 121) = 0;
    }
  }
  *((_DWORD *)this + 140) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  return *((unsigned int *)this + 140);
}

```

## disassembly

```asm
0x18002fb04  mov     [rsp+arg_10], rbx
0x18002fb09  mov     [rsp+arg_18], rsi
0x18002fb0e  mov     [rsp+arg_0], rcx
0x18002fb13  push    rdi
0x18002fb14  sub     rsp, 20h
0x18002fb18  mov     rdi, rcx
0x18002fb1b  xor     edx, edx; hFile
0x18002fb1d  mov     r8d, 800h; dwFlags
0x18002fb23  lea     rcx, LibFileName; "amsi.dll"
0x18002fb2a  call    cs:__imp_LoadLibraryExW
0x18002fb30  mov     [rdi+3E8h], rax
0x18002fb37  test    rax, rax
0x18002fb3a  jz      short loc_18002FB98
0x18002fb3c  lea     rdx, aAmsiinitialize; "AmsiInitialize"
0x18002fb43  mov     rcx, rax; hModule
0x18002fb46  call    cs:__imp_GetProcAddress
0x18002fb4c  mov     rsi, rax
0x18002fb4f  lea     rdx, aAmsiscanstring; "AmsiScanString"
0x18002fb56  mov     rcx, [rdi+3E8h]; hModule
0x18002fb5d  call    cs:__imp_GetProcAddress
0x18002fb63  mov     [rdi+3D0h], rax
0x18002fb6a  test    rsi, rsi
0x18002fb6d  jz      short loc_18002FB98
0x18002fb6f  test    rax, rax
0x18002fb72  jz      short loc_18002FB98
0x18002fb74  lea     rbx, [rdi+3C8h]
0x18002fb7b  mov     rdx, rbx
0x18002fb7e  mov     rcx, [rdi+0B8h]
0x18002fb85  mov     rax, rsi
0x18002fb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb8d  test    eax, eax
0x18002fb8f  jns     short loc_18002FB98
0x18002fb91  mov     qword ptr [rbx], 0
0x18002fb98  lea     rbx, [rdi+230h]
0x18002fb9f  mov     [rsp+28h+arg_8], rbx
0x18002fba4  mov     dword ptr [rbx], 1
0x18002fbaa  lea     rcx, [rdi+238h]; lpCriticalSection
0x18002fbb1  call    cs:__imp_InitializeCriticalSection
0x18002fbb7  jmp     short loc_18002FBCD
0x18002fbb9  mov     rax, [rsp+28h+arg_0]
0x18002fbbe  mov     dword ptr [rax+230h], 0
0x18002fbc8  mov     rbx, [rsp+28h+arg_8]
0x18002fbcd  mov     eax, [rbx]
0x18002fbcf  mov     rbx, [rsp+28h+arg_10]
0x18002fbd4  mov     rsi, [rsp+28h+arg_18]
0x18002fbd9  add     rsp, 20h
0x18002fbdd  pop     rdi
0x18002fbde  retn
```
