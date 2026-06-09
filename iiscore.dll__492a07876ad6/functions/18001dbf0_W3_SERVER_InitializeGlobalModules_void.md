# W3_SERVER::InitializeGlobalModules(void)

- ea: `0x18001dbf0`
- end: `0x18001dc97`
- name: `?InitializeGlobalModules@W3_SERVER@@QEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800147d0`

## callees

- `0x18001c5f0`
- `0x18001dbf0`
- `0x18001e020`
- `0x18002fa44`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18001dc68`
- `iisutil!PuDbgPrint` at `0x18001dc68`

## string_xrefs

- `0x18001dc4f`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`

## pseudocode

```c
__int64 __fastcall W3_SERVER::InitializeGlobalModules(W3_SERVER *this)
{
  int ModulesFromConfig; // eax
  unsigned int v3; // ebx

  MODULE_DLL::sm_cModuleCount = 0;
  qword_18004E4E0 = (__int64)&MODULE_DLL::sm_ModuleListHead;
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
0x18001dbf0  mov     [rsp+arg_0], rbx
0x18001dbf5  push    rdi
0x18001dbf6  sub     rsp, 30h
0x18001dbfa  lea     rax, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18001dc01  mov     cs:?sm_cModuleCount@MODULE_DLL@@0KA, 0; ulong MODULE_DLL::sm_cModuleCount
0x18001dc0b  lea     rdx, [rcx+3E8h]; struct MULTISZ *
0x18001dc12  mov     cs:qword_18004E4E0, rax
0x18001dc19  mov     r8d, 1; int
0x18001dc1f  mov     cs:?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18001dc26  mov     rdi, rcx
0x18001dc29  call    ?LoadModulesFromConfig@W3_SERVER@@QEAAJPEAVMULTISZ@@H@Z; W3_SERVER::LoadModulesFromConfig(MULTISZ *,int)
0x18001dc2e  mov     ebx, eax
0x18001dc30  test    eax, eax
0x18001dc32  jns     short loc_18001DC89
0x18001dc34  test    byte ptr cs:g_dwDebugFlags, 3
0x18001dc3b  jz      short loc_18001DC74
0x18001dc3d  mov     rcx, cs:g_pDebug
0x18001dc44  lea     r9, aW3ServerInitia_0; "W3_SERVER::InitializeGlobalModules"
0x18001dc4b  mov     [rsp+38h+var_10], eax
0x18001dc4f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001dc56  lea     rax, aErrorLoadingGl; "Error loading global modules.  hr = %x"...
0x18001dc5d  mov     r8d, 635h
0x18001dc63  mov     [rsp+38h+var_18], rax
0x18001dc68  call    cs:__imp_PuDbgPrint
0x18001dc6f  nop     dword ptr [rax+rax+00h]
0x18001dc74  lea     rcx, [rdi+230h]; this
0x18001dc7b  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001dc80  call    ?Terminate@MODULE_DLL@@SAXXZ; MODULE_DLL::Terminate(void)
0x18001dc85  mov     eax, ebx
0x18001dc87  jmp     short loc_18001DC8B
0x18001dc89  xor     eax, eax
0x18001dc8b  mov     rbx, [rsp+38h+arg_0]
0x18001dc90  add     rsp, 30h
0x18001dc94  pop     rdi
0x18001dc95  retn
```
