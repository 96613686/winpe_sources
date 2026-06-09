# IEIsImmersiveProcess(void *)

- ea: `0x180025440`
- end: `0x1800254f2`
- name: `?IEIsImmersiveProcess@@YAHPEAX@Z`
- size: `178`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180023d98`
- `0x1800246e8`
- `0x180065f64`

## callees

- `0x180019b40`
- `0x180025440`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025496`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025496`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180025461`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180025461`

## string_xrefs

- `0x18002548d`: `user32.dll`

## pseudocode

```c
__int64 __fastcall IEIsImmersiveProcess(void *a1)
{
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  unsigned int v4; // ebx

  InitOnceExecuteOnce(&stru_180299FB8, InitOnceDeviceFamily, 0, 0);
  if ( byte_180298C9C )
  {
    return (unsigned int)IsSpartanApp() != 0;
  }
  else
  {
    ProcAddress = (FARPROC)qword_18029A120;
    if ( qword_18029A120 )
      return ((unsigned int (__fastcall *)(void *))ProcAddress)(a1);
    Library = qword_18029A118;
    v4 = 0;
    if ( qword_18029A118 || (Library = LoadLibraryExW(L"user32.dll", 0, 0), (qword_18029A118 = Library) != 0) )
    {
      ProcAddress = GetProcAddress(Library, "IsImmersiveProcess");
      qword_18029A120 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_18029A120;
    }
    if ( ProcAddress )
      return ((unsigned int (__fastcall *)(void *))ProcAddress)(a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180025440  mov     [rsp+arg_0], rbx
0x180025445  push    rdi
0x180025446  sub     rsp, 20h
0x18002544a  mov     rdi, rcx
0x18002544d  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180025454  lea     rcx, stru_180299FB8; InitOnce
0x18002545b  xor     r9d, r9d; Context
0x18002545e  xor     r8d, r8d; Parameter
0x180025461  call    cs:__imp_InitOnceExecuteOnce
0x180025467  cmp     cs:byte_180298C9C, 0
0x18002546e  jnz     short loc_1800254E4
0x180025470  mov     rax, cs:qword_18029A120
0x180025477  test    rax, rax
0x18002547a  jnz     short loc_1800254C4
0x18002547c  mov     rax, cs:qword_18029A118
0x180025483  xor     ebx, ebx
0x180025485  test    rax, rax
0x180025488  jnz     short loc_1800254A8
0x18002548a  xor     r8d, r8d; dwFlags
0x18002548d  lea     rcx, aUser32Dll; "user32.dll"
0x180025494  xor     edx, edx; hFile
0x180025496  call    cs:__imp_LoadLibraryExW
0x18002549c  mov     cs:qword_18029A118, rax
0x1800254a3  test    rax, rax
0x1800254a6  jz      short loc_1800254DB
0x1800254a8  lea     rdx, aIsimmersivepro; "IsImmersiveProcess"
0x1800254af  mov     rcx, rax; hModule
0x1800254b2  call    cs:__imp_GetProcAddress
0x1800254b8  mov     cs:qword_18029A120, rax
0x1800254bf  test    rax, rax
0x1800254c2  jz      short loc_1800254CE
0x1800254c4  mov     rcx, rdi
0x1800254c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254cc  mov     ebx, eax
0x1800254ce  mov     eax, ebx
0x1800254d0  mov     rbx, [rsp+28h+arg_0]
0x1800254d5  add     rsp, 20h
0x1800254d9  pop     rdi
0x1800254da  retn
0x1800254db  mov     rax, cs:qword_18029A120
0x1800254e2  jmp     short loc_1800254BF
0x1800254e4  call    ?IsSpartanApp@@YAHXZ; IsSpartanApp(void)
0x1800254e9  xor     ebx, ebx
0x1800254eb  test    eax, eax
0x1800254ed  setnz   bl
0x1800254f0  jmp     short loc_1800254CE
```
