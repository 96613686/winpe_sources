# DllMain

- ea: `0x180021fc4`
- end: `0x180022161`
- name: `DllMain`
- size: `413`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180037f44`

## callees

- `0x18001f500`
- `0x180021fc4`
- `0x180022168`
- `0x1800221f8`
- `0x1800222c4`
- `0x1800222fc`
- `0x180022444`
- `0x18002247c`
- `0x1800225a4`
- `0x180037a98`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180021fe4`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180021fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800220c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800220c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002210b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022123`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002210b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022123`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // r8
  __int64 v6; // r8

  g_hInstance = hinstDLL;
  if ( fdwReason == 1 )
  {
    LdrDisableThreadCalloutsForDll(hinstDLL);
    DllMainCRTStartupForGS2((__int64)hinstDLL, 1);
    SafeAllocaInitialize();
    McGenEventRegister_EventRegister();
    qword_18007A8D8 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CNGTraceControlGuid;
    qword_18007A8D0 = 0;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    WppInitUm();
    if ( (unsigned int)InitializeCNGProv() )
      return 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      GetModuleFileNameW(0, &Filename, 0x100u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, hinstDLL);
    }
  }
  else if ( !fdwReason )
  {
    if ( g_hPromptUserInst )
    {
      FreeLibrary(g_hPromptUserInst);
      g_hPromptUserInst = 0;
    }
    if ( g_BioLibrary )
    {
      FreeLibrary(g_BioLibrary);
      g_BioLibrary = 0;
    }
    UninitializeCNGProv();
    McGenEventUnregister_EventUnregister();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v5, hinstDLL);
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x180021fc4  mov     [rsp+arg_0], rbx
0x180021fc9  push    rdi
0x180021fca  sub     rsp, 30h
0x180021fce  mov     cs:g_hInstance, rcx
0x180021fd5  mov     rbx, r8
0x180021fd8  mov     rdi, rcx
0x180021fdb  cmp     edx, 1
0x180021fde  jnz     loc_180022071
0x180021fe4  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x180021feb  nop     dword ptr [rax+rax+00h]
0x180021ff0  mov     r8, rbx
0x180021ff3  mov     edx, 1
0x180021ff8  mov     rcx, rdi
0x180021ffb  call    _DllMainCRTStartupForGS2
0x180022000  call    SafeAllocaInitialize
0x180022005  call    McGenEventRegister_EventRegister
0x18002200a  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x180022011  mov     cs:qword_18007A8D8, 1
0x18002201c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180022023  xor     ebx, ebx
0x180022025  lea     rax, WPP_MAIN_CB
0x18002202c  mov     cs:qword_18007A8D0, rbx
0x180022033  mov     cs:WPP_GLOBAL_Control, rax
0x18002203a  mov     cs:WPP_MAIN_CB, rbx
0x180022041  call    WppInitUm
0x180022046  call    InitializeCNGProv
0x18002204b  test    eax, eax
0x18002204d  jz      short loc_180022053
0x18002204f  xor     eax, eax
0x180022051  jmp     short loc_180022065
0x180022053  mov     rax, cs:WPP_GLOBAL_Control
0x18002205a  test    byte ptr [rax+1Ch], 20h
0x18002205e  jnz     short loc_1800220B9
0x180022060  mov     eax, 1
0x180022065  mov     rbx, [rsp+38h+arg_0]
0x18002206a  add     rsp, 30h
0x18002206e  pop     rdi
0x18002206f  retn
0x180022071  xor     ebx, ebx
0x180022073  test    edx, edx
0x180022075  jnz     short loc_180022060
0x180022077  mov     rcx, cs:g_hPromptUserInst; hLibModule
0x18002207e  test    rcx, rcx
0x180022081  jnz     loc_18002210B
0x180022087  mov     rcx, cs:g_BioLibrary; hLibModule
0x18002208e  test    rcx, rcx
0x180022091  jnz     loc_180022123
0x180022097  call    UninitializeCNGProv
0x18002209c  call    McGenEventUnregister_EventUnregister
0x1800220a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220a8  test    byte ptr [rcx+1Ch], 20h
0x1800220ac  jnz     loc_18002213B
0x1800220b2  call    WppCleanupUm
0x1800220b7  jmp     short loc_180022060
0x1800220b9  mov     r8d, 100h; nSize
0x1800220bf  lea     rdx, Filename; lpFilename
0x1800220c6  xor     ecx, ecx; hModule
0x1800220c8  call    cs:__imp_GetModuleFileNameW
0x1800220cf  nop     dword ptr [rax+rax+00h]
0x1800220d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220db  lea     rax, WPP_GLOBAL_Control
0x1800220e2  cmp     rcx, rax
0x1800220e5  jz      loc_180022060
0x1800220eb  test    byte ptr [rcx+1Ch], 20h
0x1800220ef  jz      loc_180022060
0x1800220f5  mov     rcx, [rcx+10h]
0x1800220f9  mov     edx, 0Ah
0x1800220fe  mov     r9, rdi
0x180022101  call    WPP_SF_qS
0x180022106  jmp     loc_180022060
0x18002210b  call    cs:__imp_FreeLibrary
0x180022112  nop     dword ptr [rax+rax+00h]
0x180022117  mov     cs:g_hPromptUserInst, rbx
0x18002211e  jmp     loc_180022087
0x180022123  call    cs:__imp_FreeLibrary
0x18002212a  nop     dword ptr [rax+rax+00h]
0x18002212f  mov     cs:g_BioLibrary, rbx
0x180022136  jmp     loc_180022097
0x18002213b  lea     rax, WPP_GLOBAL_Control
0x180022142  cmp     rcx, rax
0x180022145  jz      loc_1800220B2
0x18002214b  mov     rcx, [rcx+10h]
0x18002214f  mov     edx, 0Bh
0x180022154  mov     r9, rdi
0x180022157  call    WPP_SF_qS
0x18002215c  jmp     loc_1800220B2
```
