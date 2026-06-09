# IsProcessShutdownInProgress(void)

- ea: `0x1800037a0`
- end: `0x1800037fd`
- name: `?IsProcessShutdownInProgress@@YA_NXZ`
- size: `93`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003730`
- `0x1800048b4`
- `0x180008f48`

## callees

- `0x1800037a0`
- `0x180005b20`
- `0x180005b2c`
- `0x18000b010`

## string_xrefs

- `0x1800037cb`: `ntdll.dll`
- `0x1800037dc`: `RtlDllShutdownInProgress`

## pseudocode

```c
bool IsProcessShutdownInProgress(void)
{
  BOOLEAN (*RtlDllShutdownInProgress)(void); // rax
  HMODULE ModuleHandleW_0; // rax

  RtlDllShutdownInProgress = (BOOLEAN (*)(void))qword_180010AC8;
  if ( qword_180010AC8
    || ((ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll")) == 0
      ? (RtlDllShutdownInProgress = (BOOLEAN (*)(void))qword_180010AC8)
      : (BOOLEAN (*)(void))(RtlDllShutdownInProgress = (BOOLEAN (*)(void))GetProcAddress_0(
                                                                            ModuleHandleW_0,
                                                                            "RtlDllShutdownInProgress"),
                            qword_180010AC8 = (__int64)RtlDllShutdownInProgress),
        RtlDllShutdownInProgress) )
  {
    LOBYTE(RtlDllShutdownInProgress) = RtlDllShutdownInProgress() != 0;
  }
  return (char)RtlDllShutdownInProgress;
}

```

## disassembly

```asm
0x1800037a0  sub     rsp, 28h
0x1800037a4  mov     rax, cs:qword_180010AC8
0x1800037ab  test    rax, rax
0x1800037ae  jz      short loc_1800037CB
0x1800037b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b5  test    al, al
0x1800037b7  setnz   al
0x1800037ba  add     rsp, 28h
0x1800037be  retn
0x1800037c0  test    rax, rax
0x1800037c3  jnz     short loc_1800037B0
0x1800037c5  add     rsp, 28h
0x1800037c9  retn
0x1800037cb  lea     rcx, ModuleName; "ntdll.dll"
0x1800037d2  call    GetModuleHandleW_0
0x1800037d7  test    rax, rax
0x1800037da  jz      short loc_1800037F4
0x1800037dc  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x1800037e3  mov     rcx, rax; hModule
0x1800037e6  call    GetProcAddress_0
0x1800037eb  mov     cs:qword_180010AC8, rax
0x1800037f2  jmp     short loc_1800037C0
0x1800037f4  mov     rax, cs:qword_180010AC8
0x1800037fb  jmp     short loc_1800037C0
```
