# ShellShim_EEDllRegisterServer

- ea: `0x1800243c0`
- end: `0x1800244d9`
- name: `ShellShim_EEDllRegisterServer`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800243c0`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024419`
- `KERNEL32!GetProcAddress` at `0x18002445d`
- `KERNEL32!GetProcAddress` at `0x1800244a8`
- `KERNEL32!GetProcAddress` at `0x180024419`
- `KERNEL32!GetProcAddress` at `0x18002445d`
- `KERNEL32!GetProcAddress` at `0x1800244a8`

## string_xrefs

- `0x180024456`: `EEDllRegisterServer_RetAddr`
- `0x180024412`: `EEDllRegisterServer`
- `0x1800244a1`: `EEDllRegisterServer`

## pseudocode

```c
__int64 __fastcall ShellShim_EEDllRegisterServer(__int64 a1)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+38h] [rbp+10h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl != 3 )
  {
    if ( g_bShimImplDllUninitialized )
      return 2148734721LL;
    if ( g_pfEEDllRegisterServer_RetAddr == (int (*)(HINSTANCE, void *))-1LL )
      g_pfEEDllRegisterServer_RetAddr = (int (*)(HINSTANCE, void *))GetProcAddress(
                                                                      hModule,
                                                                      "EEDllRegisterServer_RetAddr");
    if ( g_pfEEDllRegisterServer_RetAddr )
      return ((__int64 (__fastcall *)(__int64, void *))g_pfEEDllRegisterServer_RetAddr)(a1, retaddr);
    if ( g_pfEEDllRegisterServer == (int (*)(HINSTANCE))-1LL )
      g_pfEEDllRegisterServer = (int (*)(HINSTANCE))GetProcAddress(hModule, "EEDllRegisterServer");
    if ( !g_pfEEDllRegisterServer )
      return 2148734721LL;
    ProcAddress = (FARPROC)g_pfEEDllRegisterServer;
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  }
  ProcAddress = (FARPROC)g_EEDllRegisterServer;
  if ( g_EEDllRegisterServer )
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  hModule = 0;
  result = GetRealDll(&hModule, 1);
  if ( (int)result < 0 )
    return result;
  ProcAddress = GetProcAddress(hModule, "EEDllRegisterServer");
  g_EEDllRegisterServer = (int (*)(HINSTANCE))ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
  return 2148734721LL;
}

```

## disassembly

```asm
0x1800243c0  push    rbx
0x1800243c2  sub     rsp, 20h
0x1800243c6  mov     rbx, rcx
0x1800243c9  mov     [rsp+28h+hModule], 0
0x1800243d2  lea     rcx, [rsp+28h+hModule]
0x1800243d7  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800243dc  mov     edx, 1; int
0x1800243e1  cmp     eax, edx
0x1800243e3  jz      short loc_18002442F
0x1800243e5  cmp     eax, 3
0x1800243e8  jnz     short loc_18002443A
0x1800243ea  mov     rax, cs:?g_EEDllRegisterServer@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*g_EEDllRegisterServer)(HINSTANCE__ *)
0x1800243f1  test    rax, rax
0x1800243f4  jnz     loc_1800244CC
0x1800243fa  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x1800243ff  mov     [rsp+28h+hModule], rax
0x180024404  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180024409  test    eax, eax
0x18002440b  js      short loc_180024434
0x18002440d  mov     rcx, [rsp+28h+hModule]; hModule
0x180024412  lea     rdx, aEedllregisters_0; "EEDllRegisterServer"
0x180024419  call    cs:__imp_GetProcAddress
0x18002441f  mov     cs:?g_EEDllRegisterServer@@3P6AJPEAUHINSTANCE__@@@ZEA, rax; long (*g_EEDllRegisterServer)(HINSTANCE__ *)
0x180024426  test    rax, rax
0x180024429  jnz     loc_1800244CC
0x18002442f  mov     eax, 80131701h
0x180024434  add     rsp, 20h
0x180024438  pop     rbx
0x180024439  retn
0x18002443a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180024440  test    eax, eax
0x180024442  jnz     short loc_18002442F
0x180024444  mov     rax, cs:?g_pfEEDllRegisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllRegisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002444b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002444f  jnz     short loc_18002446A
0x180024451  mov     rcx, [rsp+28h+hModule]; hModule
0x180024456  lea     rdx, aEedllregisters_1; "EEDllRegisterServer_RetAddr"
0x18002445d  call    cs:__imp_GetProcAddress
0x180024463  mov     cs:?g_pfEEDllRegisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA, rax; long (*g_pfEEDllRegisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002446a  mov     rax, cs:?g_pfEEDllRegisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllRegisterServer_RetAddr)(HINSTANCE__ *,void *)
0x180024471  test    rax, rax
0x180024474  jz      short loc_18002448F
0x180024476  mov     rax, cs:?g_pfEEDllRegisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllRegisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002447d  mov     rcx, rbx
0x180024480  mov     rdx, [rsp+28h]
0x180024485  add     rsp, 20h
0x180024489  pop     rbx
0x18002448a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18002448f  mov     rax, cs:?g_pfEEDllRegisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllRegisterServer)(HINSTANCE__ *)
0x180024496  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002449a  jnz     short loc_1800244B5
0x18002449c  mov     rcx, [rsp+28h+hModule]; hModule
0x1800244a1  lea     rdx, aEedllregisters_0; "EEDllRegisterServer"
0x1800244a8  call    cs:__imp_GetProcAddress
0x1800244ae  mov     cs:?g_pfEEDllRegisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA, rax; long (*g_pfEEDllRegisterServer)(HINSTANCE__ *)
0x1800244b5  mov     rax, cs:?g_pfEEDllRegisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllRegisterServer)(HINSTANCE__ *)
0x1800244bc  test    rax, rax
0x1800244bf  jz      loc_18002442F
0x1800244c5  mov     rax, cs:?g_pfEEDllRegisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllRegisterServer)(HINSTANCE__ *)
0x1800244cc  mov     rcx, rbx
0x1800244cf  add     rsp, 20h
0x1800244d3  pop     rbx
0x1800244d4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
