# ___crtLoadWinApiPointers

- ea: `0x10030387`
- end: `0x10030612`
- name: `___crtLoadWinApiPointers`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x10033c55`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1003038e`
- `KERNEL32!GetModuleHandleW` at `0x1003038e`
- `KERNEL32!GetProcAddress` at `0x100303a2`
- `KERNEL32!GetProcAddress` at `0x100303b5`
- `KERNEL32!GetProcAddress` at `0x100303c8`
- `KERNEL32!GetProcAddress` at `0x100303db`
- `KERNEL32!GetProcAddress` at `0x100303ee`
- `KERNEL32!GetProcAddress` at `0x10030401`
- `KERNEL32!GetProcAddress` at `0x10030414`
- `KERNEL32!GetProcAddress` at `0x10030427`
- `KERNEL32!GetProcAddress` at `0x1003043a`
- `KERNEL32!GetProcAddress` at `0x1003044d`
- `KERNEL32!GetProcAddress` at `0x10030460`
- `KERNEL32!GetProcAddress` at `0x10030473`
- `KERNEL32!GetProcAddress` at `0x10030486`
- `KERNEL32!GetProcAddress` at `0x10030499`
- `KERNEL32!GetProcAddress` at `0x100304ac`
- `KERNEL32!GetProcAddress` at `0x100304bf`
- `KERNEL32!GetProcAddress` at `0x100304d2`
- `KERNEL32!GetProcAddress` at `0x100304e5`
- `KERNEL32!GetProcAddress` at `0x100304f8`
- `KERNEL32!GetProcAddress` at `0x1003050b`
- `KERNEL32!GetProcAddress` at `0x1003051e`
- `KERNEL32!GetProcAddress` at `0x10030531`
- `KERNEL32!GetProcAddress` at `0x10030544`
- `KERNEL32!GetProcAddress` at `0x10030557`
- `KERNEL32!GetProcAddress` at `0x1003056a`
- `KERNEL32!GetProcAddress` at `0x1003057d`
- `KERNEL32!GetProcAddress` at `0x10030590`
- `KERNEL32!GetProcAddress` at `0x100305a3`
- `KERNEL32!GetProcAddress` at `0x100305b6`
- `KERNEL32!GetProcAddress` at `0x100305c9`
- `KERNEL32!GetProcAddress` at `0x100305dc`
- `KERNEL32!GetProcAddress` at `0x100305ef`
- `KERNEL32!GetProcAddress` at `0x10030602`
- `KERNEL32!GetProcAddress` at `0x10030394`

## string_xrefs

- `0x10030389`: `kernel32.dll`
- `0x100303f6`: `CreateEventExW`
- `0x10030409`: `CreateSemaphoreExW`
- `0x1003041c`: `SetThreadStackGuarantee`
- `0x1003042f`: `CreateThreadpoolTimer`
- `0x10030442`: `SetThreadpoolTimer`
- `0x10030455`: `WaitForThreadpoolTimerCallbacks`
- `0x10030468`: `CloseThreadpoolTimer`
- `0x1003047b`: `CreateThreadpoolWait`
- `0x1003048e`: `SetThreadpoolWait`
- `0x100304a1`: `CloseThreadpoolWait`
- `0x100304b9`: `FlushProcessWriteBuffers`
- `0x10030500`: `CreateSymbolicLinkW`
- `0x10030513`: `SetDefaultDllDirectories`
- `0x10030539`: `CompareStringEx`
- `0x100305f7`: `SetFileInformationByHandleW`

## pseudocode

```c
uintptr_t __crtLoadWinApiPointers()
{
  HMODULE ModuleHandleW; // edi
  uintptr_t result; // eax

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  encodedKERNEL32Functions = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FlsAlloc");
  dword_100481C4 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FlsFree");
  dword_100481C8 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FlsGetValue");
  dword_100481CC = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FlsSetValue");
  dword_100481D0 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "InitializeCriticalSectionEx");
  dword_100481D4 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CreateEventExW");
  dword_100481D8 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CreateSemaphoreExW");
  dword_100481DC = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "SetThreadStackGuarantee");
  dword_100481E0 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CreateThreadpoolTimer");
  dword_100481E4 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "SetThreadpoolTimer");
  dword_100481E8 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "WaitForThreadpoolTimerCallbacks");
  dword_100481EC = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CloseThreadpoolTimer");
  dword_100481F0 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CreateThreadpoolWait");
  dword_100481F4 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "SetThreadpoolWait");
  dword_100481F8 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CloseThreadpoolWait");
  dword_100481FC = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FlushProcessWriteBuffers");
  dword_10048200 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "FreeLibraryWhenCallbackReturns");
  dword_10048204 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetCurrentProcessorNumber");
  dword_10048208 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetLogicalProcessorInformation");
  dword_1004820C = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CreateSymbolicLinkW");
  dword_10048210 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
  dword_10048218 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "EnumSystemLocalesEx");
  dword_10048214 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "CompareStringEx");
  dword_1004821C = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetDateFormatEx");
  dword_10048220 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetLocaleInfoEx");
  dword_10048224 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetTimeFormatEx");
  dword_10048228 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetUserDefaultLocaleName");
  dword_1004822C = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "IsValidLocaleName");
  dword_10048230 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "LCMapStringEx");
  dword_10048234 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetCurrentPackageId");
  dword_10048238 = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetTickCount64");
  dword_1004823C = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "GetFileInformationByHandleExW");
  result = __security_cookie ^ (unsigned int)GetProcAddress(ModuleHandleW, "SetFileInformationByHandleW");
  dword_10048240 = result;
  return result;
}

```

## disassembly

```asm
0x10030387  push    esi
0x10030388  push    edi
0x10030389  push    offset ModuleName
0x1003038e  call    ds:__imp__GetModuleHandleW@4
0x10030394  mov     esi, ds:__imp__GetProcAddress@8
0x1003039a  mov     edi, eax
0x1003039c  push    offset aFlsalloc
0x100303a1  push    edi; hModule
0x100303a2  call    esi ; GetProcAddress(x,x)
0x100303a4  xor     eax, ___security_cookie
0x100303aa  push    offset aFlsfree
0x100303af  push    edi; hModule
0x100303b0  mov     _encodedKERNEL32Functions, eax
0x100303b5  call    esi ; GetProcAddress(x,x)
0x100303b7  xor     eax, ___security_cookie
0x100303bd  push    offset aFlsgetvalue
0x100303c2  push    edi; hModule
0x100303c3  mov     dword_100481C4, eax
0x100303c8  call    esi ; GetProcAddress(x,x)
0x100303ca  xor     eax, ___security_cookie
0x100303d0  push    offset aFlssetvalue
0x100303d5  push    edi; hModule
0x100303d6  mov     dword_100481C8, eax
0x100303db  call    esi ; GetProcAddress(x,x)
0x100303dd  xor     eax, ___security_cookie
0x100303e3  push    offset aInitializecrit
0x100303e8  push    edi; hModule
0x100303e9  mov     dword_100481CC, eax
0x100303ee  call    esi ; GetProcAddress(x,x)
0x100303f0  xor     eax, ___security_cookie
0x100303f6  push    offset aCreateeventexw
0x100303fb  push    edi; hModule
0x100303fc  mov     dword_100481D0, eax
0x10030401  call    esi ; GetProcAddress(x,x)
0x10030403  xor     eax, ___security_cookie
0x10030409  push    offset aCreatesemaphor
0x1003040e  push    edi; hModule
0x1003040f  mov     dword_100481D4, eax
0x10030414  call    esi ; GetProcAddress(x,x)
0x10030416  xor     eax, ___security_cookie
0x1003041c  push    offset aSetthreadstack
0x10030421  push    edi; hModule
0x10030422  mov     dword_100481D8, eax
0x10030427  call    esi ; GetProcAddress(x,x)
0x10030429  xor     eax, ___security_cookie
0x1003042f  push    offset aCreatethreadpo_0
0x10030434  push    edi; hModule
0x10030435  mov     dword_100481DC, eax
0x1003043a  call    esi ; GetProcAddress(x,x)
0x1003043c  xor     eax, ___security_cookie
0x10030442  push    offset aSetthreadpoolt
0x10030447  push    edi; hModule
0x10030448  mov     dword_100481E0, eax
0x1003044d  call    esi ; GetProcAddress(x,x)
0x1003044f  xor     eax, ___security_cookie
0x10030455  push    offset aWaitforthreadp
0x1003045a  push    edi; hModule
0x1003045b  mov     dword_100481E4, eax
0x10030460  call    esi ; GetProcAddress(x,x)
0x10030462  xor     eax, ___security_cookie
0x10030468  push    offset aClosethreadpoo_0
0x1003046d  push    edi; hModule
0x1003046e  mov     dword_100481E8, eax
0x10030473  call    esi ; GetProcAddress(x,x)
0x10030475  xor     eax, ___security_cookie
0x1003047b  push    offset aCreatethreadpo
0x10030480  push    edi; hModule
0x10030481  mov     dword_100481EC, eax
0x10030486  call    esi ; GetProcAddress(x,x)
0x10030488  xor     eax, ___security_cookie
0x1003048e  push    offset aSetthreadpoolw
0x10030493  push    edi; hModule
0x10030494  mov     dword_100481F0, eax
0x10030499  call    esi ; GetProcAddress(x,x)
0x1003049b  xor     eax, ___security_cookie
0x100304a1  push    offset aClosethreadpoo
0x100304a6  push    edi; hModule
0x100304a7  mov     dword_100481F4, eax
0x100304ac  call    esi ; GetProcAddress(x,x)
0x100304ae  xor     eax, ___security_cookie
0x100304b4  mov     dword_100481F8, eax
0x100304b9  push    offset aFlushprocesswr
0x100304be  push    edi; hModule
0x100304bf  call    esi ; GetProcAddress(x,x)
0x100304c1  xor     eax, ___security_cookie
0x100304c7  push    offset aFreelibrarywhe
0x100304cc  push    edi; hModule
0x100304cd  mov     dword_100481FC, eax
0x100304d2  call    esi ; GetProcAddress(x,x)
0x100304d4  xor     eax, ___security_cookie
0x100304da  push    offset aGetcurrentproc
0x100304df  push    edi; hModule
0x100304e0  mov     dword_10048200, eax
0x100304e5  call    esi ; GetProcAddress(x,x)
0x100304e7  xor     eax, ___security_cookie
0x100304ed  push    offset aGetlogicalproc
0x100304f2  push    edi; hModule
0x100304f3  mov     dword_10048204, eax
0x100304f8  call    esi ; GetProcAddress(x,x)
0x100304fa  xor     eax, ___security_cookie
0x10030500  push    offset aCreatesymbolic
0x10030505  push    edi; hModule
0x10030506  mov     dword_10048208, eax
0x1003050b  call    esi ; GetProcAddress(x,x)
0x1003050d  xor     eax, ___security_cookie
0x10030513  push    offset aSetdefaultdlld
0x10030518  push    edi; hModule
0x10030519  mov     dword_1004820C, eax
0x1003051e  call    esi ; GetProcAddress(x,x)
0x10030520  xor     eax, ___security_cookie
0x10030526  push    offset aEnumsystemloca
0x1003052b  push    edi; hModule
0x1003052c  mov     dword_10048210, eax
0x10030531  call    esi ; GetProcAddress(x,x)
0x10030533  xor     eax, ___security_cookie
0x10030539  push    offset aComparestringe
0x1003053e  push    edi; hModule
0x1003053f  mov     dword_10048218, eax
0x10030544  call    esi ; GetProcAddress(x,x)
0x10030546  xor     eax, ___security_cookie
0x1003054c  push    offset aGetdateformate
0x10030551  push    edi; hModule
0x10030552  mov     dword_10048214, eax
0x10030557  call    esi ; GetProcAddress(x,x)
0x10030559  xor     eax, ___security_cookie
0x1003055f  push    offset aGetlocaleinfoe
0x10030564  push    edi; hModule
0x10030565  mov     dword_1004821C, eax
0x1003056a  call    esi ; GetProcAddress(x,x)
0x1003056c  xor     eax, ___security_cookie
0x10030572  push    offset aGettimeformate
0x10030577  push    edi; hModule
0x10030578  mov     dword_10048220, eax
0x1003057d  call    esi ; GetProcAddress(x,x)
0x1003057f  xor     eax, ___security_cookie
0x10030585  push    offset aGetuserdefault
0x1003058a  push    edi; hModule
0x1003058b  mov     dword_10048224, eax
0x10030590  call    esi ; GetProcAddress(x,x)
0x10030592  xor     eax, ___security_cookie
0x10030598  push    offset aIsvalidlocalen
0x1003059d  push    edi; hModule
0x1003059e  mov     dword_10048228, eax
0x100305a3  call    esi ; GetProcAddress(x,x)
0x100305a5  xor     eax, ___security_cookie
0x100305ab  push    offset aLcmapstringex
0x100305b0  push    edi; hModule
0x100305b1  mov     dword_1004822C, eax
0x100305b6  call    esi ; GetProcAddress(x,x)
0x100305b8  xor     eax, ___security_cookie
0x100305be  push    offset aGetcurrentpack
0x100305c3  push    edi; hModule
0x100305c4  mov     dword_10048230, eax
0x100305c9  call    esi ; GetProcAddress(x,x)
0x100305cb  xor     eax, ___security_cookie
0x100305d1  push    offset aGettickcount64
0x100305d6  push    edi; hModule
0x100305d7  mov     dword_10048234, eax
0x100305dc  call    esi ; GetProcAddress(x,x)
0x100305de  xor     eax, ___security_cookie
0x100305e4  mov     dword_10048238, eax
0x100305e9  push    offset aGetfileinforma
0x100305ee  push    edi; hModule
0x100305ef  call    esi ; GetProcAddress(x,x)
0x100305f1  xor     eax, ___security_cookie
0x100305f7  push    offset aSetfileinforma
0x100305fc  push    edi; hModule
0x100305fd  mov     dword_1004823C, eax
0x10030602  call    esi ; GetProcAddress(x,x)
0x10030604  xor     eax, ___security_cookie
0x1003060a  pop     edi
0x1003060b  mov     dword_10048240, eax
0x10030610  pop     esi
0x10030611  retn
```
