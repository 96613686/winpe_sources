# ShellShim_EEDllUnregisterServer

- ea: `0x1800244e0`
- end: `0x1800245f9`
- name: `ShellShim_EEDllUnregisterServer`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800244e0`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024539`
- `KERNEL32!GetProcAddress` at `0x18002457d`
- `KERNEL32!GetProcAddress` at `0x1800245c8`
- `KERNEL32!GetProcAddress` at `0x180024539`
- `KERNEL32!GetProcAddress` at `0x18002457d`
- `KERNEL32!GetProcAddress` at `0x1800245c8`

## string_xrefs

- `0x180024576`: `EEDllUnregisterServer_RetAddr`
- `0x180024532`: `EEDllUnregisterServer`
- `0x1800245c1`: `EEDllUnregisterServer`

## pseudocode

```c
__int64 __fastcall ShellShim_EEDllUnregisterServer(__int64 a1)
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
    if ( g_pfEEDllUnregisterServer_RetAddr == (int (*)(HINSTANCE, void *))-1LL )
      g_pfEEDllUnregisterServer_RetAddr = (int (*)(HINSTANCE, void *))GetProcAddress(
                                                                        hModule,
                                                                        "EEDllUnregisterServer_RetAddr");
    if ( g_pfEEDllUnregisterServer_RetAddr )
      return ((__int64 (__fastcall *)(__int64, void *))g_pfEEDllUnregisterServer_RetAddr)(a1, retaddr);
    if ( g_pfEEDllUnregisterServer == (int (*)(HINSTANCE))-1LL )
      g_pfEEDllUnregisterServer = (int (*)(HINSTANCE))GetProcAddress(hModule, "EEDllUnregisterServer");
    if ( !g_pfEEDllUnregisterServer )
      return 2148734721LL;
    ProcAddress = (FARPROC)g_pfEEDllUnregisterServer;
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  }
  ProcAddress = (FARPROC)g_EEDllUnregisterServer;
  if ( g_EEDllUnregisterServer )
    return ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  hModule = 0;
  result = GetRealDll(&hModule, 1);
  if ( (int)result < 0 )
    return result;
  ProcAddress = GetProcAddress(hModule, "EEDllUnregisterServer");
  g_EEDllUnregisterServer = (int (*)(HINSTANCE))ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
  return 2148734721LL;
}

```

## disassembly

```asm
0x1800244e0  push    rbx
0x1800244e2  sub     rsp, 20h
0x1800244e6  mov     rbx, rcx
0x1800244e9  mov     [rsp+28h+hModule], 0
0x1800244f2  lea     rcx, [rsp+28h+hModule]
0x1800244f7  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800244fc  mov     edx, 1; int
0x180024501  cmp     eax, edx
0x180024503  jz      short loc_18002454F
0x180024505  cmp     eax, 3
0x180024508  jnz     short loc_18002455A
0x18002450a  mov     rax, cs:?g_EEDllUnregisterServer@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*g_EEDllUnregisterServer)(HINSTANCE__ *)
0x180024511  test    rax, rax
0x180024514  jnz     loc_1800245EC
0x18002451a  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x18002451f  mov     [rsp+28h+hModule], rax
0x180024524  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180024529  test    eax, eax
0x18002452b  js      short loc_180024554
0x18002452d  mov     rcx, [rsp+28h+hModule]; hModule
0x180024532  lea     rdx, aEedllunregiste_1; "EEDllUnregisterServer"
0x180024539  call    cs:__imp_GetProcAddress
0x18002453f  mov     cs:?g_EEDllUnregisterServer@@3P6AJPEAUHINSTANCE__@@@ZEA, rax; long (*g_EEDllUnregisterServer)(HINSTANCE__ *)
0x180024546  test    rax, rax
0x180024549  jnz     loc_1800245EC
0x18002454f  mov     eax, 80131701h
0x180024554  add     rsp, 20h
0x180024558  pop     rbx
0x180024559  retn
0x18002455a  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180024560  test    eax, eax
0x180024562  jnz     short loc_18002454F
0x180024564  mov     rax, cs:?g_pfEEDllUnregisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllUnregisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002456b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002456f  jnz     short loc_18002458A
0x180024571  mov     rcx, [rsp+28h+hModule]; hModule
0x180024576  lea     rdx, aEedllunregiste_0; "EEDllUnregisterServer_RetAddr"
0x18002457d  call    cs:__imp_GetProcAddress
0x180024583  mov     cs:?g_pfEEDllUnregisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA, rax; long (*g_pfEEDllUnregisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002458a  mov     rax, cs:?g_pfEEDllUnregisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllUnregisterServer_RetAddr)(HINSTANCE__ *,void *)
0x180024591  test    rax, rax
0x180024594  jz      short loc_1800245AF
0x180024596  mov     rax, cs:?g_pfEEDllUnregisterServer_RetAddr@@3R6AJPEAUHINSTANCE__@@PEAX@ZEA; long (*g_pfEEDllUnregisterServer_RetAddr)(HINSTANCE__ *,void *)
0x18002459d  mov     rcx, rbx
0x1800245a0  mov     rdx, [rsp+28h]
0x1800245a5  add     rsp, 20h
0x1800245a9  pop     rbx
0x1800245aa  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800245af  mov     rax, cs:?g_pfEEDllUnregisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllUnregisterServer)(HINSTANCE__ *)
0x1800245b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800245ba  jnz     short loc_1800245D5
0x1800245bc  mov     rcx, [rsp+28h+hModule]; hModule
0x1800245c1  lea     rdx, aEedllunregiste_1; "EEDllUnregisterServer"
0x1800245c8  call    cs:__imp_GetProcAddress
0x1800245ce  mov     cs:?g_pfEEDllUnregisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA, rax; long (*g_pfEEDllUnregisterServer)(HINSTANCE__ *)
0x1800245d5  mov     rax, cs:?g_pfEEDllUnregisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllUnregisterServer)(HINSTANCE__ *)
0x1800245dc  test    rax, rax
0x1800245df  jz      loc_18002454F
0x1800245e5  mov     rax, cs:?g_pfEEDllUnregisterServer@@3R6AJPEAUHINSTANCE__@@@ZEA; long (*g_pfEEDllUnregisterServer)(HINSTANCE__ *)
0x1800245ec  mov     rcx, rbx
0x1800245ef  add     rsp, 20h
0x1800245f3  pop     rbx
0x1800245f4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
