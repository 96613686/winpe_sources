# DllMain

- ea: `0x18001e5a0`
- end: `0x18001e626`
- name: `DllMain`
- size: `134`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180018704`

## callees

- `0x18000c770`
- `0x180014240`
- `0x18001e5a0`
- `0x18001ee10`
- `0x18001f210`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001e5eb`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001e5eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001e5cd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001e5cd`

## string_xrefs

- `0x18001e5c6`: `Unable to Create Debug Print Object \n`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _DWORD *DebugPrintsObject; // rax

  if ( fdwReason == 1 )
  {
    DebugPrintsObject = (_DWORD *)PuCreateDebugPrintsObject("iisutil");
    g_pDebug = DebugPrintsObject;
    if ( (DebugPrintsObject
       || (OutputDebugStringA("Unable to Create Debug Print Object \n"), (DebugPrintsObject = g_pDebug) != 0))
      && DebugPrintsObject[160] )
    {
      DisableThreadLibraryCalls(hinstDLL);
      return InitializeIISUtilProcessAttach();
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( !fdwReason )
    {
      TerminateIISUtilProcessDetach();
      g_pDebug = (HGLOBAL)PuDeleteDebugPrintsObject(g_pDebug);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18001e5a0  push    rbx
0x18001e5a2  sub     rsp, 20h
0x18001e5a6  mov     rbx, rcx
0x18001e5a9  cmp     edx, 1
0x18001e5ac  jnz     short loc_18001E5FF
0x18001e5ae  lea     rcx, aIisutil; "iisutil"
0x18001e5b5  call    PuCreateDebugPrintsObject
0x18001e5ba  mov     cs:g_pDebug, rax
0x18001e5c1  test    rax, rax
0x18001e5c4  jnz     short loc_18001E5DF
0x18001e5c6  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x18001e5cd  call    cs:__imp_OutputDebugStringA
0x18001e5d3  mov     rax, cs:g_pDebug
0x18001e5da  test    rax, rax
0x18001e5dd  jz      short loc_18001E5FB
0x18001e5df  cmp     dword ptr [rax+280h], 0
0x18001e5e6  jz      short loc_18001E5FB
0x18001e5e8  mov     rcx, rbx; hLibModule
0x18001e5eb  call    cs:__imp_DisableThreadLibraryCalls
0x18001e5f1  add     rsp, 20h
0x18001e5f5  pop     rbx
0x18001e5f6  jmp     InitializeIISUtilProcessAttach
0x18001e5fb  xor     eax, eax
0x18001e5fd  jmp     short loc_18001E620
0x18001e5ff  test    edx, edx
0x18001e601  jnz     short loc_18001E61B
0x18001e603  call    TerminateIISUtilProcessDetach
0x18001e608  mov     rcx, cs:g_pDebug; hMem
0x18001e60f  call    PuDeleteDebugPrintsObject
0x18001e614  mov     cs:g_pDebug, rax
0x18001e61b  mov     eax, 1
0x18001e620  add     rsp, 20h
0x18001e624  pop     rbx
0x18001e625  retn
```
