# DLL::GetExportByName(char const *,void * *)

- ea: `0x180010700`
- end: `0x18001076d`
- name: `?GetExportByName@DLL@@QEAAKPEBDPEAPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, LPCSTR lpProcName, FARPROC *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015d24`

## callees

- `0x180010700`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010730`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010723`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010755`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001073e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001073e`

## pseudocode

```c
__int64 __fastcall DLL::GetExportByName(LPCRITICAL_SECTION lpCriticalSection, LPCSTR lpProcName, FARPROC *a3)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned int v9; // ebx

  if ( !a3 )
    return 87;
  EnterCriticalSection(lpCriticalSection);
  ProcAddress = GetProcAddress((HMODULE)lpCriticalSection[1].DebugInfo, lpProcName);
  *a3 = ProcAddress;
  if ( ProcAddress )
  {
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    v9 = 774;
    if ( LastError )
      v9 = LastError;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v9;
}

```

## disassembly

```asm
0x180010700  mov     [rsp+arg_0], rbx
0x180010705  mov     [rsp+arg_8], rsi
0x18001070a  push    rdi
0x18001070b  sub     rsp, 20h
0x18001070f  mov     rbx, r8
0x180010712  mov     rsi, rdx
0x180010715  mov     rdi, rcx
0x180010718  test    r8, r8
0x18001071b  jnz     short loc_180010723
0x18001071d  lea     eax, [r8+57h]
0x180010721  jmp     short loc_18001075D
0x180010723  call    cs:__imp_EnterCriticalSection
0x180010729  mov     rcx, [rdi+28h]; hModule
0x18001072d  mov     rdx, rsi; lpProcName
0x180010730  call    cs:__imp_GetProcAddress
0x180010736  mov     [rbx], rax
0x180010739  test    rax, rax
0x18001073c  jnz     short loc_180010750
0x18001073e  call    cs:__imp_GetLastError
0x180010744  test    eax, eax
0x180010746  mov     ebx, 306h
0x18001074b  cmovnz  ebx, eax
0x18001074e  jmp     short loc_180010752
0x180010750  xor     ebx, ebx
0x180010752  mov     rcx, rdi; lpCriticalSection
0x180010755  call    cs:__imp_LeaveCriticalSection
0x18001075b  mov     eax, ebx
0x18001075d  mov     rbx, [rsp+28h+arg_0]
0x180010762  mov     rsi, [rsp+28h+arg_8]
0x180010767  add     rsp, 20h
0x18001076b  pop     rdi
0x18001076c  retn
```
