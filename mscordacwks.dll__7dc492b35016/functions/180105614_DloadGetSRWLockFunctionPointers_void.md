# DloadGetSRWLockFunctionPointers(void)

- ea: `0x180105614`
- end: `0x1801056af`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `155`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180105568`
- `0x180105874`

## callees

- `0x180105614`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18010563b`
- `KERNEL32!GetModuleHandleW` at `0x18010563b`
- `KERNEL32!GetProcAddress` at `0x180105658`
- `KERNEL32!GetProcAddress` at `0x180105674`
- `KERNEL32!GetProcAddress` at `0x180105658`
- `KERNEL32!GetProcAddress` at `0x180105674`

## string_xrefs

- `0x180105634`: `KERNEL32.DLL`

## pseudocode

```c
bool DloadGetSRWLockFunctionPointers(void)
{
  HMODULE ModuleHandleW; // rax
  signed __int64 v1; // rbx
  void (*ProcAddress)(unsigned __int64 *); // rax
  void (*v3)(unsigned __int64 *); // rax
  signed __int64 v4; // rax
  bool result; // al

  result = 0;
  if ( DloadKernel32 != (HINSTANCE)1 )
  {
    if ( DloadKernel32 )
      return 1;
    ModuleHandleW = GetModuleHandleW(L"KERNEL32.DLL");
    v1 = (signed __int64)ModuleHandleW;
    if ( ModuleHandleW
      && (ProcAddress = (void (*)(unsigned __int64 *))GetProcAddress(ModuleHandleW, "AcquireSRWLockExclusive")) != 0
      && (DloadAcquireSRWLockExclusive = ProcAddress,
          (v3 = (void (*)(unsigned __int64 *))GetProcAddress((HMODULE)v1, "ReleaseSRWLockExclusive")) != 0) )
    {
      DloadReleaseSRWLockExclusive = v3;
    }
    else
    {
      v1 = 1;
    }
    v4 = _InterlockedCompareExchange64((volatile signed __int64 *)&DloadKernel32, v1, 0);
    if ( (v4 || v1 != 1) && v4 != 1 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180105614  mov     [rsp+arg_0], rbx
0x180105619  push    rdi
0x18010561a  sub     rsp, 20h
0x18010561e  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x180105625  mov     edi, 1
0x18010562a  cmp     rax, rdi
0x18010562d  jz      short loc_1801056A2
0x18010562f  test    rax, rax
0x180105632  jnz     short loc_18010569D
0x180105634  lea     rcx, aKernel32Dll_1; "KERNEL32.DLL"
0x18010563b  call    cs:__imp_GetModuleHandleW
0x180105641  mov     rbx, rax
0x180105644  test    rax, rax
0x180105647  jnz     short loc_18010564E
0x180105649  mov     rbx, rdi
0x18010564c  jmp     short loc_180105686
0x18010564e  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x180105655  mov     rcx, rbx; hModule
0x180105658  call    cs:__imp_GetProcAddress
0x18010565e  test    rax, rax
0x180105661  jz      short loc_180105649
0x180105663  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x18010566a  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x180105671  mov     rcx, rbx; hModule
0x180105674  call    cs:__imp_GetProcAddress
0x18010567a  test    rax, rax
0x18010567d  jz      short loc_180105649
0x18010567f  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x180105686  xor     eax, eax
0x180105688  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x180105691  jnz     short loc_180105698
0x180105693  cmp     rbx, rdi
0x180105696  jz      short loc_1801056A2
0x180105698  cmp     rax, rdi
0x18010569b  jz      short loc_1801056A2
0x18010569d  mov     al, dil
0x1801056a0  jmp     short loc_1801056A4
0x1801056a2  xor     al, al
0x1801056a4  mov     rbx, [rsp+28h+arg_0]
0x1801056a9  add     rsp, 20h
0x1801056ad  pop     rdi
0x1801056ae  retn
```
