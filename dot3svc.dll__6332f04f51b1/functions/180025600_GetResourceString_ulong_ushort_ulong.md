# GetResourceString(ulong,ushort *,ulong)

- ea: `0x180025600`
- end: `0x180025676`
- name: `?GetResourceString@@YAKKPEAGK@Z`
- size: `118`
- prototype: `__int64 __fastcall(UINT uID, LPWSTR lpBuffer)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002567c`
- `0x18002572c`
- `0x18002584c`

## callees

- `0x180025600`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002564a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002564a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180025626`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180025626`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025663`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025630`

## string_xrefs

- `0x180025618`: `dot3svc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetResourceString(UINT uID, LPWSTR lpBuffer)
{
  DWORD LastError; // ebx
  HMODULE phModule; // [rsp+48h] [rbp+20h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(0, L"dot3svc.dll", &phModule) && LoadStringW(phModule, uID, lpBuffer, 256) )
    LastError = 1812;
  else
    LastError = GetLastError();
  if ( phModule )
    FreeLibrary(phModule);
  return LastError;
}

```

## disassembly

```asm
0x180025600  mov     [rsp+arg_0], rbx
0x180025605  push    rdi
0x180025606  sub     rsp, 20h
0x18002560a  mov     rbx, rdx
0x18002560d  mov     [rsp+28h+phModule], 0
0x180025616  mov     edi, ecx
0x180025618  lea     rdx, aDot3svcDll_0; "dot3svc.dll"
0x18002561f  xor     ecx, ecx; dwFlags
0x180025621  lea     r8, [rsp+28h+phModule]; phModule
0x180025626  call    cs:__imp_GetModuleHandleExW
0x18002562c  test    eax, eax
0x18002562e  jnz     short loc_18002563A
0x180025630  call    cs:__imp_GetLastError
0x180025636  mov     ebx, eax
0x180025638  jmp     short loc_180025659
0x18002563a  mov     rcx, [rsp+28h+phModule]; hInstance
0x18002563f  mov     r9d, 100h; cchBufferMax
0x180025645  mov     r8, rbx; lpBuffer
0x180025648  mov     edx, edi; uID
0x18002564a  call    cs:__imp_LoadStringW
0x180025650  test    eax, eax
0x180025652  jz      short loc_180025630
0x180025654  mov     ebx, 714h
0x180025659  mov     rcx, [rsp+28h+phModule]; hLibModule
0x18002565e  test    rcx, rcx
0x180025661  jz      short loc_180025669
0x180025663  call    cs:__imp_FreeLibrary
0x180025669  mov     eax, ebx
0x18002566b  mov     rbx, [rsp+28h+arg_0]
0x180025670  add     rsp, 20h
0x180025674  pop     rdi
0x180025675  retn
```
