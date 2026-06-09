# FCanStopService(void)

- ea: `0x140005014`
- end: `0x14000507d`
- name: `?FCanStopService@@YAHXZ`
- size: `105`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1400045f0`
- `0x140007374`
- `0x140007780`
- `0x1400078f0`

## callees

- `0x140005014`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x14000502f`
- `KERNEL32!GetModuleHandleExW` at `0x14000502f`
- `KERNEL32!GetProcAddress` at `0x140005045`
- `KERNEL32!GetProcAddress` at `0x140005045`
- `KERNEL32!FreeLibrary` at `0x14000505e`
- `KERNEL32!FreeLibrary` at `0x14000506d`
- `KERNEL32!FreeLibrary` at `0x14000505e`
- `KERNEL32!FreeLibrary` at `0x14000506d`

## string_xrefs

- `0x140005026`: `Msi.dll`

## pseudocode

```c
__int64 FCanStopService(void)
{
  unsigned int (*ProcAddress)(void); // rax
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(0, L"Msi.dll", &phModule) )
  {
    ProcAddress = (unsigned int (*)(void))GetProcAddress(phModule, "QueryInstanceCount");
    if ( ProcAddress && ProcAddress() )
    {
      FreeLibrary(phModule);
      return 0;
    }
    FreeLibrary(phModule);
  }
  return 1;
}

```

## disassembly

```asm
0x140005014  sub     rsp, 28h
0x140005018  lea     r8, [rsp+28h+phModule]; phModule
0x14000501d  mov     [rsp+28h+phModule], 0
0x140005026  lea     rdx, ModuleName; "Msi.dll"
0x14000502d  xor     ecx, ecx; dwFlags
0x14000502f  call    cs:__imp_GetModuleHandleExW
0x140005035  test    eax, eax
0x140005037  jz      short loc_140005073
0x140005039  mov     rcx, [rsp+28h+phModule]; hModule
0x14000503e  lea     rdx, aQueryinstancec; "QueryInstanceCount"
0x140005045  call    cs:__imp_GetProcAddress
0x14000504b  test    rax, rax
0x14000504e  jz      short loc_140005068
0x140005050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005055  test    eax, eax
0x140005057  jz      short loc_140005068
0x140005059  mov     rcx, [rsp+28h+phModule]; hLibModule
0x14000505e  call    cs:__imp_FreeLibrary
0x140005064  xor     eax, eax
0x140005066  jmp     short loc_140005078
0x140005068  mov     rcx, [rsp+28h+phModule]; hLibModule
0x14000506d  call    cs:__imp_FreeLibrary
0x140005073  mov     eax, 1
0x140005078  add     rsp, 28h
0x14000507c  retn
```
