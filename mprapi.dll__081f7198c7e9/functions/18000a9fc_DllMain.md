# DllMain

- ea: `0x18000a9fc`
- end: `0x18000aaf5`
- name: `DllMain`
- size: `249`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012e4`

## callees

- `0x18000a9fc`
- `0x18002b708`
- `0x18002b884`
- `0x18002b954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000aa1d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000aa34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000aa1d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000aa34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000aa77`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000aa77`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aab0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aac6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aadf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aab0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aac6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aadf`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aa56`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aa56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa81`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  DWORD LastError; // ebx

  if ( !fdwReason )
  {
    if ( dword_180078C88 )
      DeleteCriticalSection(&DsrLock);
    if ( dword_180078C8C )
      DeleteCriticalSection(&CfgLock);
    if ( _InterlockedExchange(&g_bRpcCsInitialized, 0) )
      DeleteCriticalSection(&g_RpcCs);
    RasMprApiUnRegisterEtw(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
    return 1;
  }
  if ( fdwReason != 1 )
    return 1;
  InitializeCriticalSection(&DsrLock);
  dword_180078C88 = 1;
  InitializeCriticalSection(&CfgLock);
  dword_180078C8C = 1;
  if ( (int)McGenEventRegister_EventRegister() >= 0 )
    SetLibParams();
  DisableThreadLibraryCalls(hinstDLL);
  if ( g_bRpcCsInitialized )
    return 1;
  LastError = 0;
  if ( !InitializeCriticalSectionAndSpinCount(&g_RpcCs, 0xFA0u) )
    LastError = GetLastError();
  g_bRpcCsInitialized = 1;
  return LastError == 0;
}

```

## disassembly

```asm
0x18000a9fc  push    rbx
0x18000a9fe  sub     rsp, 20h
0x18000aa02  mov     rbx, rcx
0x18000aa05  test    edx, edx
0x18000aa07  jz      loc_18000AAA0
0x18000aa0d  cmp     edx, 1
0x18000aa10  jnz     loc_18000AAEA
0x18000aa16  lea     rcx, DsrLock; lpCriticalSection
0x18000aa1d  call    cs:__imp_InitializeCriticalSection
0x18000aa23  mov     cs:dword_180078C88, 1
0x18000aa2d  lea     rcx, CfgLock; lpCriticalSection
0x18000aa34  call    cs:__imp_InitializeCriticalSection
0x18000aa3a  mov     cs:dword_180078C8C, 1
0x18000aa44  call    McGenEventRegister_EventRegister
0x18000aa49  test    eax, eax
0x18000aa4b  js      short loc_18000AA53
0x18000aa4d  call    SetLibParams
0x18000aa52  nop
0x18000aa53  mov     rcx, rbx; hLibModule
0x18000aa56  call    cs:__imp_DisableThreadLibraryCalls
0x18000aa5c  cmp     cs:g_bRpcCsInitialized, 0
0x18000aa63  jnz     loc_18000AAEA
0x18000aa69  xor     ebx, ebx
0x18000aa6b  mov     edx, 0FA0h; dwSpinCount
0x18000aa70  lea     rcx, g_RpcCs; lpCriticalSection
0x18000aa77  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000aa7d  test    eax, eax
0x18000aa7f  jnz     short loc_18000AA89
0x18000aa81  call    cs:__imp_GetLastError
0x18000aa87  mov     ebx, eax
0x18000aa89  mov     cs:g_bRpcCsInitialized, 1
0x18000aa93  xor     eax, eax
0x18000aa95  test    ebx, ebx
0x18000aa97  setz    al
0x18000aa9a  jmp     short loc_18000AAEF
0x18000aa9c  xor     eax, eax
0x18000aa9e  jmp     short loc_18000AAEF
0x18000aaa0  cmp     cs:dword_180078C88, 0
0x18000aaa7  jz      short loc_18000AAB6
0x18000aaa9  lea     rcx, DsrLock; lpCriticalSection
0x18000aab0  call    cs:__imp_DeleteCriticalSection
0x18000aab6  cmp     cs:dword_180078C8C, 0
0x18000aabd  jz      short loc_18000AACC
0x18000aabf  lea     rcx, CfgLock; lpCriticalSection
0x18000aac6  call    cs:__imp_DeleteCriticalSection
0x18000aacc  xor     eax, eax
0x18000aace  xchg    eax, cs:g_bRpcCsInitialized
0x18000aad4  test    eax, eax
0x18000aad6  jz      short loc_18000AAE5
0x18000aad8  lea     rcx, g_RpcCs; lpCriticalSection
0x18000aadf  call    cs:__imp_DeleteCriticalSection
0x18000aae5  call    RasMprApiUnRegisterEtw
0x18000aaea  mov     eax, 1
0x18000aaef  add     rsp, 20h
0x18000aaf3  pop     rbx
0x18000aaf4  retn
```
