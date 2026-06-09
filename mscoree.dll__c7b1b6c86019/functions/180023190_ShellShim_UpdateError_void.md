# ShellShim_UpdateError(void)

- ea: `0x180023190`
- end: `0x18002329c`
- name: `?ShellShim_UpdateError@@YAXXZ`
- size: `268`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180001c10`
- `0x180023190`
- `0x18002a230`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800231e0`
- `KERNEL32!GetProcAddress` at `0x18002322b`
- `KERNEL32!GetProcAddress` at `0x180023272`
- `KERNEL32!GetProcAddress` at `0x1800231e0`
- `KERNEL32!GetProcAddress` at `0x18002322b`
- `KERNEL32!GetProcAddress` at `0x180023272`

## string_xrefs

- `0x180023224`: `UpdateError_RetAddr`
- `0x18002326b`: `UpdateError`

## pseudocode

```c
void ShellShim_UpdateError(void)
{
  int ShimImpl; // eax
  void (*ProcAddress)(void); // rax
  void *retaddr; // [rsp+28h] [rbp+0h]
  HMODULE hModule; // [rsp+30h] [rbp+8h] BYREF

  hModule = 0;
  ShimImpl = GetShimImpl(&hModule);
  if ( ShimImpl == 3 )
  {
    ProcAddress = g_UpdateError;
    if ( g_UpdateError )
      goto LABEL_16;
    hModule = 0;
    if ( (int)GetRealDll(&hModule, 1) >= 0 )
    {
      ProcAddress = (void (*)(void))GetProcAddress(hModule, (LPCSTR)0x14);
      g_UpdateError = ProcAddress;
      if ( ProcAddress )
        goto LABEL_16;
    }
  }
  else if ( ShimImpl == 2 && !g_bShimImplDllUninitialized )
  {
    if ( g_pfUpdateError_RetAddr == (void (*)(void *))-1LL )
      g_pfUpdateError_RetAddr = (void (*)(void *))GetProcAddress(hModule, "UpdateError_RetAddr");
    if ( g_pfUpdateError_RetAddr )
    {
      ((void (__fastcall *)(void *))g_pfUpdateError_RetAddr)(retaddr);
      return;
    }
    if ( g_pfUpdateError == (void (*)(void))-1LL )
      g_pfUpdateError = (void (*)(void))GetProcAddress(hModule, "UpdateError");
    if ( g_pfUpdateError )
    {
      ProcAddress = g_pfUpdateError;
LABEL_16:
      ProcAddress();
    }
  }
}

```

## disassembly

```asm
0x180023190  sub     rsp, 28h
0x180023194  lea     rcx, [rsp+28h+hModule]
0x180023199  mov     [rsp+28h+hModule], 0
0x1800231a2  call    ?GetShimImpl@@YA?AW4ShimImplStatus@@PEAPEAUHINSTANCE__@@@Z; GetShimImpl(HINSTANCE__ * *)
0x1800231a7  cmp     eax, 3
0x1800231aa  jnz     short loc_1800231FB
0x1800231ac  mov     rax, cs:?g_UpdateError@@3P6AXXZEA; void (*g_UpdateError)(void)
0x1800231b3  test    rax, rax
0x1800231b6  jnz     loc_180023292
0x1800231bc  lea     edx, [rax+1]; int
0x1800231bf  mov     [rsp+28h+hModule], rax
0x1800231c4  lea     rcx, [rsp+28h+hModule]; HINSTANCE *
0x1800231c9  call    ?GetRealDll@@YAJPEAPEAUHINSTANCE__@@H@Z; GetRealDll(HINSTANCE__ * *,int)
0x1800231ce  test    eax, eax
0x1800231d0  js      loc_180023297
0x1800231d6  mov     rcx, [rsp+28h+hModule]; hModule
0x1800231db  mov     edx, 14h; lpProcName
0x1800231e0  call    cs:__imp_GetProcAddress
0x1800231e6  mov     cs:?g_UpdateError@@3P6AXXZEA, rax; void (*g_UpdateError)(void)
0x1800231ed  test    rax, rax
0x1800231f0  jz      loc_180023297
0x1800231f6  jmp     loc_180023292
0x1800231fb  cmp     eax, 2
0x1800231fe  jnz     loc_180023297
0x180023204  mov     eax, cs:?g_bShimImplDllUninitialized@@3HC; int volatile g_bShimImplDllUninitialized
0x18002320a  test    eax, eax
0x18002320c  jnz     loc_180023297
0x180023212  mov     rax, cs:?g_pfUpdateError_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfUpdateError_RetAddr)(void *)
0x180023219  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002321d  jnz     short loc_180023238
0x18002321f  mov     rcx, [rsp+28h+hModule]; hModule
0x180023224  lea     rdx, aUpdateerrorRet; "UpdateError_RetAddr"
0x18002322b  call    cs:__imp_GetProcAddress
0x180023231  mov     cs:?g_pfUpdateError_RetAddr@@3R6AXPEAX@ZEA, rax; void (*g_pfUpdateError_RetAddr)(void *)
0x180023238  mov     rax, cs:?g_pfUpdateError_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfUpdateError_RetAddr)(void *)
0x18002323f  test    rax, rax
0x180023242  jz      short loc_180023259
0x180023244  mov     rax, cs:?g_pfUpdateError_RetAddr@@3R6AXPEAX@ZEA; void (*g_pfUpdateError_RetAddr)(void *)
0x18002324b  mov     rcx, [rsp+28h]
0x180023250  add     rsp, 28h
0x180023254  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180023259  mov     rax, cs:?g_pfUpdateError@@3R6AXXZEA; void (*g_pfUpdateError)(void)
0x180023260  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023264  jnz     short loc_18002327F
0x180023266  mov     rcx, [rsp+28h+hModule]; hModule
0x18002326b  lea     rdx, aUpdateerror_0; "UpdateError"
0x180023272  call    cs:__imp_GetProcAddress
0x180023278  mov     cs:?g_pfUpdateError@@3R6AXXZEA, rax; void (*g_pfUpdateError)(void)
0x18002327f  mov     rax, cs:?g_pfUpdateError@@3R6AXXZEA; void (*g_pfUpdateError)(void)
0x180023286  test    rax, rax
0x180023289  jz      short loc_180023297
0x18002328b  mov     rax, cs:?g_pfUpdateError@@3R6AXXZEA; void (*g_pfUpdateError)(void)
0x180023292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023297  add     rsp, 28h
0x18002329b  retn
```
