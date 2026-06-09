# ShellShim_DllCanUnloadNow

- ea: `0x180007b40`
- end: `0x180007c27`
- name: `ShellShim_DllCanUnloadNow`
- size: `231`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a90`
- `0x180007b40`
- `0x18002d0e4`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180007bac`
- `KERNEL32!GetProcAddress` at `0x180007bf2`
- `KERNEL32!GetProcAddress` at `0x180007bac`
- `KERNEL32!GetProcAddress` at `0x180007bf2`

## string_xrefs

- `0x180007ba2`: `DllCanUnloadNow_RetAddr`
- `0x180007be8`: `DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall ShellShim_DllCanUnloadNow()
{
  int (*v0)(unsigned __int16 *, void *); // rdx
  __int64 v1; // rcx
  HMODULE v2; // rbx
  void *retaddr; // [rsp+28h] [rbp+0h]

  v2 = 0;
  if ( !(_DWORD)g_shimImplStatus )
    InitShimImpl(v1, v0);
  if ( (_DWORD)g_shimImplStatus == 2 )
    v2 = g_hShimImplInst;
  if ( (_DWORD)g_shimImplStatus == 1 )
    return -2146232575;
  if ( (_DWORD)g_shimImplStatus == 3 )
    return DllCanUnloadNow();
  if ( g_bShimImplDllUninitialized )
    return -2146232575;
  if ( g_pfDllCanUnloadNow_RetAddr == (int (*)(void *))-1LL )
    g_pfDllCanUnloadNow_RetAddr = (int (*)(void *))GetProcAddress(v2, "DllCanUnloadNow_RetAddr");
  if ( g_pfDllCanUnloadNow_RetAddr )
    return ((__int64 (__fastcall *)(void *))g_pfDllCanUnloadNow_RetAddr)(retaddr);
  if ( g_pfDllCanUnloadNow == (int (*)(void))-1LL )
    g_pfDllCanUnloadNow = (int (*)(void))GetProcAddress(v2, "DllCanUnloadNow");
  if ( !g_pfDllCanUnloadNow )
    return -2146232575;
  else
    return g_pfDllCanUnloadNow();
}

```

## disassembly

```asm
0x180007b40  push    rbx
0x180007b42  sub     rsp, 20h
0x180007b46  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007b4c  xor     ebx, ebx
0x180007b4e  test    eax, eax
0x180007b50  jnz     short loc_180007B57
0x180007b52  call    ?InitShimImpl@@YAXXZ; InitShimImpl(void)
0x180007b57  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007b5d  cmp     eax, 2
0x180007b60  jnz     short loc_180007B69
0x180007b62  mov     rbx, cs:?g_hShimImplInst@@3REAUHINSTANCE__@@EA; HINSTANCE__ * g_hShimImplInst
0x180007b69  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180007b6f  cmp     eax, 1
0x180007b72  jz      loc_180007C1C
0x180007b78  cmp     eax, 3
0x180007b7b  jnz     short loc_180007B87
0x180007b7d  add     rsp, 20h
0x180007b81  pop     rbx
0x180007b82  jmp     DllCanUnloadNow
0x180007b87  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x180007b8d  test    eax, eax
0x180007b8f  jnz     loc_180007C1C
0x180007b95  mov     rax, cs:?g_pfDllCanUnloadNow_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllCanUnloadNow_RetAddr)(void *)
0x180007b9c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007ba0  jnz     short loc_180007BB9
0x180007ba2  lea     rdx, aDllcanunloadno_2; "DllCanUnloadNow_RetAddr"
0x180007ba9  mov     rcx, rbx; hModule
0x180007bac  call    cs:__imp_GetProcAddress
0x180007bb2  mov     cs:?g_pfDllCanUnloadNow_RetAddr@@3R6AJPEAX@ZEA, rax; long (*g_pfDllCanUnloadNow_RetAddr)(void *)
0x180007bb9  mov     rax, cs:?g_pfDllCanUnloadNow_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllCanUnloadNow_RetAddr)(void *)
0x180007bc0  test    rax, rax
0x180007bc3  jz      short loc_180007BDB
0x180007bc5  mov     rax, cs:?g_pfDllCanUnloadNow_RetAddr@@3R6AJPEAX@ZEA; long (*g_pfDllCanUnloadNow_RetAddr)(void *)
0x180007bcc  mov     rcx, [rsp+28h]
0x180007bd1  add     rsp, 20h
0x180007bd5  pop     rbx
0x180007bd6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdb  mov     rax, cs:?g_pfDllCanUnloadNow@@3R6AJXZEA; long (*g_pfDllCanUnloadNow)(void)
0x180007be2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007be6  jnz     short loc_180007BFF
0x180007be8  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x180007bef  mov     rcx, rbx; hModule
0x180007bf2  call    cs:__imp_GetProcAddress
0x180007bf8  mov     cs:?g_pfDllCanUnloadNow@@3R6AJXZEA, rax; long (*g_pfDllCanUnloadNow)(void)
0x180007bff  mov     rax, cs:?g_pfDllCanUnloadNow@@3R6AJXZEA; long (*g_pfDllCanUnloadNow)(void)
0x180007c06  test    rax, rax
0x180007c09  jz      short loc_180007C1C
0x180007c0b  mov     rax, cs:?g_pfDllCanUnloadNow@@3R6AJXZEA; long (*g_pfDllCanUnloadNow)(void)
0x180007c12  add     rsp, 20h
0x180007c16  pop     rbx
0x180007c17  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180007c1c  mov     eax, 80131701h
0x180007c21  add     rsp, 20h
0x180007c25  pop     rbx
0x180007c26  retn
```
