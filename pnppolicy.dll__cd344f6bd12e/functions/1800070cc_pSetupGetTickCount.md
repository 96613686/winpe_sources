# pSetupGetTickCount

- ea: `0x1800070cc`
- end: `0x180007160`
- name: `pSetupGetTickCount`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800057a8`

## callees

- `0x1800070cc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18000714f`
- `KERNEL32!GetTickCount64` at `0x18000714f`
- `KERNEL32!GetModuleHandleW` at `0x1800070e9`
- `KERNEL32!GetModuleHandleW` at `0x1800070e9`
- `KERNEL32!GetProcAddress` at `0x1800070fe`
- `KERNEL32!GetProcAddress` at `0x1800070fe`

## string_xrefs

- `0x1800070e2`: `ntdll.dll`

## pseudocode

```c
ULONGLONG pSetupGetTickCount()
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( dword_180011748 )
  {
    ProcAddress = (FARPROC)qword_180011740;
  }
  else
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryUnbiasedInterruptTime");
      qword_180011740 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_180011740;
    }
    dword_180011748 = 1;
  }
  if ( ProcAddress && ((unsigned int (__fastcall *)(unsigned __int64 *))ProcAddress)(&v4) )
    return v4 / 0x2710;
  else
    return GetTickCount64();
}

```

## disassembly

```asm
0x1800070cc  sub     rsp, 28h
0x1800070d0  cmp     cs:dword_180011748, 0
0x1800070d7  mov     [rsp+28h+arg_0], 0
0x1800070e0  jnz     short loc_180007120
0x1800070e2  lea     rcx, ModuleName; "ntdll.dll"
0x1800070e9  call    cs:__imp_GetModuleHandleW
0x1800070ef  test    rax, rax
0x1800070f2  jz      short loc_18000710D
0x1800070f4  lea     rdx, aRtlqueryunbias; "RtlQueryUnbiasedInterruptTime"
0x1800070fb  mov     rcx, rax; hModule
0x1800070fe  call    cs:__imp_GetProcAddress
0x180007104  mov     cs:qword_180011740, rax
0x18000710b  jmp     short loc_180007114
0x18000710d  mov     rax, cs:qword_180011740
0x180007114  mov     cs:dword_180011748, 1
0x18000711e  jmp     short loc_180007127
0x180007120  mov     rax, cs:qword_180011740
0x180007127  test    rax, rax
0x18000712a  jz      short loc_18000714F
0x18000712c  lea     rcx, [rsp+28h+arg_0]
0x180007131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007136  test    eax, eax
0x180007138  jz      short loc_18000714F
0x18000713a  mov     rax, 346DC5D63886594Bh
0x180007144  mul     [rsp+28h+arg_0]
0x180007149  shr     rdx, 0Bh
0x18000714d  jmp     short loc_180007158
0x18000714f  call    cs:__imp_GetTickCount64
0x180007155  mov     rdx, rax
0x180007158  mov     rax, rdx
0x18000715b  add     rsp, 28h
0x18000715f  retn
```
