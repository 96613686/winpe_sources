# ShellShim_InitSSAutoEnterThread(void)

- ea: `0x180022d10`
- end: `0x180022e16`
- name: `?ShellShim_InitSSAutoEnterThread@@YAPEAJXZ`
- size: `262`
- prototype: `int *(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180022d10`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180022d62`
- `KERNEL32!GetProcAddress` at `0x180022da2`
- `KERNEL32!GetProcAddress` at `0x180022de9`
- `KERNEL32!GetProcAddress` at `0x180022d62`
- `KERNEL32!GetProcAddress` at `0x180022da2`
- `KERNEL32!GetProcAddress` at `0x180022de9`

## string_xrefs

- `0x180022d9b`: `InitSSAutoEnterThread_RetAddr`
- `0x180022de2`: `InitSSAutoEnterThread`

## pseudocode

```c
int *ShellShim_InitSSAutoEnterThread(void)
{
  int ShimImpl; // eax
  int *(*ProcAddress)(void); // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 0;
  if ( ShimImpl == 3 )
  {
    ProcAddress = g_InitSSAutoEnterThread;
    if ( !g_InitSSAutoEnterThread )
    {
      hModule = 0;
      if ( (int)GetRealDll(&hModule, 1) < 0 )
        return 0;
      ProcAddress = (int *(*)(void))GetProcAddress(hModule, (LPCSTR)0x13);
      g_InitSSAutoEnterThread = ProcAddress;
      if ( !ProcAddress )
        return 0;
    }
  }
  else
  {
    if ( g_bShimImplDllUninitialized )
      return 0;
    if ( g_pfInitSSAutoEnterThread_RetAddr == (int *(*)(void *))-1LL )
      g_pfInitSSAutoEnterThread_RetAddr = (int *(*)(void *))GetProcAddress(hModule, "InitSSAutoEnterThread_RetAddr");
    if ( g_pfInitSSAutoEnterThread_RetAddr )
      return (int *)((__int64 (__fastcall *)(void *))g_pfInitSSAutoEnterThread_RetAddr)(retaddr);
    if ( g_pfInitSSAutoEnterThread == (int *(*)(void))-1LL )
      g_pfInitSSAutoEnterThread = (int *(*)(void))GetProcAddress(hModule, "InitSSAutoEnterThread");
    if ( !g_pfInitSSAutoEnterThread )
      return 0;
    ProcAddress = g_pfInitSSAutoEnterThread;
  }
  return ProcAddress();
}

```

## disassembly

```asm
0x180022d10  sub     rsp, 28h
0x180022d14  lea     rcx, [rsp+28h+hModule]
0x180022d19  mov     [rsp+28h+hModule], 0
0x180022d22  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180022d27  mov     edx, 1; int
0x180022d2c  cmp     eax, edx
0x180022d2e  jz      short loc_180022D78
0x180022d30  cmp     eax, 3
0x180022d33  jnz     short loc_180022D7F
0x180022d35  mov     rax, cs:?g_InitSSAutoEnterThread@@3P6APEAJXZEA; long * (*g_InitSSAutoEnterThread)(void)
0x180022d3c  test    rax, rax
0x180022d3f  jnz     loc_180022E0D
0x180022d45  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x180022d4a  mov     [rsp+28h+hModule], rax
0x180022d4f  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180022d54  test    eax, eax
0x180022d56  js      short loc_180022D78
0x180022d58  mov     rcx, [rsp+28h+hModule]; hModule
0x180022d5d  mov     edx, 13h; lpProcName
0x180022d62  call    cs:__imp_GetProcAddress
0x180022d68  mov     cs:?g_InitSSAutoEnterThread@@3P6APEAJXZEA, rax; long * (*g_InitSSAutoEnterThread)(void)
0x180022d6f  test    rax, rax
0x180022d72  jnz     loc_180022E0D
0x180022d78  xor     eax, eax
0x180022d7a  add     rsp, 28h
0x180022d7e  retn
0x180022d7f  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180022d85  test    eax, eax
0x180022d87  jnz     short loc_180022D78
0x180022d89  mov     rax, cs:?g_pfInitSSAutoEnterThread_RetAddr@@3R6APEAJPEAX@ZEA; long * (*g_pfInitSSAutoEnterThread_RetAddr)(void *)
0x180022d90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022d94  jnz     short loc_180022DAF
0x180022d96  mov     rcx, [rsp+28h+hModule]; hModule
0x180022d9b  lea     rdx, aInitssautoente_1; "InitSSAutoEnterThread_RetAddr"
0x180022da2  call    cs:__imp_GetProcAddress
0x180022da8  mov     cs:?g_pfInitSSAutoEnterThread_RetAddr@@3R6APEAJPEAX@ZEA, rax; long * (*g_pfInitSSAutoEnterThread_RetAddr)(void *)
0x180022daf  mov     rax, cs:?g_pfInitSSAutoEnterThread_RetAddr@@3R6APEAJPEAX@ZEA; long * (*g_pfInitSSAutoEnterThread_RetAddr)(void *)
0x180022db6  test    rax, rax
0x180022db9  jz      short loc_180022DD0
0x180022dbb  mov     rax, cs:?g_pfInitSSAutoEnterThread_RetAddr@@3R6APEAJPEAX@ZEA; long * (*g_pfInitSSAutoEnterThread_RetAddr)(void *)
0x180022dc2  mov     rcx, [rsp+28h]
0x180022dc7  add     rsp, 28h
0x180022dcb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180022dd0  mov     rax, cs:?g_pfInitSSAutoEnterThread@@3R6APEAJXZEA; long * (*g_pfInitSSAutoEnterThread)(void)
0x180022dd7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022ddb  jnz     short loc_180022DF6
0x180022ddd  mov     rcx, [rsp+28h+hModule]; hModule
0x180022de2  lea     rdx, aInitssautoente_0; "InitSSAutoEnterThread"
0x180022de9  call    cs:__imp_GetProcAddress
0x180022def  mov     cs:?g_pfInitSSAutoEnterThread@@3R6APEAJXZEA, rax; long * (*g_pfInitSSAutoEnterThread)(void)
0x180022df6  mov     rax, cs:?g_pfInitSSAutoEnterThread@@3R6APEAJXZEA; long * (*g_pfInitSSAutoEnterThread)(void)
0x180022dfd  test    rax, rax
0x180022e00  jz      loc_180022D78
0x180022e06  mov     rax, cs:?g_pfInitSSAutoEnterThread@@3R6APEAJXZEA; long * (*g_pfInitSSAutoEnterThread)(void)
0x180022e0d  add     rsp, 28h
0x180022e11  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
