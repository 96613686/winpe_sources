# ShellShim_RunDll32ShimW

- ea: `0x180026980`
- end: `0x180026a8a`
- name: `ShellShim_RunDll32ShimW`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180026980`
- `0x18002e810`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800269f3`
- `KERNEL32!GetProcAddress` at `0x180026a49`
- `KERNEL32!GetProcAddress` at `0x1800269f3`
- `KERNEL32!GetProcAddress` at `0x180026a49`

## string_xrefs

- `0x1800269ec`: `RunDll32ShimW_RetAddr`
- `0x180026a42`: `RunDll32ShimW`

## pseudocode

```c
__int64 __fastcall ShellShim_RunDll32ShimW(__int64 a1, __int64 a2, _WORD *a3, unsigned int a4)
{
  int ShimImpl; // eax
  HMODULE hModule[7]; // [rsp+30h] [rbp-38h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  hModule[0] = 0;
  ShimImpl = GetShimImpl(hModule);
  if ( ShimImpl == 1 )
    return 2148734721LL;
  if ( ShimImpl == 3 )
    return RunDll32ShimW(a1, a2, a3, a4);
  if ( g_bShimImplDllUninitialized )
    return 2148734721LL;
  if ( g_pfRunDll32ShimW_RetAddr == (int (*)(HWND, HINSTANCE, const unsigned __int16 *, int, void *))-1LL )
    g_pfRunDll32ShimW_RetAddr = (int (*)(HWND, HINSTANCE, const unsigned __int16 *, int, void *))GetProcAddress(
                                                                                                   hModule[0],
                                                                                                   "RunDll32ShimW_RetAddr");
  if ( g_pfRunDll32ShimW_RetAddr )
    return ((__int64 (__fastcall *)(__int64, __int64, _WORD *, _QWORD, void *))g_pfRunDll32ShimW_RetAddr)(
             a1,
             a2,
             a3,
             a4,
             retaddr);
  if ( g_pfRunDll32ShimW == (int (*)(HWND, HINSTANCE, const unsigned __int16 *, int))-1LL )
    g_pfRunDll32ShimW = (int (*)(HWND, HINSTANCE, const unsigned __int16 *, int))GetProcAddress(
                                                                                   hModule[0],
                                                                                   "RunDll32ShimW");
  if ( !g_pfRunDll32ShimW )
    return 2148734721LL;
  else
    return ((__int64 (__fastcall *)(__int64, __int64, _WORD *, _QWORD))g_pfRunDll32ShimW)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180026980  push    rbx
0x180026982  push    rbp
0x180026983  push    rsi
0x180026984  push    rdi
0x180026985  sub     rsp, 48h
0x180026989  mov     rbp, rcx
0x18002698c  mov     [rsp+68h+hModule], 0
0x180026995  lea     rcx, [rsp+68h+hModule]
0x18002699a  mov     ebx, r9d
0x18002699d  mov     rdi, r8
0x1800269a0  mov     rsi, rdx
0x1800269a3  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800269a8  cmp     eax, 1
0x1800269ab  jz      loc_180026A7C
0x1800269b1  cmp     eax, 3
0x1800269b4  jnz     short loc_1800269CC
0x1800269b6  mov     r9d, ebx
0x1800269b9  mov     r8, rdi
0x1800269bc  mov     rdx, rsi
0x1800269bf  mov     rcx, rbp
0x1800269c2  call    RunDll32ShimW
0x1800269c7  jmp     loc_180026A81
0x1800269cc  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x1800269d2  test    eax, eax
0x1800269d4  jnz     loc_180026A7C
0x1800269da  mov     rax, cs:?g_pfRunDll32ShimW_RetAddr@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGHPEAX@ZEA; long (*g_pfRunDll32ShimW_RetAddr)(HWND__ *,HINSTANCE__ *,ushort const *,int,void *)
0x1800269e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800269e5  jnz     short loc_180026A00
0x1800269e7  mov     rcx, [rsp+68h+hModule]; hModule
0x1800269ec  lea     rdx, aRundll32shimwR; "RunDll32ShimW_RetAddr"
0x1800269f3  call    cs:__imp_GetProcAddress
0x1800269f9  mov     cs:?g_pfRunDll32ShimW_RetAddr@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGHPEAX@ZEA, rax; long (*g_pfRunDll32ShimW_RetAddr)(HWND__ *,HINSTANCE__ *,ushort const *,int,void *)
0x180026a00  mov     rax, cs:?g_pfRunDll32ShimW_RetAddr@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGHPEAX@ZEA; long (*g_pfRunDll32ShimW_RetAddr)(HWND__ *,HINSTANCE__ *,ushort const *,int,void *)
0x180026a07  test    rax, rax
0x180026a0a  jz      short loc_180026A30
0x180026a0c  mov     rax, cs:?g_pfRunDll32ShimW_RetAddr@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGHPEAX@ZEA; long (*g_pfRunDll32ShimW_RetAddr)(HWND__ *,HINSTANCE__ *,ushort const *,int,void *)
0x180026a13  mov     r9d, ebx
0x180026a16  mov     rcx, [rsp+68h]
0x180026a1b  mov     r8, rdi
0x180026a1e  mov     [rsp+68h+var_48], rcx
0x180026a23  mov     rdx, rsi
0x180026a26  mov     rcx, rbp
0x180026a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2e  jmp     short loc_180026A81
0x180026a30  mov     rax, cs:?g_pfRunDll32ShimW@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@ZEA; long (*g_pfRunDll32ShimW)(HWND__ *,HINSTANCE__ *,ushort const *,int)
0x180026a37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026a3b  jnz     short loc_180026A56
0x180026a3d  mov     rcx, [rsp+68h+hModule]; hModule
0x180026a42  lea     rdx, aRundll32shimw_0; "RunDll32ShimW"
0x180026a49  call    cs:__imp_GetProcAddress
0x180026a4f  mov     cs:?g_pfRunDll32ShimW@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@ZEA, rax; long (*g_pfRunDll32ShimW)(HWND__ *,HINSTANCE__ *,ushort const *,int)
0x180026a56  mov     rax, cs:?g_pfRunDll32ShimW@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@ZEA; long (*g_pfRunDll32ShimW)(HWND__ *,HINSTANCE__ *,ushort const *,int)
0x180026a5d  test    rax, rax
0x180026a60  jz      short loc_180026A7C
0x180026a62  mov     rax, cs:?g_pfRunDll32ShimW@@3R6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@ZEA; long (*g_pfRunDll32ShimW)(HWND__ *,HINSTANCE__ *,ushort const *,int)
0x180026a69  mov     r9d, ebx
0x180026a6c  mov     r8, rdi
0x180026a6f  mov     rdx, rsi
0x180026a72  mov     rcx, rbp
0x180026a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a7a  jmp     short loc_180026A81
0x180026a7c  mov     eax, 80131701h
0x180026a81  add     rsp, 48h
0x180026a85  pop     rdi
0x180026a86  pop     rsi
0x180026a87  pop     rbp
0x180026a88  pop     rbx
0x180026a89  retn
```
