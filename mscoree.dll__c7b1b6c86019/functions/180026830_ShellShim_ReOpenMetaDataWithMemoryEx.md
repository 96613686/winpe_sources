# ShellShim_ReOpenMetaDataWithMemoryEx

- ea: `0x180026830`
- end: `0x18002696c`
- name: `ShellShim_ReOpenMetaDataWithMemoryEx`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180026830`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180026895`
- `KERNEL32!GetProcAddress` at `0x1800268dc`
- `KERNEL32!GetProcAddress` at `0x180026932`
- `KERNEL32!GetProcAddress` at `0x180026895`
- `KERNEL32!GetProcAddress` at `0x1800268dc`
- `KERNEL32!GetProcAddress` at `0x180026932`

## string_xrefs

- `0x1800268d5`: `ReOpenMetaDataWithMemoryEx_RetAddr`
- `0x18002688e`: `ReOpenMetaDataWithMemoryEx`
- `0x18002692b`: `ReOpenMetaDataWithMemoryEx`

## pseudocode

```c
__int64 __fastcall ShellShim_ReOpenMetaDataWithMemoryEx(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  int ShimImpl; // eax
  FARPROC ProcAddress; // rax
  __int64 result; // rax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl != 3 )
  {
    if ( g_bShimImplDllUninitialized )
      return 2148734721LL;
    if ( g_pfReOpenMetaDataWithMemoryEx_RetAddr == (int (*)(void *, const void *, unsigned int, unsigned int, void *))-1LL )
      g_pfReOpenMetaDataWithMemoryEx_RetAddr = (int (*)(void *, const void *, unsigned int, unsigned int, void *))GetProcAddress(hModule[0], "ReOpenMetaDataWithMemoryEx_RetAddr");
    if ( g_pfReOpenMetaDataWithMemoryEx_RetAddr )
      return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, void *))g_pfReOpenMetaDataWithMemoryEx_RetAddr)(
               a1,
               a2,
               a3,
               a4,
               retaddr);
    if ( g_pfReOpenMetaDataWithMemoryEx == (int (*)(void *, const void *, unsigned int, unsigned int))-1LL )
      g_pfReOpenMetaDataWithMemoryEx = (int (*)(void *, const void *, unsigned int, unsigned int))GetProcAddress(
                                                                                                    hModule[0],
                                                                                                    "ReOpenMetaDataWithMemoryEx");
    if ( !g_pfReOpenMetaDataWithMemoryEx )
      return 2148734721LL;
    ProcAddress = (FARPROC)g_pfReOpenMetaDataWithMemoryEx;
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))ProcAddress)(a1, a2, a3, a4);
  }
  ProcAddress = (FARPROC)g_ReOpenMetaDataWithMemoryEx;
  if ( g_ReOpenMetaDataWithMemoryEx )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD))ProcAddress)(a1, a2, a3, a4);
  hModule[0] = 0;
  result = GetRealDll(hModule, 1);
  if ( (int)result < 0 )
    return result;
  ProcAddress = GetProcAddress(hModule[0], "ReOpenMetaDataWithMemoryEx");
  g_ReOpenMetaDataWithMemoryEx = (int (*)(void *, const void *, unsigned int, unsigned int))ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(a1, a2, a3, a4);
  return 2148734721LL;
}

```

## disassembly

```asm
0x180026830  push    rbx
0x180026832  push    rbp
0x180026833  push    rsi
0x180026834  push    rdi
0x180026835  sub     rsp, 48h
0x180026839  mov     rbp, rcx
0x18002683c  mov     [rsp+68h+hModule], 0
0x180026845  lea     rcx, [rsp+68h+hModule]
0x18002684a  mov     ebx, r9d
0x18002684d  mov     edi, r8d
0x180026850  mov     rsi, rdx
0x180026853  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x180026858  mov     edx, 1; int
0x18002685d  cmp     eax, edx
0x18002685f  jz      short loc_1800268AB
0x180026861  cmp     eax, 3
0x180026864  jnz     short loc_1800268B9
0x180026866  mov     rax, cs:?g_ReOpenMetaDataWithMemoryEx@@3P6AJPEAXPEBXKK@ZEA; long (*g_ReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x18002686d  test    rax, rax
0x180026870  jnz     loc_180026956
0x180026876  lea     rcx, [rsp+68h+hModule]; HINSTANCE *
0x18002687b  mov     [rsp+68h+hModule], rax
0x180026880  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x180026885  test    eax, eax
0x180026887  js      short loc_1800268B0
0x180026889  mov     rcx, [rsp+68h+hModule]; hModule
0x18002688e  lea     rdx, aReopenmetadata_2; "ReOpenMetaDataWithMemoryEx"
0x180026895  call    cs:__imp_GetProcAddress
0x18002689b  mov     cs:?g_ReOpenMetaDataWithMemoryEx@@3P6AJPEAXPEBXKK@ZEA, rax; long (*g_ReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x1800268a2  test    rax, rax
0x1800268a5  jnz     loc_180026956
0x1800268ab  mov     eax, 80131701h
0x1800268b0  add     rsp, 48h
0x1800268b4  pop     rdi
0x1800268b5  pop     rsi
0x1800268b6  pop     rbp
0x1800268b7  pop     rbx
0x1800268b8  retn
0x1800268b9  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800268bf  test    eax, eax
0x1800268c1  jnz     short loc_1800268AB
0x1800268c3  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx_RetAddr@@3R6AJPEAXPEBXKK0@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx_RetAddr)(void *,void const *,ulong,ulong,void *)
0x1800268ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800268ce  jnz     short loc_1800268E9
0x1800268d0  mov     rcx, [rsp+68h+hModule]; hModule
0x1800268d5  lea     rdx, aReopenmetadata_3; "ReOpenMetaDataWithMemoryEx_RetAddr"
0x1800268dc  call    cs:__imp_GetProcAddress
0x1800268e2  mov     cs:?g_pfReOpenMetaDataWithMemoryEx_RetAddr@@3R6AJPEAXPEBXKK0@ZEA, rax; long (*g_pfReOpenMetaDataWithMemoryEx_RetAddr)(void *,void const *,ulong,ulong,void *)
0x1800268e9  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx_RetAddr@@3R6AJPEAXPEBXKK0@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx_RetAddr)(void *,void const *,ulong,ulong,void *)
0x1800268f0  test    rax, rax
0x1800268f3  jz      short loc_180026919
0x1800268f5  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx_RetAddr@@3R6AJPEAXPEBXKK0@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx_RetAddr)(void *,void const *,ulong,ulong,void *)
0x1800268fc  mov     r9d, ebx
0x1800268ff  mov     rcx, [rsp+68h]
0x180026904  mov     r8d, edi
0x180026907  mov     [rsp+68h+var_48], rcx
0x18002690c  mov     rdx, rsi
0x18002690f  mov     rcx, rbp
0x180026912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026917  jmp     short loc_1800268B0
0x180026919  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx@@3R6AJPEAXPEBXKK@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x180026920  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026924  jnz     short loc_18002693F
0x180026926  mov     rcx, [rsp+68h+hModule]; hModule
0x18002692b  lea     rdx, aReopenmetadata_2; "ReOpenMetaDataWithMemoryEx"
0x180026932  call    cs:__imp_GetProcAddress
0x180026938  mov     cs:?g_pfReOpenMetaDataWithMemoryEx@@3R6AJPEAXPEBXKK@ZEA, rax; long (*g_pfReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x18002693f  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx@@3R6AJPEAXPEBXKK@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x180026946  test    rax, rax
0x180026949  jz      loc_1800268AB
0x18002694f  mov     rax, cs:?g_pfReOpenMetaDataWithMemoryEx@@3R6AJPEAXPEBXKK@ZEA; long (*g_pfReOpenMetaDataWithMemoryEx)(void *,void const *,ulong,ulong)
0x180026956  mov     r9d, ebx
0x180026959  mov     r8d, edi
0x18002695c  mov     rdx, rsi
0x18002695f  mov     rcx, rbp
0x180026962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026967  jmp     loc_1800268B0
```
