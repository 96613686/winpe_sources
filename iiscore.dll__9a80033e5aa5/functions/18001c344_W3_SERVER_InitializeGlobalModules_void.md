# W3_SERVER::InitializeGlobalModules(void)

- ea: `0x18001c344`
- end: `0x18001c3e4`
- name: `?InitializeGlobalModules@W3_SERVER@@QEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013690`

## callees

- `0x18001aed0`
- `0x18001c344`
- `0x18001c6fc`
- `0x18002d07c`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001c3bc`
- `iisutil!PuDbgPrint` at `0x18001c3bc`

## string_xrefs

- `0x18001c3a3`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

## pseudocode

```c
__int64 __fastcall W3_SERVER::InitializeGlobalModules(W3_SERVER *this)
{
  int ModulesFromConfig; // eax
  unsigned int v3; // ebx

  MODULE_DLL::sm_cModuleCount = 0;
  qword_18004B4E0 = (__int64)&MODULE_DLL::sm_ModuleListHead;
  MODULE_DLL::sm_ModuleListHead.Flink = &MODULE_DLL::sm_ModuleListHead;
  ModulesFromConfig = W3_SERVER::LoadModulesFromConfig(this, (W3_SERVER *)((char *)this + 1000), 1);
  v3 = ModulesFromConfig;
  if ( ModulesFromConfig >= 0 )
    return 0;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
      1589,
      "W3_SERVER::InitializeGlobalModules",
      "Error loading global modules.  hr = %x\n",
      ModulesFromConfig);
  MODULE_LIST::FreeModules((W3_SERVER *)((char *)this + 560));
  MODULE_DLL::Terminate();
  return v3;
}

```

## disassembly

```asm
0x18001c344  mov     [rsp+arg_0], rbx
0x18001c349  push    rdi
0x18001c34a  sub     rsp, 30h
0x18001c34e  lea     rax, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18001c355  mov     cs:?sm_cModuleCount@MODULE_DLL@@0KA, 0; ulong MODULE_DLL::sm_cModuleCount
0x18001c35f  lea     rdx, [rcx+3E8h]; struct MULTISZ *
0x18001c366  mov     cs:qword_18004B4E0, rax
0x18001c36d  mov     r8d, 1; int
0x18001c373  mov     cs:?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18001c37a  mov     rdi, rcx
0x18001c37d  call    ?LoadModulesFromConfig@W3_SERVER@@QEAAJPEAVMULTISZ@@H@Z; W3_SERVER::LoadModulesFromConfig(MULTISZ *,int)
0x18001c382  mov     ebx, eax
0x18001c384  test    eax, eax
0x18001c386  jns     short loc_18001C3D7
0x18001c388  test    byte ptr cs:g_dwDebugFlags, 3
0x18001c38f  jz      short loc_18001C3C2
0x18001c391  mov     rcx, cs:g_pDebug
0x18001c398  lea     r9, aW3ServerInitia_0; "W3_SERVER::InitializeGlobalModules"
0x18001c39f  mov     [rsp+38h+var_10], eax
0x18001c3a3  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001c3aa  lea     rax, aErrorLoadingGl; "Error loading global modules.  hr = %x"...
0x18001c3b1  mov     r8d, 635h
0x18001c3b7  mov     [rsp+38h+var_18], rax
0x18001c3bc  call    cs:__imp_PuDbgPrint
0x18001c3c2  lea     rcx, [rdi+230h]; this
0x18001c3c9  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001c3ce  call    ?Terminate@MODULE_DLL@@SAXXZ; MODULE_DLL::Terminate(void)
0x18001c3d3  mov     eax, ebx
0x18001c3d5  jmp     short loc_18001C3D9
0x18001c3d7  xor     eax, eax
0x18001c3d9  mov     rbx, [rsp+38h+arg_0]
0x18001c3de  add     rsp, 30h
0x18001c3e2  pop     rdi
0x18001c3e3  retn
```
