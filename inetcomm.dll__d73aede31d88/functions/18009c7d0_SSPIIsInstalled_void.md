# SSPIIsInstalled(void)

- ea: `0x18009c7d0`
- end: `0x18009c862`
- name: `?SSPIIsInstalled@@YAJXZ`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009c868`
- `0x1800aa8b0`

## callees

- `0x18009c7d0`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x18009c7f9`
- `KERNEL32!LoadLibraryA` at `0x18009c7f9`
- `KERNEL32!GetProcAddress` at `0x18009c815`
- `KERNEL32!GetProcAddress` at `0x18009c815`
- `KERNEL32!FreeLibrary` at `0x18009c838`
- `KERNEL32!FreeLibrary` at `0x18009c838`
- `KERNEL32!LeaveCriticalSection` at `0x18009c854`
- `KERNEL32!LeaveCriticalSection` at `0x18009c854`
- `KERNEL32!EnterCriticalSection` at `0x18009c7dd`
- `KERNEL32!EnterCriticalSection` at `0x18009c7dd`

## string_xrefs

- `0x18009c80b`: `InitSecurityInterfaceW`
- `0x18009c7ed`: `security.dll`

## pseudocode

```c
__int64 SSPIIsInstalled(void)
{
  unsigned int v0; // ebx
  HMODULE LibraryA; // rax
  __int64 (*ProcAddress)(void); // rax

  EnterCriticalSection(&g_csDllMain);
  if ( qword_1800F3440 )
    goto LABEL_6;
  v0 = 1;
  LibraryA = LoadLibraryA("security.dll");
  qword_1800F3440 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "InitSecurityInterfaceW");
    if ( ProcAddress )
    {
      qword_1800F3448 = ProcAddress();
      if ( !qword_1800F3448 )
      {
        FreeLibrary(qword_1800F3440);
        qword_1800F3440 = 0;
        goto LABEL_7;
      }
LABEL_6:
      v0 = 0;
    }
  }
LABEL_7:
  LeaveCriticalSection(&g_csDllMain);
  return v0;
}

```

## disassembly

```asm
0x18009c7d0  push    rbx
0x18009c7d2  sub     rsp, 20h
0x18009c7d6  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009c7dd  call    cs:__imp_EnterCriticalSection
0x18009c7e3  cmp     cs:qword_1800F3440, 0
0x18009c7eb  jnz     short loc_18009C84B
0x18009c7ed  lea     rcx, aSecurityDll; "security.dll"
0x18009c7f4  mov     ebx, 1
0x18009c7f9  call    cs:__imp_LoadLibraryA
0x18009c7ff  mov     cs:qword_1800F3440, rax
0x18009c806  test    rax, rax
0x18009c809  jz      short loc_18009C84D
0x18009c80b  lea     rdx, aInitsecurityin_0; "InitSecurityInterfaceW"
0x18009c812  mov     rcx, rax; hModule
0x18009c815  call    cs:__imp_GetProcAddress
0x18009c81b  test    rax, rax
0x18009c81e  jz      short loc_18009C84D
0x18009c820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c825  mov     cs:qword_1800F3448, rax
0x18009c82c  test    rax, rax
0x18009c82f  jnz     short loc_18009C84B
0x18009c831  mov     rcx, cs:qword_1800F3440; hLibModule
0x18009c838  call    cs:__imp_FreeLibrary
0x18009c83e  mov     cs:qword_1800F3440, 0
0x18009c849  jmp     short loc_18009C84D
0x18009c84b  xor     ebx, ebx
0x18009c84d  lea     rcx, ?g_csDllMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009c854  call    cs:__imp_LeaveCriticalSection
0x18009c85a  mov     eax, ebx
0x18009c85c  add     rsp, 20h
0x18009c860  pop     rbx
0x18009c861  retn
```
