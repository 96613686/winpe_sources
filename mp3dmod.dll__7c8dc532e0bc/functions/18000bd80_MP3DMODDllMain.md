# MP3DMODDllMain

- ea: `0x18000bd80`
- end: `0x18000bddf`
- name: `MP3DMODDllMain`
- size: `95`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000bd80`
- `0x18000e6e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000bdc3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000bdc3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdd7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdd7`

## pseudocode

```c
BOOL __stdcall MP3DMODDllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    InitializeCriticalSection(&g_CriticalSection);
  }
  else if ( !fdwReason && !lpReserved )
  {
    DeleteCriticalSection(&g_CriticalSection);
  }
  return DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18000bd80  mov     [rsp+arg_0], rbx
0x18000bd85  mov     [rsp+arg_8], rsi
0x18000bd8a  push    rdi
0x18000bd8b  sub     rsp, 20h
0x18000bd8f  mov     rdi, r8
0x18000bd92  mov     ebx, edx
0x18000bd94  mov     rsi, rcx
0x18000bd97  cmp     edx, 1
0x18000bd9a  jz      short loc_18000BDBC
0x18000bd9c  test    edx, edx
0x18000bd9e  jz      short loc_18000BDCB
0x18000bda0  mov     r8, rdi; lpvReserved
0x18000bda3  mov     edx, ebx; fdwReason
0x18000bda5  mov     rcx, rsi; hinstDLL
0x18000bda8  mov     rbx, [rsp+28h+arg_0]
0x18000bdad  mov     rsi, [rsp+28h+arg_8]
0x18000bdb2  add     rsp, 20h
0x18000bdb6  pop     rdi
0x18000bdb7  jmp     _DllMainCRTStartup
0x18000bdbc  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bdc3  call    cs:__imp_InitializeCriticalSection
0x18000bdc9  jmp     short loc_18000BDA0
0x18000bdcb  test    rdi, rdi
0x18000bdce  jnz     short loc_18000BDA0
0x18000bdd0  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bdd7  call    cs:__imp_DeleteCriticalSection
0x18000bddd  jmp     short loc_18000BDA0
```
