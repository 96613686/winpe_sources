# DloadGetSRWLockFunctionPointers(void)

- ea: `0x18003eb24`
- end: `0x18003ebbf`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `155`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ea78`
- `0x18003ed84`

## callees

- `0x18003eb24`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003eb4b`
- `KERNEL32!GetModuleHandleW` at `0x18003eb4b`
- `KERNEL32!GetProcAddress` at `0x18003eb68`
- `KERNEL32!GetProcAddress` at `0x18003eb84`
- `KERNEL32!GetProcAddress` at `0x18003eb68`
- `KERNEL32!GetProcAddress` at `0x18003eb84`

## string_xrefs

- `0x18003eb44`: `KERNEL32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18003eb24  mov     [rsp+arg_0], rbx
0x18003eb29  push    rdi
0x18003eb2a  sub     rsp, 20h
0x18003eb2e  mov     rax, cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DloadKernel32
0x18003eb35  mov     edi, 1
0x18003eb3a  cmp     rax, rdi
0x18003eb3d  jz      short loc_18003EBB2
0x18003eb3f  test    rax, rax
0x18003eb42  jnz     short loc_18003EBAD
0x18003eb44  lea     rcx, aKernel32Dll_1; "KERNEL32.DLL"
0x18003eb4b  call    cs:__imp_GetModuleHandleW
0x18003eb51  mov     rbx, rax
0x18003eb54  test    rax, rax
0x18003eb57  jnz     short loc_18003EB5E
0x18003eb59  mov     rbx, rdi
0x18003eb5c  jmp     short loc_18003EB96
0x18003eb5e  lea     rdx, aAcquiresrwlock; "AcquireSRWLockExclusive"
0x18003eb65  mov     rcx, rbx; hModule
0x18003eb68  call    cs:__imp_GetProcAddress
0x18003eb6e  test    rax, rax
0x18003eb71  jz      short loc_18003EB59
0x18003eb73  lea     rdx, aReleasesrwlock; "ReleaseSRWLockExclusive"
0x18003eb7a  mov     cs:?DloadAcquireSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadAcquireSRWLockExclusive)(unsigned __int64 *)
0x18003eb81  mov     rcx, rbx; hModule
0x18003eb84  call    cs:__imp_GetProcAddress
0x18003eb8a  test    rax, rax
0x18003eb8d  jz      short loc_18003EB59
0x18003eb8f  mov     cs:?DloadReleaseSRWLockExclusive@@3P6AXPEA_K@ZEA, rax; void (*DloadReleaseSRWLockExclusive)(unsigned __int64 *)
0x18003eb96  xor     eax, eax
0x18003eb98  lock cmpxchg cs:?DloadKernel32@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * DloadKernel32
0x18003eba1  jnz     short loc_18003EBA8
0x18003eba3  cmp     rbx, rdi
0x18003eba6  jz      short loc_18003EBB2
0x18003eba8  cmp     rax, rdi
0x18003ebab  jz      short loc_18003EBB2
0x18003ebad  mov     al, dil
0x18003ebb0  jmp     short loc_18003EBB4
0x18003ebb2  xor     al, al
0x18003ebb4  mov     rbx, [rsp+28h+arg_0]
0x18003ebb9  add     rsp, 20h
0x18003ebbd  pop     rdi
0x18003ebbe  retn
```
