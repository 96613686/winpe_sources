# ShellShim_ReOpenMetaDataWithMemory

- ea: `0x1800266f0`
- end: `0x180026828`
- name: `ShellShim_ReOpenMetaDataWithMemory`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x1800266f0`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026755`
- `KERNEL32!GetProcAddress` at `0x1800267a3`
- `KERNEL32!GetProcAddress` at `0x1800267f1`
- `KERNEL32!GetProcAddress` at `0x180026755`
- `KERNEL32!GetProcAddress` at `0x1800267a3`
- `KERNEL32!GetProcAddress` at `0x1800267f1`

## string_xrefs

- `0x18002679c`: `ReOpenMetaDataWithMemory_RetAddr`
- `0x1800267ea`: `ReOpenMetaDataWithMemory`

## pseudocode

```c
__int64 __fastcall ShellShim_ReOpenMetaDataWithMemory(__int64 a1, __int64 a2, unsigned int a3)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl != 3 )
  {
    if ( g_bShimImplDllUninitialized )
      return 2148734721LL;
    if ( g_pfReOpenMetaDataWithMemory_RetAddr == (int (*)(void *, const void *, unsigned int, void *))-1LL )
      g_pfReOpenMetaDataWithMemory_RetAddr = (int (*)(void *, const void *, unsigned int, void *))GetProcAddress(
                                                                                                    hModule,
                                                                                                    "ReOpenMetaDataWithMemory_RetAddr");
    if ( g_pfReOpenMetaDataWithMemory_RetAddr )
      return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, void *))g_pfReOpenMetaDataWithMemory_RetAddr)(
               a1,
               a2,
               a3,
               retaddr);
    if ( g_pfReOpenMetaDataWithMemory == (int (*)(void *, const void *, unsigned int))-1LL )
      g_pfReOpenMetaDataWithMemory = (int (*)(void *, const void *, unsigned int))GetProcAddress(
                                                                                    hModule,
                                                                                    "ReOpenMetaDataWithMemory");
    if ( !g_pfReOpenMetaDataWithMemory )
      return 2148734721LL;
    ProcAddress = (FARPROC)g_pfReOpenMetaDataWithMemory;
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD))ProcAddress)(a1, a2, a3);
  }
  ProcAddress = (FARPROC)g_ReOpenMetaDataWithMemory;
  if ( g_ReOpenMetaDataWithMemory )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD))ProcAddress)(a1, a2, a3);
  hModule = 0;
  result = GetRealDll(&hModule, 1);
  if ( (int)result < 0 )
    return result;
  ProcAddress = GetProcAddress(hModule, (LPCSTR)0x17);
  g_ReOpenMetaDataWithMemory = (int (*)(void *, const void *, unsigned int))ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(a1, a2, a3);
  return 2148734721LL;
}

```

## disassembly

```asm
0x1800266f0  mov     rax, rsp
0x1800266f3  mov     [rax+8], rbx
0x1800266f7  mov     [rax+10h], rsi
0x1800266fb  push    rdi
0x1800266fc  sub     rsp, 30h
0x180026700  mov     rsi, rcx
0x180026703  mov     qword ptr [rax+20h], 0
0x18002670b  lea     rcx, [rax+20h]
0x18002670f  mov     ebx, r8d
0x180026712  mov     rdi, rdx
0x180026715  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x18002671a  mov     edx, 1; int
0x18002671f  cmp     eax, edx
0x180026721  jz      short loc_18002676B
0x180026723  cmp     eax, 3
0x180026726  jnz     short loc_180026780
0x180026728  mov     rax, cs:?g_ReOpenMetaDataWithMemory@@3P6AJPEAXPEBXK@ZEA; long (*g_ReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x18002672f  test    rax, rax
0x180026732  jnz     loc_180026815
0x180026738  lea     rcx, [rsp+38h+hModule]; HINSTANCE *
0x18002673d  mov     [rsp+38h+hModule], rax
0x180026742  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180026747  test    eax, eax
0x180026749  js      short loc_180026770
0x18002674b  mov     rcx, [rsp+38h+hModule]; hModule
0x180026750  mov     edx, 17h; lpProcName
0x180026755  call    cs:__imp_GetProcAddress
0x18002675b  mov     cs:?g_ReOpenMetaDataWithMemory@@3P6AJPEAXPEBXK@ZEA, rax; long (*g_ReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x180026762  test    rax, rax
0x180026765  jnz     loc_180026815
0x18002676b  mov     eax, 80131701h
0x180026770  mov     rbx, [rsp+38h+arg_0]
0x180026775  mov     rsi, [rsp+38h+arg_8]
0x18002677a  add     rsp, 30h
0x18002677e  pop     rdi
0x18002677f  retn
0x180026780  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180026786  test    eax, eax
0x180026788  jnz     short loc_18002676B
0x18002678a  mov     rax, cs:?g_pfReOpenMetaDataWithMemory_RetAddr@@3R6AJPEAXPEBXK0@ZEA; long (*g_pfReOpenMetaDataWithMemory_RetAddr)(void *,void const *,ulong,void *)
0x180026791  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026795  jnz     short loc_1800267B0
0x180026797  mov     rcx, [rsp+38h+hModule]; hModule
0x18002679c  lea     rdx, aReopenmetadata_4; "ReOpenMetaDataWithMemory_RetAddr"
0x1800267a3  call    cs:__imp_GetProcAddress
0x1800267a9  mov     cs:?g_pfReOpenMetaDataWithMemory_RetAddr@@3R6AJPEAXPEBXK0@ZEA, rax; long (*g_pfReOpenMetaDataWithMemory_RetAddr)(void *,void const *,ulong,void *)
0x1800267b0  mov     rax, cs:?g_pfReOpenMetaDataWithMemory_RetAddr@@3R6AJPEAXPEBXK0@ZEA; long (*g_pfReOpenMetaDataWithMemory_RetAddr)(void *,void const *,ulong,void *)
0x1800267b7  test    rax, rax
0x1800267ba  jz      short loc_1800267D8
0x1800267bc  mov     rax, cs:?g_pfReOpenMetaDataWithMemory_RetAddr@@3R6AJPEAXPEBXK0@ZEA; long (*g_pfReOpenMetaDataWithMemory_RetAddr)(void *,void const *,ulong,void *)
0x1800267c3  mov     r8d, ebx
0x1800267c6  mov     r9, [rsp+38h]
0x1800267cb  mov     rdx, rdi
0x1800267ce  mov     rcx, rsi
0x1800267d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267d6  jmp     short loc_180026770
0x1800267d8  mov     rax, cs:?g_pfReOpenMetaDataWithMemory@@3R6AJPEAXPEBXK@ZEA; long (*g_pfReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x1800267df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800267e3  jnz     short loc_1800267FE
0x1800267e5  mov     rcx, [rsp+38h+hModule]; hModule
0x1800267ea  lea     rdx, aReopenmetadata_1; "ReOpenMetaDataWithMemory"
0x1800267f1  call    cs:__imp_GetProcAddress
0x1800267f7  mov     cs:?g_pfReOpenMetaDataWithMemory@@3R6AJPEAXPEBXK@ZEA, rax; long (*g_pfReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x1800267fe  mov     rax, cs:?g_pfReOpenMetaDataWithMemory@@3R6AJPEAXPEBXK@ZEA; long (*g_pfReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x180026805  test    rax, rax
0x180026808  jz      loc_18002676B
0x18002680e  mov     rax, cs:?g_pfReOpenMetaDataWithMemory@@3R6AJPEAXPEBXK@ZEA; long (*g_pfReOpenMetaDataWithMemory)(void *,void const *,ulong)
0x180026815  mov     r8d, ebx
0x180026818  mov     rdx, rdi
0x18002681b  mov     rcx, rsi
0x18002681e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026823  jmp     loc_180026770
```
