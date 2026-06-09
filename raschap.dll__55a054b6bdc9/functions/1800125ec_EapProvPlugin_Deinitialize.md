# EapProvPlugin_Deinitialize

- ea: `0x1800125ec`
- end: `0x18001264b`
- name: `EapProvPlugin_Deinitialize`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042f0`

## callees

- `0x1800125ec`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012614`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012614`

## pseudocode

```c
__int64 EapProvPlugin_Deinitialize()
{
  HMODULE v0; // rcx
  __int64 result; // rax

  v0 = g_hEapProvPluginDll;
  if ( g_hEapProvPluginDll )
  {
    if ( *(&g_EapProvPluginDllFunctionTable + 1) )
    {
      (*(&g_EapProvPluginDllFunctionTable + 1))();
      v0 = g_hEapProvPluginDll;
    }
    FreeLibrary(v0);
    g_hEapProvPluginDll = 0;
  }
  result = 0;
  *(_OWORD *)&g_EapProvPluginDllFunctionTable = 0;
  qword_1800339A8 = 0;
  *(_OWORD *)&xmmword_180033988 = 0;
  xmmword_180033998 = 0;
  return result;
}

```

## disassembly

```asm
0x1800125ec  sub     rsp, 28h
0x1800125f0  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hEapProvPluginDll
0x1800125f7  test    rcx, rcx
0x1800125fa  jz      short loc_180012625
0x1800125fc  mov     rax, qword ptr cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A+8; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180012603  test    rax, rax
0x180012606  jz      short loc_180012614
0x180012608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260d  mov     rcx, cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x180012614  call    cs:__imp_FreeLibrary
0x18001261a  mov     cs:?g_hEapProvPluginDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hEapProvPluginDll
0x180012625  xorps   xmm0, xmm0
0x180012628  xor     eax, eax
0x18001262a  movups  cs:?g_EapProvPluginDllFunctionTable@@3U_EAPPROVPLUGIN_FUNCTION_TABLE@@A, xmm0; _EAPPROVPLUGIN_FUNCTION_TABLE g_EapProvPluginDllFunctionTable
0x180012631  mov     cs:qword_1800339A8, rax
0x180012638  movups  cs:xmmword_180033988, xmm0
0x18001263f  movups  cs:xmmword_180033998, xmm0
0x180012646  add     rsp, 28h
0x18001264a  retn
```
